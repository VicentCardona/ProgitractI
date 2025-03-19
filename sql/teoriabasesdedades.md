


En aquest món interconnectat, cada acció que realitzem esdevé una dada. [cite: 16] Des de la cerca d'informació a internet fins a la interacció a les xarxes socials, passant per les compres en línia i el visionat de sèries en plataformes de «streaming». Totes aquestes dades necessiten ser emmagatzemades, gestionades i processades de manera eficient perquè la informació estigui disponible a l'instant. Aquí és on entra en joc el món de les bases de dades.

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-15.jpeg) [cite: 19]

Quantitat de dades que es van generar a cada minut del 2023, en algunes aplicacions populars. [cite: 19]

Les **bases de dades** no són només el cor de gairebé totes les aplicacions web i serveis que fem servir diàriament, sinó que també són imprescindibles en àmbits tan variats com la medicina, per al seguiment d'historials clínics; [cite: 20, 21] la meteorologia, en la predicció del temps; o fins i tot en l'esport, per analitzar el rendiment dels atletes. [cite: 21, 22] Per exemple, cada vegada que fem servir una aplicació per monitoritzar les nostres rutes de «running», estem veient el nostre progrés alhora que estem interactuant amb bases de dades que emmagatzemen i processen les nostres distàncies, rutes, temps i comparatives. [cite: 22, 23]

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-16.jpeg) [cite: 23]

Pantalles d'una aplicació esportiva popular

Les bases de dades s'han tornat imprescindibles en l'era del «big data», on la capacitat de processar ràpid grans quantitats d'informació pot ser la diferència entre prendre una decisió encertada o quedar-se enrere. [cite: 24] Per exemple, les recomanacions personalitzades que ens fan les plataformes de comerç electrònic es basen en complexos anàlisis de dades emmagatzemades sobre els nostres hàbits de compra i preferències. [cite: 24, 25]

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-17.jpeg) [cite: 25]

Exemple del sistema de recomanacions d'Amazon

Endinsar-nos en l'estudi de les bases de dades ens permetrà comprendre com s'estructuren les dades en taules, registres i camps, com es defineixen i manipulen mitjançant llenguatges específics com SQL, i com es poden extreure informacions valuoses a través de vistes, informes i formularis. [cite: 25, 26] A més, explorarem les diferències entre els sistemes gestors de bases de dades relacionals, fonamentals per entendre la lògica darrere de l'emmagatzemament de dades interrelacionades, i les bases de dades **NoSQL**, fonamentals per manejar volums de dades massius que no s'ajusten bé a esquemes predefinits. [cite: 26, 27] L'habilitat per gestionar i analitzar dades s'ha convertit en una competència clau en el mercat laboral actual. [cite: 27, 28] En aquest sentit, conèixer el funcionament i l'aplicació de les bases de dades ens obre les portes a una àmplia gamma d'oportunitats professionals. [cite: 28, 29]

## 8.1. Sistemes gestors de bases de dades relacionals.

És fonamental comprendre que estem parlant d'una eina clau en el món de la informàtica i la gestió de la informació. [cite: 29, 30] Però abans de conèixer què és un Sistema Gestor de Bases de Dades -SGBD-, necessitem saber què és una base de dades. [cite: 30, 31]

Una **base de dades** és un conjunt d'informació estructurada relativa a un tema determinat. [cite: 31, 32] Aquest tema pot englobar un gran nombre de contextos dels quals ens interessa mantenir-nos al corrent i que volem tenir freqüentment actualitzats. [cite: 32, 33] Pràcticament qualsevol sistema d'informació o coneixement pot estructurar-se i classificar-se en una base de dades. [cite: 33, 34]

Fins fa relativament pocs anys, les bases de dades eren analògiques, és a dir, contenien informació en paper o textos impresos. [cite: 34, 35] No obstant això, amb l'arribada de l'era digital i el Big Data s'ha fet imprescindible l'ús de bases de dades informatitzades. [cite: 35, 36] Gràcies a les bases de dades en format digital s'han pogut solucionar molts dels problemes que sorgien arran de la ingent quantitat d'informació que es maneja en l'actualitat. [cite: 36, 37] Per exemple, permeten estalviar espai, agilitar les consultes i es pot emmagatzemar molta més informació. [cite: 37, 38] T'imagines com d'embolicós seria obtenir el llistat de publicacions d'un usuari d'una xarxa social si tot estigués emmagatzemat en paper? [cite: 38, 39]

Els programes que han fet això possible es denominen **Sistemes Gestors de Bases de Dades (SGBD)** o, en anglès, _Database Management System (DBMS)_. [cite: 39, 40] Aquest tipus de programes faciliten enormement l'emmagatzemament de dades i la posterior consulta d'aquests. [cite: 40, 41] Al principi eren usats sobretot per grans empreses o administracions públiques, però en l'actualitat també els fan servir tot tipus d'usuaris o empreses (per exemple, per crear el registre d'usuaris d'un web). [cite: 41, 42]

Els SGBD no només emmagatzemen dades de manera eficient, sinó que també permeten la seva recuperació, actualització i gestió a través de relacions lògiques entre ells. [cite: 42, 43] Aquests sistemes es basen en el model relacional de dades, un enfocament que organitza la informació en **taules** compostes per **files** i **columnes**. [cite: 43, 44]

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-118.png) [cite: 44]

Tres taules -Productes, Clients i Comandes- d'una base de dades

Els SGBD funcionen sota el principi que cada dada està relacionada d'alguna manera amb una altra, permetent així consultes complexes i el manteniment de les relacions entre les dades a través de regles definides. [cite: 45] Aquesta capacitat per establir relacions complexes entre diferents taules és el que els fa tan potents per al maneig de grans volums d'informació estructurada. [cite: 45, 46]

Però, aquesta és només la punta de l'iceberg, ja que un SGBD ens ofereix tota aquesta funcionalitat: [cite: 46]

-   **Definició de dades**: permeten la creació i modificació de l'estructura de les bases de dades a través d'un **Llenguatge de Definició de Dades (DDL)**. [cite: 46, 47] Això inclou la creació de taules, definició de camps, i establiment de restriccions i relacions entre taules. [cite: 47, 48]
-   **Manipulació de dades**: ofereixen eines per inserir, actualitzar, esborrar i consultar dades emmagatzemades, utilitzant un **Llenguatge de Manipulació de Dades (DML)**. [cite: 48, 49] Aquestes operacions són fonamentals per al maneig diari de les dades dins de la base de dades. [cite: 49, 50]
-   **Control de transaccions**: gestionen transaccions, que són seqüències d'operacions de manipulació de dades tractades com una sola unitat. [cite: 50, 51] Això assegura la integritat de les dades a través de propietats com l'atomicitat, consistència, aïllament i durabilitat (ACID). [cite: 51, 52]
-   **Seguretat**: proveeixen mecanismes per controlar l'accés a les dades, assegurant que només usuaris autoritzats puguin realitzar operacions específiques. [cite: 52, 53] Això inclou la gestió de permisos i rols, així com la implementació de polítiques de seguretat per protegir les dades. [cite: 53, 54]
-   **Integritat de dades**: mantenen la precisió i consistència de les dades a través de restriccions d'integritat, unicitat i de comprovació, que asseguren que les dades emmagatzemades compleixin regles específiques.
-   **Consultes avançades**: permeten la realització de consultes complexes utilitzant el **Llenguatge de Consulta Estructurada (SQL)**, incloent operacions com «join», subconsultes, funcions agregades i vistes, per extreure informació significativa de les dades emmagatzemades.
-   **Optimització de consultes**: inclouen optimitzadors de consultes que analitzen i determinen la manera més eficient d'executar una consulta, millorant el rendiment de la base de dades.
-   **Suport per a procediments emmagatzemats**: permeten definir procediments en la pròpia base de dades, que s'executen automàticament en resposta a esdeveniments específics, millorant l'eficiència i centralitzant la lògica de negoci.
-   **Gestió de la concurrència**: gestionen l'accés concurrent a les dades per assegurar que múltiples usuaris puguin treballar amb la base de dades simultàniament sense interferir entre si, mitjançant el control de bloquejos i versions de dades.
-   **Còpia de seguretat**: ofereixen eines per crear còpies de seguretat de les dades i recuperar la base de dades en cas d'errors o pèrdua de dades, assegurant la seva disponibilitat.
-   **Suport per a dades massives**: alguns SGBD estan dissenyats per manejar grans volums de dades per la qual cosa ofereixen funcionalitats molt demandades en aquest tipus de tasques.

Un exemple pràctic de l'aplicació dels SGBD el trobem en el sector bancari, on és vital gestionar enormes quantitats de dades relacionades amb clients, comptes, transaccions i préstecs. Un SGBD permet als bancs emmagatzemar aquestes dades de forma segura, realitzar operacions com actualitzar saldos de comptes, processar pagaments i generar informes financers de manera eficient.

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-119.png)

Entre els SGBD més destacats avui dia es troben MySQL, Oracle Database, Microsoft SQL Server i PostgreSQL. Cada un d'aquests sistemes té les seves pròpies característiques, avantatges i desavantatges, però tots comparteixen la capacitat de treballar amb dades relacionals de manera eficient.

| **MySQL**: àmpliament utilitzat en aplicacions web, és conegut per la seva simplicitat i eficàcia en el maneig de llocs web dinàmics. | <img loading="lazy" decoding="async" src="https://lh7-us.googleusercontent.com/m8uotRKpgSleSFMNRkDa72-f8KWd9TOK0CMaiy_euxK3en9-_PNuJjtbaxxvJ-cqRFPNlTOZ8Jixy0ksRcTsJ0w5AlT_KdU3TOv1HZt7xTuUCfHsKisgnvfSbFKGj-vEq6P2xFwzfioUkjvmnL3PJoE" width="286" height="164"> |
| **Oracle Database**: ofereix una solució robusta per a grans empreses, destacant per la seva escalabilitat, seguretat i conjunt de característiques per al processament de transaccions complexes. | <img loading="lazy" decoding="async" src="https://lh7-us.googleusercontent.com/LK8k2sDnPjFp4SWin6rkwMJmJfjdGupTcL7yPTwocytK4eFerV3PpbEDG-1GO_AktUEYkMmsQMXb3OLyr8nukDK2aD3meTCXmZFg1KSpBGANJLbMjKXFPYcQOig5nDAxI5PT7EU_87cMkRU0ILrTnI0" width="286" height="164"> |
| **Microsoft SQL Server**: integrat estretament amb productes Microsoft, és ideal per a entorns que ja depenen de la infraestructura de Microsoft. | <img loading="lazy" decoding="async" src="https://lh7-us.googleusercontent.com/aOmIot25fg7ugKcRH-vt1QqDq9rPWMNrOuxo4NDyshvg94bKMLECWk4I99sdKLkVpzusbAfuw_Hp1sIfqPIibGZTYpzFNnbMdhCPO1JMxImKuZie1K4T_5EzbNTjQOR2QBRnNNgx9x6P5T0RIffbtsI" width="286" height="164"> |
| **PostgreSQL**: un sistema de codi obert, ressalta per la seva conformitat amb els estàndards SQL i la seva capacitat per manejar una àmplia gamma de càrregues de treball, des de simples consultes fins a anàlisis de dades complexes. | <img loading="lazy" decoding="async" src="https://lh7-us.googleusercontent.com/IUDKhEfIpGYAjKvgvMKZglQHCB9MIe_GFci4rCU8DEaYL_pzJa4PBIH4STEiVIm2q5KykNnZrvq4fVct10rj_vv8DtRd32dvdfaTNpX3qpNs0_NUljpOWL_ASXbdbv8RS_Y46Y41CzY2qbU2QTmNeLg" width="286" height="164"> |

## 8.2. Taules, registres i camps. Tipus de dades.

En el nucli dels sistemes gestors de bases de dades relacionals es troben les taules, registres, i camps, conceptes fonamentals que estructuren la manera en què s'emmagatzema i organitza la informació. Aquest esquema facilita l'emmagatzemament de dades de manera sistemàtica i eficient, la seva recuperació, actualització i gestió.

Anem a desglossar cada un d'aquests elements i com interactuen entre si per formar la base de qualsevol base de dades relacional.

### 8.2.1. Taules

Una **taula** és una estructura que organitza dades en files i columnes, de manera similar a com es visualitza un full de càlcul. Cada taula emmagatzema dades sobre un tipus específic d'entitat, per exemple, clients, productes, o comandes.

Aquest és l'aspecte d'una taula que emmagatzema dades personals:

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-120.png)

### 8.2.2. Registres

Un **registre** (també anomenat **fila** o **tupla**) en una taula representa un únic element o instància de l'entitat que descriu la taula. Per exemple, en una taula de clients, un registre seria un client específic.

Seguint amb l'exemple anterior, cada fila seria un registre:

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-121.png)

### 8.2.3. Camps

Els **camps** (també anomenats **columnes** o **atributs**) són els components individuals d'informació en un registre. Cada camp té un tipus de dada específic que defineix la naturalesa de les dades que pot contenir, com a text, nombres, dates, etc.

Per exemple, un camp «Nom de Client» pot ser de tipus text, mentre que un camp «Data de Naixement» seria de tipus data.

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-122.png)

### 8.2.4. Tipus de dades

Els SGBD suporten diversos **tipus de dades** per adaptar-se a les necessitats específiques d'emmagatzemament d'informació. **El tipus de dada es defineix sobre cada camp -columna-**, quan estem creant la taula. Modificar el tipus de dada d'un camp una vegada que la taula està carregada de registres, és mala idea, ja que podrien produir-se inconsistències.

Aquests tipus de dades inclouen:

-   **Text**: per emmagatzemar cadenes de caràcters, com a noms, adreces o descripcions.
-   **Nombres**: existeixen diversos tipus numèrics, inclosos enters i decimals, per emmagatzemar nombres amb o sense decimals.
-   **Data i hora**: per emmagatzemar dates, hores o ambdues, permetent realitzar operacions com a càlculs d'intervals o comparacions de dates.
-   **Booleà**: per emmagatzemar valors verdader o fals, útil per definir camps amb només dos possibles valors, estats o condicions.
-   **Blob (_Binary Large Object_)**: per emmagatzemar dades binàries, com a imatges, arxius d'àudio o qualsevol altre tipus d'arxiu multimèdia.

_**Exercici 8.1 – Identificant entitats**_

Ara que ja tens coneixements bàsics sobre el més elemental de les bases de dades, has d'entrenar l'extracció d'informació del teu interès per construir una base de dades, a partir de l'enunciat d'un problema.

Per a cada un d'aquests supòsits, es demana que:

-   Identifiquis cada una de les taules que podria tenir una base de dades que gestionés aquest sistema d'informació, i els posis un nom representatiu.
-   Identifiquis cada un dels camps de cada taula i triïs el tipus de dada més apropiat per a ells.
-   Si en l'enunciat no apareix de forma explícita un camp que creguis que és necessari, pots afegir-lo pel teu compte.
-   Creïs la taula amb els seus corresponents camps i l'omplis amb almenys 5 registres cadascuna.

Aquests són els 5 supòsits sobre els quals has de fer tot l'anterior:

1.  **COOL SHOES**.

    Es desitja desenvolupar un sistema d'informació per gestionar les vendes, l'inventari i els clients d'una sabateria en línia. Aquest sistema haurà de permetre el registre dels productes disponibles, incloent informació sobre el model, la talla, el color, el preu i la quantitat en estoc. A més, haurà de gestionar les comandes realitzades pels clients, incloent dades del client, detalls de la comanda i estat de l'enviament.
2.  **CITIUS ALTIUS FORTIUS**. Un club esportiu necessita un sistema per administrar els seus socis, les activitats esportives que ofereix i les inscripcions a aquestes activitats. El sistema ha d'incloure informació sobre cada soci (nom, edat, contacte), les diferents activitats disponibles (nom de l'activitat, horari, entrenador assignat) i el registre d'inscripcions, indicant quin soci s'ha inscrit en quina activitat.
3.  **BEYOND LANGUAGE**. Per a una acadèmia d'anglès es requereix un sistema que gestioni tant els estudiants com els cursos i professors. Aquest sistema ha de permetre registrar informació sobre els estudiants (nom, nivell d'anglès, contacte), els cursos oferts (nom del curs, nivell, horari, professor) i les assignacions d'estudiants a cursos, incloent les qualificacions obtingudes.
4.  **GAS LOVERS**. Un concessionari de motos necessita un sistema per administrar les vendes, l'inventari de motos i els clients. El sistema haurà d'incloure informació detallada de cada moto (marca, model, any, preu, característiques tècniques), les dades dels clients (nom, adreça, contacte) i els registres de vendes realitzades, especificant la moto venuda, el client i la data de la venda.
5.  **FOOD** **ROCKET**. Un restaurant vol implementar un sistema per gestionar el seu menú, les reserves i les comandes a domicili. Aquest sistema ha de contenir informació sobre els plats del menú (nom del plat, ingredients, preu), les reserves realitzades pels clients (nom del client, nombre de comensals, data i hora de la reserva) i les comandes a domicili (detalls de la comanda, adreça de lliurament, estat de la comanda).

\[A l'aula tens un exemple resolt, perquè entenguis el que es demana\]

**Lliurament**: has de lliurar un **enllaç públic de Google Docs** abans de la data límit indicada a l'aula.

## 8.3. Claus i relacions.

En l'univers de les bases de dades relacionals, les claus i relacions ens permeten establir connexions lògiques entre les diferents dades emmagatzemades. Aquests conceptes són **fonamentals per assegurar la integritat de les dades, evitar duplicitats innecessàries i facilitar la recuperació eficient de la informació**.

### 8.3.1. Claus

Una **clau** és un atribut o conjunt d'atributs que serveix per identificar de manera única cada registre dins d'una taula. Les claus juguen un paper vital en el manteniment de la integritat de les dades i en la definició de les relacions entre taules.

Existeixen diversos tipus de claus, però les dues més importants són aquestes:

-   **Clau primària (_primary key_)**: un atribut o conjunt d'atributs que identifica de manera única cada registre en una taula. No hi pot haver dos registres en una taula amb la mateixa clau primària, i no pot ser nul·la.
-   **Clau forana (_foreign key_)**: un atribut en una taula que és la clau primària en una altra taula. Les claus foranes s'utilitzen per establir i fer complir una relació entre dues taules.

És obligatori definir una clau primària per a cada taula d'una base de dades.

Per exemple, si tenim una taula -com la que hem vist més amunt- d'alumnes, quin atribut seria clau primària?

Per respondre a aquesta pregunta hem de preguntar-nos: **quin atribut fa que cada alumne sigui diferent de tots els altres?** Si ho penses per un moment, arribaràs a la conclusió que el DNI és la dada que identifica unívocament a cada alumne, i en general, a cada persona.

Per tant, el camp DNI seria la clau primària de la taula ALUMNES.

Considerem ara aquestes dues taules, que formarien part d'una hipotètica base de dades anomenada **TALLER**.

En la nostra aplicació per gestionar un taller de cotxes, hi haurà diverses taules, però dues d'elles seran: **PROPIETARI** i **VEHICLE**:

**PROPIETARI**

| **DNI** | **Nom** | **Cognoms** | **Telèfon** |
| :------ | :------- | :----------- | :---------- |
| 45112558B | Juan   | Méndez Álvarez | 665000111   |
| 27000112Z | Alberto | García Castaño | 778552121   |
| 41445698K | Lucia  | López Toledo   | 615804142   |

**VEHICLE**

| **Matrícula** | **Marca** | **Model** | **Cilindrada** |
| :------------ | :------- | :------ | :----------- |
| 3399GHF       | Toyota | Corolla | 1.9          |
| 5641BCD       | Mercedes | CLA     | 1.6          |
| 9099KDF       | Nissan | Primera | 2.5          |

Com pots veure, la taula **PROPIETARI** té una clau primària -el **DNI**– que identifica de forma única a cada propietari. De la mateixa manera, la taula **VEHICLE** té una clau primària -la **Matrícula**– que identifica de manera única a cada vehicle.

Però les taules no estan relacionades, és a dir, no sabem qui és el propietari de cada vehicle, la qual cosa fa impossible gestionar els pagaments de les reparacions que se li facin a aquest vehicle.

És necessari, afegir algun camp a la taula **VEHICLE** que ens permeti relacionar cada vehicle amb el seu propietari.

**VEHICLE**

| **Matrícula** | **Marca** | **Model** | **Cilindrada** | **Propietari** |
| :------------ | :------- | :------ | :----------- | :------------- |
| 3399GHF       | Toyota | Corolla | 1.9          | 27000112Z      |
| 5641BCD       | Mercedes | CLA     | 1.6          | 27000112Z      |
| 9099KDF       | Nissan | Primera | 2.5          | 45112558B      |

Ara, sí que sabem que el Toyota i el Mercedes són d'Alberto, i el Nissan és de Juan. A aquest camp que hem afegit a la taula **VEHICLE** \-Propietari- és al qual anomenem **clau forana**, perquè ens permet relacionar cada fila de la taula **VEHICLE** amb una fila de la taula **PROPIETARI**.

Aquesta relació hem de deixar-la establerta dissenyant un **diagrama relacional de la base de dades**.

En l'exemple anterior, seria:

!(https://lopegonzalez.es/wp-content/uploads/2024/02/image-18.jpeg)

Quan dissenyem una base de dades és **completament imprescindible** definir tant les claus primàries de totes les taules, com les claus foranes que ens permetin relacionar unes taules amb altres.

_**Exercici resolt – YouTube DB**_

Tots sabem com funciona YouTube, però és un gegant que emmagatzema un munt de dades de tot el que ocorre, i no totes aquestes dades són evidents.

Centrem-nos en els més visibles: tenim uns usuaris que pugen vídeos, comenten i se subscriuen. A més volem portar el compte de les visualitzacions per país, per veure les tendències de cada zona geogràfica.

A
------------