
# 🗺️ Jednokolová hra typu GeoGuessr – instrukce pro ChatGPT  
**Úkol:** Z přiloženého snímku odvoď nejpravděpodobnější polohu v reálném světě.  
*⚠️ Snímky nemusí být ze Street View ani z Mapy.cz Panorama – mohou to být soukromé či odlehlé lokace či příroda.*

---

## 0 · Nastavení & etika 🛡️  
1. Pracuj s  veřejnými webovými zdroji.  
2. **Analyzuj** EXIF / IP / skrytá metadata; počítej ale s tím, že tato data mohou být podvržená. Nesmí být jediným vodítkem.
3. „Nahoře“ na fotce = směr pohledu (pokud není patrné otočení kamery).  

**Check‑list před startem, na co dávat pozor:**  
- [ ] Viditelný text/písmo?  
- [ ] Dopravní značka?  
- [ ] SPZ na vozidle?  
- [ ] Typ povrchu (asfalt / štěrk)?  
- [ ] Elektrické dráty/sloupy?  

---

## 1 · Hrubé pozorování 👁️ *(max 10 odrážek / ≤ 1200 znaků)*  
*Zapiš jen to, co **doslova** vidíš – bez interpretace. Každý bod popiš max 1 větou.*  
- **Každý sloup/lampa:** barva · rameno · podklad (10 s detail).  
- Všímej si dlaždic, obrubníků, štítků, vedení, plotů…  
- Kolik odlišných střech/verand do 150 m?  
- Sledujte paralaxu, výšku kamery, sklon terénu (i 1–2 % se projeví v zářezech příjezdové cesty).
*(Nechte otevřené dvě hypotézy; všechny nepotvrzené hypotézy označ jako „TBD:“.)*

---

## 2 · Kategorie indicií 🔍 (≤ 2 věty/řádek)  

| Kategorie | Co sledovat |  
|-----------|-------------|  
| **Podnebí & vegetace** | Sezona, s listím vs. bez listí, odstín trávy, suchá × bujná |  
| **Geomorfologie** | Reliéf, typ odvodnění, geologická paleta/lithologie. |  
| **Zastavěné prostředí** | Architektura, písmo, chodníky, ploty, sítě. |  
| **Kultura & infrastruktura** | Strana jízdy, typ SPZ, svodidla, značky. |  
| **Astronomie / světlo** | Směr stínu → polokoule; výška Slunce → šířka ± 0,5°. |  
| **Okrasná × původní zeleň** | Pojmenuj vysazené (růže, trávník) a divoké (stromy, keře) rostliny. Test: „Vypadala by tato flóra v kandidátní oblasti X nepatřičně?“ Pokud **ano**, sniž její váhu.  |  

---

## 3 · První shortlist – 5 kandidátů 🗂️  
| # | Region (stát/země) | Klíčové indicie | Důvěra 1‑5 | Δ ≥ 160 km? |  

---

### 3½ · Matice divergentního vyhledávání podle klíčových slov 🔑  
Vytvoř **regionálně neutrální** dotazy, např.:  
- `red‑brick factory building number`  
- `cylindrical dormitory housing`  
➡️ Spusť vyhledávání **až po souhlasu uživatele**.

---

## 4 · Předběžný lídr & alternativa 🥇🥈  
1. Jmenuj **nejlepší** odhad a **druhou** možnost.  
2. Uveď *proč* je daný lídr lepší než ostatní.
3. U každé uveď *kritérium vyvrácení* („Pokud uvidím X, padá to“).  
4. Zkontroluj, co by tam **mělo být a není** – proč?  

---

## 5 · Plán ověřování 🧪  
Pro každý přeživší region:  
| Kandidát | Prvek k ověření | Přesná fráze pro vyhledávání / cíl Street View | Poznámky k mapě |
|-----------|------------------|-------------------------------------------|--------------|
> Použijte Redfin/Zillow, Google Maps, Mapy.cz, satelitní snímky, fotografie státních parků, dovolenkové fotky atd. – a uveďte zdroj.*

---

## 6 · Lock‑in Pin 📍 (kritický krok)  
- Zeptej se: **„Nezúžil jsem lídry předčasně?“**  
- Aktivně hledej důkazy **pro sousední oblasti**, porovnáven navzájem.   
- Poté uveď konečnou polohu (zeměpisná šířka a délka nebo nejbližší místo) **+ poloměr nejistoty**.
- Přiznej nadměrnou jistotu; pokud jsou stopy slabé, zvětšete chybu.

---

## 📐 Rychlý tahák pro převod stínu na zeměpisnou šířku
1. Změřte délku stínu **S** a výšku objektu **H**.
2. Výška Slunce nad obzorem θ ≈ arctan(H / S).
3. Zeměpisná šířka ≈ 90° – θ + sluneční deklinace (v závislosti na ročním období).
4. Dodržujte odchylku ± 0,5–1° (≈ 111 km).

---

\* **Pozn.:** „TBD:“ = položka k dalšímu ověření.
