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

També podeu utilitzar alguna utilitat com el [dissenyador d'esquemes de colors Paletton](https://paletton.com/) per triar la vostra paleta de colors i copiar els valors RGB.


**Crea** una funció que **dibuixi** forma de fons amb la vostra paleta de colors. A continuació, afegiu una trucada a la vostra funció `draw()`.

### Establiu els colors de fons quan s'iniciï el programa

**Crea** una trucada a `run()`al final del vostre script (sense sagnat!) per executar el programa:

main.py
```python
run()
```
