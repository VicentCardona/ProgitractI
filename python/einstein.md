# Einstein
Fins i tot si no heu estudiat física (recentment o mai!), potser haureu sentit que `E = mc^2`, on `E` representa l'energia (mesurada en Joules), `m` representa massa (mesurada en quilograms) i `c` representa la velocitat de la llum (mesurada aproximadament com 300000000 metres per segon), segons [Albert Einstein](https://en.wikipedia.org/wiki/Albert_Einstein) et al. Essencialment, la fórmula significa que massa i energia són equivalents.

En un fitxer anomenat `einstein.py`, implementeu un programa en Python que demana a l'usuari la massa com a nombre enter (en quilograms) i després produeix el nombre equivalent de Joules com a nombre enter. Suposem que l'usuari introduirà un nombre enter.

-   -   Recordeu que `input`retorna un `str`.
-   Recordeu que `int` pot convertir un `str`a un `int`, segons [documentació de funcions, enters](https://docs.python.org/es/3/library/functions.html#int)
-   Recordeu que Python inclou diverses funcions integrades, segons [documentació de funcions](https://docs.python.org/es/3/library/functions.html). . Investiga per a verure exemples d'ús.



## Abans que comencis

Inicieu sessió a [cs50.dev](https://cs50.dev/) , feu clic a la finestra del vostre terminal i executeu `cd`\-lo sol. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
$
```
A continuació executeu
```
mkdir einstein
```
per crear una carpeta cridada `einstein` al vostre espai de codi.

Després executar
```
cd einstein
```
per canviar els directoris a aquesta carpeta. Ara hauríeu de veure el missatge del vostre terminal com a `einstein/ $`. Ara pots executar
```
code einstein.py
```

per crear un fitxer anomenat `einstein.py`on escriureu el vostre programa.

## Com provar

A continuació s'explica com provar el codi manualment:

-   Executeu el vostre programa amb `python einstein.py`. Escriviu `1`i premeu Enter. El vostre programa hauria de sortir:
-   Executeu el vostre programa amb `python einstein.py`. Escriviu `14`i premeu Enter. El vostre programa hauria de sortir:
-   Executeu el vostre programa amb `python einstein.py`. Escriviu `50`i premeu Enter. El vostre programa hauria de sortir

Podeu executar el següent per comprovar el vostre codi mitjançant `check50`, un programa que CS50 utilitzarà per provar el vostre codi quan l'envieu. Però assegureu-vos de provar-ho vosaltres mateixos també!

```
check50 cs50/problems/2022/python/einstein
```

Les emoticones verdes signifiquen que el vostre programa ha superat una prova! Els cenys vermells indicaran que el vostre programa ha sortit alguna cosa inesperada. Visiteu l'URL que `check50`surt per veure l'entrada `check50`lliurada al vostre programa, quina sortida esperava i quina sortida va donar realment el vostre programa.

## Com enviar

Al vostre terminal, executeu el següent per enviar el vostre treball.

```
submit50 cs50/problems/2022/python/einstein
```
