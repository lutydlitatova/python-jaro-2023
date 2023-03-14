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

2. Zkopíruj si obsah souboru [posta.txt](posta.txt) do regex101 jako testovací řetězec. Vymysli regulární výraz, který označí všechny "poslední řádky adresy" v textu. Poslední řádka adresy zpravidla obsahuje PSČ a název obce, například `190 16 PRAHA 916` nebo `742 45 FULNEK`. Celkem by jich mělo být 18.

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