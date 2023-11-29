## Calculadora de propina

> “—De gente bien nacida es agradecer los beneficios que reciben, y uno de los pecados que más a Dios ofende es la ingratitud”
> 
> \- Don Quijote de La Mancha, 1605

Als Eivissa, s'acostuma a deixar una propina al servidor després de sopar en un restaurant, normalment una quantitat igual al 10% o més del cost del menjar. No et preocupis, a continuació he escrit una calculadora de propines per a tu!

```
def main():
    euros = euros_a_float(input("Quant ha costat el menjar? "))
    percentatge = percentatge_a_float(input("Quin percentatge t'agradaria deixar? "))
    tip = euros * percentatge
    print(f"Deixa {tip:.2f}€")


def euros_a_float(€):
    # TODO


def percentatge_a_float(percent):
    # TODO


main()
```

Bé, hem escrit _la majoria_ d'una calculadora de propina per a tu. Malauradament, no hem tingut temps d'implementar dues funcions:

-   `euros_a_float`, que hauria d'acceptar un `str` com a entrada (formatat com a `##.##€`, on cada `#` és un dígit decimal) , traieu l'`€` final i retorneu l'import com a `float`. Per exemple, donat `50.00€` com a entrada, hauria de retornar `50.0`.
-   `percentatge_a_float`, que hauria d'acceptar un `str` com a entrada (formatat com a `##%`, on cada `#` és un dígit decimal) , elimineu el final `%` i torneu el percentatge com a `float`. Per exemple, donat `15%` com a entrada, hauria de retornar `0.15`.

Suposem que l'usuari introduirà valors en els formats esperats.

Pistes

-   Recordeu que `input` retorna un `str`, segons [documentació d'input](https://docs.python.org/es/3/library/functions.html#input).
-   Recordeu que `float` pot convertir un `str` en un `float`, per [documentació de float](https://docs.python.org/es/3/library/functions.html#float).
-   Recordeu que un `str` inclou molts mètodes, segons [documentació de mètodes en cadenes](https://docs.python.org/es/3/library/stdtypes.html#string-methods).

## Abans que comencis

Inicieu la sessió a [cs50.dev](https://cs50.dev/), feu clic a la finestra del vostre terminal i executeu `cd` sol. Hauríeu de trobar que la sol·licitud de la vostra finestra de terminal s'assembla a la següent:
```
cd
```

A continuació, executeu
```
mkdir
```

per crear una carpeta anomenada `tip` al vostre espai de codi.

Després executar
```
cd tip
```

per canviar els directoris a aquesta carpeta. Ara hauríeu de veure el missatge del vostre terminal com `tip/ $`. Ara podeu executar
```
code tip.py
```

per crear un fitxer anomenat `tip.py`. Copieu i enganxeu el codi anterior en un fitxer i completeu les implementacions de `euros_a_float` i `percentatge_a_float`, substituint cada `TODO` per una o més línies del vostre propi codi.

## Com provar

A continuació s'explica com provar el codi manualment:

-   Executeu el vostre programa amb `python tip.py`. Escriviu `50.00€` i premeu Intro. A continuació, escriviu `15%` i premeu Intro. El vostre programa hauria de sortir:
```
Deixa 7.50€
```
-   Executeu el vostre programa amb `python tip.py`. Escriviu `100.00€` i premeu Intro. A continuació, escriviu `18%` i premeu Intro. El vostre programa hauria de sortir:
```
Deixa 18.00€
```
-   Executeu el vostre programa amb `python tip.py`. Escriviu `15.00€` i premeu Intro. A continuació, escriviu `25%` i premeu Intro. El vostre programa hauria de sortir
```
Deixa 3.75€
```



## Com enviar

Al vostre terminal, executeu el següent per enviar el vostre treball.

```
submit50 cs50/problems/2022/python/tip
```

Al classroom, entrega una captura d'haver fet les proves anteriorment esmenades així com el programa tip.py (l'hauras de descarregar de l'IDE)
