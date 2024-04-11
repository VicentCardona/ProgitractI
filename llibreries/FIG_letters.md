# Letres de Frank, Ian i Glen

[FIGlet](https://es.wikipedia.org/wiki/FIGlet) , que porta el nom de [les letres de Frank, Ian i Glen](http://www.figlet.org/faq.html) , és un programa de principis dels anys 90 per fer lletres grans a partir del text normal, una forma d' [art ASCII](https://en.wikipedia.org/wiki/ASCII_art) :

```
 _ _ _          _   _     _  
| (_) | _____  | |_| |__ (_)___  
| | | |/ / _ \ | __| '_ \| / __|  
| | |   <  __/ | |_| | | | \__ \  
|_|_|_|\_\___|  \__|_| |_|_|___/  
```

Entre els Escriu de lletra admesos per FIGlet es troben els de [figlet.org/examples.html](http://www.figlet.org/examples.html) .

Des de llavors, FIGlet s'ha portat a Python com un mòdul anomenat [pyfiglet](https://pypi.org/project/pyfiglet/0.7/) .

En un fitxer anomenat `figlet.py`, implementeu un programa que:

-   S'espera zero o dos arguments de línia d'ordres
-   Zero si l'usuari vol enviar text amb una font aleatòria.
-   Dos si l'usuari vol generar text amb un Escriu de lletra específic, en aquest cas el primer dels dos hauria de ser `-f`o `--font`, i el segon dels dos hauria de ser el nom del Escriu de lletra.
-   Demana a l'usuari un `str`text.
-   Emet aquest text amb el Escriu de lletra desitjat.

Si l'usuari proporciona dos arguments de línia d'ordres i el primer no és `-f`o `--font`el segon no és el nom d'un Escriu de lletra, el programa hauria de sortir `sys.exit`amb un missatge d'error.

### Pistes

-   Podeu instal·lar `pyfiglet`amb:
```python
pip install pyfiglet
```
-   La documentació de pyfiglet no és molt clara, però podeu utilitzar el mòdul de la següent manera:
    
    ``` python
     from   pyfiglet   import   Figlet   
      
     figlet   =   Figlet  () 
    ```
    Pots obtindre una `llista`de les fonts disponibles amb codi com aquest:
    ``` python
    figlet.getFonts()
    ```
    Pots seleccionar la font que vols utilitzar amb codi com el següent, on `f`es el nom de la font com una `str`:
    ```python
    figlet.setFont(font=f)
    ```
    
    I podeu produir text amb aquesta font amb un codi com aquest, on `s`es troba aquest text com a `str`:
    
    ```
     print  (  figlet  .  renderText  (  s  )) 
-   Tingueu en compte que el `random`mòdul inclou unes quantes funcions, segons [docs.python.org/3/library/random.html](https://docs.python.org/3/library/random.html) .
  

## Demostració

<script async="" data-autoplay="1" data-cols="80" data-loop="1" data-rows="12" id="asciicast-LIo5QcHpUiXepVFiL4fTBwmuE" src="https://asc
iinema.org/a/LIo5QcHpUiXepVFiL4fTBwmuE.js"></script>


## Abans que comencis

Inicieu sessió [a cs50.dev](https://cs50.dev/) , feu clic a la finestra del vostre terminal i executeu `cd` sol. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
$
```
A continuació executeu
```
mkdir figlet
```
per crear una carpeta cridada `figlet`al vostre espai de codi.

Després executar
```
cd figlet
```
per canviar els directoris a aquesta carpeta. Ara hauríeu de veure el missatge del vostre terminal com a `figlet/ $`. Ara pots executar
```
code figlet.py
```

per crear un fitxer anomenat `figlet.py`on escriureu el vostre programa.

## Com provar

A continuació s'explica com provar el codi manualment:

-   Executeu el vostre programa amb `python figlet.py test`. El vostre programa hauria de sortir mitjançant `sys.exit`i imprimir un missatge d'error:
  ```
Ivalid usage
```
-   Executeu el vostre programa amb `python figlet.py -a slant`. El vostre programa hauria de sortir mitjançant `sys.exit`i imprimir un missatge d'error:
   ```
Ivalid usage
```
-   Executeu el vostre programa amb `python figlet.py -f invalid_font`. El vostre programa hauria de sortir mitjançant `sys.exit`i imprimir un missatge d'error:
```
Ivalid usage
```
-   Executeu el vostre programa amb `python figlet.py -f slant`. Escriu `CS50`. El vostre programa hauria d'imprimir el següent:
    
    ```
       ___________ __________   
      / ____/ ___// ____/ __ \  
     / /    \__ \/___ \/ / / /  
    / /___ ___/ /___/ / /_/ /   
    \____//____/_____/\____/    
    ```
    
-   Executeu el vostre programa amb `python figlet.py -f rectangles`. Escriu `Hello, world`. El vostre programa hauria d'imprimir el següent:
    
    ```
     _____     _ _                        _   _   
    |  |  |___| | |___      _ _ _ ___ ___| |_| |  
    |     | -_| | | . |_   | | | | . |  _| | . |  
    |__|__|___|_|_|___| |  |_____|___|_| |_|___|  
                      |_|                         
    ```
    
-   Executeu el vostre programa amb `python figlet.py -f alphabet`. Escriu `Moo`. El vostre programa hauria d'imprimir el següent:
    
    ```
    M   M           
    MM MM           
    M M M ooo ooo   
    M   M o o o o   
    M   M ooo ooo                       
    ```
    

Podeu executar el següent per comprovar el vostre codi mitjançant `check50`, un programa que CS50 utilitzarà per provar el vostre codi quan l'envieu. Però assegureu-vos de provar-ho vosaltres mateixos també!

```
check50 cs50/problems/2022/python/figlet
```

## Com entregar

Entrega, a la tasca de classroom:

- Arxiu
- Captura del `check50`
- Video "Demo" del programa

# Crèdits
#### Autor:  Vicent Cardona
#### Departament Tecnologia [Ies Quartó de Portmany](http://iesquartodeportmany.es/)
#### Abril 2024


Llicència Creative Commons [Reconeixement-NoComercial-CompartirIgual 4.0 Internacional](https://creativecommons.org/licenses/by-nc-sa/4.0/) (CC BY-NC-SA 4.0).

Material adaptat del curs  [Introducció a la informàtica CS50](https://cs50.harvard.edu/x/2024/) compartit amb la mateixa llicència.
