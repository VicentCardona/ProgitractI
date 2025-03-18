
# Adivina el nombre

Estic pensant en un nombre entre 1 i 100...

## Quin es?
Es 50! Pero que fariem si fos més aleatori? Implementa un programa que:

- Demana a l'usuari un nivell, `n`. Si l'usuari no introdueix un nombre enter positiu, el programa hauria de tornar a demanar.
- Genera aleatòriament un nombre enter entre 1 i `n\`, inclosos, utilitzant el mòdul `random`.
- Demana a l'usuari que endevini aquest nombre enter. Si la suposició no és un nombre enter positiu, el programa hauria de tornar a demanar a l'usuari.
- Si la conjectura és més petita que aquest nombre sencer, el programa hauria de sortir "Massa petit!" i tornar a demanar a l'usuari.
- Si la conjectura és més gran que aquest nombre sencer, el programa hauria de sortir "Massa gran!" i tornar a demanar a l'usuari.
Si la conjectura és la mateixa que l'enter, el programa hauria de sortir Just be! i sortir.

## Demo

<iframe width="692" height="284" src="https://www.youtube.com/embed/PmSNNcuiy7w" title="Guessing Game" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Pistes

1. Importa el modul `random` o, si ho prefereixes:
    ```python
    from random import randint
    ```
    Tingueu en compte que el modul `random` inclou múltiples funcions, segons 
[documentació de python](https://docs.python.org/es/3/library/random.html)

2. Demana el nivell, `n` assegurant-se que és un nombre enter positiu, utilitza un bucle infinit i recull un `ValueError` per als valors no numèrics.
3. Genera un nombre aleatori entre 1 i n
4. Demana a l'usuari que endevnini el nombre.




## Com provar

- Escriviu `gat` en el missatge que demana l'entrada d'usuari i premeu Enter. El vostre programa us hauria de tornar a demanar.

- Escriviu `-1` en el missatge que demana l'entrada d'usuari i premeu Enter. El vostre programa us hauria de tornar a demanar.

- Escriviu `10` en el missatge que demana l'entrada d'usuari i premeu Enter. Ara el vostre programa hauria d'estar preparat per acceptar conjectures.
Guess:   
Executeu el vostre programa amb python game.py. Escriviu 10a una indicació que digui Level:i premeu Enter. A continuació, escriviu cat. El vostre programa 
- Escriviu `1` en el missatge que demana l'entrada d'usuari i premeu Enter. A continuació, escriviu `1`. El vostre programa hauria de sortir:
```
just be!
```
- Escriviu `10` en el missatge que demana l'entrada d'usuari i premeu Enter. A continuació, escriviu `100`. El vostre programa hauria de sortir:

```
massa gran!
Sembla que estas endevinant fora de l'interval especificat
```

- Escriviu `1000` en el missatge que demana l'entrada d'usuari i premeu Enter. A continuació, escriviu `1`. El vostre programa molt probablement de sortir:


```
massa petit!
```


Entrega a la tasca de a classroom el programa i un video de "demo" de les proves.
