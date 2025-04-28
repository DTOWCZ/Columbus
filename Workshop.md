[![enter image description here](https://www.wistron.cz/wp-content/uploads/2022/10/logo-light.svg)](http://www.wistron.cz)
# Agent Builder Workshop
## 👨‍🏫 Úvod
**Co je AI agent?**
> AI agent je digitální asistent, který reaguje na dotazy nebo úkoly uživatele na základě předem nastaveného promptu, znalostní báze. Může vyhledávat informace, plnit opakované úkoly a rozhodovat se na základě logiky. 

> Použítí: jako vyhledávač interních dokumentů, pomocník na HR dotazy, automatický vyplňovač formulářů nebo kontrolor dat.


## 🤖 **Začneme tvorbou vlastního agenta**

1. ### **Vstup do Agent Builderu**
	- Ukáž vstupní obrazovku
	- Kliknout na **"Create Agent"**

2. ### **Volba šablony**
	- Rozdíl mezi Blank / Basic / Advanced
	> Blank = od nuly, Basic = prompt-only, Advanced = prompt + API/pluginy
	- Zvolíme např. **Basic Agent Template**

3. ### **Nastavení Basic Info**
	- Vyplnit jméno (CZ + EN)
	- Ikona + Popis služby
	- Volitelně: Co-editing members

4. ### **Model a Prompt (Reply Settings)**
	- Vybrat model (Gemini / GPT)
	> Gemini = Google, lepší pro tabulky; GPT = OpenAI, lepší pro přirozený jazyk
	- Ukázat pole pro prompt
	- Použít Prompt Generator nebo napsat vlastní
	> Př.: "Jsi HR asistent, pomáháš odpovídat na otázky o docházce podle interních pravidel."

5. ### **Knowledge Reference (volitelné)**
	- Ukázat možnost nahrání znalostní báze (např. PDF, .txt)
	> Př.: směrnice, tabulky, manuály

6. ### **Agent Tools (volitelné)**
	- Ukázat co je Plugin a Code Interpreter (jen zmínit)
	> Plugin = napojení na API (např. docházka), Code Interpreter = výpočty, grafy

7. ### **Advanced Toolkit (jen zmínit)**
	- Logic DB + API nastavení (pro pokročilé)
	> Logic DB = pravidla, např. "neobvyklé přihlášení = riziko"



## ⚖️ **Testování agenta (Agent Lab)**
- Ukázat, jak napsat otázku a jak agent odpovídá
- Tokeny, historie dotazů, ladění odpovědí


## 🌐 **Publikace a sdílení agenta**
- Rozdíl mezi **Draft** a **Publish**
- Jak udělit přístup dalším uživatelům (Request Access)
- Ukázat, kde se agent objeví v levém menu


## ❓**Časté dotazy (Q&A)**
**Q: Co když agent neodpovídá?**
> Zkontroluj model, prompt a znalostní bázi. Může jít o chybný token nebo chybějící obsah.

**Q: Jak poznám, že se něco pokazilo?**
> V Agent Labu sleduj tokeny a chybové hlášky (např. context length exceeded).

**Q: Jak sdílet agenta s kolegy?**
> Přes tlačítko "Request Authorization" nebo přidat uživatele jako Co-editora.

**Q: Rozdíl Plugin vs API?**
> API je obecné rozhraní, plugin je napojení agenta na konkrétní funkci v API (musí být zaregistrován v Columbus).


## 🎓 Závěr
- **Návody a zdroje:**
  - https://wistron.sharepoint.com/sites/PoweredbyColumbus
  - [Agent Builder - English User Manual.pdf](https://wistron.sharepoint.com/sites/PoweredbyColumbus/SiteAssets/Forms/AllItems.aspx?id=/sites/PoweredbyColumbus/SiteAssets/%E6%AA%94%E6%A1%88%E9%80%A3%E7%B5%90_En/Agent%20Builder%20%E6%93%8D%E4%BD%9C%E6%89%8B%E5%86%8A_20250325_En.pdf&parent=/sites/PoweredbyColumbus/SiteAssets/%E6%AA%94%E6%A1%88%E9%80%A3%E7%B5%90_En&p=true&ga=1)
  - https://stackedit.io/app#
  - http://editor.md.ipandao.com/en.html
  - https://github.com/AImarkdown/main/tree/main/examples

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0ODAzMTk5OTksMTA2MzYzNzMzLDIwMz
g5MDEyNDJdfQ==
-->