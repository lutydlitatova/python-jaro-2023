# ukol-04

## Zadání

Uvažuj, že píšeš jednoduchou aplikaci pro zasílání SMS zpráv. Napiš program, který provede následující činnosti:

1. Zeptá se uživatele na číslo, kam chce zprávu zaslat a ověří, že číslo má správný formát.
1. Zeptá se uživatele na zprávu, kterou chce zaslat. Následně vypíše, kolik zpráva bude stát.

Tvůj program bude obsahovat dvě funkce:
1. První funkce ověří telefonní číslo. Uvažuj, že telefonní číslo může být devítimístné nebo třináctimístné (pokud je na začátku předvolba "+420"). Funkce ověří, jestli je číslo platné. Pokud je platné, vrátí hodnotu `True`, jinak vrátí hodnotu `False`.
1. Druhá funkce spočte cenu zprávy. Uživatel platí 3 Kč za každých započatých 180 znaků.

Tvůj program nejprve ověří pomocí první funkce správnost telefonního čísla. Pokud není platné,
vypíše chybu, v opačném případě se zeptá na text zprávy a pomocí druhé funkce určí její cenu, kterou
vypíše uživateli.

Tipy: 
* Nemusíte kontrolovat, zda uživatel zadal skutečně číslo, či zda jsou tam i jiné znaky. To jsme
v kurzu zatím neřešili.
* Pro kontrolu předvolby použijte _slicing_ (viz první lekce) pro získání prvních 4 znaků řetězce. Ty porovnejte s řetězcem `"+420"`.

---

## Nepovinný bonus 1

Zkus svoji první funkci upravit tak, že si bude umět poradit s mezerami v telefonním čísle. Mezer se zbavíš například tak, že použiješ metodu `.replace()`.
První parametr metody `replace` je znak, který chceš nahradit, a druhý parametr nový znak. Pokud se chceš nějakého znaku zbavit, "nahraď" ho prázdným řetězcem `""`.

* Odkaz na dokumentaci metody `replace`: https://docs.python.org/3/library/stdtypes.html#str.replace

---

## Nepovinný bonus 2
Přidej svým funkcím _typování_, aby bylo jasné, jaký typy mají parametry tvých funkcí a jaká je návratová hodnota tvých funkcí.

_K typování se dostaneme až v 5. lekci. Pokud chceš, můžeš úlohu řešit předem pomocí [Čtení na doma](https://kodim.cz/kurzy/uvod-do-progr-2/uvod-do-programovani-2/vlastni-funkce/cteni-na-doma)_