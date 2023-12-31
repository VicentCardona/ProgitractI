## Veu d'interior

ESCRIURE EN MAJÚSCULES ÉS COM CRIDAR.

El millor és fer servir la vostra "veu d'interior" de vegades, escrivint completament en minúscules.

Implementeu un programa a `indoor.py`en Python que demana l'entrada a l'usuari i després emet la mateixa entrada en minúscules. La puntuació i els espais en blanc s'han de mostrar sense canvis. És benvingut, però no és obligatori, demanar a l'usuari de manera explícita, com passant un `str`propi com a argument a `input`.

Per exemple:

```
Introduce un texto: Vicent Cardona
Texto en minúsculas: vicent cardona
```

<details>
<summary>Pistes</summary>
<br>

  -   Recordeu que `input`retorna un `str`.
  -   Recordeu que a `str`inclou molts mètodes, segons [documentació de mètodes](https://docs.python.org/es/3/library/stdtypes.html#string-methods) trobem un mètode anomenat `str.lower()`.
</details>

## Abans que comencis

Executeu `cd` sol a la finestra del vostre terminal. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
$
```

A continuació, executeu
```
mkdir indoor
```

per crear una carpeta anomenada `indoor` al vostre espai de codi.

Després executar
```
cd indoor
```

per canviar els directoris a aquesta carpeta. Ara hauríeu de veure el missatge del vostre terminal com `indoor/ $`. Ara podeu executar
```
code indoor
```

per crear un fitxer anomenat `indoor.py` on escriureu el vostre programa.

## Com provar

El primer de tot, proveu vosaltres mateixos:

-   Executeu el vostre programa ` indoor.py`. Escriviu `HOLA`i premeu Enter. El vostre programa hauria de sortir `hola`.
-   Executeu el vostre programa ` indoor.py`. Escriviu `AIXÒ ES PROGITRACT1`i premeu Enter. El vostre programa hauria de sortir `això es progitract1`.
-   Executeu el vostre programa ` indoor.py`. Escriviu `50`i premeu Enter. El vostre programa hauria de sortir `50`.


Si trobeu un error que diu que el vostre fitxer no es pot obrir, torneu sobre els vostres passos per assegurar-vos que sou a la vostra carpeta `indoor` i que heu desat el vostre `indoor.py` fitxer allà. Recordeu com?

Podeu executar el següent per comprovar el vostre codi mitjançant `check50`, un programa que CS50 utilitzarà per provar el vostre codi quan l'envieu. Però assegura't de provar-ho tu mateix!

```
check50 cs50/problems/2022/python/indoor
```

Les emoticones verdes signifiquen que el vostre programa ha superat una prova! Els cenys vermells indicaran que el vostre programa ha sortit alguna cosa inesperada.
## Com enviar

Atèn a les explicacions del teu professor per a enviar.
