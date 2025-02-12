# Art encriptada


El primer que cal fer quan es crea art amb Python es utilitzar la `Llibreria Processing` és i afegir `def setup():`
per definir una funció `setup` que s'executa una vegada al començament del programa.

**Crea:** definiu la funció `setup()` al vostre codi per establir la mida de la finestra de sortida. La funció `size()` s'utilitza per indicar la mida del llenç. Els arguments indiquen l'amplada i l'alçada en píxels.

### Establiu la mida de la pantalla quan s'iniciï el programa

main.py - setup()

```python
def setup(): 
   size(400, 400) # 400 by 400 works well for an art canvas
```

**Tria:** Experimenteu amb els números de la vostra funció `setup()` i executeu el vostre codi per trobar una mida que us agradi.

La funció `draw()` executa contínuament les línies de codi contingudes dins del seu bloc fins que el programa s'atura. Es truca automàticament directament després de `setup()`.

**Crea:** defineix la funció `draw` al teu script.

**Tria:** penseu en els colors que utilitzareu per al vostre art i creeu algunes variables que mantinguin els valors de color al començament de `draw()`.

### Colors RGB

També podeu utilitzar alguna utilitat com el [dissenyador d'esquemes de colors Paletton](https://paletton.com/) per triar la vostra paleta de colors i copiar els valors RGB.


**Crea** una funció que **dibuixi** forma de fons amb la vostra paleta de colors. A continuació, afegiu una trucada a la vostra funció `draw()`.

### Establiu els colors de fons quan s'iniciï el programa

**Crea** una trucada a `run()`al final del vostre script (sense sagnat!) per executar el programa:

main.py
```python
run()
```
