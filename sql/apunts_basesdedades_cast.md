# Apunts de SQL Bàsic 

## 1. Introducció a SQL: Què és això?

Imagina que tens una col·lecció enorme de cromos, cançons a Spotify, o els teus contactes al mòbil. Com ho organitzes tot? Les **bases de dades** són com arxivadors digitals súper organitzats. I **SQL** (Structured Query Language) és l'**idioma especial** que fem servir per **parlar amb aquests arxivadors**.

Amb SQL pots:
* **Demanar informació:** "Mostra'm totes les cançons de Rosalia" o "Quins amics viuen a Barcelona?".
* **Afegir coses noves:** "Guarda aquest nou contacte" o "Afegeix aquesta cançó a la meva playlist".
* **Canviar coses:** "Actualitza la puntuació d'aquest jugador" o "Canvia el número de telèfon d'aquest contacte".
* **Esborrar coses:** "Elimina aquesta cançó que ja no m'agrada".
* **Crear l'estructura:** "Crea un nou arxivador (taula) per guardar informació sobre videojocs".

**Conceptes Clau (Com s'organitza tot):**

* **Base de Dades Relacional:** Pensa-hi com una carpeta gegant amb molts **arxivadors (taules)** dins. Aquests arxivadors estan connectats entre si (per exemple, l'arxivador de `Cançons` pot connectar amb el d'`Artistes`).
* **Taula:** És com un **arxivador** o una **graella** (tipus Excel) on guardes informació sobre **un tema concret**. Exemples: una taula per a `Usuaris`, una per a `Cançons`, una per a `Puntuacions`.
* **Columna (Camp):** Són les **etiquetes** de cada calaix o capçalera de la graella. Defineixen **quin tipus d'informació** guardes. A la taula `Cançons`, les columnes podrien ser `titol`, `artista`, `durada`.
* **Fila (Registre):** És cada **element individual** que guardes, com una fitxa completa dins l'arxivador. A la taula `Cançons`, cada fila seria una cançó específica amb el seu títol, artista i durada.

## 2. Els Comandaments Màgics (Fonamentals)

Aquests són els "encanteris" bàsics de SQL:

* **`SELECT`**: El més popular! Serveix per **demanar i veure** la informació que vulguis. És el "Mostra'm...".
* **`INSERT INTO`**: Per **afegir** una fila nova (una cançó nova, un usuari nou...).
* **`UPDATE`**: Per **modificar** informació que ja existeix (canviar un nom, actualitzar una puntuació...).
* **`DELETE`**: Per **eliminar** una fila sencera (esborrar un missatge, eliminar un jugador...).
* **`CREATE TABLE`**: Per **construir** una taula nova des de zero (crear la llista de personatges del teu joc).
* **`DROP TABLE`**: Per **destruir** una taula sencera (compte amb aquest, que ho esborra tot!).

## 3. Refinant la Màgia: Clàusules i Operadors

Aquests són "ingredients extra" que afegeixes als comandaments (sobretot a `SELECT`) per fer coses més específiques.

---

### 3.1. `SELECT`: Escollir Què Veus

Amb `SELECT` tries quines **columnes** (quina informació específica) vols veure.

* **`SELECT *`**: L'asterisc (`*`) és el comodí "ensenya-m'ho **tot**". Mostra totes les columnes de la taula. Va bé per fer una ullada ràpida.

    *Taula d'Exemple: `Usuaris` (d'una app imaginària)*
    | id_usuari | nom_usuari | email         | ciutat    |
    | :-------- | :--------- | :------------ | :-------- |
    | 1         | annagm     | anna@email.com| Madrid    |
    | 2         | llui_gamer | luis@email.com| Barcelona |
    | 3         | evart      | eva@email.com | Madrid    |

    ```sql
    -- Selecciona TOT de la taula Usuaris
    SELECT * FROM Usuaris;
    ```
    *Resultat:* Veureies tota la informació dels 3 usuaris.

* **`SELECT columnes_especifiques`**: Millor triar només el que necessites, separant els noms de les columnes per comes.

    *Taula d'Exemple: `Usuaris` (la mateixa de dalt)*

    ```sql
    -- Selecciona només el nom d'usuari i la ciutat
    SELECT nom_usuari, ciutat FROM Usuaris;
    ```
    *Resultat:*
    | nom_usuari | ciutat    |
    | :--------- | :-------- |
    | annagm     | Madrid    |
    | llui_gamer | Barcelona |
    | evart      | Madrid    |

* **`DISTINCT`**: Per veure només els valors **únics**, sense repeticions.

    *Taula d'Exemple: `Usuaris` (la mateixa de dalt)*

    ```sql
    -- Quines ciutats diferents tenim? (Sense repetir Madrid)
    SELECT DISTINCT ciutat FROM Usuaris;
    ```
    *Resultat:*
    | ciutat    |
    | :-------- |
    | Madrid    |
    | Barcelona |

---

### 3.2. `WHERE`: Posar Condicions (Filtrar!)

La clàusula **`WHERE`** és súper útil! És com dir: "Mostra'm només els que compleixin **aquesta condició**". Ideal per trobar exactament el que busques.

* **`WHERE ... = 'valor'`**: Troba els que siguin **exactament iguals** a alguna cosa. (El text va entre cometes simples `' '`).

    *Taula d'Exemple: `Usuaris` (la mateixa de dalt)*

    ```sql
    -- Mostra només els usuaris de Madrid
    SELECT nom_usuari, email FROM Usuaris WHERE ciutat = 'Madrid';
    ```
    *Resultat:* Només veuries l'Anna i l'Eva.

* **`WHERE ... > numero`**: Troba els que siguin **més grans** que un número.

    *Taula d'Exemple: `PuntuacionsJoc`*
    | id_partida | nom_jugador | punts | nivell |
    | :--------- | :---------- | :---- | :----- |
    | 1          | llui_gamer  | 1500  | 5      |
    | 2          | annagm      | 2500  | 8      |
    | 3          | evart       | 1200  | 4      |

    ```sql
    -- Mostra les partides amb més de 1400 punts
    SELECT nom_jugador, punts FROM PuntuacionsJoc WHERE punts > 1400;
    ```
    *Resultat:* Veureies la partida d'en Lluís i l'Anna.

* **`WHERE ... >= numero`**: Troba els que siguin **més grans O iguals** a un número.

    *Taula d'Exemple: `PuntuacionsJoc` (la mateixa de dalt)*

    ```sql
    -- Mostra les partides amb 1500 punts o més
    SELECT nom_jugador, punts FROM PuntuacionsJoc WHERE punts >= 1500;
    ```
    *Resultat:* Veureies la partida d'en Lluís (1500) i l'Anna (2500).

    *(També pots usar `<`, `<=`, `<>` o `!=` per a "més petit que", "més petit o igual que", i "diferent de")*

* **`AND`**: Per posar **dues (o més) condicions** que s'han de complir **totes dues**.

    *Taula d'Exemple: `Usuaris`*
    | id_usuari | nom_usuari | email           | ciutat    | actiu |
    | :-------- | :--------- | :-------------- | :-------- | :---- |
    | 1         | annagm     | ana@email.com   | Madrid    | 1     |
    | 2         | llui_gamer | luis@email.com  | Barcelona | 1     |
    | 3         | evart      | eva@email.com   | Madrid    | 0     |
    | 4         | carles_pro | carlos@mail.com | Madrid    | 1     |

    ```sql
    -- Mostra usuaris de Madrid I que estiguin actius (actiu = 1)
    SELECT nom_usuari FROM Usuaris WHERE ciutat = 'Madrid' AND actiu = 1;
    ```
    *Resultat:* Només veuries `annagm` i `carles_pro`.

* **`OR`**: Per posar **dues (o més) condicions** on només cal que se'n compleixi **una**.

    *Taula d'Exemple: `CançonsPlaylist`*
    | id_canço | titol        | artista    | genere     | durada_seg |
    | :------- | :----------- | :--------- | :--------- | :--------- |
    | 1        | Malamente    | Rosalia    | Flamenc Pop| 150        |
    | 2        | Boig per tu  | Sau        | Rock Català| 245        |
    | 3        | Milionària   | Rosalia    | Pop Rumba  | 185        |
    | 4        | Corazón Partío| A. Sanz   | Pop Llatí  | 300        |

    ```sql
    -- Mostra cançons de Rosalia O que durin menys de 180 segons
    SELECT titol, artista FROM CançonsPlaylist WHERE artista = 'Rosalia' OR durada_seg < 180;
    ```
    *Resultat:* Veureies 'Malamente' (Rosalia), 'Milionària' (Rosalia) i 'Malamente' (dura menys de 180s). *Ups, 'Malamente' compleix les dues!*

* **`IN`**: Una manera curta de dir "que sigui **un d'aquests** valors". Molt útil per no escriure molts `OR`.

    *Taula d'Exemple: `Usuaris` (la mateixa d'abans)*

    ```sql
    -- Mostra usuaris que siguin de Barcelona O de València
    SELECT nom_usuari, ciutat FROM Usuaris WHERE ciutat IN ('Barcelona', 'València');
    ```
    *Resultat:* Veureies `llui_gamer` (Barcelona) i altres si n'hi hagués de València.

* **`LIKE`**: Per buscar text que **s'assembli** a alguna cosa, usant **comodins**:
    * `%`: Significa "qualsevol cosa" (cap, una o moltes lletres).
    * `_`: Significa "exactament una lletra qualsevol".

    *Taula d'Exemple: `Usuaris`*
    | id_usuari | nom_usuari | email                 |
    | :-------- | :--------- | :-------------------- |
    | 1         | annagm     | anna@email.com        |
    | 2         | llui_gamer | luis@email.es         |
    | 3         | evart      | eva@altre.com         |
    | 4         | anna_lopez | anna.lopez@email.com  |

    ```sql
    -- Troba usuaris que comencin per 'anna'
    SELECT nom_usuari FROM Usuaris WHERE nom_usuari LIKE 'anna%';
    -- Resultat: annagm, anna_lopez

    -- Troba emails que acabin en '.com'
    SELECT email FROM Usuaris WHERE email LIKE '%.com';
    -- Resultat: anna@email.com, eva@altre.com, anna.lopez@email.com

    -- Troba usuaris que tinguin 'gamer' al nom
    SELECT nom_usuari FROM Usuaris WHERE nom_usuari LIKE '%gamer%';
    -- Resultat: llui_gamer
    ```

* **`NULL`**: Representa que **no hi ha valor**, que està buit o és desconegut. **Important:** No és el mateix que 0 o un text buit `''`. Per buscar valors `NULL`, has d'usar **`IS NULL`** o **`IS NOT NULL`**.

    *Taula d'Exemple: `PerfilsUsuaris`*
    | id_usuari | nom_usuari | bio        | data_registre |
    | :-------- | :--------- | :--------- | :------------ |
    | 1         | annagm     | Hola!      | 2025-01-10    |
    | 2         | llui_gamer | NULL       | 2025-02-15    |
    | 3         | evart      | Artista :) | 2025-03-20    |
    | 4         | carles_pro | NULL       | 2025-04-01    |

    ```sql
    -- Troba usuaris que NO han escrit la seva bio (és NULL)
    SELECT nom_usuari FROM PerfilsUsuaris WHERE bio IS NULL;
    ```
    *Resultat:* `llui_gamer`, `carles_pro`.

    ```sql
    -- Troba usuaris que SÍ tenen bio
    SELECT nom_usuari, bio FROM PerfilsUsuaris WHERE bio IS NOT NULL;
    ```
    *Resultat:* `annagm`, `evart`.

---

### 3.3. `ORDER BY` i `LIMIT`: Ordenar i Limitar Resultats

* **`ORDER BY`**: Per **ordenar** els resultats com vulguis (alfabèticament, per números...). Per defecte ordena de petit a gran (`ASC` - ascendent). Pots dir-li que ordeni al revés amb `DESC` (descendent).

    *Taula d'Exemple: `PuntuacionsJoc` (la mateixa d'abans)*

    ```sql
    -- Mostra les puntuacions ordenades de MÉS ALTA a MÉS BAIXA
    SELECT nom_jugador, punts FROM PuntuacionsJoc ORDER BY punts DESC;
    ```
    *Resultat:* Primer sortiria l'Anna (2500), després en Lluís (1500) i finalment l'Eva (1200).

    ```sql
    -- Ordena per nivell (de més baix a més alt) i si empaten, per nom
    SELECT nom_jugador, nivell, punts FROM PuntuacionsJoc ORDER BY nivell ASC, nom_jugador ASC;
    ```

* **`LIMIT`**: Per dir "només vull veure els **primers N** resultats". Perfecte per a rànquings (Top 3, Top 10...).

    *Taula d'Exemple: `PuntuacionsJoc` (ordenada per punts DESC com abans)*

    ```sql
    -- Mostra només els 2 millors jugadors (els 2 primers després d'ordenar)
    SELECT nom_jugador, punts FROM PuntuacionsJoc ORDER BY punts DESC LIMIT 2;
    ```
    *Resultat:* Només veuries l'Anna i en Lluís.

---

### 3.4. `GROUP BY`: Agrupar Coses Iguals

* **`GROUP BY`**: Agrupa les files que tenen el **mateix valor** en una columna. S'usa molt amb funcions que calculen coses per grup (com comptar quants hi ha a cada grup - `COUNT`, que veurem més endavant).

    *Taula d'Exemple: `Usuaris`*
    | id_usuari | nom_usuari | ciutat    |
    | :-------- | :--------- | :-------- |
    | 1         | annagm     | Madrid    |
    | 2         | llui_gamer | Barcelona |
    | 3         | evart      | Madrid    |
    | 4         | carles_pro | Sevilla   |
    | 5         | maria_bcn  | Barcelona |

    ```sql
    -- Agrupa per ciutat (per després poder comptar quants hi ha a cada una)
    SELECT ciutat FROM Usuaris GROUP BY ciutat;
    ```
    *Resultat (només les ciutats, sense repetir):*
    | ciutat    |
    | :-------- |
    | Madrid    |
    | Barcelona |
    | Sevilla   |
    *(Per saber quants n'hi ha a cada ciutat, faríem: `SELECT ciutat, COUNT(*) FROM Usuaris GROUP BY ciutat;`)*

---

### 3.5. Subconsultes: Una Consulta Dins d'una Altra

* **Subconsultes (Nested Queries)**: Són com fer una **pregunta dins d'una altra pregunta**. SQL primer resol la pregunta de dins (la subconsulta) i després usa el resultat per resoldre la pregunta principal.

    *Taula d'Exemple: `CançonsPlaylist` (la mateixa d'abans)*
    *Taula d'Exemple: `Artistes`*
    | id_artista | nom_artista | genere_principal | pais |
    | :--------- | :---------- | :--------------- | :--- |
    | 1          | Rosalia     | Urbà/Flamenc    | ES   |
    | 2          | Sau         | Rock             | ES   |
    | 3          | A. Sanz     | Pop Llatí        | ES   |

    ```sql
    -- Mostra les cançons d'artistes que són d'Espanya ('ES')
    -- 1r: La subconsulta busca els ID dels artistes d'Espanya
    -- 2n: La consulta principal busca cançons que coincideixin amb aquests IDs
    SELECT titol
    FROM CançonsPlaylist
    WHERE artista IN (SELECT nom_artista FROM Artistes WHERE pais = 'ES');
    ```
    *Resultat:* Totes les cançons de l'exemple, ja que tots els artistes són 'ES'.

---

### 3.6. `Date`: Treballar amb Dates

Les dates són importants (quan es va crear un post, quan es va fer una compra...). SQL té funcions per treballar amb elles, però **canvien una mica** segons la base de dades que usis (MySQL, PostgreSQL...).

* **Exemple Genèric (la funció exacta pot canviar):**

    *Taula d'Exemple: `PostsInstagram`*
    | id_post | id_usuari | text_post       | data_publicacio |
    | :------ | :-------- | :-------------- | :-------------- |
    | 101     | annagm    | Foto platja!    | 2025-04-28      |
    | 102     | llui_gamer| Nou rècord!     | 2025-05-01      |
    | 103     | annagm    | Sopar amics :)  | 2025-05-01      |

    ```sql
    -- Selecciona posts publicats l'1 de Maig de 2025
    -- La funció DATE() treu només la part de la data (per si hi hagués hora)
    SELECT id_post, text_post FROM PostsInstagram WHERE DATE(data_publicacio) = '2025-05-01';

    -- Treure l'any de publicació (la funció pot ser YEAR() o EXTRACT(YEAR FROM ...))
    SELECT YEAR(data_publicacio) AS any_post FROM PostsInstagram WHERE id_post = 101;
    -- Resultat: 2025
    ```
    ***Sempre*** *cal mirar la documentació de la base de dades específica!*

---

### 3.7. `JOIN`: Unir Taules (El Poder de les Relacions!)

Els **`JOIN`** són súper potents! Permeten **combinar informació de diferents taules** que estan relacionades. Per exemple, per veure el nom de l'usuari (taula `Usuaris`) al costat de les seves puntuacions (taula `PuntuacionsJoc`).

* **`INNER JOIN`**: El més típic. Combina files només quan hi ha una **coincidència en les dues taules**. Si un usuari no té puntuacions, no sortirà en el resultat d'unir `Usuaris` amb `PuntuacionsJoc`.

    *Taula d'Exemple: `Usuaris`*
    | id_usuari | nom_usuari | ciutat    |
    | :-------- | :--------- | :-------- |
    | 1         | annagm     | Madrid    |
    | 2         | llui_gamer | Barcelona |
    | 3         | evart      | Madrid    |

    *Taula d'Exemple: `PuntuacionsJoc`*
    | id_partida | id_usuari_fk | punts | nivell |
    | :--------- | :----------- | :---- | :----- |
    | 1          | 2            | 1500  | 5      | -- Lluís
    | 2          | 1            | 2500  | 8      | -- Anna
    | 3          | 2            | 1800  | 6      | -- Lluís (una altra partida)

    ```sql
    -- Mostra el nom de l'usuari al costat dels seus punts
    -- Uneix les taules on l'id_usuari coincideix
    SELECT Usuaris.nom_usuari, PuntuacionsJoc.punts
    FROM Usuaris
    INNER JOIN PuntuacionsJoc ON Usuaris.id_usuari = PuntuacionsJoc.id_usuari_fk;
    ```
    *Resultat:*
    | nom_usuari | punts |
    | :--------- | :---- |
    | llui_gamer | 1500  |
    | annagm     | 2500  |
    | llui_gamer | 1800  |
    *(L'Eva no surt perquè no té puntuacions a la taula `PuntuacionsJoc`)*

* **`Multiple Joins`**: Pots **encadenar `JOIN`s** per unir tres, quatre o més taules!

    *Afegim Taula `Jocs`*
    | id_joc | nom_joc      | genere   |
    | :----- | :----------- | :------- |
    | 10     | Aventures 3D | Aventura |
    | 20     | Curses Bojes | Curses   |

    *Modifiquem `PuntuacionsJoc` per incloure `id_joc_fk`*
    | id_partida | id_usuari_fk | id_joc_fk | punts | nivell |
    | :--------- | :----------- | :-------- | :---- | :----- |
    | 1          | 2            | 10        | 1500  | 5      |
    | 2          | 1            | 20        | 2500  | 8      |
    | 3          | 2            | 10        | 1800  | 6      |

    ```sql
    -- Mostra nom d'usuari, nom del joc i punts
    SELECT u.nom_usuari, j.nom_joc, p.punts
    FROM Usuaris AS u -- 'AS u' és un àlies (un nom curt) per a la taula
    INNER JOIN PuntuacionsJoc AS p ON u.id_usuari = p.id_usuari_fk
    INNER JOIN Jocs AS j ON p.id_joc_fk = j.id_joc;
    ```
    *Resultat:*
    | nom_usuari | nom_joc      | punts |
    | :--------- | :----------- | :---- |
    | llui_gamer | Aventures 3D | 1500  |
    | annagm     | Curses Bojes | 2500  |
    | llui_gamer | Aventures 3D | 1800  |

* **`Joins with WHERE`**: Pots afegir un `WHERE` **després** dels `JOIN`s per filtrar el resultat combinat.

    *Usant l'exemple anterior*
    ```sql
    -- Mostra només les puntuacions del joc 'Aventures 3D'
    SELECT u.nom_usuari, j.nom_joc, p.punts
    FROM Usuaris AS u
    INNER JOIN PuntuacionsJoc AS p ON u.id_usuari = p.id_usuari_fk
    INNER JOIN Jocs AS j ON p.id_joc_fk = j.id_joc
    WHERE j.nom_joc = 'Aventures 3D';
    ```
    *Resultat:* Només les dues partides d'en Lluís.

* **`LEFT JOIN`**: Aquest és interessant! Manté **totes** les files de la taula de l'**esquerra** (la del `FROM`) i les combina amb la de la dreta (la del `LEFT JOIN`). Si no hi ha coincidència a la dreta, posa `NULL`. Perfecte per veure "tots els usuaris i les seves puntuacions (si en tenen)".

    *Usant `Usuaris` i `PuntuacionsJoc`*
    ```sql
    -- Mostra TOTS els usuaris i les seves puntuacions (si en tenen)
    SELECT Usuaris.nom_usuari, PuntuacionsJoc.punts
    FROM Usuaris -- Taula esquerra
    LEFT JOIN PuntuacionsJoc ON Usuaris.id_usuari = PuntuacionsJoc.id_usuari_fk; -- Taula dreta
    ```
    *Resultat:*
    | nom_usuari | punts |
    | :--------- | :---- |
    | annagm     | 2500  |
    | llui_gamer | 1500  |
    | llui_gamer | 1800  |
    | evart      | NULL  | -- L'Eva surt, però amb NULL perquè no té puntuacions
    *(També hi ha `RIGHT JOIN` (manté tot de la dreta) i `FULL OUTER JOIN` (manté tot de les dues))*

* **`Self Join`**: Unir una taula **amb si mateixa**. Sembla estrany, però és útil per a relacions dins la mateixa taula (ex: una llista d'usuaris on un pot ser "amic de" un altre usuari de la mateixa llista). Cal usar **àlies** (noms curts) per no confondre les "dues còpies" de la taula.

    *Taula d'Exemple: `Empleats` (amb qui és el seu cap)*
    | id_empleat | nom       | id_cap |
    | :--------- | :-------- | :----- |
    | 1          | DirectorA | NULL   | -- El director no té cap
    | 2          | Anna      | 1      |
    | 3          | Lluís     | 1      |
    | 4          | Eva       | 2      | -- El cap de l'Eva és l'Anna

    ```sql
    -- Mostra cada empleat i el nom del seu cap
    SELECT emp.nom AS NomEmpleat, cap.nom AS NomDelCap
    FROM Empleats AS emp -- La taula com a "empleat"
    LEFT JOIN Empleats AS cap ON emp.id_cap = cap.id_empleat; -- La mateixa taula com a "cap"
    ```
    *Resultat:*
    | NomEmpleat | NomDelCap |
    | :--------- | :-------- |
    | DirectorA  | NULL      |
    | Anna       | DirectorA |
    | Lluís      | DirectorA |
    | Eva        | Anna      |

---

**Un Últim Consell:** La millor manera d'aprendre SQL és **practicar**! Busca "SQL Fiddle", "SQL Online Compiler" o usa el de `sql-easy.com` per provar aquests comandaments amb les taules d'exemple o inventa't les teves. Juga, experimenta i mira què passa! 😉

*Aquest document cobreix els conceptes bàsics. SQL té moltes més coses, i cada base de dades pot tenir petits detalls diferents.*


