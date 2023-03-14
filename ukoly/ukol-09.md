# ukol-09: Teplota ve městech

_Úkol můžeš odevzdat buďto jako Jupyter Notebook `.ipynb`, nebo jako klasický program `.py`._

Stáhni si soubor [temperature.csv](./temperature.csv), který obsahuje informace o průměrné teplotě v různých městech v **listopadu 2017**.


Vypiš si prvních několik řádků, ať si prohlédneš strukturu tabulky. 

Dále napiš následující dotazy:
* Dotaz na měření, která byla provedena v Praze. Je na datech něco zvláštního? Napadá tě, čím to může být? [Zde](https://cs.wikipedia.org/wiki/Stupe%C5%88_Fahrenheita) je nápověda.
* Dotaz na měření, ve kterých je teplota (sloupec `AvgTemperature`) vyšší než 80 stupňů.
* Dotaz na měření, ve kterých je teplota vyšší než 60 stupňů a současně bylo měření provedeno v regionu (sloupec `Region`) Evropa (Europe).
* Dotaz na extrémní hodnoty, tj. měření, ve kterých je teplota vyšší než 80 stupňů nebo menší než -20 stupňů.

---

## Nepovinný bonus 1

Nainstaluj si modul `pytemperature` a zkus si vytvořit nový sloupec, který bude obsahovat průměrnou templotu ve stupních Celsia.

Ve svém programu nejprve proveď import modulu `pytemperature`. Nový sloupec pak přidáš do tabulky tak, že nalevo od `=` vložíš tabulku a název nového sloupce do hranatých závorek. Napravo pak můžeš provádět výpočty pomocí již existujících sloupců. Můžeš např. použít funkci `f2c` z modulu `pytemperature`, která převede teplotu ze stupňů Fahrenheita na stupně Celsia.

```python
import pytemperature

df["AvgTemperatureCelsia"] = pytemperature.f2c(df["AvgTemperature"])
```

Nyní můžeš zpracovat následující příklady:

* Dotaz na měření, ve kterých je teplota (sloupec `AvgTemperatureCelsia`) vyšší než 30 stupňů Celsia.
* Dotaz na měření, ve kterých je teplota vyšší než 15 stupňů Celsia a současně bylo měření provedeno v regionu (sloupec `Region`) Evropa (Europe).
* Dotaz na extrémní hodnoty, tj. měření, ve kterých je teplota vyšší než 30 stupňů Celsia nebo menší než -10 stupňů. Jsou některé hodnoty podezřelé?

---

## Nepovinný bonus 2

Pokračuj ve své práci s informacemi o průměrných teplotách. Pokud jsi zpracoval/a první bonus, můžeš pracovat s teplotami ve stupních Celsia.

Napiš následující dotazy:

* Dotaz na řádky z 13. listopadu 2017 (sloupec `Day` musí mít hodnotu 13).
* Dotaz na řádky z 13. listopadu 2017 ze Spojených států amerických (sloupec `Day` musí mít hodnotu 13 a sloupec `Country` hodnotu US). Výsledek dotazu si ulož do nové tabulky a použij ji jako vstup pro následující dotaz.
* Pro data z předchozího dotazu napiš dotaz na řádky ve městech (sloupec `City`) Washington a Philadelphia.