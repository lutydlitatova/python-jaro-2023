# ukol-05

## Zadání

Mějme zadaný následující seznam naměřených teplot. Seznam obsahuje teploty naměřené pro každý den v týdnu ve čtyřech časech - ráno, v poledne, večer a v noci.

```py
teploty = [
    [2.1, 5.2, 6.1, -0.1],
    [2.2, 4.8, 5.6, -1.0],
    [3.3, 6.5, 5.9, 1.2],
    [2.9, 5.6, 6.0, 0.0],
    [2.0, 4.6, 5.5, -1.2],
    [1.0, 3.2, 2.1, -2.0],
    [0.4, 2.7, 1.3, -2.8]
]
```

1. Vytvoř seznam průměrných teplot pro každý den.
1. Vytvoř seznam ranních teplot.
1. Vytvoř seznam nočních teplot.
1. Vytvoř seznam dvouprvkových seznamů obsahujících pouze polední a noční teplotu.

---

```py
# Vytvoř seznam průměrných teplot pro každý den.
denni_prumer = [sum(den) / len(den) for den in teploty]

# Vytvoř seznam ranních teplot.
ranni_teploty = [den[0] for den in teploty]

# Vytvoř seznam nočních teplot.
# Varianta 1
nocni_teploty = [den[-1] for den in teploty]
# Varianta 2
nocni_teploty = [den[3] for den in teploty]

# Vytvoř seznam dvouprvkových seznamů obsahujících pouze polední a noční teplotu.
# Varianta 1
poledni_nocni_teploty = [[den[1], den[-1]] for den in teploty]
# Varianta 2
poledni_nocni_teploty = [[den[1], den[3]] for den in teploty]
```

---

## Nepovinný bonus

Krom teplot máme k dispozici i informaci o dnu v týdnu:

```py
teploty = [
    ["pondělí", 2.1, 5.2, 6.1, -0.1],
    ["úterý", 2.2, 4.8, 5.6, -1.0],
    ["středa", 3.3, 6.5, 5.9, 1.2],
    ["čtvrtek", 2.9, 5.6, 6.0, 0.0],
    ["pátek", 2.0, 4.6, 5.5, -1.2],
    ["sobota", 1.0, 3.2, 2.1, -2.0],
    ["neděle", 0.4, 2.7, 1.3, -2.8]
]
```

Pomocí _dict comprehension_ vytvoř slovník, který bude mít následující formát, kde klíčem bude den v týdnu, a hodnotou průměrná teplota ten den.

```
{den: průměrná teplota}
```

---

```py
print({den[0]: sum(den[1:]) / len(den[1:]) for den in teploty})

# Varianta se zaokrouhlením
print({den[0]: round(sum(den[1:]) / len(den[1:]), 2) for den in teploty})
```
