# ukol-03

_V tomto úkolu využiješ znalosti z kapitoly [Slovníky a cykly](https://kodim.cz/kurzy/uvod-do-progr-2/uvod-do-programovani-2/slovniky/slovniky-a-cykly)_

---

## Zadání

Soubor [body.json](./body.json) je JSON, který obsahuje informace o získaných bodech z písemky.

* Soubor si ulož a načti do slovníku.

* Z písemky nebude známka, ale jen Pass/Fail hodnocení neboli prospěl(a)/neprospěl(a). Vytvoř nový slovník. Jeho klíče budou opět jména žáků, a hodnotou bude řetězec `"Pass"`, pokud má jednotlivec alespoň než 60 bodů. Pokud má méně než 60, hodnota bude `"Fail"`.

* Výsledný slovník ulož jako JSON do souboru `prospech.json`.

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
