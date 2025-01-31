# Sistema Solar

Coneix els diccionaris de Python creant un model del sistema solar.

**Els límits dels models:** fins i tot els models molt avançats deixen de banda detalls per fer-los més fàcils de construir i executar. De fet, no és possible fer un model precís de tot el sistema solar, ja que tots els planetes s'estiren els uns als altres a causa de la gravetat. Com a resultat, encara no s'han inventat les matemàtiques per predir on aniran exactament.  
Aquest model utilitza l'ordre dels planetes i les seves velocitats i mides. Però, per exemple, Mercuri ha de ser prou lent perquè pugueu fer-hi clic. Per tant, el model fa que Mercuri sigui més ràpid que els altres planetes, però no tan ràpid com realment és.

### El que farem:

-   Utilitzar **diccionaris** per emmagatzemar i cercar dades
-   Carregar dades d'un fitxer als **diccionaris**
-   Crear un model animat i interactiu del sistema solar mitjançant la biblioteca `p5`.

**Diccionaris:** quan feu un diccionari de Python, emmagatzema coses que podeu cercar més tard. Això s'assembla molt a un diccionari normal. Però la versió de Python pot emmagatzemar molt més que els significats de les paraules!

## Crear un diccionari

Per començar, recollireu informació sobre Mercuri i dibuixareu la seva òrbita.

![Un fons negre amb un cercle groc, envoltat per un anell blanc.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_orbit.png)

Obriu el projecte "Sistema Solar" . L'editor de codi Raspberry Pi s'obrirà en una altra pestanya del navegador.

### Fes un diccionari

Els diccionaris de Python us permeten buscar una **clau** i obtenir-ne el **valor** . Això podria ser una paraula i el seu significat, que són tots dos text. Però també podeu utilitzar una clau de text (com ara `'distance'`) per obtenir un valor que sigui un número, o qualsevol altra cosa que pugueu emmagatzemar a Python.
<details>
<summary>Diccionaris Python</summary>
<br>
Un diccionari de Python emmagatzema parells de **claus** i **valors** .

Les claus i els valors poden ser gairebé qualsevol valor que pugueu emmagatzemar a Python. Encara que les llistes i els diccionaris no poden ser claus.

Podeu utilitzar una clau per obtenir el seu valor associat.

Per fer un diccionari, feu servir claudàtors `{}`, amb `key: value`parells dins. Un parell és una clau, seguida de dos punts ( `:`), seguit del valor connectat a aquesta clau. Per exemple:

```python
persona = {
    'edat': 12,
    'altura': 149.5,
    'cabell': 'marró',
}
```

Aquí, `edat`, `altura`, i `cabell`són claus. Podeu utilitzar-los per buscar els seus valors entre claudàtors `[]`. Per exemple:

```python
print(persona['cabell'])
```

Això imprimirà el valor `marró`.
</details>

Trobeu el comentari `# funció carregar_planetes` al projecte inicial. Creeu la funció a sota del comentari. Dins de la funció, feu un diccionari `mercuri` global (es pot fer servir la variable fora de la funció). A continuació, afegeix informació sobre Mercuri al diccionari.

| clau | Valor |
| --- | --- |
| nom | Mercuri |
| color | Color (165, 42, 42) |
| mida | 15 |
| òrbita | 150 |
| velocitat | 1 |
| informació | El planeta més petit i ràpid. |

Els claudàtors `{}` s'utilitzen per començar i acabar el diccionari. Els dos punts `:`s'utilitzen per separar la clau i els valors. `,`S'utilitza una coma per separar cada element del diccionari.

```python
def load_planets():
    global mercuri

    mercuri = {
        'nom': 'mercuri',
        'colo': Color(165, 42, 42),
        'tamany': 15,
        'orbita': 150,
        'velocitat': 1,
        'info': 'El planeta més petit i més veloç'
    }
```

**Consell:** podeu posar cada parell `clau: valor` a la seva pròpia línia. Això fa que el codi sigui més fàcil de llegir, però assegureu-vos de mantenir-lo tot dins de les claus`{}`.

L'ús d'un diccionari us permet conservar tota la informació sobre Mercuri en un sol lloc. Això fa que sigui més fàcil trobar-lo i canviar-lo si cal.

Truca `load_planets()`a la teva `setup()`funció.

main.py — setup()

```python
def setup(): # Put code to run once here size(400, 400) load_planets()
```

### Dibuixa l'òrbita de Mercuri

**Modelar òrbites:** les òrbites dels planetes reals no són cercles perfectes, sinó que tenen la forma d'una el·lipse. Però utilitzar cercles fa que el model sigui més fàcil de construir!

Podeu obtenir un valor d'un diccionari posant la seva clau entre claudàtors `[]`, de la mateixa manera que obteniu un element de llista pel seu índex. Per exemple, `mercury['size']`obtindria el valor coincident `15`.

Busca el `#draw_orbits function`comentari. Creeu la `draw_orbits()`funció a sota. A continuació, dibuixeu l'òrbita de Mercuri `ellipse`centrada al centre del model `width/2`i `height/2`. La mida del `ellipse`will serà `mercury['orbit']`, que s'emmagatzema al vostre diccionari com a `150`.

### Dibuixa una el·lipse

```python
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)
    # Make it white
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
```

Exeuteu la vostra funció `draw_orbits()` des de la vostra funció `draw()`

main.py — dibuixa()

```python
def draw(): # Put code to run every frame here background(0) no_stroke() draw_sun() draw_orbits()
```

**Prova:** executeu el vostre codi i vegeu com apareix l'òrbita de Mercuri.

![Un fons negre amb un cercle groc, envoltat per un anell blanc.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_orbit.png)

**Depuració:** si veieu un missatge sobre `mercury`"no definit":

-   Comproveu la vostra `load_planets()`funció per assegurar-vos que declara `mercury`com`global`
-   Comproveu que `load_planets()`està cridat`setup()`

**Depuració:** si l'òrbita no apareix:

-   Comproveu que heu cridat `draw_orbits()`a la vostra `draw()`funció
-   Comproveu `draw_orbits()`que heu utilitzat `stroke(255)`per fer l'el·lipse blanca

**Depuració:** si l'òrbita és un cercle ple, en lloc d'un anell, comproveu que teniu `no_fill()`a la vostra `draw_orbits()`funció.

**Depuració:** si obteniu un `bad input`error, comproveu que teniu un `:`entre les claus i els valors del vostre `mercury`diccionari i que cada línia (excepte l'última) tingui una coma.

## Feu Mercuri

Ara posareu Mercuri en òrbita del sol.

![Un fons negre amb un cercle groc, envoltat per un anell blanc. Un cercle vermell orbita al voltant de l'anell.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_click.gif)

### Dibuixa Mercuri

La `make_planet()`funció s'escriu en un fitxer separat que s'inclou com a part del projecte d'inici i s'importa `main.py`per utilitzar-lo.

`make_planet()`utilitza el color, l'òrbita, la mida i la velocitat d'un planeta per dibuixar el planeta que orbita al voltant del sol.

Busca el `# draw_planets function`comentari. Creeu la funció a sota.

Feu variables per emmagatzemar els valors necessaris per dibuixar Mercuri. A continuació, crida a `make_planet()`, passant-li aquests valors.

### Paràmetres en funcions

main.py — draw\_planets()

```python
# draw_planets function def draw_planets(): colour = mercury['colour'] orbit = mercury['orbit'] size = mercury['size'] speed = mercury['speed'] make_planet( colour, orbit, size, speed )
```

**Consell:** heu creat el vostre diccionari amb una línia per a cada `key: value`parell. Podeu fer el mateix quan passeu valors a una funció per facilitar la lectura del vostre codi.

Afegiu una trucada a `draw_planets()`a la `draw()`funció.

main.py — dibuixa()

```python
def draw(): # Put code to run every frame here background(0) no_stroke() draw_sun() draw_orbits() draw_planets()
```

**Prova:** executeu el vostre codi i vegeu Mercuri en òrbita!

![Un fons negre amb un cercle groc, envoltat per un anell blanc. Un cercle vermell orbita al voltant de l'anell.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury.gif)

**Depuració:** si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a `make_planet()`. Assegureu-vos que l'ortografia sigui la mateixa en `load_planets()`. També és important que les lletres siguin majúscules o minúscules.

**Depuració:** si Mercuri no apareix:

-   Comprova que estàs `draw_planets()`trucant`draw()`
-   Assegureu-vos que aquesta trucada sigui després`background(0)`

**Depuració:** si Mercury és massa gran, massa lent o no és visible, comproveu que el vostre `draw_planets()`codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

### Parla als usuaris sobre el planeta

Els usuaris faran clic a Mercury i el vostre programa imprimirà la informació en `mercury['info']`.

La `mouse_pressed()`funció es va incloure com a part del projecte inicial. Conté codi per obtenir el valor hexadecimal d'un color en què ha fet clic un usuari. Podeu utilitzar això per dir a quin planeta han fet clic.

Cerca `mouse_pressed()`i afegeix una `if`declaració. Teniu `print`el nom i la informació de Mercuri quan l'usuari faci clic al planeta.

main.py — mouse\_pressed()

```python
def mouse_pressed(): # Put code to run when the mouse is pressed here pixel_colour = Color(get(mouse_x, mouse_y)).hex # Here the RGB value is converted to Hex so it can be used in a string comparison later if pixel_colour == mercury['colour'].hex: print(mercury['name']) print(mercury['info'])
```

Quan l'usuari fa clic en un píxel, es recupera el valor de color hexadecimal del píxel i es compara amb els colors dels planetes. Si el color del píxel és el mateix que el color d'un planeta, es mostra informació sobre aquest planeta.

**Prova:** executeu el vostre codi i feu clic a Mercury per veure la seva informació impresa. Si es mou massa ràpid, canvieu el `frame_rate`valor de la `run()`funció per alentir tot el model.

![Un fons negre amb un cercle groc, envoltat per un anell blanc. Un cercle vermell orbita al voltant de l'anell. La informació sobre Mercuri apareix a la sortida de text.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_click.gif)

**Depuració:** si no passa res quan feu clic a Mercury, comproveu el vostre `if`extracte. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens `==`i no `=`.

**Depuració:** si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus ( `'name'`i `'info'`) a `mouse_pressed()`. Assegureu-vos que l'ortografia sigui la mateixa en `load_planets()`.

### Guarda el teu projecte
Dibuixa Mercuri
La make_planet()funció s'escriu en un fitxer separat que s'inclou com a part del projecte d'inici i s'importa main.pyper utilitzar-lo.

make_planet()utilitza el color, l'òrbita, la mida i la velocitat d'un planeta per dibuixar el planeta que orbita al voltant del sol.


Busca el # draw_planets functioncomentari. Creeu la funció a sota.

Feu variables per emmagatzemar els valors necessaris per dibuixar Mercuri. A continuació, crida a make_planet(), passant-li aquests valors.

Paràmetres en funcions
main.py — draw_planets()
# draw_planets function
def draw_planets():
    colour = mercury['colour']
    orbit = mercury['orbit']
    size = mercury['size']
    speed = mercury['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )
Consell: heu creat el vostre diccionari amb una línia per a cada key: valueparell. Podeu fer el mateix quan passeu valors a una funció per facilitar la lectura del vostre codi.


Afegiu una trucada a draw_planets()a la draw()funció.

main.py — dibuixa()
def draw():
    # Put code to run every frame here
    background(0)
    no_stroke()
    draw_sun()
    draw_orbits()
    draw_planets()

Prova: executeu el vostre codi i vegeu Mercuri en òrbita!

Un fons negre amb un cercle groc, envoltat per un anell blanc. Un cercle vermell orbita al voltant de l'anell.

Depuració: si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a make_planet(). Assegureu-vos que l'ortografia sigui la mateixa en load_planets(). També és important que les lletres siguin majúscules o minúscules.

Depuració: si Mercuri no apareix:

Comprova que estàs draw_planets()trucantdraw()
Assegureu-vos que aquesta trucada sigui desprésbackground(0)
Depuració: si Mercury és massa gran, massa lent o no és visible, comproveu que el vostre draw_planets()codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

Parla als usuaris sobre el planeta
Els usuaris faran clic a Mercury i el vostre programa imprimirà la informació en mercury['info'].

La mouse_pressed()funció es va incloure com a part del projecte inicial. Conté codi per obtenir el valor hexadecimal d'un color en què ha fet clic un usuari. Podeu utilitzar això per dir a quin planeta han fet clic.


Cerca mouse_pressed()i afegeix una ifdeclaració. Teniu printel nom i la informació de Mercuri quan l'usuari faci clic al planeta.

main.py — mouse_pressed()
def mouse_pressed():
    # Put code to run when the mouse is pressed here
    pixel_colour = Color(get(mouse_x, mouse_y)).hex  # Here the RGB value is converted to Hex so it can be used in a string comparison later

    if pixel_colour == mercury['colour'].hex:
        print(mercury['name'])
        print(mercury['info'])
Quan l'usuari fa clic en un píxel, es recupera el valor de color hexadecimal del píxel i es compara amb els colors dels planetes. Si el color del píxel és el mateix que el color d'un planeta, es mostra informació sobre aquest planeta.


Prova: executeu el vostre codi i feu clic a Mercury per veure la seva informació impresa. Si es mou massa ràpid, canvieu el frame_ratevalor de la run()funció per alentir tot el model.

Un fons negre amb un cercle groc, envoltat per un anell blanc. Un cercle vermell orbita al voltant de l'anell. La informació sobre Mercuri apareix a la sortida de text.

Depuració: si no passa res quan feu clic a Mercury, comproveu el vostre ifextracte. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens ==i no =.

Depuració: si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus ( 'name'i 'info') a mouse_pressed(). Assegureu-vos que l'ortografia sigui la mateixa en load_planets().

## Fer Venus

És hora que Venus s'uneixi a Mercuri en el teu model.

![Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc. La informació sobre Venus apareix a la sortida de text.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/venus_info.gif)

Els valors d'altres planetes es troben al `planets.csv`fitxer.

### Què hi ha a planets.csv?

### Carregueu les dades

Afegiu una `global`variable per a Venus a la vostra `load_planets()`funció:

main.py — load\_planets()

```python
# load_planets function def load_planets(): global mercury, venus
```

A sota del `mercury`diccionari, carregueu `planets.csv`a una `data`variable. A continuació, utilitzeu la `splitlines()`funció per dividir la cadena de text en `data`una llista. Cada línia de la cadena es convertirà en un element de la llista.

### Llegir un fitxer amb Python

main.py — load\_planets()

```python
mercury = { 'name': 'Mercury', 'colour': Color(165, 42, 42), 'size': 15, 'orbit': 150, 'speed': 1, 'info': 'The smallest and fastest planet.' } with open('planets.csv') as f: data = f.read() lines = data.splitlines()
```

Ara teniu les dades al vostre programa. A continuació, convertireu aquestes dades en diccionaris, com el que vau fer per a Mercury. `lines[2]`té les dades de Venus i `lines[3]`té les dades de la Terra.

Dividiu `lines[2]`entre comes i deseu-lo a `planet`. A continuació, imprimiu `planet`.

main.py — load\_planets()

```python
with open('planets.csv') as f: data = f.read() lines = data.splitlines() planet = lines[2].split(',') # Split Venus' data print(planet)
```

**Prova:** proveu d'executar el vostre codi i mireu la llista de dades que imprimeix. Observeu que els números estan dins de cometes `'`. Això demostra que Python les veu com a cadenes de text, en lloc de nombres amb els quals podria fer matemàtiques.

![La informació sobre Venus, impresa com a llista.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/venus_dict.png)

**Depuració:** si `planet`imprimeix una llista amb un sol element, comproveu que teniu `','`a `()`la `lines[2].split()`.

**Depuració:** si veieu un missatge sobre `split`"no definit", comproveu que l'heu inclòs `lines[2].`abans.

**Depuració:** si veieu un missatge com `'list' object has no attribute 'split'`, comproveu que heu inclòs `[2]`després de `lines`.

**Consell:** ara que l'heu utilitzat per fer proves, podeu fer comentaris `print(planet)`amb `#`.

Carregueu la llista de valors des `planet`d'un `venus`diccionari. Mentre feu el diccionari, canvieu els números de text a números. S'utilitza `int()`per a nombres enters i `float()`per a decimals.

main.py — load\_planets()

```python
with open('planets.csv') as f: data = f.read() lines = data.splitlines() planet = lines[2].split(',') # Split Venus' data #print(planet) venus = { 'name': planet[0], 'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])), # Make them numbers 'size': int(planet[4]), # int() for whole numbers 'orbit': int(planet[5]), 'speed': float(planet[6]), # float() for decimals 'info': planet[7] }
```

### Dibuixa l'òrbita

Aneu a la vostra `draw_orbits()`funció i afegiu l'òrbita de Venus.

main.py — draw\_orbits()

```python
# draw_orbits function def draw_orbits(): no_fill() stroke(255) # Make it white ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit']) ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])
```

**Prova:** executa el teu codi i veu com apareix l'òrbita de Venus.

![Un fons negre amb un cercle groc, envoltat de dos anells blancs. Un cercle vermell orbita al voltant del cercle groc de l'anell interior.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_venus_orbit.gif)

**Depuració:** si veieu un missatge sobre `venus`"no definit", marqueu `load_planets()`. Assegureu-vos que heu declarat `venus` com a `global`.

### Dibuixa el planeta

Aneu a la vostra `draw_planets()`funció. Afegeix una `make_planet()`trucada, passant-li els valors de Venus.

**Consell:** podeu copiar i enganxar el codi que heu utilitzat per fer Mercury per estalviar temps i escriure. Només has de canviar totes les mencions de `mercury`a `venus`a la còpia.

### Copiar i enganxar

main.py — draw\_planets()

```python
# draw_planets function def draw_planets(): colour = mercury['colour'] orbit = mercury['orbit'] size = mercury['size'] speed = mercury['speed'] make_planet( colour, orbit, size, speed ) colour = venus['colour'] orbit = venus['orbit'] size = venus['size'] speed = venus['speed'] make_planet( colour, orbit, size, speed )
```

**Prova:** executeu el vostre codi i comproveu que Venus orbita al voltant del Sol.

![Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/mercury_venus.gif)

**Depuració:** si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a `make_planet()`. Assegureu-vos que l'ortografia sigui la mateixa en `load_planets()`. També és important que les lletres siguin majúscules o minúscules.

**Depuració:** si algun planeta és massa gran, massa lent o no és visible, comproveu que el vostre `draw_planets()`codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

### Explica als usuaris sobre Venus

Igual que Mercuri, Venus hauria d'imprimir un fet interessant quan hi feu clic.

Afegiu declaracions després de la declaració que `mouse_pressed()`vau fer per a Mercuri. Feu que aquests comprovin el color de Venus. Aleshores, si hi ha coincidència, el fet correcte.`elif``if``print()`

main.py — mouse\_pressed()

```python
def mouse_pressed(): # Put code to run when the mouse is pressed here pixel_colour = Color(get(mouse_x, mouse_y)).hex # Here the RGB value is converted to Hex so it can be used in a string comparison later if pixel_colour == mercury['colour'].hex: print(mercury['name']) print(mercury['info']) elif pixel_colour == venus['colour'].hex: print(venus['name']) print(venus['info'])
```

**Prova:** executeu el vostre codi. Feu clic a Venus per veure la seva informació impresa.

![Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc. La informació sobre Venus apareix a la sortida de text.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/venus_info.gif)

**Depuració:** si no passa res quan feu clic a Venus, comproveu-ne la `elif`declaració. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens `==`i no `=`.




Fer Venus
És hora que Venus s'uneixi a Mercuri en el teu model.

Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc. La informació sobre Venus apareix a la sortida de text.

Els valors d'altres planetes es troben al planets.csvfitxer.

Què hi ha a planets.csv?
Carregueu les dades

Afegiu una globalvariable per a Venus a la vostra load_planets()funció:

main.py — load_planets()
# load_planets function
def load_planets():
    global mercury, venus

A sota del mercurydiccionari, carregueu planets.csva una datavariable. A continuació, utilitzeu la splitlines()funció per dividir la cadena de text en datauna llista. Cada línia de la cadena es convertirà en un element de la llista.

Llegir un fitxer amb Python
main.py — load_planets()
    mercury = {
        'name': 'Mercury',
        'colour': Color(165, 42, 42),
        'size': 15,
        'orbit': 150,
        'speed': 1,
        'info': 'The smallest and fastest planet.'
    }

    with open('planets.csv') as f:
        data = f.read()
        lines = data.splitlines()
Ara teniu les dades al vostre programa. A continuació, convertireu aquestes dades en diccionaris, com el que vau fer per a Mercury. lines[2]té les dades de Venus i lines[3]té les dades de la Terra.


Dividiu lines[2]entre comes i deseu-lo a planet. A continuació, imprimiu planet.

main.py — load_planets()
    with open('planets.csv') as f:
        data = f.read()
        lines = data.splitlines()

    planet = lines[2].split(',')  # Split Venus' data
    print(planet)

Prova: proveu d'executar el vostre codi i mireu la llista de dades que imprimeix. Observeu que els números estan dins de cometes '. Això demostra que Python les veu com a cadenes de text, en lloc de nombres amb els quals podria fer matemàtiques.

La informació sobre Venus, impresa com a llista.

Depuració: si planetimprimeix una llista amb un sol element, comproveu que teniu ','a ()la lines[2].split().

Depuració: si veieu un missatge sobre split"no definit", comproveu que l'heu inclòs lines[2].abans.

Depuració: si veieu un missatge com 'list' object has no attribute 'split', comproveu que heu inclòs [2]després de lines.

Consell: ara que l'heu utilitzat per fer proves, podeu fer comentaris print(planet)amb #.


Carregueu la llista de valors des planetd'un venusdiccionari. Mentre feu el diccionari, canvieu els números de text a números. S'utilitza int()per a nombres enters i float()per a decimals.

main.py — load_planets()
    with open('planets.csv') as f:
        data = f.read()
        lines = data.splitlines()

    planet = lines[2].split(',')  # Split Venus' data
    #print(planet)
    venus = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),  # Make them numbers
        'size': int(planet[4]),  # int() for whole numbers
        'orbit': int(planet[5]),
        'speed': float(planet[6]),  # float() for decimals
        'info': planet[7]
    }

Dibuixa l'òrbita
Aneu a la vostra draw_orbits()funció i afegiu l'òrbita de Venus.

main.py — draw_orbits()
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255) # Make it white

    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])

Prova: executa el teu codi i veu com apareix l'òrbita de Venus.

Un fons negre amb un cercle groc, envoltat de dos anells blancs. Un cercle vermell orbita al voltant del cercle groc de l'anell interior.

Depuració: si veieu un missatge sobre venus"no definit", marqueu load_planets(). Assegureu-vos que heu declarat venus com a global.

Dibuixa el planeta

Aneu a la vostra draw_planets()funció. Afegeix una make_planet()trucada, passant-li els valors de Venus.

Consell: podeu copiar i enganxar el codi que heu utilitzat per fer Mercury per estalviar temps i escriure. Només has de canviar totes les mencions de mercurya venusa la còpia.

Copiar i enganxar
main.py — draw_planets()
# draw_planets function
def draw_planets():
    colour = mercury['colour']
    orbit = mercury['orbit']
    size = mercury['size']
    speed = mercury['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

    colour = venus['colour']
    orbit = venus['orbit']
    size = venus['size']
    speed = venus['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

Prova: executeu el vostre codi i comproveu que Venus orbita al voltant del Sol.

Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc.

Depuració: si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a make_planet(). Assegureu-vos que l'ortografia sigui la mateixa en load_planets(). També és important que les lletres siguin majúscules o minúscules.

Depuració: si algun planeta és massa gran, massa lent o no és visible, comproveu que el vostre draw_planets()codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

Explica als usuaris sobre Venus
Igual que Mercuri, Venus hauria d'imprimir un fet interessant quan hi feu clic.


Afegiu declaracions després de la declaració que mouse_pressed()vau fer per a Mercuri. Feu que aquests comprovin el color de Venus. Aleshores, si hi ha coincidència, el fet correcte.elififprint()

main.py — mouse_pressed()
def mouse_pressed():
    # Put code to run when the mouse is pressed here
    pixel_colour = Color(get(mouse_x, mouse_y)).hex  # Here the RGB value is converted to Hex so it can be used in a string comparison later

    if pixel_colour == mercury['colour'].hex:
        print(mercury['name'])
        print(mercury['info'])
    elif pixel_colour == venus['colour'].hex:
        print(venus['name'])
        print(venus['info'])

Prova: executeu el vostre codi. Feu clic a Venus per veure la seva informació impresa.

Un fons negre amb un cercle groc, envoltat de dos anells blancs. Als anells, cercles vermells i rosats orbiten al voltant del cercle groc. La informació sobre Venus apareix a la sortida de text.

Depuració: si no passa res quan feu clic a Venus, comproveu-ne la elifdeclaració. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens ==i no =.







Fer la Terra
Ara acaba el model afegint el planeta on et trobes!

Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc. La informació sobre la Terra apareix a la sortida de text.

Carregueu les dades

Afegiu una globalvariable per a la Terra a la vostra load_planets()funció:

main.py — load_planets()
# load_planets function
def load_planets():
    global mercury, venus, earth
Ja teniu les dades al vostre programa: les dades de la Terra es van carregar linesquan vau carregar planets.csv.


A sota del venusdiccionari, dividiu-lo lines[3]i poseu-lo en un earthdiccionari.

Consell: podeu copiar i enganxar el codi que heu utilitzat per fer el venusdiccionari per estalviar-vos temps. A continuació, feu petits canvis: lines[2]a lines[3]i venusa earth.

main.py — load_planets()
    with open('planets.csv') as f:
        data = f.read()
        lines = data.splitlines()

    planet = lines[2].split(',')
    #print(planet)
    venus = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),
        'orbit': int(planet[5]),
        'speed': float(planet[6]),
        'info': planet[7]
    }

    planet = lines[3].split(',')
    earth = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),
        'orbit': int(planet[5]),
        'speed': float(planet[6]),
        'info': planet[7]
    }
Dibuixa l'òrbita

Aneu a la vostra draw_orbits()funció i afegiu l'òrbita de la Terra.

main.py — draw_orbits()
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white

    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])
    ellipse(width / 2, height / 2, earth['orbit'], earth['orbit'])

Prova: executa el teu codi i veu com apareix l'òrbita de la Terra.

Un fons negre amb un cercle groc, envoltat per tres anells blancs. En dos dels anells, cercles vermells i rosats orbiten al voltant del cercle groc.

Depuració: si veieu un missatge sobre earth"no definit", marqueu load_planets(). Assegureu-vos que heu declarat earth com a global.

Dibuixa la Terra

Aneu a la vostra draw_planets()funció. Afegeix una make_planet()trucada, passant-li els valors de la Terra. Igual que amb Venus, podeu copiar i enganxar el codi aquí per estalviar-vos una mica de feina.

main.py — draw_planets()
# draw_planets function
def draw_planets():
    colour = mercury['colour']
    orbit = mercury['orbit']
    size = mercury['size']
    speed = mercury['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

    colour = venus['colour']
    orbit = venus['orbit']
    size = venus['size']
    speed = venus['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

    colour = earth['colour']
    orbit = earth['orbit']
    size = earth['size']
    speed = earth['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

Prova: executeu el vostre codi i comproveu que la Terra orbita al voltant del Sol.

Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc.

Depuració: si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a make_planet(). Assegureu-vos que l'ortografia sigui la mateixa en load_planets(). També és important que les lletres siguin majúscules o minúscules.

Depuració: si algun planeta és massa gran, massa lent o no és visible, comproveu que el vostre draw_planets()codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

Parleu als usuaris sobre la Terra
Igual que Mercuri i Venus, la Terra hauria d'imprimir un fet interessant quan hi feu clic.


Afegiu mouse_pressed()una elifdeclaració per a la Terra com la que vau fer per a Venus. Feu que comproveu el color de la Terra. Aleshores, si hi ha coincidència, print()el fet correcte.

main.py — mouse_pressed()
def mouse_pressed():
    # Put code to run when the mouse is pressed here
    pixel_colour = Color(get(mouse_x, mouse_y)).hex  # Here the RGB value is converted to Hex so it can be used in a string comparison later

    if pixel_colour == mercury['colour'].hex:
        print(mercury['name'])
        print(mercury['info'])
    elif pixel_colour == venus['colour'].hex:
        print(venus['name'])
        print(venus['info'])
    elif pixel_colour == earth['colour'].hex:
        print(earth['name'])
        print(earth['info'])

Prova: executeu el vostre codi. Feu clic a la Terra per veure la seva informació impresa.

Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc. La informació sobre la Terra apareix a la sortida de text.

Depuració: si no passa res quan feu clic a la Terra, comproveu-ne la elifdeclaració. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens ==i no =.

## Fer la Terra

Ara acaba el model afegint el planeta on et trobes!

![Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc. La informació sobre la Terra apareix a la sortida de text.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/all_planets_info.gif)

### Carregueu les dades

Afegiu una `global`variable per a la Terra a la vostra `load_planets()`funció:

main.py — load\_planets()

```python
# load_planets function def load_planets(): global mercury, venus, earth
```

Ja teniu les dades al vostre programa: les dades de la Terra es van carregar `lines`quan vau carregar `planets.csv`.

A sota del `venus`diccionari, dividiu-lo `lines[3]`i poseu-lo en un `earth`diccionari.

**Consell:** podeu copiar i enganxar el codi que heu utilitzat per fer el `venus`diccionari per estalviar-vos temps. A continuació, feu petits canvis: `lines[2]`a `lines[3]`i `venus`a `earth`.

main.py — load\_planets()

```python
with open('planets.csv') as f: data = f.read() lines = data.splitlines() planet = lines[2].split(',') #print(planet) venus = { 'name': planet[0], 'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])), 'size': int(planet[4]), 'orbit': int(planet[5]), 'speed': float(planet[6]), 'info': planet[7] } planet = lines[3].split(',') earth = { 'name': planet[0], 'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])), 'size': int(planet[4]), 'orbit': int(planet[5]), 'speed': float(planet[6]), 'info': planet[7] }
```

### Dibuixa l'òrbita

Aneu a la vostra `draw_orbits()`funció i afegiu l'òrbita de la Terra.

main.py — draw\_orbits()

```python
# draw_orbits function def draw_orbits(): no_fill() stroke(255) # Make it white ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit']) ellipse(width / 2, height / 2, venus['orbit'], venus['orbit']) ellipse(width / 2, height / 2, earth['orbit'], earth['orbit'])
```

**Prova:** executa el teu codi i veu com apareix l'òrbita de la Terra.

![Un fons negre amb un cercle groc, envoltat per tres anells blancs. En dos dels anells, cercles vermells i rosats orbiten al voltant del cercle groc.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/all_orbit.gif)

**Depuració:** si veieu un missatge sobre `earth`"no definit", marqueu `load_planets()`. Assegureu-vos que heu declarat `earth` com a `global`.

### Dibuixa la Terra

Aneu a la vostra `draw_planets()`funció. Afegeix una `make_planet()`trucada, passant-li els valors de la Terra. Igual que amb Venus, podeu copiar i enganxar el codi aquí per estalviar-vos una mica de feina.

main.py — draw\_planets()

```python
# draw_planets function def draw_planets(): colour = mercury['colour'] orbit = mercury['orbit'] size = mercury['size'] speed = mercury['speed'] make_planet( colour, orbit, size, speed ) colour = venus['colour'] orbit = venus['orbit'] size = venus['size'] speed = venus['speed'] make_planet( colour, orbit, size, speed ) colour = earth['colour'] orbit = earth['orbit'] size = earth['size'] speed = earth['speed'] make_planet( colour, orbit, size, speed )
```

**Prova:** executeu el vostre codi i comproveu que la Terra orbita al voltant del Sol.

![Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/all_planets.gif)

**Depuració:** si rebeu un missatge sobre "KeyError", comproveu l'ortografia de les vostres claus a `make_planet()`. Assegureu-vos que l'ortografia sigui la mateixa en `load_planets()`. També és important que les lletres siguin majúscules o minúscules.

**Depuració:** si algun planeta és massa gran, massa lent o no és visible, comproveu que el vostre `draw_planets()`codi sigui el mateix que l'exemple. En particular, comproveu que les claus estiguin en l'ordre correcte.

### Parleu als usuaris sobre la Terra

Igual que Mercuri i Venus, la Terra hauria d'imprimir un fet interessant quan hi feu clic.

Afegiu `mouse_pressed()`una `elif`declaració per a la Terra com la que vau fer per a Venus. Feu que comproveu el color de la Terra. Aleshores, si hi ha coincidència, `print()`el fet correcte.

main.py — mouse\_pressed()

```python
def mouse_pressed(): # Put code to run when the mouse is pressed here pixel_colour = Color(get(mouse_x, mouse_y)).hex # Here the RGB value is converted to Hex so it can be used in a string comparison later if pixel_colour == mercury['colour'].hex: print(mercury['name']) print(mercury['info']) elif pixel_colour == venus['colour'].hex: print(venus['name']) print(venus['info']) elif pixel_colour == earth['colour'].hex: print(earth['name']) print(earth['info'])
```

**Prova:** executeu el vostre codi. Feu clic a la Terra per veure la seva informació impresa.

![Un fons negre amb un cercle groc, envoltat per tres anells blancs. Als anells, cercles vermells, rosats i blaus orbiten al voltant del cercle groc. La informació sobre la Terra apareix a la sortida de text.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/all_planets_info.gif)

**Depuració:** si no passa res quan feu clic a la Terra, comproveu-ne la `elif`declaració. Assegureu-vos que s'assembla exactament a l'exemple anterior. Comprova que tens `==`i no `=`.

### Guarda el teu projecte

[](https://projects.raspberrypi.org/en/projects/solar-system-simulator/3)[Test ràpid](https://projects.raspberrypi.org/en/projects/solar-system-simulator/5)

## Actualitza el teu projecte

En aquest pas, afegiu més planetes al vostre model o canvieu els que teniu.

![Un model del sistema solar amb els vuit planetes.](https://projects-static.raspberrypi.org/projects/solar-system-simulator/7daa045501b7dc7919107b0b723ec7dc7e5a4abe/en/images/full_solar.gif)

### Afegeix més planetes

El `planets.csv`fitxer també té informació per als altres cinc planetes. Afegiu-ne tants com vulgueu.

Per afegir un planeta al vostre model haureu de:

-   Afegeix el codi per carregar-lo`load_planets()`
-   Afegiu codi per dibuixar la seva òrbita`draw_orbits()`
-   Afegeix codi per dibuixar el planeta`draw_planets()`
-   Afegiu el codi per notar quan es fa clic al planeta i imprimiu-ne la informació`mouse_pressed()`

**Consell:** no oblideu que podeu copiar i enganxar codi!

Augmenta la `size()`teva `setup()`funció per fer que el model sigui prou gran per veure els teus nous planetes; `size(900, 900)`els encaixarà a tots.

### Crea un planeta!

Afegiu un planeta addicional al sistema solar. Creeu una `global`variable nova amb un diccionari. A continuació, afegiu el codi per dibuixar-lo i imprimir-ne la informació.
