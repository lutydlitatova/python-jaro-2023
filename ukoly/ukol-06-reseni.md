# ukol-06

## Zadání

1. Pomocí nástroje regex101 vymysli regulární výraz, který označí platná data a neoznačí neplatná data:

* platná data:
```
2.2.2022
13. 8. 1999
4/5/2001
```

* neplatná data:
```
5.123.458.91
21.4
8./9
```

---
Zde je mnoho variant, například:
```
\d\d?[./] ?\d\d?[./] ?\d{4}
```

```
\d{1,2}[./] ?\d{1,2}[./] ?\d{4}
```

```
(\d\d?[./] ?){2}\d{4}
```

```
(\d{1,2}[./] ?){2}\d{4}
```

---

2. Zkopíruj si obsah souboru [posta.txt](posta.txt) do regex101 jako testovací řetězec. Vymysli regulární výraz, který označí všechny "poslední řádky adresy" v textu. Poslední řádka adresy zpravidla obsahuje PSČ a název obce, například `190 16 PRAHA 916` nebo `742 45 FULNEK`. Celkem by jich mělo být 18.

---
Například:
```
\d{3} \d{2}  ?\w+ ?\w+ ?\w+ ?\d*
```

```
\d{3} \d{2}  ?(\w ?)+( \d+)?
```
---

## Nepovinný bonus

Napiš program, který se zeptá uživatele na jeho přihlašovací jméno, e-mailovou adresu a heslo. Po každém zadaném údaji program ověří jeho správnost podle následujících pravidel:

* uživatelské jméno smí obsahovat malá a velká písmena (nesmí obsahovat žádné jiné znaky), jeho minimálná délka je 6 znaků a jeho maximální délka je 10 znaků.
* heslo smí obsahovat malá a velká písmena, číslice, a následující speciální znaky: `_`, `-`, `.`, `+`, `=`. Jeho minimálná délka je 12 znaků a jeho maximální délka je 30 znaků.
* e-mail by měl být validním e-mailem :slightly_smiling_face: Tady jsou nějaké testovací příklady (viz [zdroj](https://gist.github.com/cjaoude/fd9910626629b53c4d25))
  * příklady platných e-mailových adres:
    ```
    email@example.com
    firstname.lastname@example.com
    email@subdomain.example.com
    firstname+lastname@example.com
    email@123.123.123.123
    email@[123.123.123.123]
    "email"@example.com
    1234567890@example.com
    email@example-one.com
    _______@example.com
    email@example.name
    email@example.museum
    email@example.co.jp
    firstname-lastname@example.com
    ```
  * příklady neplatných e-mailových adres:
    ```
    plainaddress
    #@%^%#$@#$@#.com
    @example.com
    Joe Smith <email@example.com>
    email.example.com
    email@example@example.com
    .email@example.com
    email.@example.com
    email..email@example.com
    あいうえお@example.com
    email@example.com (Joe Smith)
    email@example
    email@-example.com
    email@example.web
    email@111.222.333.44444
    email@example..com
    Abc..123@example.com
    ```

  *Zkuste se zaměřit na to, aby program pokryl co nejvíce platných e-mailových adres. Cílem není pokrýt všechny platné, a vyloučit všechny neplatné, ale zkusit si napsat regex, který to zvládne co nejlépe, i když třeba ne perfektně! Bonus odevzdej, i když nebude dokonalý.*

---
Například:

```py
import re

prihlasovaci_jmeno_regex = re.compile(r"[a-zA-Z]{6,10}")
email_regex = re.compile(r"[\w_+.\"-]+@\[?[\w-]+(\.[\w-]+)*\]?")
heslo_regex = re.compile(r"[\w_\-.+=]{12,30}")

prihlasovaci_jmeno = input("Zadejte prihlasovaci jmeno: ")
if not prihlasovaci_jmeno_regex.fullmatch(prihlasovaci_jmeno):
    print(
        "Nesprávný formát uživatelského jména. "
        "Uživatelské jméno smí obsahovat malá a velká písmena "
        "(nesmí obsahovat žádné jiné znaky), jeho minimálná délka je 6 znaků "
        "a jeho maximální délka je 10 znaků."
    )

email = input("Zadejte e-mailovou adresu: ")
if not email_regex.fullmatch(email):
    print("Neplatná e-mailová adresa.")

heslo = input("Zadejte heslo: ")
if not heslo_regex.fullmatch(heslo):
    print(
        "Nesprávný formát hesla. "
        "Heslo smí obsahovat malá a velká písmena, číslice, "
        "a následující speciální znaky: `_`, `-`, `.`, `+`, `=`. "
        "Jeho minimálná délka je 12 znaků a jeho maximální délka je 30 znaků."
    )
```
