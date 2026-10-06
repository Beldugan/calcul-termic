# Calculul termic al motorului cu ardere internă

Aplicație web pentru proiectul **Procese și caracteristici ale motoarelor cu ardere internă** (Universitatea „Ovidius” din Constanța, FIMIM, Autovehicule rutiere, anul III).

Face același calcul ca foaia `PCMAI_Calcul_termic_2026-2027.xlsx`, cu aceleași formule și rezultate:

- admisia, comprimarea, arderea (MAS izocoră; MAC cu întârziere la autoaprindere, ardere izocoră și izobară), destinderea;
- parametrii indicați, efectivi și constructivi, inclusiv recalculul cu D și S rotunjite;
- verificările T_a, T_r și P_e și încadrarea în valorile uzuale;
- diagrama indicată p–V și p–α, din 5 în 5 °RAC;
- caracteristica exterioară de turație (relațiile Leiderman);
- tabelele u, i ale gazelor și ale amestecurilor.

Metoda de calcul:

- calculul se face la 1 kg de combustibil;
- bilanțul energetic folosește energia internă și entalpia reale ale gazelor (polinoame NASA – GRI-Mech 3.0);
- interpolarea este liniară, pe grila din 50 în 50 K;
- n₁ și n₂ se obțin prin 8 iterații de punct fix.

Pentru exemplele rezolvate din îndrumar (MAS, cap. 10, și MAC, cap. 11) rezultatele coincid cu cele din Excel la nivelul erorilor de rotunjire ale calculatorului (abatere relativă sub 10⁻¹²).

## Fișiere

| Fișier | Conținut |
|---|---|
| `index.html` | pagina aplicației |
| `style.css` | aspectul, inclusiv modul întunecat și tipărirea |
| `app.js` | interfața: formularul, tabelele de rezultate, graficele, exportul CSV |
| `calc.js` | motorul de calcul (formulele din foaia Excel) |
| `tabele.js` | tabelele u, i pentru CO₂, H₂O, O₂, N₂ (Anexa A din îndrumar) |

Aplicația nu are dependențe externe și nu trimite date nicăieri. Datele introduse se păstrează în browser și în adresa paginii, așa că un link copiat deschide aceeași temă.

## Publicare pe GitHub Pages

Adresa din codul QR al îndrumarului este:

**https://beldugan.github.io/UOClectii/calcul-termic/**

Pentru ca adresa să funcționeze:

1. În depozitul `UOClectii`, creați un folder `calcul-termic`.
2. Încărcați în el cele cinci fișiere de mai sus. Pe GitHub: *Add file → Upload files*, cu calea `calcul-termic/`.
3. Faceți *Commit*. După 1–2 minute pagina este disponibilă la adresa de mai sus.

Dacă puneți aplicația în alt depozit sau în alt folder, adresa se schimbă și codul QR din îndrumar trebuie refăcut.

## Utilizare

1. Alegeți tipul motorului (MAS sau MAC) și completați datele temei. Butoanele „MAS (cap. 10)” și „MAC (cap. 11)” încarcă exemplele din îndrumar, pentru control.
2. Rezultatele se recalculează la fiecare modificare. Filele urmează foile din Excel: Admisie, Comprimare, Ardere, Destindere, Performanțe, Verificări, Diagrama, Caracteristica, Tabele.
3. Dacă ΔT_r > 5 %, aplicația propune preluarea lui T_r′ și recalcularea.
4. „Descarcă rezultatele (CSV)” salvează toate valorile într-un fișier care se deschide în Excel. „Tipărește” produce toate filele, una după alta, gata de salvat ca PDF.
