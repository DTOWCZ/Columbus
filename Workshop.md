[![enter image description here](https://www.wistron.cz/wp-content/uploads/2022/10/logo-light.svg)](http://www.wistron.cz)
# Agent Builder Workshop
## 👨‍🏫 Úvod
**Co je AI agent?**
> AI agent je digitální asistent, který reaguje na dotazy nebo úkoly uživatele na základě předem nastaveného promptu, znalostní báze nebo přídavného pluginu. Může vyhledávat informace, plnit opakované úkoly a rozhodovat se na základě logiky. 

> Použítí: jako vyhledávač informací na webu, v interních dokumentech, pomocník na HR dotazy, automatický vyplňovač formulářů, generování fonrmulovaného textu nebo pro kontrolu dat.


## 🤖 **Začneme tvorbou vlastního agenta**

1. ### **Vstup do Agent Builderu**
	- Ukáž vstupní obrazovku
	- Kliknout na **"Create Agent"**

2. ### **Volba šablony**
	- Rozdíl mezi Blank / Basic / Advanced
	> Blank = od nuly, Basic = prompt-only, Advanced = prompt + API/pluginy
	- Zvolíme např. **Basic Agent Template**

3. ### **Nastavení Basic Info**
	- Ikona (nepovinná)
	- Jméno (CZ + EN)
	- Popis služby (CZ + EN)
	- Category  (Personal)
	- Co-editing members (volitelně pro spolupráci na AI Agentovi) 

4. ### **Reply Settings (Model a Prompt)**
	- Vybrat model (Gemini / GPT)
	> Gemini = Google, lepší pro tabulky; GPT = OpenAI, lepší pro přirozený jazyk
	- Ukázat pole pro prompt
	- Použít Prompt Generator nebo napsat vlastní
	> Př.: "Jsi HR asistent, pomáháš odpovídat na otázky o docházce podle interních pravidel."

5. ### **Knowledge Reference (volitelné)**
	- Ukázat možnost nahrání znalostní báze
		- Interní  (spravované Columbus týmem)
		- Externí (volitelných 10 souborů)
	> Př.: směrnice, tabulky, manuály

6. ### **Agent Tools (volitelné)**
	- **Code Interpreter** → možnosti spuštění python kódu v pozadí a díky toho generovat grafy atd..
	- **Capture Web Content** → nová funkce pro taháni informací z internetu -   pouze ověřené weby jako .gov nebo .org
	- **Plugin** → oficiálně schválené  a udržované pluginy od týmu Columbus (zatím pouze vyhledávání na internetu)
	- **Logic DB** → konfigurace specifických pravidel a podmínek, pro rozhodování AI Agenta
	- **API** → nastavení (pro pokročilé)


## ⚖️ **Testování agenta (Agent Lab)**
- Ukázat, jak napsat otázku a jak agent odpovídá
	- probrat Markdown
- Tokeny, historie dotazů, ladění odpovědí
	- (Prompt Tokens  1146  | Completion Tokens  32  | Total Tokens  1178  )


## 🌐 **Publikace a sdílení agenta**
- Rozdíl **Draft** a **Publish**
- Jak udělit přístup dalším uživatelům (Request Access): 
	- https://forms.office.com/pages/responsepage.aspx?id=4JUH3sDX6065u7yU2JgNO-P1J_OgjchCmLU73Tef495UN1IyOEZLSDlGTFRBTFZGQU8wVkkxM1JCWiQlQCN0PWcu&route=shorturl
- Ukázat, kde se agent objeví po **Publish** vytvoření.
- Ukázat, kde najít hlavní web Columbus:  
	- https://wistron.sharepoint.com/sites/PoweredbyColumbus/SitePages/en/0.0.0_Home.aspx


## ❓**Časté dotazy (Q&A)**
**Q: Co když agent neodpovídá?**
> Zkontroluj model, prompt a znalostní bázi. Může jít o chybný token nebo chybějící obsah.

**Q: Jak poznám, že se něco pokazilo?**
> V Agent Labu sleduj tokeny a chybové hlášky (např. context length exceeded).

**Q: Jak sdílet agenta s kolegy?**
> Přes tlačítko "Request Authorization" nebo přidat uživatele jako Co-editora.

**Q: Rozdíl Plugin vs API?**
> API je obecné rozhraní, plugin je napojení agenta na konkrétní funkci v API (musí být zaregistrován v Columbus).
> API vyžaduje IT podporu a projekt musí být zaregistrován v Azure z důvodu bezpečnosti


## 🎓 Závěr
- **Návody a zdroje:**
  - https://wistron.sharepoint.com/sites/PoweredbyColumbus
  - [Agent Builder - English User Manual.pdf](https://wistron.sharepoint.com/sites/PoweredbyColumbus/SiteAssets/Forms/AllItems.aspx?id=/sites/PoweredbyColumbus/SiteAssets/%E6%AA%94%E6%A1%88%E9%80%A3%E7%B5%90_En/Agent%20Builder%20%E6%93%8D%E4%BD%9C%E6%89%8B%E5%86%8A_20250325_En.pdf&parent=/sites/PoweredbyColumbus/SiteAssets/%E6%AA%94%E6%A1%88%E9%80%A3%E7%B5%90_En&p=true&ga=1)
  - https://stackedit.io/app#
  - http://editor.md.ipandao.com/en.html
  - https://github.com/AImarkdown/main/tree/main/examples

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY2NDc3NjYwMSwxMDYzNjM3MzMsMjAzOD
kwMTI0Ml19
-->