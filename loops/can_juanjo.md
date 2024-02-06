# El Bar de Can Juanjo

![FotoBarJuanjo](https://vicentcardona.github.io/ProgitractI/logo_juanjo.jpg)

Sens dupte, el lloc més popular de l'institut es el Bar d'en Juanjo. Aquest ofereix multituts d'snacks, segons el `dict` següent, on el valor de cada clau és un preu en euros:

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

Implementeu un programa que permet a un usuari fer una comanda, demanant els artícles, un per línea, fins que l'usuari introdueix Ctrl+d (que és una manera habitual d'acabar l'entrada d'un programa. El programa ha d'imprimiur el cost total de tots els elements introduïts fins el moment, amb el sufix del signe d'euros `€` i formatejat amb 2 decimals. Tracteu l'usuari **sense distinció de majúscules o minúscules** i ignoreu qualsevol entrada que no sigui un element de la "carta".



## A tenir en compte:

- Podeu detectar quan l'usuari ha introduït Ctrl+d agafant un codi [`EOFError`](https://docs.python.org/es/3/library/exceptions.html#EOFError) com:
```python
try:
  item = input()
except EOFError:
  ...
```
La idea es que imprimeixi una nova linea per així 
  
