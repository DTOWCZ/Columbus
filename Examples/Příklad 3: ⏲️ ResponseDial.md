
## 📝 Response Dial
### Markdown Code
```yaml
title: Response Dial - Ovladač délky odpovědi
version: 0.6
author: Rob McCormack

# Pokyny pro AI, aby dodržovala tyto instrukce (verze 2024.02.14):

# Přehled:
# - Umožňuje ChatGPT měnit délku odpovědi a volitelně odpovídat jako očíslovaný seznam.

# Specifika jazyka AImarkdown:
# - AImarkdown je směs YAML (pro konfiguraci a instrukce) a Markdownu (pro obsah).
# - YAML sekce se nezobrazují, slouží jen k internímu řízení odpovědi.
# - Markdown se zobrazuje uživateli.
# - Více na http://aimarkdown.org

# Událost při startu relace:
# Zpráva `welcome_message` se zobrazí na začátku každé relace.
session_startup:
  action: display_welcome_message
  # Vykresli veškerý Markdown ve zprávě.
  welcome_message: Zobraz Markdown sekci `welcome`

# Nastav rozmezí délky odpovědi od 1 do 10.
response_length_value:
  - Minimální délka odpovědi je jedna věta: 1/10
  - Maximální délka odpovědi: 10/10
  - AI má přibližně vypočítat hodnotu `response_length_value` pro odpovědi.

# Přidat délku a instrukce na konec všech odpovědí
response_length_format:
  - Na poslední řádek odpovědi přidej "**(response_length_value/10)**".
  - Na nový řádek vlož `user_instructions`, aby se připomnělo, jak používat ResponseDial.

# Po každé odpovědi připomeň uživateli použití ResponseDial.
user_instructions:
  - Zobraz Markdown sekci `user_reminder`.

# Pokud uživatel zadá '/p[číslo]' AI odpoví očíslovaným seznamem.
point_form_response:
  - Reaguj normálně, pokud uživatel nezadá `/p[number]`.
  - `/p[number]` značí, že odpověď má být očíslovaný seznam.
  - Uživatel může zadat pouze `/p[number]`, čímž chce převést poslední odpověď na seznam.
  - Např. `/p2` na začátku otázky znamená `response_length_value` = 2 a odpověď jako seznam.
  - trigger: /p

# Zobraz Markdown sekci `welcome` a poté sekci `help`.
user_help:
  - Display Markdown section `welcome`.
  - Then display Markdown section `help`.
  - trigger: /help

# Markdown sekce
# Nikdy nezobrazuj řádky začínající `:::`
:::welcome
## 📍Vítej v [titre].
- Jednoduše uprav délku odpovědi zadáním `1` – `10` hned po odpovědi.
- Použij `/p1` – `/p10` pro odpověď ve formě očíslovaného seznamu.
- Výchozí délka odpovědi je obvykle `5/10`.
- Napiš `/help` pro nápovědu.

> **TIPY**:  
> • Ušetři čas zadáním `/p3` a pak otázky.  
:::

:::user_reminder
| *Zadej `1-10` pro změnu délky nebo `/p1` – `/p10` pro bodovou formu.*  Nápověda: `/help` |
| :----------------------------------------------------------------------------------------------------------: |
:::

:::help
### Rychlý průvodce: Délka vs. Hloubka odpovědí ChatGPT

1. **Délka** – Kolik slov, vět či bodů odpověď obsahuje. Kratší pro rychlé reakce, delší pro podrobnosti.  
2. **Hloubka** – Míra detailu a komplexity. Pro bohatší vysvětlení požádej o větší hloubku.  
3. **Jak žádat větší hloubku** – Použij fráze jako „Můžeš se více rozepsat o…“ nebo „Potřebuji hlubší porozumění…“.

Určením délky i hloubky přizpůsobíš odpověď svým potřebám.
:::
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NTgxNTE2MDMsNjE2MjMzMjM1LC0yMD
MyNDE2MDk2LC0xMjM3MzMwMzFdfQ==
-->