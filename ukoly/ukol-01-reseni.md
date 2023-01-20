# ukol-01

## Zadání:

Napiš program, který bude obsahovat jednu proměnnou `jmeno`. Tato proměnná bude obsahovat libovolné křestní jméno (třeba tvoje).
Tvůj program vytvoří e-mailovou adresu na základě této proměnné, s doménou `czechitas.cz` a tuto e-mailovou adresu vypíše.

Tedy pokud bude hodnota proměnné `jmeno` například `Jindřiška`, pak program vypíše `Jindřiška@czechitas.cz`.

--- 
```py
jmeno = "Anna"

# Můžeme využít f-string (formátovaný řetězec)
print(f"{jmeno}@czechitas.cz")
# nebo klasicky spojit řetězce pomocí +
print(jmeno + "@czechitas.cz")
```

_Zahlédla jsem úkoly, kde se jméno načítalo od uživatele pomocí funkce `input`, pak úkoly kde i doména byla
uložená do proměnné a několik dalších variací, které jsou všechny samozřejmě v pořádku :clap:_

--- 

## Nepovinný bonus:

Napiš program, který bude obsahovat proměnnou `jmeno_a_prijmeni`. Obsah proměnné načti od uživatele pomocí funkce `input`. 

```py
jmeno_a_prijmeni = input("Zadejte jméno a příjmení: ")
```

Tvůj program postupně vypíše několik způsobů formátování jména:
* všechna písmena velká (vypíše např. `JANA MALÁ`)

```py
print(jmeno_a_prijmeni.upper())
```
* všechna písmena malá (vypíše např. `jana malá`)

```py
print(jmeno_a_prijmeni.lower())
```

* standardní varianta - první písmeno velké, další malá (vypíše např. `Jana Malá`)

_Můžeme využít metodu `title`:_
```py
print(jmeno_a_prijmeni.title())
```

_Nebo `jmeno_a_prijmeni` rozdělit na dvě proměnné, můžeme předpokládat, že jsou oddělená mezerou.
Pak pomocí indexace a slicingu oddělíme první znak jména a přijmení od zbytku:_
```py
jmeno = jmeno_a_prijmeni.split()[0]
prijmeni = jmeno_a_prijmeni.split()[1]
# Můžeme využít f-string (formátovaný řetězec)
print(f'{jmeno[0].upper()}{jmeno[1:].lower()} {prijmeni[0].upper()}{prijmeni[1:].lower()}')
# nebo klasicky spojit řetězce pomocí +
print(jmeno[0].upper() + jmeno[1:].lower() + " " + prijmeni[0].upper() + prijmeni[1:].lower())
```

* iniciály (vypíše např. `J. M.`)
_Pomocí výše vytvořených pomocných proměnných `jmeno` a `prijmeni`:_
```py
# Můžeme využít f-string (formátovaný řetězec)
print(f"{jmeno[0].upper()}. {prijmeni[0].upper()}.")
# nebo klasicky spojit řetězce pomocí +
print(jmeno[0].upper() + ". " + prijmeni[0].upper() + ".")
```
* křestní jméno zkrácené na první písmeno a příjmení, pokud je křestní jméno delší než 5 znaků. Jinak vypíše standardní variantu, tj. první písmeno velké, další malá
(u vstupu `Jarmila Malá` by došlo ke zkrácení křestního jména, zatímco u vstupu `Jana Malá` nikoliv)

```py
if len(jmeno) > 5:
    print(f"{jmeno[0].upper()}. {prijmeni.title()}")
    # Pripadne:
    print(f"{jmeno[0].upper()}. {prijmeni.capitalize()}")
    # Nebo:
    print(f"{jmeno[0].upper()}. {prijmeni[0].upper()}{prijmeni[1:].lower()}")
else:
    print(jmeno_a_prijmeni.title())
```
