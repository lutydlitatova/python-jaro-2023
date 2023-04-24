# ukol-03

## Zadání

Soubor [body.json](./body.json) je JSON, který obsahuje informace o získaných bodech z písemky.

* Soubor si ulož a načti do slovníku.

* Z písemky nebude známka, ale jen Pass/Fail hodnocení neboli prospěl(a)/neprospěl(a). Vytvoř nový slovník. Jeho klíče budou opět jména žáků, a hodnotou bude řetězec `"Pass"`, pokud má jednotlivec alespoň než 60 bodů. Pokud má méně než 60, hodnota bude `"Fail"`.

* Výsledný slovník ulož jako JSON do souboru `prospech.json`.

---

```py
import json

with open("body.json", "r") as infile:
    body = json.load(infile)

prospech = {}

for student in body:
    if body[student] >= 60:
        prospech[student] = "Pass"
    else:
        prospech[student] = "Fail"

with open("prospech.json", "w") as outfile:
    json.dump(prospech, outfile, ensure_ascii=False, indent=4)
```

---

## Nepovinný bonus

Krom souboru s body si ulož a načti do druhého slovníku ještě soubor [bonusy.json](./bonusy.json). Obsahuje bonusové body získané během semestru. Pozor, bonusové body získali jen někteří žáci.

Tvým úkolem je žákům přiřadit známky na základě *součtu* bodů z písemky a bonusových bodů. Bodová rozhraní (vztahují se na součet) najdeš zde:

```
1: 90 a více
2: 70-89
3: 50-69
4: 30-49
5: 29 a méně
```

* Výsledný slovník ulož jako JSON do souboru `znamky.json`.

---

```py
with open("bonusy.json", "r") as infile:
    bonusy = json.load(infile)

znamky = {}

for student in body:
    # Spocteme celkovy pocet bodu
    if student in bonusy:
        body_celkem = body[student] + bonusy[student]
    else:
        body_celkem = body[student]
    # Urcime znamku na zaklade celkoveho poctu bodu
    if body_celkem >= 90:
        znamka = 1
    elif body_celkem >= 70:
        znamka = 2
    elif body_celkem >= 50:
        znamka = 3
    elif body_celkem >= 30:
        znamka = 4
    else:
        znamka = 5
    # Ulozime znamku do slovniku
    znamky[student] = znamka

with open("znamky.json", "w") as outfile:
    json.dump(znamky, outfile, ensure_ascii=False, indent=4)
```
