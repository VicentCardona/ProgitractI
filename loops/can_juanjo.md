# El Bar de Can Juanjo

![FotoBarJuanjo](https://vicentcardona.github.io/ProgitractI/logo_juanjo.jpg)

Sense dubte, el lloc més popular de l'institut és el Bar d'en Juanjo. Aquest ofereix multituds de snacks, segons el `dict` següent, on el valor de cada clau és un preu en euros:

```python
{
  "pizza formatge": 2.00,
  "gofre xocolata": 2.00,
  "kinder bueno": 1.50,
  "pals de pipes": 1.40,
  "yogur fruita": 2.75,
  "chips Ahoy": 1.30,
  "doritos": 1.10,
  "bocata vegetal": 2.85,
  "bocata Pernil Salat": 2.40,
}
```

Implementeu un programa que permet a un usuari fer una comanda, demanant els articles, un per línia, fins que l'usuari introdueix Ctrl+d (que és una manera habitual d'acabar l'entrada d'un programa. El programa ha d'imprimiur el cost total de tots els elements introduïts fins al moment, amb el sufix del signe d'euros `€` i formatat amb 2 decimals. Tracteu l'usuari **sense distinció de majúscules o minúscules** i ignoreu qualsevol entrada que no sigui un element de la "carta".

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=XJojPe1GSAs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## A tenir en compte:

- Podeu detectar quan l'usuari ha introduït Ctrl+d agafant un codi [`EOFError`](https://docs.python.org/es/3/library/exceptions.html#EOFError) com:
```python
try:
  item = input()
except EOFError:
  ...
```
- Introduir `Ctrl+d` no necessita prémer Enter. Recorda que pots introduir línies com a programador simplement imprimint `\n`-
- Tingues en compte que `dict` inclou molts [mètodes](docs.python.org/es/3/library/stdtypes.html#mapping-types-dict) i admet operacions com:
```python
if clau in d:
  ...
```
On `d` es un `dict` i clau és un `str`.

https://www.youtube.com/watch?v=XJojPe1GSAs
  
