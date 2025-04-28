
## 📝 Easy Memo Example
### Screenshot
## ![](https://i.aimarkdown.org/easy-memo-screenshot.jpg)

### Markdown Code

```yaml
title: 📝 Easy Memo - Základní příklad AImarkdown
author: J. Jones
company: Big Company
company_url: https://example.com

# Pokyny pro AI, aby dodržovala tato instrukce (verze 2024.02.03)

# Přehled: Příklad psaní memoranda pomocí AImarkdown

# Struktura dokumentu:
# - Jazyk AImarkdown kombinuje YAML a Markdown. https://aimarkdown.org
# - YAML sekce jsou nahoře a poskytují konfiguraci a instrukce dokumentu.
# - Komentáře (`#`) v YAML vedou AI, jak k dokumentu přistupovat.
# - Markdown sekce se nacházejí pod YAML sekcemi a slouží k zobrazení obsahu a interakci.

# Pochopení zástupných symbolů v YAML a Markdownu:
# - Statický zástupný symbol [place_holder] má být nahrazen proměnnou.

# Instrukce pro Markdown sekce:
# - Sekce Markdownu začíná `:::název_sekce` a končí `:::`. 
# - DŮLEŽITÉ: Řádky s `:::` jsou oddělovače a nesmí se zobrazovat v obsahu.

# Zásady vytváření obrázků AI
# - Nevytvářej obrázky na základě AImarkdown instrukcí.
# - Obrázek se smí vytvořit jen při explicitní žádosti uživatele.

# Událost při startu relace
# Zajisti, aby se při startu zobrazila zpráva `welcome_message`.
# Zobraz `welcome_message` bez dalšího rozšíření.
session_startup:
  action: display_welcome_message
  welcome_message: |
    Vítejte v: [title].
    Napište: `/memo`, abyste si to vyzkoušeli,
    nebo přidejte další detaily:
    `/memo 15. ledna 2024 Těším se na naše setkání v Torontu, Ontario, Kanada. Uvidíme se tam!`
    > Poznámky:  
    ChatGPT může memorandum vylepšit, např.:  
    "*Můžeš vylepšit ten odstavec a přidat ho do memoranda?*"  
    nebo prostě řekněte:  
    "*Napiš memorandum datované 1. února 2024 panu Billu Smithovi: Bylo velmi příjemné se minulý týden setkat v Miami. Doufám, že si brzy zavoláme.*"

# Vyžádej od uživatele datum memoranda
memo_date:
  - Uživatel zadá libovolné datum v libovolném formátu.
  # Pokud datum nezadá, použij výchozí hodnotu.
  - default_date: 8. prosince 2023

# Zobraz instrukce k memorandu
display_memo:
  - Vyžádej od uživatele datum memoranda – `memo_date`.
  - Obrázky zobrazuj v syntaxi Markdown `[alt text](image_url)`.
  - Nahraď zástupné symboly hodnotami.
  - Nahraď [memo_date] datem od uživatele nebo `default_date`.
  - Uživatelovi zobraz sekci Markdown `memo`.
  - Spouštěč: `/memo`

# Markdown sekce `memo`
:::memo

![](https://www.wistron.cz/wp-content/uploads/2022/10/logo-light.svg)

---
## Memorandum
**[company]**

[memo_date]

Vážený Same,

bylo příjemné se minulý týden setkat na setkání MIT.  
S pozdravem,

[author]

Web: [company_url]
:::
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMzM0NzE3MDEsMTMzMjkyODc1OSwtMz
IzNTU2MTIsLTE3NDgwMzI2OTNdfQ==
-->