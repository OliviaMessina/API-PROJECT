# API-PROJECT
### Olivia MESSINA & Nassriat YOUSSOUF
 Créer une BDD et la remplir des données venant d'une API 

# Table of Contents
  * [SUPERHEROS](#SUPERHEROS)
     - [Info API SUPERHEROS](#Info-API-SUPERHEROS)
     - [Dictionnaire des données SUPERHEROS](#Dictionnaire-des-données-SUPERHEROS)
     - [Création des tables SUPERHEROS](#Création-des-tables-SUPERHEROS)
     - [Schéma de base de données SUPERHEROS](#Schéma-de-base-de-données-SUPERHEROS)
     - [Remplissage des tables SUPERHEROS](#Remplissage-des-tables-SUPERHEROS)
     - [Exemples de requêtes SQL SUPERHEROS](#Exemples-de-requêtes-SQL-SUPERHEROS)
  * [MARVEL](#MARVEL)
     - [Info API MARVEL](#Info-API-MARVEL)
     - [Dictionnaire des données MARVEL](#Dictionnaire-des-données-MARVEL)
     - [Création des tables MARVEL](#Création-des-tables-MARVEL)
     - [Schéma de base de données MARVEL](#Schéma-de-base-de-données-MARVEL)
     - [Remplissage des tables MARVEL](#Remplissage-des-tables-MARVEL)
     - [Exemples de requêtes SQL MARVEL](#Exemples-de-requêtes-SQL-MARVEL)
  * [PAYS](#PAYS)
     - [Info API PAYS](#Info-API-PAYS)
     - [Dictionnaire des données PAYS](#Dictionnaire-des-données-PAYS)
     - [Création des tables PAYS](#Création-des-tables-PAYS)
     - [Schéma de base de données PAYS](#Schéma-de-base-de-données-PAYS)
     - [Remplissage des tables PAYS](#Remplissage-des-tables-PAYS)
     - [Exemples de requêtes SQL PAYS](#Exemples-de-requêtes-SQL-PAYS)
  
  # SUPERHEROS
  ![Capture](https://user-images.githubusercontent.com/74513460/103438065-0ff7bd00-4c2f-11eb-80ee-e2814fca8078.PNG)
  
  ## Info API SUPERHEROS
  Endpoint utilisé : **`http(s)://superheroapi.com/api/access-token/search/name`**
  
  **Étape 1** : Récupérer l'_access-token_ en se connectant avec un compte FACEBEOOK 
  
  Pour cette API, il y a deux manières d'obtenir les données des Superheros :
  + À partir de l'**id**
  + À partir du **nom**
  
  Pour récupérer un maximum de données, nous avons cherché à partir du nom : **`http(s)://superheroapi.com/api/access-token/search/a`**
  
  Nous avons fait **`search/a`** car logiquement, plusieurs Superheros ont la lettre **'a'** dans leur prénom 
  
  ## Dictionnaire des données SUPERHEROS
  **Étape 2** : Récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurées (un extrait) :
  
  ![JSON SUPERHEROS](https://user-images.githubusercontent.com/74513460/103439914-77b70380-4c41-11eb-97ea-bb0f8fb8bcb7.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![DIFFERENTES TABLES SUPERHEROS](https://user-images.githubusercontent.com/74513460/103440004-61f60e00-4c42-11eb-8fc0-08253a64f9d1.PNG)
  
  ## Création des tables SUPERHEROS
  **Étape 3** : Création des différentes tables à partir de Python dans SQL
  
  Comme vu précédemment, nous avons au total sept tables dans la database **SUPERHEROS** (la database a été créée dans SQL SERVER avant de pouvoir l'utiliser).
  
  Nous allons nous baser sur une seule table **APPEARANCE** pour expliquer plus en détail.
  
  Tout d'abord, il faut connecter *Python* à *SQL SERVER* en utilisant la librairie **`pyodbc`**. 
  
  ``` python
  import pyodbc
  conn = pyodbc.connect('Driver={SQL Server};'
                      'Server=ServerName;'
                      'Database=SUPERHEROS;'
                      'Trusted_Connection=yes;') 
  ```
 
  Ensuite, il faut faire la requête permettant de créer la table **APPEARANCE** dans *SQL SERVER* contenant ses attributs
  
  ![CODE appearance](https://user-images.githubusercontent.com/74513460/103443256-a04cf680-4c5d-11eb-9464-bda81e38d530.PNG)
  
  Nous avons créé cette méthode pour toutes les tables.
  
  ## Schéma de base de données SUPERHEROS
  
  Après avoir créé toutes les tables, nous pouvons aller sur SQL SERVER afin de visualiser le schéma de données.
  
  ![SCHEMA BDD SUPERHEROS](https://user-images.githubusercontent.com/74513460/103443837-1142dd00-4c63-11eb-9a76-ce90dcf00a4d.PNG)
  
  ## Remplissage des tables SUPERHEROS
  **Étape 4** : Remplissage des tables à partir de Python et les visualiser sur SQL SERVER
  
  Après avoir rempli les tables à partir de Python, nous pouvons désormais les visualiser sur SQL SERVER.
  
  1) **PERSONNAGE**
   Nom de chaque personnage
  
  ![SQL PERSONNAGE](https://user-images.githubusercontent.com/74513460/103444129-e1490900-4c65-11eb-995d-05fe54863027.PNG)
  
  2) **APPEARANCE**
  Apparence du personnage
  
  ![SQL APPEARANCE](https://user-images.githubusercontent.com/74513460/103444124-db532800-4c65-11eb-8866-8e8e49c04f23.PNG)
  
  3) **POWERSTATS**
  
  Powerstats pour le caractère donné
  
  ![SQL POWERSTATS](https://user-images.githubusercontent.com/74513460/103444131-e73eea00-4c65-11eb-95d9-3576740a7a0e.PNG)
  
  4) **BIOGRAPHY**
  
  Biographie du personnage
  
  ![SQL BIOGRAPHY](https://user-images.githubusercontent.com/74513460/103444125-e017dc00-4c65-11eb-8854-f672764e0033.PNG)
  
  5) **CONNECTION**
  
  Les connexions du personnage
  
  ![SQL CONNECTION](https://user-images.githubusercontent.com/74513460/103444126-e0b07280-4c65-11eb-9cd3-6946db954bb7.PNG)
  
  6) **WORK**
  
  Travail/occupation du personnage
  
  ![SQL WORK](https://user-images.githubusercontent.com/74513460/103444132-e7d78080-4c65-11eb-9bea-8e8707c9d088.PNG)
  
  7) **IMAGE**
  
  image du personnage, s'il existe
  
  ![SQL IMAGE](https://user-images.githubusercontent.com/74513460/103444127-e0b07280-4c65-11eb-8d7e-e25bc6150770.PNG)
  
   ## Exemples de requêtes SQL SUPERHEROS
  
  Pour tester notre base de données, on a effectué des requêtes SQL à partir des tables de la database
  
  1) **Tous les Superheros et leur nom complet qui sont de race humaine**
  
  ![REQUETE tous les SH FN ID - de race humaine](https://user-images.githubusercontent.com/74513460/103446944-62fc5f00-4c85-11eb-8598-64aab42afa8c.PNG)
  
  2) **Tous les Superheros qui ont une intelligence comprise entre 60 et 70**
  
![REQUETE tous les SH qui ont une intelligence comprise entre 60 et 70](https://user-images.githubusercontent.com/74513460/103446945-6394f580-4c85-11eb-92c0-1bcb3236a6a6.PNG)

  3) **Top 100 des Superheros par ordre alphabétique ayant le maximum de combat**
  
![Top 100 des superheros par ordre alphabetique et le maximu de combat effectué](https://user-images.githubusercontent.com/74513460/103446962-917a3a00-4c85-11eb-9204-9f22e844bc21.PNG)

 4) **Nom des Superheros qui n'ont pas de cheveux "Hair Color= No Hair"**
  
  ![Nom des SH qui n'ont pas de cheveux No_Hair](https://user-images.githubusercontent.com/74513460/103446965-92ab6700-4c85-11eb-8616-fba7b6e025c4.PNG)
  
  ---
  
   # MARVEL
  ![PAGE DE GARDE](https://user-images.githubusercontent.com/74513460/103438125-b6dc5900-4c2f-11eb-90c2-972255a1aaa5.PNG)

   ## Info API MARVEL
   Endpoint utilisé : **`http(s)://gateway.marvel.com/`**
   
   **Étape 1** : Récupérer la _public key_ & la _private key_ en se connectant avec un compte MARVEL 
   
   Après avoir créer le compte, il faut utiliser ces deux clés (_public key_ & _private key_) pour obtenir les deux autres paramètres obligatoires :
   
  + **ts** : correspond au premier chiffre de la _public key_
  + **hast** : correspond au codage md5( _ts_+ _public key_ + _private key_ )
   
  Cela va donc nous donner pour les paramètres : **```params={"apikey":"_public key_","ts": "_ts_","hash": "_hash_"}```**
  
  Pour cette API, il y a plusieurs manières d'obtenir les données des Superheros :
  + À partir de **characters**
  + À partir de **comics**
  + À partir de **creators**
  + À partir de **events**
  + À partir de **stories**
  
  Pour récupérer les données, nous avons utilisé : **`http(s)://gateway.marvel.com/v1/public/characters`**
  
  Il faut savoir que le nombre de données est limité à 100 
  
  ## Dictionnaire des données MARVEL
  **Étape 2** : Récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurées (un extrait) :
  
  ![JSON MARVEL](https://user-images.githubusercontent.com/74513460/103439922-82719880-4c41-11eb-86e6-60f7bf57327e.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![LES DIFFRERENTES TABLES MARVEL](https://user-images.githubusercontent.com/74513460/103439985-47bc3000-4c42-11eb-98a2-f440e7c916c2.PNG)
 
  ## Création des tables MARVEL
  **Étape 3** : Création des différentes tables à partir de Python dans SQL
  
  Comme vu précédemment, nous avons au total douze tables dans la database **MARVEL** (la database a été créée dans SQL SERVER avant de pouvoir l'utiliser).
  
  Nous allons nous baser sur une seule table **CHARACTERS** pour expliquer plus en détail.
  
  Tout d'abord, il faut connecter *Python* à *SQL SERVER* en utilisant la librairie **`pyodbc`**. 
  
  ``` python
  import pyodbc
  conn = pyodbc.connect('Driver={SQL Server};'
                      'Server=ServerName;'
                      'Database=MARVEL;'
                      'Trusted_Connection=yes;') 
  ```
 
  Ensuite, il faut faire la requête permettant de créer la table **CHARACTERS** dans *SQL SERVER* contenant ses attributs
  
  ![CODE characters](https://user-images.githubusercontent.com/74513460/103443480-ee62f980-4c5f-11eb-9574-35802861820b.PNG)
  
  Nous avons créé cette méthode pour toutes les tables.
   
  ## Schéma de base de données MARVEL
  
  Après avoir créé toutes les tables, nous pouvons aller sur SQL SERVER afin de visualiser le schéma de données.
  
  ![SCHEMA BDD MARVEL](https://user-images.githubusercontent.com/74513460/103443826-01c39400-4c63-11eb-9a24-6b1007924a50.PNG)
  
   ## Remplissage des tables MARVEL
  **Étape 4** : Remplissage des tables à partir de Python et les visualiser sur SQL SERVER
  
  Après avoir rempli les tables à partir de Python, nous pouvons désormais les visualiser sur SQL SERVER.
  
  1) **CHARACTERS**
  
  Le nom du personnage
  
  ![SQL CHARACTERS](https://user-images.githubusercontent.com/74513460/103444247-2d487d80-4c67-11eb-820d-35edc9e1a38d.PNG)
  
  2) **COMICS**
  
  Une liste de ressources contenant des bandes dessinées mettant en vedette ce personnage
  
  ![SQL COMICS](https://user-images.githubusercontent.com/74513460/103444248-2de11400-4c67-11eb-8b69-c41688d2fbf4.PNG)
  
  3) **SERIES**
  
  Une liste de ressources de séries dans lesquelles ce personnage apparaît
  
  ![SQL SERIES](https://user-images.githubusercontent.com/74513460/103444256-30436e00-4c67-11eb-82dd-bbaa8972fe8c.PNG)
  
  4) **STORIES**
  
  Une liste de ressources d'histoires dans lesquelles ce personnage apparaît
  
  ![SQL STORIES](https://user-images.githubusercontent.com/74513460/103444258-30dc0480-4c67-11eb-8bf8-2f9003aa5a17.PNG)
  
  5) **EVENTS**
  
  Une liste de ressources d'événements dans lesquels ce personnage apparaît
  
  ![SQL EVENTS](https://user-images.githubusercontent.com/74513460/103444251-2e79aa80-4c67-11eb-9280-519ebaf48062.PNG)

  6) **DESCRIPTION**
  
  Une courte biographie ou une description du personnage
  
  ![SQL DESCRIPTION](https://user-images.githubusercontent.com/74513460/103444250-2e79aa80-4c67-11eb-83a5-dc579cbe4c2b.PNG)
  
  7) **URL**
  
  Un ensemble d'URL de site Web public pour la ressource
  
  ![SQL URL](https://user-images.githubusercontent.com/74513460/103444261-31749b00-4c67-11eb-8a3f-6ef8c902eb6e.PNG)

  8) **THUMBNAIL**
  
  L'image représentative de ce personnage
  
  ![SQL THUMBNAIL](https://user-images.githubusercontent.com/74513460/103444260-30dc0480-4c67-11eb-8dfe-2d28cdd24df4.PNG)
 
 9) **ITEMS COMICS**
 
 Liste de ressources de bandes déssinées liées au personnage
 
  ![SQL ITEMS COMICS](https://user-images.githubusercontent.com/74513460/103444252-2f124100-4c67-11eb-9b86-b8014f137548.PNG)
  
  10) **ITEMS EVENTS**
  
  Liste de ressources d'évènement liées au personnage
  
  ![SQL ITEMS EVENTS](https://user-images.githubusercontent.com/74513460/103444253-2faad780-4c67-11eb-9657-3d4c461fbb1b.PNG)

  11) **ITEMS SERIES**
  
  Liste de ressources de série liées au personnage
  
  ![SQL ITEMS SERIES](https://user-images.githubusercontent.com/74513460/103444254-2faad780-4c67-11eb-8df5-09ac936d9ddd.PNG)

  12) **ITEMS STORIES**
  
  Liste de ressources d'histoires liées au personnage
  
  ![SQL ITEMS STORIES](https://user-images.githubusercontent.com/74513460/103444255-30436e00-4c67-11eb-8ae5-c4bf247ca1a4.PNG)

   ## Exemples de requêtes SQL MARVEL
  
  Pour tester notre base de données, on a effectué des requêtes SQL à partir des tables de la database
  
  1) **Les Superheros qui n'ont pas de description**
  
  ![les superheros qui ont des description est egal à null](https://user-images.githubusercontent.com/74513460/103446966-92ab6700-4c85-11eb-8057-a247cce5d633.PNG)

  2) **Superheros ayant un nombre de BD dont le nombre de séries est supérieur à la moyenne**
  
  ![Superheros ayant sortie une BD dont le nombre de serie est superieur à la moyenne](https://user-images.githubusercontent.com/74513460/103446964-9212d080-4c85-11eb-8157-28fc7f5c3807.PNG)

 3) **Superheros qui ont une extension JPG et dont le nombre total d'articles disponibles est égal à 0**
 
 ![Superheros qui ont des vignettes JGN (ou JPG) mais qui n'ont pas de stories available](https://user-images.githubusercontent.com/74513460/103446963-9212d080-4c85-11eb-945c-2d75e490c04b.PNG)

  ---
  
   # PAYS
  ![PAGE DE GARDE1](https://user-images.githubusercontent.com/74513460/103438112-acba5a80-4c2f-11eb-9f9d-d9cbecfdab6f.PNG)
  
  ## Info API PAYS
  
  Endpoint utilisé : **`http(s)://restcountries.eu/rest/v2/all`**
   
  **Étape 1** : Pas besoin de créer un compte ou avoir une _public key_
   
  Pour récupérer toutes les données, nous avons utilisé le Endpoint ci-dessus
  
  ## Dictionnaire des données PAYS
  **Étape 2** : Récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurées (un extrait) :
  
  ![JSON_PAYS](https://user-images.githubusercontent.com/74513460/103439918-7d144e00-4c41-11eb-9bec-5c7749220dab.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![CODE_DIFFERENTES_TABLES PAYS](https://user-images.githubusercontent.com/74513460/103439996-53a7f200-4c42-11eb-9159-345a6db26d6d.PNG)
  
   ## Création des tables PAYS
  **Étape 3** : Création des différentes tables à partir de Python dans SQL
  
  Comme vu précédemment, nous avons au total huit tables dans la database **PAYS** (la database a été créée dans SQL SERVER avant de pouvoir l'utiliser).
  
  Nous allons nous baser sur une seule table **GEOGRAPHY** pour expliquer plus en détail.
  
  Tout d'abord, il faut connecter *Python* à *SQL SERVER* en utilisant la librairie **`pyodbc`**. 
  
  ``` python
  import pyodbc
  conn = pyodbc.connect('Driver={SQL Server};'
                      'Server=ServerName;'
                      'Database=PAYS;'
                      'Trusted_Connection=yes;') 
  ```
 
  Ensuite, il faut faire la requête permettant de créer la table **GEOGRAPHY** dans *SQL SERVER* contenant ses attributs
  
  ![CODE geography](https://user-images.githubusercontent.com/74513460/103446799-f2087780-4c83-11eb-9bdb-059892d7943c.PNG)

  
  Nous avons créé cette méthode pour toutes les tables.
  
  ## Schéma de base de données PAYS
  
  Après avoir créé toutes les tables, nous pouvons aller sur SQL SERVER afin de visualiser le schéma de données.
  
  ![SCHEMA_BDD PAYS](https://user-images.githubusercontent.com/74513460/103443820-f40e0e80-4c62-11eb-9787-404152fe05b1.PNG)
  
   ## Remplissage des tables PAYS
  **Étape 4** : Remplissage des tables à partir de Python et les visualiser sur SQL SERVER
  
  Après avoir rempli les tables à partir de Python, nous pouvons désormais les visualiser sur SQL SERVER.
  
  1) **PAYS**
  
  ![SQL_PAYS](https://user-images.githubusercontent.com/74513460/103444506-16a32600-4c69-11eb-931e-ca833ba8938f.PNG)

  2) **GEOGRAPHY**
  
  ![SQL_GEOGRAPHY](https://user-images.githubusercontent.com/74513460/103444502-1571f900-4c69-11eb-957c-5a5a1b1724d1.PNG)

  3) **REGIONAL BLOCS**
  
  ![SQL_REGIONAL_BLOCS](https://user-images.githubusercontent.com/74513460/103444507-16a32600-4c69-11eb-9114-fa1ac2dbf3ec.PNG)

  4) **ORIGIN**
  
  ![SQL_ORIGIN](https://user-images.githubusercontent.com/74513460/103444505-160a8f80-4c69-11eb-83d3-aa2f79785457.PNG)

  5) **SPECIAL CODES**
  
  ![SQL_SPECIAL_CODES](https://user-images.githubusercontent.com/74513460/103444508-173bbc80-4c69-11eb-955c-84601eaff968.PNG)

  6) **LANGUAGES**
  
  ![SQL_LANGUAGES](https://user-images.githubusercontent.com/74513460/103444504-160a8f80-4c69-11eb-9588-11a6e639f4b9.PNG)

  7) **CURRENCIES**
  
  ![SQL_CURRENCIES](https://user-images.githubusercontent.com/74513460/103444501-14d96280-4c69-11eb-87f0-8be8327d1878.PNG)

  8) **TRANSLATION**
  
  ![SQL_TRANSLATION](https://user-images.githubusercontent.com/74513460/103444509-173bbc80-4c69-11eb-89ef-962baad1294a.PNG)
  
  ## Exemples de requêtes SQL PAYS
  
  Pour tester notre base de données, on a effectué des requêtes SQL à partir des tables de la database
  
  1) **Combien de Pays ont pour acronym "EU" ?**
  
  ![REQUETE cb de pays ont pour acronym EU](https://user-images.githubusercontent.com/74513460/103446953-6d1e5d80-4c85-11eb-87e4-7a552b364bd3.PNG)
  
  2) **Quels sont les pays qui ne sont pas de la Subregion "Southern Asia" ?**
  
![REQUETE pays qui ne sont pas dans Southern Asia](https://user-images.githubusercontent.com/74513460/103446954-6db6f400-4c85-11eb-94e0-e5b15aba2f87.PNG)

 3) **Quelle est le nombre de la population totale en Afrique ?**
 
 ![REQUETE Population totale in Africa](https://user-images.githubusercontent.com/74513460/103446955-6e4f8a80-4c85-11eb-8cdd-81a28bcd93ab.PNG)
 
  ---
