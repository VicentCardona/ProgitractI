## El que faràs

Descobreix el poder de les llistes en Python creant un gràfic interactiu de medalles olímpiques.

**Els Jocs Olímpics** van començar el 1896: milers d'atletes representen centenars de nacions d'arreu del món. Els jocs moderns es van inspirar en els antics concursos celebrats a Olímpia, Grècia.

El que faràs:

-   Utilitzar **llistes** per emmagatzemar dades relacionades
-   Crear un **gràfic** utilitzant la biblioteca `pygal`
-   Carregar dades fent que el programa **llegeixi un fitxer**
- 
## Fes un gràfic

Crear un gràfic i algunes llistes de dades per mostrar-hi.

![Un gràfic de barres que mostra les medalles guanyades pels Estats Units, la Gran Bretanya i França.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list.png)

Obriu el [projecte inicial de Representant Campions](https://editor.raspberrypi.org/en/projects/charting-champions-starter) . L'editor de codi Raspberry Pi s'obrirà en una altra pestanya del navegador.

Si teniu un compte de Raspberry Pi, podeu fer clic a **Desa** per desar una còpia del codi d'inici a la vostra biblioteca.

Si no utilitzeu l'editor de codi al vostre navegador, haureu de descarregar els fitxers del projecte i és possible que hàgiu d'instal·lar-lo `pygal`abans de poder-lo importar.

### Fitxers de projecte fora de línia

### Instal·lació de pygal

El projecte inicial ja té algun codi per importar la `pygal`biblioteca, que utilitzareu per dibuixar el vostre gràfic.

main.py

```python
from pygal import bar
```

### Fes un gràfic

Cerqueu el comentari  `# Create a chart` i afegiu el codi a sota per fer un gràfic de barres anomenat `grafic` i doneu un títol al vostre gràfic.

main.py

```python
# Create a chart
grafic = Bar(title='Medalles Olímpiques')
```

Executeu `grafic.render()`per mostrar el gràfic.

main.py

```python
# Display the chart
grafic.render()
```

**Prova:** executeu el vostre codi per veure el gràfic. Estarà buit perquè encara no té dades.

![Les paraules "medalles olímpiques" sobre fons negre.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/empty_chart.png)


### Afegeix algunes dades

Python pot emmagatzemar dades relacionades com una **llista** . Podeu crear llistes utilitzant `[]`. Els elements d'una llista es separen amb comes.

Creeu tres llistes de dades per mostrar-les al vostre gràfic.

Cada llista emmagatzemarà el nom d'una nació i el nombre de medalles guanyades per aquesta nació.


```python
# Add data to the chart
us = ['United States', 2399]
gb = ['Great Britain', 1304]
fr = ['France', 751]
```

Quan emmagatzemeu alguna cosa en una llista, obté un **índex** . Un índex és un número que indica la posició d'un element en una llista. Els índexs de llista comencen de `0`, en lloc de `1`.

Podeu obtenir un element d'una llista pel seu índex. Per exemple, `my_list[3]` obtindrà el **quart** element a `my_list`, perquè els índexs comencen a `0`.

Utilitzeu els índexs de les vostres llistes i `grafic.add()`per a mostrar les vostres dades. El nom de la nació a l'element 0 s'utilitzarà com a etiqueta de categoria per al gràfic i la quantitat de medalles a l'element 1 determinarà l'alçada de la barra.



```python
gb = ['Great Britain', 1304]

grafic.add(us[0], us[1])
grafic.add(gb[0], gb[1])
grafic.add(fr[0], fr[1])
```

**Prova:** executeu el vostre codi per veure el gràfic.

![Un gràfic de barres que mostra les medalles guanyades pels Estats Units, Rússia i la Gran Bretanya.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list.png)

**Depuració** : si veieu un missatge sobre un `IndexError`, el vostre codi està intentant obtenir un valor d'un índex de llista que no existeix (p. ex. `us[2]`). Per solucionar això:

-   Comproveu cadascuna de les vostres línies `grafic.add` per assegurar-vos que només utilitzeu `0`i `1`com a índexs.
-   Comproveu les línies on heu creat les vostres llistes. Assegureu-vos que cada llista té dos elements, separats per una coma.

Ara carrega dos equips més afegint llistes i nous `grafic.add()`.



```python
# Add data to the chart
us = ['United States', 2399]
gb = ['Great Britain', 1304]
fr = ['France', 751]
ge = ['Germany', 655]
ch = ['China', 636]
grafic.add(us[0], us[1])
grafic.add(gb[0], gb[1])
grafic.add(fr[0], fr[1])
grafic.add(ge[0], ge[1])
grafic.add(ch[0], ch[1])
```

**Prova:** executeu el vostre codi per veure el gràfic actualitzat. Intenta fer clic al nom dels Estats Units. A continuació, observeu el canvi d'escala del gràfic.

![Un gràfic de barres que mostra les medalles guanyades pels Estats Units, la Gran Bretanya, França, Alemanya i la Xina. Quan es fa clic al nom dels Estats Units, la barra més alta desapareix del gràfic, que canvia la mida.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list_2.gif)

**Depuració** : si veieu un missatge sobre un `IndexError`, el vostre codi està intentant obtenir un valor d'un índex de llista que no existeix (p. ex. `fr[2]`). Per solucionar això:

-   Comproveu les línies on heu creat les vostres llistes. Assegureu-vos que cada llista té dos elements, separats per una coma.
  
## Carregar dades d'un fitxer

El gràfic té bona pinta! Però, gairebé 150 nacions han competit als Jocs Olímpics. Per dibuixar-los, carregareu les seves dades des d'un fitxer. Estalviarà molt d'escriptura!

![Un gràfic de barres que mostra el recompte de medalles de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

**Ordinadors i dades** Tot just esteu començant a aprendre a fer que el vostre ordinador funcioni amb dades. Els ordinadors poden fer coses sorprenents amb les dades adequades. I poden llegir més dades en minuts que un humà en anys. Python és un dels millors llenguatges de programació que hi ha per a dades. Python és el que fa l'algoritme de YouTube, que tria els vídeos per mostrar-vos.

Obriu el [segon projecte inicial](https://editor.raspberrypi.org/en/projects/charting-champions-second-starter) . L'editor de codi Raspberry Pi s'obrirà en una altra pestanya del navegador.

Hi ha diversos fitxers `.csv` inclosos en aquest projecte inicial que contenen les dades que necessiteu per als vostres gràfics.

Obriu `medals.csv` i mireu les dades que hi ha. Vegeu com cada línia té un nom d'equip i el nombre de medalles que ha guanyat, separats per una coma.

![L'editor de codi de Raspberry Pi amb el fitxer de medalles ressaltat i obert, que mostra una llista de països i números de medalles separats amb una coma.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/medals-tab.png)

**Els fitxers CSV** són fitxers de valors separats per comes. Contenen dades en files i columnes, com una taula. Cada línia és una fila, amb comes que separen els valors d'aquesta fila en columnes. ![Unes quantes línies d'un fitxer csv.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/csv_sample.png)

Haureu de convertir cada línia de `medals.csv`en una cadena de text i un número a Python, com a les llistes que heu fet.

Feu clic a la `main.py`pestanya i afegiu codi per carregar el fitxer en una variable mitjançant `with open() as`. A continuació, utilitzeu un `for`bucle a `print`cada línia de la variable.

El `for`bucle us permetrà repetir el codi. Així que carregaràs centenars d'equips al teu gràfic amb només unes poques línies de codi!

### Llegir un fitxer amb Python

main.py

```python
# Add data to the chart
with open('medals.csv') as f:
for line in f: print(line)
```

**Prova:** executeu el vostre codi i mireu el text que imprimeix.

Observeu que cada línia té dos valors, separats per comes.

![Una llista de cadenes de text, impresa en moltes línies.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/lines.png)

Cada cadena que imprimeix el vostre bucle està formada per dues peces separades per una coma. La vostra `grafic.add()`funció necessita cadascuna d'aquestes peces com a entrades separades.

La funció `split()` divideix una cadena en una llista, igual que les llistes que heu fet anteriorment. La `split(',')`funció crea un nou element de llista cada vegada que veu una coma.

Posa una `#`al davant del codi que s'imprimeix `line`. Això convertirà aquest codi en un comentari, de manera que Python l'ignorarà.

Utilitzeu el `split()`mètode per dividir cada picada en a `,`i després emmagatzemar la primera i la segona peces en una llista nova. A continuació, imprimiu aquestes llistes.

main.py

```python
with open('medals.csv') as f:

for line in f:
  #print(line)
  pieces = line.split(',')
  # Breaks the string into a list print(pieces)
  # Print each list
```

**Consell:** `split()` podeu dividir una cadena en una llista al voltant de qualsevol text que vulgueu. Podeu dividir la puntuació, una lletra o fins i tot paraules senceres.

**Prova:** executeu el vostre codi i mireu el text que imprimeix. Cada línia hauria de ser una llista amb dos elements. Podeu notar que el segon element té `\n`al final. `\n`sol ser invisible. Indica a l'ordinador que ha arribat al final de la línia d'un fitxer.

![Moltes llistes, cadascuna amb dos elements, impreses.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/tally.png)

**Depuració:** si `pieces`esteu imprimint com a llistes amb només un element, comproveu que teniu `','`a `()`la `line.split()`.

**Depuració:** si veieu un missatge sobre `split`"no definit", comproveu que l'heu inclòs `line.`abans.

Carregueu les vostres dades al gràfic com a part del vostre `for`bucle. `team`és una cadena per la qual cosa es pot utilitzar com a etiqueta al gràfic. `medal`actualment és una cadena, però s'ha de convertir en un número. Podeu utilitzar la `int()`funció per **llançar** una cadena a un número.


```python
with open('medals.csv') as f:
  for line in f:
    #print(line)
    pieces = line.split(',')
    #print(pieces)
    team = pieces[0]
    medals = pieces[1]
    grafic.add(team, int(medals))
    # Make medals a number
```

**Consell:** ara també podeu utilitzar `#`per convertir-lo `print(pieces)`en un comentari.

**Prova:** executeu el vostre codi i mireu el gràfic que crea. Proveu de passar el cursor per sobre d'algunes de les barres o feu clic als noms dels equips per afegir-los i eliminar-los del gràfic.

![Un gràfic de barres que mostra el recompte de medalles de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

**Depuració:** si el vostre gràfic està buit, comproveu que teniu `int(medals)`al vostre `chart.add()`.

**Depuració:** si veieu un missatge sobre un `IndexError`, el vostre codi està intentant obtenir un valor d'un índex de llista que no existeix (p. ex. `pieces[2]`). Per solucionar això:

-   Comproveu cadascuna de les vostres variables `team`i `medals`per assegurar-vos que només utilitzeu `0`i `1`com a índexs.
-   Comproveu les `pieces`llistes impreses per assegurar-vos que tenen dos elements: `['Tonga', '1\n']`, no `['Tonga,1\n']`. Si no ho fan, comproveu que teniu `','`a la `()`de `line.split()`.
-   Comproveu que no teniu cap línia en blanc a la part inferior del fitxer .csv.

## Investiga amb dades

Ara el vostre programa pot dibuixar gràfics a partir de fitxers de dades. Podeu utilitzar-lo en diferents fitxers per comparar els seus gràfics i veure què podeu aprendre.

![Un gràfic de barres que mostra les poblacions de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

### Qui té més medalles?

Mira el gràfic que has fet. Com més alta sigui una barra, més medalles ha guanyat aquest equip. Passeu el ratolí per sobre d'algunes de les barres més altes i observeu a quins equips pertanyen.

![Un gràfic de barres que mostra les poblacions de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

Per què podrien tenir més medalles?

Una bona idea podria ser mirar tant la població com la riquesa dels equips, per veure si hi ha algun tipus de patró.

**Anàlisi de dades:** la gent ha fet aquest tipus d'investigacions des de molt abans que s'inventessin els ordinadors. Per exemple, a la dècada de 1850, Florence Nightingale, una infermera, va utilitzar gràfics i gràfics per mostrar la importància de la prevenció de malalties per atendre els malalts. ![Carta de causes de mortalitat de Florence Nightingale.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/nightingale.jpeg)

### Mides de la població

Un fitxer, anomenat `pop.csv`, amb dades sobre les poblacions de diferents països, forma part del projecte d'arrencada. Com que les dades `pop.csv`també estan formades per una cadena de text i un número, podeu reutilitzar el vostre codi només amb petits canvis.

Canvieu el títol del gràfic, la `width`del gràfic, el fitxer que esteu obrint i el nom de la categoria per dibuixar un gràfic a partir de les dades de població a `pop.csv`.

main.py

```python
chart = Bar(title='Population', width='600')
# Add data to the chart

 with open('pop.csv') as f:
for line in f:
  #print(line)
  pieces = line.split(',')
  #print(pieces)
  team = pieces[0]
  population = pieces[1]
  grafic.add(team, int(population))
  # Make population a number
```

Ara executeu el vostre programa i mireu el gràfic que dibuixa.

![Un gràfic de barres que mostra les poblacions de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/pop.gif)

Passeu el ratolí per sobre de les barres més grans i observeu a quins països pertanyen. Feu clic als noms dels més grans per eliminar-los del gràfic; això us permetrà veure de prop els altres. Algun dels països amb molta gent té un gran nombre de medalles?

### Riquesa

Un fitxer anomenat `gdp.csv`forma part del projecte inicial. Té dades sobre el PIB anual de diferents països. Igual que amb `pop.csv`, només haureu de fer petits canvis per utilitzar-lo.

**El PIB** és el Producte Interior Brut. Mesura el valor, en diners, de tot el que es produeix en una àrea durant un període de temps determinat. Pot mesurar la riquesa d'una zona.

Canvieu el títol del gràfic, el fitxer que esteu obrint i el nom de la categoria per dibuixar un gràfic a partir de les dades del PIB a `gdp.csv`.

El `gdp.csv`fitxer emmagatzema el PIB com a nombres decimals. Actualitzeu el tipus de `int`a `float`perquè els números tinguin el format correcte.

main.py

```python
chart.title = 'GDP'
# Add data to the chart
with open('gdp.csv') as f:
for line in f:
#print(line)
pieces = line.split(',')
#print(pieces)
team = pieces[0]
gdp = pieces[1]
chart.add(team, float(gdp))
# Make GDP a number
```

Ara executeu el vostre programa i mireu el gràfic que dibuixa.

![Un gràfic de barres que mostra el PIB de moltes nacions. La informació apareix quan el ratolí passa per sobre d'una barra. Les barres desapareixen quan es fa clic als noms de les nacions.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/gdp.gif)

Passeu el ratolí per sobre de les barres més grans i observeu a quins països pertanyen. Feu clic als noms dels més grans per eliminar-los del gràfic; això us permetrà mirar més de prop els altres. Algun dels equips dels països més rics va tenir un gran nombre de medalles?

### Què has trobat?

Què vas descobrir utilitzant el teu programa per mirar aquestes dades?

-   Hi ha alguns indicis que el nombre de persones que ha de triar un equip l'ajuda a guanyar medalles.
-   Però la població no explica com països com França tenen tantes medalles. O per què l'Índia no té tantes medalles com la Xina o els EUA.
-   Els diners sembla que expliquen més. La majoria dels països que tenen moltes medalles també tenen un PIB elevat.
-   Cap dels dos ho explica tot. Hi ha equips que no segueixen aquest patró.

### Jamaica ho fa millor que els països més grans i rics

Així que hi ha més coses per guanyar medalles olímpiques que només persones i diners. Què més podria ser? Quines altres idees podríeu provar i quin tipus de dades necessitaríeu per fer-ho?

[](https://projects.raspberrypi.org/en/projects/charting-champions/2)[Test ràpid](https://projects.raspberrypi.org/en/projects/charting-champions/4)

## Actualitza el teu projecte

En aquest pas, canvieu l'aspecte del vostre gràfic o quines dades utilitza.

![Un gràfic circular que mostra el temps d'execució de les pel·lícules de Marvel.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/mcu_pie.png)

### Utilitzeu un gràfic circular

Proveu d'utilitzar un gràfic circular per a un aspecte diferent o per mostrar com es divideix alguna cosa.

Per crear un gràfic circular en lloc d'un gràfic de barres, canvieu la importació de `pygal`a `Pie`en lloc de `Bar`. Feu el mateix per a la funció que crideu per crear `chart`.

### Utilitzeu un conjunt de dades diferent

Podeu carregar i dibuixar qualsevol dada que hi hagi en un `.csv`fitxer amb el programa que heu escrit.

**Trieu:** Trieu un fitxer de dades diferent per al vostre projecte. N'hi ha dos disponibles:

-   `mcu.csv`és el temps d'execució i els ingressos bruts de les pel·lícules de Marvel Cinematic Universe
-   `carbon.csv`és el total (milers de tones) i les emissions de diòxid de carboni per persona (tones) de diferents països i regions

Actualitzeu el codi que llegeix de `medals.csv`per llegir des del vostre fitxer nou.

Aquests fitxers tenen més d'una columna de números. Utilitzeu els índexs de la `tally`llista per triar quins voleu afegir al vostre gràfic.

Les dades de diòxid de carboni utilitzen números amb decimals. Per convertir-los a partir de cadenes de text, haureu d'utilitzar `float()`en comptes de `int()`.

