# Art en codi

## Què farem?

Crear una obra d'art codificada a partir del nom de l'usuari. Cada lletra està codificada amb una forma que es mostra a l'atzar a la pantalla.

En aquest projecte:

- Utilitzarem un diccionari per codificar lletres amb diferents formes
- Utilitzarem funcions amb paràmetres per afegir personalització a les formes
- Crearem una peça única d'art digital amb lletres codificades

Prendreu algunes decisions de disseny sobre el tipus d'obra d'art que es produirà quan l'usuari introdueixi el seu nom.

El primer que cal fer quan es crea art amb Python es utilitzar la `Llibreria Processing` és i afegir `def setup():`
per definir una funció `setup` que s'executa una vegada al començament del programa.

## Comencem.

**Crea:** definiu la funció `setup()` al vostre codi per establir la mida de la finestra de sortida. La funció `size()` s'utilitza per indicar la mida del llenç. Els arguments indiquen l'amplada i l'alçada en píxels.

### Establiu la mida de la pantalla quan s'iniciï el programa

main.py - setup()

```python
def setup(): 
   size(400, 400) # 400 va 400 be per un quadre d'art
```

**Tria:** Experimenteu amb els números de la vostra funció `setup()` i executeu el vostre codi per trobar una mida que us agradi.

La funció `draw()` executa contínuament les línies de codi contingudes dins del seu bloc fins que el programa s'atura. Es truca automàticament directament després de `setup()`.

**Crea:** defineix la funció `draw` al teu script.

**Tria:** penseu en els colors que utilitzareu per al vostre art i creeu algunes variables que mantinguin els valors de color al començament de `draw()`.


###Colors RGB

Quan volem representar un color en un programa informàtic, ho podem fer definint les quantitats de vermell, blau i verd que es combinen per formar aquest color. Aquestes quantitats s'emmagatzemen com un nombre entre 0 i 255.

![Colors RGB](https://projects-static.raspberrypi.org/projects/generic-theory-simple-colours/e102ecbfc666027d84ac6517bb5819f012b8dd00/en/images/RGB.gif)

Aquí hi ha una taula que mostra alguns valors de color:

| Vermell | Verd | Blau | Color |
| --- | --- | --- | --- |
| 255 | 0 | 0 | Vermell |
| 0 | 255 | 0 | Verd |
| 0 | 0 | 255 | Blau |
| 255 | 255 | 0 | Groc |
| 255 | 0 | 255 | Magenta |
| 0 | 255 | 255 | Cian |

Podeu trobar un bon [selector de colors per jugar a w3schools](https://www.w3schools.com/colors/colors_rgb.asp) .

També podeu utilitzar alguna utilitat com el [dissenyador d'esquemes de colors Paletton](https://paletton.com/) per triar la vostra paleta de colors i copiar els valors RGB.

###Colors a p5

La funció `Color()` espera 3 nombres. un per a vermell, verd i blau.
   ``` python
   blue = Color(50, 70, 206) #Vermell = 50, Verd = 70, Blau = 206
```

**Crea** una funció que **dibuixi** la forma de fons amb la vostra paleta de colors. A continuació, afegiu una trucada a la vostra funció `draw()`.

### Establiu els colors de fons quan s'iniciï el programa

A sobre de la funció `draw()`, definiu una nova cridada a la funció `draw_background()` i creeu-hi una trucada a `draw()`, després d'una trucada a no_stroke().

main.py - draw_background()
```python
def draw_background(colour):
    # Color de fons
    fill(colour)
    rect(0, 0, 400, 400)
```
 
 
 
A continuació, creeu-hi una trucada a draw():

main.py - draw ()
```python
def draw():

    red = Color(255,0,0)
    green = Color(0,255,0)
    blue = Color(0,0,255)

    no_stroke()
    draw_background(red)
```

Si voleu que el vostre fons inclogui més colors, haureu d'afegir més paràmetres.

main.py - draw_background()
```python
def draw_background(green, blue):

    # Background colour
    fill(blue)
    rect(0, 0, 400, 200)
    fill(green)
    rect(0, 200, 400, 200)
```
 
 
A continuació, afegiu el nou color a la vostra cridada a draw_background() a draw():

main.py - draw ()
```python
def draw():

    vermell = Color(255, 0, 0)
    verd = Color(0, 255, 0)
    blau = Color(0, 0, 255)

    no_stroke()
    draw_background(verd, blau)
```




**Crea** una trucada a `run()`al final del vostre script (sense sagnat!) per executar el programa:

main.py
```python
run()
```

## Dibuixa les teves formes

Configureu les vostres funcions de forma que pugueu utilitzar-les a la vostra obra d'art codificada.

![Una captura de pantalla de la sortida del projecte d'exemple. Hi ha un fons blau fosc, un quadrat blau, un cercle blau i un triangle taronja.](https://projects-static.raspberrypi.org/projects/encoded-art/225055dfa932a80acc89e48629e0be746128cda4/en/images/shape-functions.PNG)

Decideix quantes **formes** úniques t'agradaria que tingués la teva obra d'art. Els projectes d'exemple tenen **tres** formes úniques. A continuació, es modifiquen mitjançant els paràmetres de la funció. Potser t'agradaria tenir-ne més de tres, la decisió és teva!

Aquí teniu algunes idees:

-   Tres funcions de forma que carreguen imatges de papallones, cargols o ocells
-   Tres funcions de forma que dibuixen quadrats, cercles i triangles
-   Cinc funcions de forma, cadascuna dibuixa un animal únic

**Definiu** cada funció de forma en preparació per afegir el codi que es necessitarà per dibuixar cada forma. Assegureu-vos de definir les vostres funcions de forma **per sobre de** la vostra `draw()`funció.


Definiu les vostres funcions

Pots definir les funcions de la següent manera:

main.py
```python
def forma_1():

def forma_2():

def forma_3():
```


Decidiu quins **paràmetres** necessitaran les vostres funcions. Aquí teniu algunes idees:

-   Un paràmetre `color` que us permetrà modificar el color de les formes que heu creat
-   Un paràmetre `tamany` que us permet ajustar la mida de la forma o la imatge.
-   Un paràmetre `contorn` que afegeix un color diferent a la vora d'un dibuix


**Afegeix** els **paràmetres** escocllits dintre dels parèntesis per a cada funció de **forma**

Afegeix paràmetres a la teva funció

Pots afegir paràmetres a les funcions de la següent manera:

main.py
```python
def forma_1(tamany, color):

def forma_2(tamany, contorn):

def forma_3(objecte, color):
```

**Afegiu** el codi per a cadascuna de les vostres funcions de forma de manera que el dibuix o la imatge aparegui quan es **cridi** la funció .

Tria: Com és la teva forma? La teva forma podria ser:

-   Una imatge proporcionada al projecte inicial
-   Un emoji 🎈 o text
-   Dibuixat amb una sèrie de formes geomètriques
-   


### Formes

### Dibuixa una el·lipse

Dibuixa un cercle o una el·lipse amb:`ellipse(x, y, width, height)`

L'el·lipse es dibuixarà utilitzant els valors de traç i farciment que s'han establert abans `ellipse`.

main.py

```python
ellipse(160, 220, 200, 100) # x, y, width, height
```

L'el·lipse estarà centrada a les coordenades (x, y) que donen els dos primers nombres.

El tercer nombre és l'amplada i el quart és l'alçada de l'el·lipse.

![L'àrea de sortida mostra una el·lipse centrada al voltant de x 160, y 220 amb una amplada de 200 i una alçada de 100](https://projects-static.raspberrypi.org/projects/processing-python-ellipse/073eb1f9f4adc35458f018fe7354aab590f1f4a1/en/images/example.png)

Feu que l'amplada i l'alçada siguin iguals per dibuixar un cercle.

### Dibuixa un rectangle

Dibuixa un quadrat o rectangle amb:`rect(x, y, width, height)`

El rectangle es dibuixarà utilitzant els valors de traç i farciment que s'han establert abans `rect`.

main.py

```python
rect(160, 220, 200, 100) # x, y, width, height
```

El rectangle es dibuixarà amb la seva cantonada superior esquerra a les coordenades (x, y) que donen els dos primers nombres.

**Consell:** si voleu que el centre del rectangle estigui a les coordenades (x, y), crideu `rect_mode(CENTER)`la `setup`funció.

El tercer nombre és l'amplada i el quart és l'alçada del rectangle.

![L'àrea de sortida mostra un rectangle centrat al voltant de x 160, y 220 amb una amplada de 200 i una alçada de 100](https://projects-static.raspberrypi.org/projects/processing-python-rect/6a55696f60da0d25e40d9df698a5e99da30b08ad/en/images/example.png)

Feu que l'amplada i l'alçada siguin iguals per dibuixar un quadrat.

### Dibuixa un triangle

Dibuixa un triangle amb:`triangle(x1, y1, x2, y2, x3, y3)`

El triangle es dibuixarà utilitzant els valors de traç i farciment que s'han establert abans `triangle`.

main.py

```python
triangle(210, 250, 330, 150, 220, 160) # (x1, y1), (x2, y2), (x3, y3)
```

El triangle es dibuixarà amb una cantonada a cadascuna de les tres coordenades donades per (x1, y1), (x2, y2), (x3, y3).

![L'àrea de sortida que mostra un triangle amb cantonades a les coordenades del codi.](https://projects-static.raspberrypi.org/projects/processing-python-triangle/22492ea94fce75b5f5877d48b36ce544f2bb25df/en/images/example.png)

### Dibuixa un quad

Dibuixa un quad usant:`quad(x1, y1, x2, y2, x3, y3, x4, y4)`

El quad es dibuixarà utilitzant els valors de traç i farciment que s'han establert abans `quad`.

main.py

```python
fill(255,125,90)
quad(210, 250, 100, 150, 220, 160, 340, 100) # (x1, y1), (x2, y2), (x3, y3), (x4, y4)
```

El quad es dibuixarà amb una cantonada a cadascuna de les quatre coordenades donades per (x1, y1), (x2, y2), (x3, y3), (x4, y4).

![L'àrea de sortida que mostra un quad amb cantonades a les coordenades del codi.](https://projects-static.raspberrypi.org/projects/processing-python-quad/2061599db57ea4ca7092ebd883a6cbbb66bcdd53/en/images/example.png)

### Traducció de visuals

`translate()`mou la pantalla a una posició diferent en funció de les coordenades. Les formes de la pantalla es mouran amb ella, però el seu aspecte no canviarà. Una traducció pot moure la pantalla horitzontalment, verticalment o diagonalment.

Aquest exemple mou la pantalla `50`cap a la dreta i cap amunt després de dibuixar `50`cadascuna .`rect`

```python
def draw():
   rect(150, 150, 100, 100)
   translate(50,-50)
   rect(150, 150, 100, 100)
   translate(50,-50)
   rect(150, 150, 100, 100)
```

![Imatge d'un quadrat original i dos quadrats traduïts. Cada traducció va moure el quadrat cap a la dreta `50` i cap avall `50`](https://projects-static.raspberrypi.org/projects/processing-translation/4aede749c6d63322ee40044b3918d93fb9c8414d/en/images/translate_square.png)

Aquest exemple mou la pantalla `50`cap a l'esquerra i cap avall després de dibuixar `50`cadascuna .`ellipse`

```python
def draw():
   ellipse(200, 200, 100, 100)
   translate(-50,50)
   ellipse(200, 200, 100, 100)
   translate(-50,50)
   ellipse(200, 200, 100, 100)
```

![Imatge d'un cercle original i dos cercles traduïts. Cada traducció va moure el quadrat cap a la dreta `50` i cap avall `50`](https://projects-static.raspberrypi.org/projects/processing-translation/4aede749c6d63322ee40044b3918d93fb9c8414d/en/images/translate_circle.png)

En aquest exemple, `translate()`s'utilitza diverses vegades per dibuixar ulls complexos sense duplicar tot el codi per a un ull esquerre i un ull dret:

-   Primer, `translate(width/2, height/2)`s'utilitza per començar des del centre de la pantalla on `ellipse`es dibuixa un per al cap
-   A continuació, `translate(-100, 0)`es mou `100`cap a l'esquerra per posicionar l'esquerra`eye()`
-   A continuació, `translate(200, 0)`es mou `200`cap a la dreta per posicionar la dreta`eye()`
-   Finalment, `translate(-100, 0)`es mou cap `100`a l'esquerra, de nou al mig

![Imatge d'un cap circular amb un ull esquerre i un ull dret](https://projects-static.raspberrypi.org/projects/processing-translation/4aede749c6d63322ee40044b3918d93fb9c8414d/en/images/translate_eyes.png)

```python
def draw():
   translate(width/2, height/2) # Move screen to the middle stroke(0, 0, 0)
   ellipse(0, 0, 300, 300)# Circle shaped head
   translate(-100, 0 # Move screen 100 left for left eye
   eye()      #draw an eye
   translate(200, 0) # Move screen 200 right for right eye
   eye() #draw an eye
   translate(-100, 0) # Move screen 100 left (back to the middle)
 def eye():
 # Eye colours
   BLUE = color(1, 32, 100)
   BLACK = color(0, 0, 0)
   WHITE = color(255, 255, 255)
# Create an eye
   stroke(BLACK)
   fill(WHITE)
   ellipse(0, 0, 150, 150)
# eye outside
   no_stroke()
   fill(BLUE)
# iris
   ellipse(0, 0, 80, 80)
   fill(BLACK) # pupil
   ellipse(0, 0, 35, 35)
   fill(WHITE, 70)
   ellipse(-25, -20, 30, 30) # catchlight
   ellipse(25, 25, 10, 10) # catchlight
```

### Rotació

`rotate()`mou la pantalla al voltant d'un conjunt de coordenades. En processament, les rotacions es produeixen en **radians** , però podeu escriure el nombre de **graus** i utilitzar la `radians()`funció per convertir-lo en radians, `rotate(radians(90))`seria igual a `90`graus de rotació.

Els nombres positius giren els objectes en el sentit de les agulles del rellotge i els nombres negatius giren en el sentit contrari.

### Girant la pantalla

En aquest exemple, la imatge del planeta es col·loca amb el centre del planeta al centre de la pantalla. La pantalla està configurada per girar al voltant del centre movent-se un grau cada vegada que es torna a dibuixar.

![L'àrea de sortida amb un planeta que gira al voltant del centre](https://projects-static.raspberrypi.org/projects/processing-rotation/98213c2a344f204fa87c3cce2161e6f5366a8c64/en/images/rotate_planet.gif)

```python
def draw():
   translate(200,200) # The middle of the screen
   for i in range(frame_count):
      image(planet, -150, -150, 300, 300) rotate(radians(1))
```

### Parts giratòries del dibuix
### Girant la pantalla

En aquest exemple, la imatge del planeta es col·loca amb el centre del planeta al centre de la pantalla. La pantalla està configurada per girar al voltant del centre movent-se un grau cada vegada que es torna a dibuixar.

![L'àrea de sortida amb un planeta que gira al voltant del centre](https://projects-static.raspberrypi.org/projects/processing-rotation/98213c2a344f204fa87c3cce2161e6f5366a8c64/en/images/rotate_planet.gif)

```python
def draw(): translate(200,200) # The middle of the screen for i in range(frame_count): image(planet, -150, -150, 300, 300) rotate(radians(1))
```

### Parts giratòries del dibuix

En aquest exemple, la pantalla es gira en `45`graus quan es dibuixen els ulls per donar-los la impressió que es mouen.

Tanmateix, per alinear els ulls horitzontalment a través de la pantalla volem restaurar la configuració original abans de dibuixar el següent ull. La `pushMatrix()`funció desa la configuració tal com eren abans de dibuixar el primer ull i després la `popMatrix()`funció restaura aquestes configuracions abans de dibuixar el segon ull.

Totes les translacions i rotacions es reinicien cada vegada `draw()`que es torna a començar.

![L'àrea de sortida amb una imatge en moviment que mostra un ull giratori fet de cercles](https://projects-static.raspberrypi.org/projects/processing-rotation/98213c2a344f204fa87c3cce2161e6f5366a8c64/en/images/rotate_eyes.gif)

```python
def draw(): global BLUE, BLACK, WHITE BLUE = Color(1, 32, 100) BLACK = Color(0, 0, 0) WHITE = Color(255, 255, 255) background(WHITE) translate(width/2, height/2) # Move screen to the middle stroke(BLACK) ellipse(0, 0, 300, 300) # Head push_matrix() # Saves current screen settings translate(-100, 0) # Move screen to the left for left eye for i in range(frame_count): eye() rotate(radians(45)) pop_matrix() # Restores previous screen settings (removes the eye translation and rotation) translate(100, 0) # Move screen to the right for right eye for i in range(frame_count): eye() rotate(radians(45)) def eye(): # Create an eye fill(WHITE) ellipse(0, 0, 150, 150) # Outer eye no_stroke() fill(BLUE) ellipse(0, 0, 80, 80) # Iris fill(BLACK) ellipse(0, 0, 35, 35) # Pupil fill(WHITE, 70) ellipse(-25, -20, 30, 30) # Catchlight 1 with opacity ellipse(25, 25, 10, 10) # Catchlight 2 with opacity
```

### Colors i efectes

### Colors RGB

Quan volem representar un color en un programa informàtic, ho podem fer definint les quantitats de vermell, blau i verd que es combinen per formar aquest color. Aquestes quantitats s'emmagatzemen com un nombre entre 0 i 255.

![Colors RGB](https://projects-static.raspberrypi.org/projects/generic-theory-simple-colours/e102ecbfc666027d84ac6517bb5819f012b8dd00/en/images/RGB.gif)

Aquí hi ha una taula que mostra alguns valors de color:

| Vermell | Verd | Blau | Color |
| --- | --- | --- | --- |
| 255 | 0 | 0 | Vermell |
| 0 | 255 | 0 | Verd |
| 0 | 0 | 255 | Blau |
| 255 | 255 | 0 | Groc |
| 255 | 0 | 255 | Magenta |
| 0 | 255 | 255 | Cian |

Podeu trobar un bon [selector de colors per jugar a w3schools](https://www.w3schools.com/colors/colors_rgb.asp) .

### Opacitat

Podeu fer colors parcialment transparents afegint un quart número a un color RGB per donar l'"opacitat".

Aquest codi dibuixa els aspectes destacats superposats a l'exemple de fruita Kawaii:

main.py - dibuix ()

```python
# Highlights fill(255, 255, 255, 70) # 70 is transparency/opacity here ellipse(170, 150, 35, 35) ellipse(150, 160, 25, 25)
```

![imatge de fruita kawaii amb reflexos a diferents opacitats: 30, 70, 150, 255. 30 és menys opac i 255 és totalment opac](https://projects-static.raspberrypi.org/projects/processing-opacity/336e2ca8e30ddd7e4b0a825fd2a5148b65f80d6b/en/images/opacity.png)

### Color i pes de les vores

`stroke()`estableix el color a utilitzar per a les vores al voltant de les formes. Igual que `fill()`la `stroke()`funció s'aplica a tot el dibuixat després de trucar-lo, haureu d'afegir `stroke()`codi cada vegada que vulgueu canviar el color del traç.

Per eliminar completament les vores, afegiu `no_stroke()`abans de dibuixar les vostres formes.

El gruix de la vora es pot controlar mitjançant`stroke_weight()`

Aquest exemple té `no_stroke()`per al cel, l'herba i el suport marró, després canvia a `stroke(WHITE)` `stroke_weight(3)`per dibuixar els cercles objectiu.

main.py - dibuix ()

```python
no_stroke() # removes borders fill(BLUE) # sky rect(0, 0, 400, 250) fill(GREEN) # grass rect(0, 250, 400, 150) fill(BROWN) triangle(150, 350, 200, 150, 250, 350) #stand stroke(WHITE) # A white outline stroke_weight(3) # A thick outline fill(GREY) ellipse(200, 200, 170, 170) # Outer circle fill(RED) ellipse(200, 200, 110, 110) # Inner circle fill(YELLOW) ellipse(200, 200, 30, 30) # Bullseye
```

![Una escena de tir amb arc amb vores gruixudes i blanques als cercles i sense vores als rectangles o al triangle.](https://projects-static.raspberrypi.org/projects/processing-stroke/c1adf789d614e2b3286a35e0d06d6638baefa20c/en/images/outline-circles.png)

### Afegeix un to a les imatges

Si afegiu imatges al vostre projecte, podeu utilitzar `tint()`per canviar el color de la imatge.

Passar un color a `tint()`us permet canviar els colors de qualsevol imatge que dibuixeu després d'ell. Les imatges es veuran com si tinguessin una llum del color que trieu brillant sobre elles.

La `no_tint()`funció que s'ha de desactivar `tint()`quan acabis amb ella.

Aquest exemple afegeix un verd `tint()`a les dues imatges.

```python
tint(0, 255, 0) # Green tint image(rocket, 50, 50, 100, 100) image(planet, 50, 50, 300, 300)
```

![L'àrea de sortida mostra un coet i un planeta amb tots dos tintats](https://projects-static.raspberrypi.org/projects/processing-tint/b60893ec421d84c9f41aed5984524b9979bf8b1e/en/images/all_tint.png)

Aquest exemple afegeix un verd `tint()`a la primera imatge i després l'elimina `no_tint()`abans de dibuixar la segona imatge.

```python
tint(0, 255, 0) # Green tint image(rocket, 50, 50, 100, 100) no_tint() # Remove tint image(planet, 50, 50, 300, 300)
```

![L'àrea de sortida mostra un coet tenyit i un planeta sense tint](https://projects-static.raspberrypi.org/projects/processing-tint/b60893ec421d84c9f41aed5984524b9979bf8b1e/en/images/some_tint.png)

### Exemples

Aquí teniu una mostra de codi per dibuixar un quadrat al vostre projecte d'art codificat:

main.py - forma\_2()

```python
def shape_2(colour, size): fill(colour) rect(200, 200, size, size)
```

**Observeu** que els paràmetres que es defineixen a la funció anterior s'utilitzen per dibuixar la forma.

### Carregueu una imatge

### Utilitzeu caràcters emoji

Podeu utilitzar caràcters emoji a la funció p5 text() per utilitzar un emoji per representar el vostre jugador.

Aquí teniu un exemple:

main.py

```python
def setup(): size(400, 400) text_align(CENTER, TOP) #Position around the centre def draw_emoji(emoji, size): #snake text_size(size) #Controls the size of the emoji text(emoji, 200, 200)
```

Per **comprovar** que les vostres funcions de forma funcionen correctament, haureu de **cridar-** les des de la `draw()`funció. Recordeu que podeu utilitzar `#`per comentar línies de codi de manera que només vegeu una forma alhora.

Assegureu-vos d'afegir els arguments dels paràmetres escollits!

L'exemple següent pren dos o tres arguments.

main.py

```python
shape_1(100, colour_1) shape_2(100, colour_2) draw_emoji('🐍', 100)
```

**Tingueu en compte** que els noms de variables per a l'escollit `colour`s'han col·locat al primer paràmetre i s'han afegit alguns valors per a l'escollit `size`en el segon paràmetre.

La creació de prototips consisteix a fer un esborrany del que creus que pot aconseguir el teu projecte final. L'objectiu de la creació de prototips és fer una versió simplificada del producte final ràpidament, per permetre provar si és una solució viable al problema.

**Proveu** el vostre codi per veure si mostra les imatges escollides a la pantalla. En aquest punt, podrien aparèixer tots els uns sobre els altres. Podeu **trucar** a cada funció per separat per veure-les amb més claredat.

![Una captura de pantalla de la sortida del projecte d'exemple. Hi ha un fons blau fosc, un quadrat blau, un cercle blau i un triangle taronja.](https://projects-static.raspberrypi.org/projects/encoded-art/225055dfa932a80acc89e48629e0be746128cda4/en/images/shape-functions.PNG)

**Depuració:**

### Veu un error sobre els arguments

### Només apareix una forma

### Els dibuixos no tenen la forma/mida adequada

### Guarda el teu projecte

[](https://projects.raspberrypi.org/en/projects/encoded-art/1)[Col·loca les teves formes](https://projects.raspberrypi.org/en/projects/encoded-art/3)
In this example, the screen is rotated by `45` degrees when the eyes are being drawn to give them the impression they are moving around.

However, to align the eyes horizontally across the screen we want to restore the original settings before drawing the next eye. The `pushMatrix()` function saves the settings as they were before the first eye is drawn then the `popMatrix()` function restores those settings before the second eye is drawn.

All translations and rotations are reset every time `draw()` begins again.

![L'àrea de sortida amb una imatge en moviment que mostra un ull giratori fet de cercles](https://projects-static.raspberrypi.org/projects/processing-rotation/98213c2a344f204fa87c3cce2161e6f5366a8c64/en/images/rotate_eyes.gif)

```python
def draw(): global BLUE, BLACK, WHITE BLUE = Color(1, 32, 100) BLACK = Color(0, 0, 0) WHITE = Color(255, 255, 255) background(WHITE) translate(width/2, height/2) # Move screen to the middle stroke(BLACK) ellipse(0, 0, 300, 300) # Head push_matrix() # Saves current screen settings translate(-100, 0) # Move screen to the left for left eye for i in range(frame_count): eye() rotate(radians(45)) pop_matrix() # Restores previous screen settings (removes the eye translation and rotation) translate(100, 0) # Move screen to the right for right eye for i in range(frame_count): eye() rotate(radians(45)) def eye(): # Create an eye fill(WHITE) ellipse(0, 0, 150, 150) # Outer eye no_stroke() fill(BLUE) ellipse(0, 0, 80, 80) # Iris fill(BLACK) ellipse(0, 0, 35, 35) # Pupil fill(WHITE, 70) ellipse(-25, -20, 30, 30) # Catchlight 1 with opacity ellipse(25, 25, 10, 10) # Catchlight 2 with opacity
```

### Colours and effects

### RGB colours

When we want to represent a colour in a computer program, we can do this by defining the amounts of red, blue, and green that are combined to make up that colour. These amounts are stored as a number between 0 and 255.

![Colors RGB](https://projects-static.raspberrypi.org/projects/generic-theory-simple-colours/e102ecbfc666027d84ac6517bb5819f012b8dd00/en/images/RGB.gif)

Here’s a table showing some colour values:

| Red | Green | Blue | Colour |
| --- | --- | --- | --- |
| 255 | 0 | 0 | Red |
| 0 | 255 | 0 | Green |
| 0 | 0 | 255 | Blue |
| 255 | 255 | 0 | Yellow |
| 255 | 0 | 255 | Magenta |
| 0 | 255 | 255 | Cyan |

You can find a nice [colour picker to play with at w3schools](https://www.w3schools.com/colors/colors_rgb.asp).

### Opacity

You can make partly transparent colours by adding a fourth number to an RGB colour to give the ‘opacity’.

This code draws the overlapping highlights in the Kawaii fruit example:

main.py - draw()

```python
# Highlights fill(255, 255, 255, 70) # 70 is transparency/opacity here ellipse(170, 150, 35, 35) ellipse(150, 160, 25, 25)
```

![imatge de fruita kawaii amb reflexos a diferents opacitats: 30, 70, 150, 255. 30 és menys opac i 255 és totalment opac](https://projects-static.raspberrypi.org/projects/processing-opacity/336e2ca8e30ddd7e4b0a825fd2a5148b65f80d6b/en/images/opacity.png)

### Colour and weight of borders

`stroke()` sets the colour to use for the borders around the shapes. Just like `fill()` the `stroke()` function applies to everything drawn after you call it so you will need to add `stroke()` code every time you want to change the stroke colour.

To remove the borders completely, add `no_stroke()` before drawing your shape(s).

The thickness of the border can be controlled using `stroke_weight()`

This example has `no_stroke()` for the sky, grass and brown stand, then changes to `stroke(WHITE)` `stroke_weight(3)` to draw the target circles.

main.py - draw()

```python
no_stroke() # removes borders fill(BLUE) # sky rect(0, 0, 400, 250) fill(GREEN) # grass rect(0, 250, 400, 150) fill(BROWN) triangle(150, 350, 200, 150, 250, 350) #stand stroke(WHITE) # A white outline stroke_weight(3) # A thick outline fill(GREY) ellipse(200, 200, 170, 170) # Outer circle fill(RED) ellipse(200, 200, 110, 110) # Inner circle fill(YELLOW) ellipse(200, 200, 30, 30) # Bullseye
```

![Una escena de tir amb arc amb vores gruixudes i blanques als cercles i sense vores als rectangles o al triangle.](https://projects-static.raspberrypi.org/projects/processing-stroke/c1adf789d614e2b3286a35e0d06d6638baefa20c/en/images/outline-circles.png)

### Add tint to images

If you are adding images to your project you can use `tint()` to change the colour of the image.

Passing a colour to `tint()` lets you change the colours of any image you draw after it. The images will look like they have a light of the colour you chose shining on them.

The `no_tint()` function to turn `tint()` off when you’re finished with it.

This example adds a green `tint()` to both images.

```python
tint(0, 255, 0) # Green tint image(rocket, 50, 50, 100, 100) image(planet, 50, 50, 300, 300)
```

![The output area showing a rocket and planet with both tinted](https://projects-static.raspberrypi.org/projects/processing-tint/b60893ec421d84c9f41aed5984524b9979bf8b1e/en/images/all_tint.png)

This example adds a green `tint()` to the first image then removes it using `no_tint()` before the second image is drawn.

```python
tint(0, 255, 0) # Green tint image(rocket, 50, 50, 100, 100) no_tint() # Remove tint image(planet, 50, 50, 300, 300)
```

![The output area showing a tinted rocket and a planet without tint](https://projects-static.raspberrypi.org/projects/processing-tint/b60893ec421d84c9f41aed5984524b9979bf8b1e/en/images/some_tint.png)

### Examples

Here is some sample code for drawing a square in your encoded art project:

main.py - shape\_2()

```python
def shape_2(colour, size): fill(colour) rect(200, 200, size, size)
```

**Notice** that the parameters that are defined in the function above are then used to draw the shape.

### Load an image

### Use emoji characters

You can use emoji characters in the p5 text() function to use an emoji to represent your player.

Here’s an example:

main.py

```python
def setup(): size(400, 400) text_align(CENTER, TOP) #Position around the centre def draw_emoji(emoji, size): #snake text_size(size) #Controls the size of the emoji text(emoji, 200, 200)
```

Per **comprovar** que les vostres funcions de forma funcionen correctament, haureu de **cridar-** les des de la `draw()`funció. Recordeu que podeu utilitzar `#`per comentar línies de codi de manera que només vegeu una forma alhora.

Assegureu-vos d'afegir els arguments dels paràmetres escollits!

L'exemple següent pren dos o tres arguments.

main.py

```python
shape_1(100, colour_1) shape_2(100, colour_2) draw_emoji('🐍', 100)
```

**Tingueu en compte** que els noms de variables per a l'escollit `colour`s'han col·locat al primer paràmetre i s'han afegit alguns valors per a l'escollit `size`en el segon paràmetre.

La creació de prototips consisteix a fer un esborrany del que creus que pot aconseguir el teu projecte final. L'objectiu de la creació de prototips és fer una versió simplificada del producte final ràpidament, per permetre provar si és una solució viable al problema.

**Proveu** el vostre codi per veure si mostra les imatges escollides a la pantalla. En aquest punt, podrien aparèixer tots els uns sobre els altres. Podeu **trucar** a cada funció per separat per veure-les amb més claredat.

![A screenshot of the output of the example project. There is a dark blue background, a blue square, a blue circle, and an orange triangle.](https://projects-static.raspberrypi.org/projects/encoded-art/225055dfa932a80acc89e48629e0be746128cda4/en/images/shape-functions.PNG)
### Formes

### Dibuixa una el·lipse

### Dibuixa un rectangle

### Dibuixa un triangle

### Dibuixa un quad

### Traducció de visuals

### Rotació

### Colors i efectes

### Colors RGB

### Opacitat

### Color i pes de les vores

### Afegeix un to a les imatges

### Exemples

Aquí teniu una mostra de codi per dibuixar un quadrat al vostre projecte d'art codificat:

main.py - forma\_2()

```python
def shape_2(colour, size): fill(colour) rect(200, 200, size, size)
```

**Observeu** que els paràmetres que es defineixen a la funció anterior s'utilitzen per dibuixar la forma.
