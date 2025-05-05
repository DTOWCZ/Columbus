Jsi AI agent, který překládá texty ve všech formátech JSON.

# Kroky
**Před jakýmkoli zpracováním použij pravidla definovaná v Logic Database a řiď se jimi při všech krocích 1–4.**
1. **Rozpoznávání vstupu**: Identifikujte a zpracujte vstup, který je ve formátu JSON.
2. **Detekce jazyka**: Detekce zdrojového jazyka textu ve struktuře JSON.
3. **Překlad**: Přeložte text do požadovaného cílového jazyka při zachování struktury JSON.
4. **Formace výstupu**: Ujistěte se,  že je přeložený obsah správně naformátován zpět do původního rozvržení JSON.

# Výstupní formát
Konečným výstupem musí být objekt JSON se zachováním všech klíčů a netextových hodnot, přičemž původní texty budou nahrazeny jejich překlady.

# Příklady
**Příklad 1**
- **Vstup**:
		Přelož do Češtiny 
    ```json
    {
      "title": "House",
      "description": "It is a big house.",
      "metadata": {
        "author": "Jan Novák"
      }
    }
    ```
- **Výstup** (v Češtině):
    ```json
    {
      "title": "Dům",
      "description": "To je velký dům.",
      "metadata": {
        "author": "Jan Novák"
      }
    }
    ```

**Příklad 2**
- **Vstup**:
  		Přelož do Angličtiny
    ```json
    {
      "product": "Káva",
      "details": {
        "type": "Arabica",
        "origin": "Kolumbie"
      }
    }
    ```
- **Výstup** (v Angličtině):
    ```json
    {
      "product": "Coffee",
      "details": {
        "type": "Arabica",
        "origin": "Colombia"
      }
    }
    ```

# Poznámky
– Ujistěte se, že veškerá syntaxe JSON, včetně klíčů, které by se neměly překládat, zůstala nedotčena.
- Přiměřeně zacházet s okrajovými případy, jako jsou prázdné řetězce nebo nepřeložitelný text ve struktuře JSON.


```
let 
    Zdroj = SharePoint.Files("https://wistron.sharepoint.com/teams/WiwynnProject-InterlockBIData/", [ApiVersion = 15]),
    #"Filtrované řádky" = Table.SelectRows(Zdroj, each Text.Contains([Name], "Wiwynn Amber Production Dashboard")),
    #"Filtrované řádky1" = Table.SelectRows(#"Filtrované řádky", each [Folder Path] = "https://wistron.sharepoint.com/teams/WiwynnProject-InterlockBIData/Shared Documents/Dashboard/"),
    #"Seřazené řádky" = Table.Sort(#"Filtrované řádky1", {{"Date created", Order.Descending}}),
    #"Posledni excel" = Table.FirstN(#"Seřazené řádky", 1),
    Content = #"Posledni excel"{0}[Content],
    #"Importovaný Excelový sešit" = Excel.Workbook(Content),
    Summary_Sheet = #"Importovaný Excelový sešit"{[Item="Summary",Kind="Sheet"]}[Data],
    #"Záhlaví se zvýšenou úrovní" = Table.PromoteHeaders(Summary_Sheet, [PromoteAllScalars=true]),
    #"Vyplněné dolů" = Table.FillDown(#"Záhlaví se zvýšenou úrovní", {"Actualinputdate"}),
    #"Přejmenované RAW sloupce" = Table.TransformColumnNames(
        #"Vyplněné dolů",
        each let n = Text.Trim(Text.Lower(Text.Replace(_, " ", ""))) in
            if n="customer" then "Customer"
            else if n="exf" then "Exf"
            else if n="plannedstartdate" then "Planned start date"
            else if n="type" then "Type"
            else if n="rackstatus" then "Order Status"
            else if n="materialreadydate" then "Material Readiness"
            else if n="rackqty" then "Rack Qty"
            else if n="l10unitqty" then "L10unitQTY"
            else if n="l10unitqtyno.2" then "L10unitQtyNo.2"
            else if n="releasedqty" then "ReleasedQTY"
            else if n="dockdate" then "Dock-date"
            else _
    ),
    #"Zachované sloupce" = Table.SelectColumns(
        #"Přejmenované RAW sloupce",
        {"Customer","Exf","Planned start date","Type","Order Status",
        "Material Readiness","L10unitQTY","L10unitQtyNo.2","Rack Qty",
        "ReleasedQTY","Dock-date","AWSPO"}
    ),
    #"Změněný typ" = Table.TransformColumnTypes(#"Zachované sloupce", {{"Rack Qty", Int64.Type}, {"ReleasedQTY", Int64.Type}}),
    #"Odebrané prázdné řádky" = Table.SelectRows(#"Změněný typ", each not List.IsEmpty(List.RemoveMatchingItems(Record.FieldValues(_), {"", null}))),
    #"Nahrazená hodnota" = Table.ReplaceValue(#"Odebrané prázdné řádky", null, 0, Replacer.ReplaceValue, {"ReleasedQTY", "L10unitQtyNo.2", "L10unitQTY"}),
    #"Přidané: Rack" = Table.AddColumn(#"Nahrazená hodnota", "Build plan for Rack", each [Rack Qty] - [ReleasedQTY]),
    #"Přidané: Servers" = Table.AddColumn(#"Přidané: Rack", "Build plan for Servers", each [Build plan for Rack] * ([L10unitQTY] + [L10unitQtyNo.2])),
    #"Přejmenované sloupce" = Table.TransformColumnNames(#"Přidané: Servers",
        each let normalized = Text.Trim(Text.Lower(Text.Replace(_, " ", ""))) in
            if normalized = "plannedstartdate" then "Planned start date"
            else if normalized = "type" then "Type"
            else if normalized = "rackstatus" then "Order Status"
            else if normalized = "materialreadydate" then "Material Readiness"
            else if normalized = "rackqty" then "Rack Qty"
            else _
    ),
    #"Přeuspořádané sloupce" = Table.ReorderColumns(#"Přejmenované sloupce",
        {"Customer","Exf","Planned start date","Type","Order Status","Build plan for Rack","Build plan for Servers","Material Readiness","L10unitQTY","L10unitQtyNo.2","Rack Qty","ReleasedQTY"}
    ),
    #"Změněný typ1" = Table.TransformColumnTypes(#"Přeuspořádané sloupce", {{"Build plan for Servers", Int64.Type}, {"L10unitQTY", Int64.Type}, {"Dock-date", type date}}),
    #"Prazdne OS je NON-CTB" = Table.ReplaceValue(#"Změněný typ1", "", "NON-CTB", Replacer.ReplaceValue, {"Order Status"})
in
    #"Prazdne OS je NON-CTB"
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTE1ODg3OTUsMTIwNzkzODAzOV19
-->