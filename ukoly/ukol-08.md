# ukol-08: Adopce zvířat

_Úkol můžeš odevzdat buďto jako Jupyter Notebook `.ipynb`, nebo jako klasický program `.py`._

Stáhni si [dataset](https://raw.githubusercontent.com/lutydlitatova/czechitas-datasets/main/datasets/adopce-zvirat.csv), který obsahuje seznam zvířat k adopci v ZOO Praha. Zdroj dat je [Národní katalog otevřených dat](https://data.gov.cz/).

* Data si načti pomocí metody `pandas.read_csv()`. Pozor, nastav oddělovač na znak středníku. Využij parametr `sep`.

* Seznam se s daty. Kolik má tabulka řádek a sloupců? Jak se sloupce jmenují?

* Které zvíře se nachází na záznamu s indexem 34? Vypiš název tohoto zvířete v češtině a v angličtině.

---

## Nepovinný bonus

Využij metody [`sort_values()`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html) (a libovolných dalších metod), ke zjištění následujících informací:
* Adopce kterých zvířat je nejdražší?
* Které zvíře je alfabeticky poslední v češtině? Které v angličtině?

Bonus můžeš doplnit o nějaké vlastní pozorování.
