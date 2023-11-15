## Fent cares

Abans que hi hagués emoji, hi havia [emoticones](https://en.wikipedia.org/wiki/List_of_emoticons) , on el text semblava `:)`a una cara feliç i el text semblava `:(`a una cara trista. Avui en dia, els programes solen convertir les emoticones en emoji automàticament!

En un fitxer anomenat `faces.py`, implementeu una funció anomenada `convert`que accepta a `str`com a entrada i retorna la mateixa entrada amb qualsevol `:)`convertit a ![🙂](https://twemoji.maxcdn.com/v/14.0.2/72x72/1f642.png)(també conegut com a [cara lleugerament somrient](https://emojipedia.org/slightly-smiling-face/) ) i qualsevol `:(`convertit a ![🙁](https://twemoji.maxcdn.com/v/14.0.2/72x72/1f641.png)(també conegut com a [cara lleugerament arrugada](https://emojipedia.org/slightly-frowning-face/) ). La resta de text s'ha de retornar sense canvis.

A continuació, en aquest mateix fitxer, implementeu una funció anomenada `main`que demana l'entrada a l'usuari, crida `convert`a aquesta entrada i imprimeix el resultat. És benvingut, però no és obligatori, demanar a l'usuari de manera explícita, com passant un `str`propi com a argument a `input`. Assegureu-vos de trucar `main`a la part inferior del fitxer.


-   Recordeu que `input` retorna un `str`.
-   Recordeu que a `str`inclou molts mètodes, segons [documentació de mètodes](https://docs.python.org/es/3/library/stdtypes.html#string-methods). En aques cas necessitaràs la funció `str.replace()`. La qual pren 2 arguments. Investiga per a verure exemples d'ús.
-   Un emoji és en realitat només un caràcter, així que pots citar-lo com qualsevol `str`, a la com `🥰` . I pots copiar i enganxar l'emoji d'aquesta pàgina al teu propi codi segons sigui necessari.!

## Abans que comencis

Executeu `cd`\-lo sol a la finestra de la vostra terminal. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
$
```
A continuació executeu
```
mkdir faces
```
per crear una carpeta cridada `faces`al vostre espai de codi.
```
cd faces
```
Després executar
```
cd faces
```

per canviar els directoris a aquesta carpeta. Ara hauríeu de veure el missatge del vostre terminal com a `faces/ $`. Ara pots executar
```
code faces.py
```
per crear un fitxer anomenat `faces.py`on escriureu el vostre programa.

## Com provar

A continuació s'explica com provar el codi manualment:

Podeu executar el següent per comprovar el vostre codi mitjançant `check50`, un programa que s'utilitzarà per provar el vostre codi quan l'envieu. Però assegureu-vos de provar-ho vosaltres mateixos també!

```
check50 cs50/problems/2022/python/faces
```

Les emoticones verdes signifiquen que el vostre programa ha superat una prova! Les frases vermelles indicaran que el vostre programa ha sortit alguna cosa inesperada. Visiteu l'URL que `check50`surt per veure l'entrada `check50`lliurada al vostre programa, quina sortida esperava i quina sortida va donar realment el vostre programa.

## Com enviar

Al vostre terminal, executeu el següent per enviar el vostre treball.

```
submit50 cs50/problems/2022/python/faces
```
