# Salutació Federal Savings Bank
<iframe width="765" height="429" src="https://www.youtube.com/embed/IN6cJ_wGmsk" title="SEINFELD Bank Retention Pledge Must Say Hello 100 Dollars.wmv" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

A la [temporada 7, episodi 24](https://en.wikipedia.org/wiki/The_Invitations) de [Seinfeld](https://en.wikipedia.org/wiki/Seinfeld), [Kramer](https://en.wikipedia.org/wiki/Cosmo_Kramer) visita un banc que es compromet a donar 100 dòlars a qualsevol persona que no sigui rebut amb un "hola". En canvi, Kramer és rebut amb un "hola", que insisteix que no és un "hola", i per això demana 100 dòlars. El gerent del banc proposa un compromís: "Vas rebre una salutació que comença amb una 'h', com sonen 20 dòlars?" Kramer accepta.

En un fitxer anomenat `bank.py`, implementeu un programa que demani a l'usuari una salutació. Si la salutació comença amb "hola", sortiu `$0`. Si la salutació comença amb una “h” (però no “hola”), sortiu `$20`. En cas contrari, sortiu `$100`. Ignoreu qualsevol espai en blanc inicial de la salutació de l'usuari i tracteu la salutació de l'usuari sense distingir entre majúscules i minúscules.

- Recurdeu que un `str` o *string* inclou molts mètodes, segons [la documentació de python](https://docs.python.org/es/3/library/stdtypes.html#string-methods).
- En aquest cas, hauràs d'emprar els mètodes `str.startswith()` i `str.strip()`.

## Abans que comencis

Inicieu la sessió a [cs50.dev](https://cs50.dev/), feu clic a la finestra del vostre terminal i executeu `cd` sol. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
$
```
A continuació executau
```
mkdir bank
```
per crear una carpeta anomenada `bank` al vostre espai de codi.

Després executeu
```
cd bank
```
per canviar els directoris a aquesta carpeta. Ara haureu de veure el missatge del vostre terminal com `bank/ $`. Ara podeu executar
```
code bank.py
```
per a crear un fitxer anomenat `bank.py` on escriureu el vostre programa.

## Com provar

A continuació s'explica com provar el codi manualment:

- Executeu el vostre programa amb `python bank.py`. Escriviu `Hello` i premeu Intro. El vostre programa hauria de sortir:
```
$0 
```
- Executeu el vostre programa amb `python bank.py`. Escriviu `Hello, Newman` i premeu Intro. El vostre programa hauria de sortir:
```
$0
```
Executeu el vostre programa amb `python bank.py`. Escriviu `How you doing?` i premeu Intro. El vostre programa hauria de sortir
```
$20
```
Executeu el vostre programa amb `python bank.py`. Escriviu `What's happening?` i premeu Intro. El vostre programa hauria de sortir
```
$100
```

Podeu executar el següent per comprovar el vostre codi mitjançant `check50`. Però assegura't de provar-ho tu mateix!
```
check50 cs50/problems/2022/python/bank
```
Les emoticones verdes signifiquen que el vostre programa ha superat una prova! Els cenys vermells indicaran que el vostre programa ha sortit alguna cosa inesperada. 

## Com enviar

Realitza la prova `check 50` i fes una captura dels resultats. Descarrega l'arxiu `bank.py`y carregal juntament amb la captura a la tasca de Classroom.
