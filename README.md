# API-PROJECT
### Olivia MESSINA & Nassriat YOUSSOUF
 Créer une BDD et la remplir des données venant d'une API 

# Table of Contents
  * [SUPERHEROS](#SUPERHEROS)
     - [Info API SUPERHEROS](#Info-API-SUPERHEROS)
     - [Dictionnaire des données SUPERHEROS](#Dictionnaire-des-données-SUPERHEROS)
  * [MARVEL](#MARVEL)
     - [Info API MARVEL](#Info-API-MARVEL)
     - [Dictionnaire des données MARVEL](#Dictionnaire-des-données-MARVEL)
  * [PAYS](#PAYS)
     - [Info API PAYS](#Info-API-PAYS)
     - [Dictionnaire des données PAYS](#Dictionnaire-des-données-PAYS)
  
  ## SUPERHEROS
  ![Capture](https://user-images.githubusercontent.com/74513460/103438065-0ff7bd00-4c2f-11eb-80ee-e2814fca8078.PNG)
  
  ### Info API SUPERHEROS
  Endpoint utilisé : **`http(s)://superheroapi.com/api/access-token/search/name`**
  
  **Étape 1** : récupérer l'_access-token_ en se connectant avec un compte FACEBEOOK 
  
  Pour cette API, il y a 2 manières d'obtenir les données des Superheros :
  + À partir de l'**id**
  + À partir du **nom**
  
  Pour récupérer un maximum de données, nous avons cherché à partir du nom : **`http(s)://superheroapi.com/api/access-token/search/a`**
  
  Nous avons fait **`search/a`** car logiquement, plusieurs Superheros ont la lettre **'a'** dans le prénom 
  
  ### Dictionnaire des données SUPERHEROS
  **Étape 2** : récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurés (un extrait) :
  
  ![JSON SUPERHEROS](https://user-images.githubusercontent.com/74513460/103439914-77b70380-4c41-11eb-97ea-bb0f8fb8bcb7.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![DIFFERENTES TABLES SUPERHEROS](https://user-images.githubusercontent.com/74513460/103440004-61f60e00-4c42-11eb-8fc0-08253a64f9d1.PNG)
  
  ---
  
   ## MARVEL
  ![PAGE DE GARDE](https://user-images.githubusercontent.com/74513460/103438125-b6dc5900-4c2f-11eb-90c2-972255a1aaa5.PNG)

   ### Info API MARVEL
   Endpoint utilisé : **`http(s)://gateway.marvel.com/`**
   
   **Étape 1** : récupérer la _public key_ & la _private key_ en se connectant avec un compte MARVEL 
   
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
  
  ### Dictionnaire des données MARVEL
  **Étape 2** : récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurés (un extrait) :
  
  ![JSON MARVEL](https://user-images.githubusercontent.com/74513460/103439922-82719880-4c41-11eb-86e6-60f7bf57327e.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![LES DIFFRERENTES TABLES MARVEL](https://user-images.githubusercontent.com/74513460/103439985-47bc3000-4c42-11eb-98a2-f440e7c916c2.PNG)
  
   

  ---
  
   ## PAYS
  ![PAGE DE GARDE1](https://user-images.githubusercontent.com/74513460/103438112-acba5a80-4c2f-11eb-9f9d-d9cbecfdab6f.PNG)
  
  ### Info API PAYS
  
  Endpoint utilisé : **`http(s)://restcountries.eu/rest/v2/all`**
   
  **Étape 1** : pas besoin de créer un compte ou avoir une _public key_
   
  Pour récupérer toutes les données, nous avons utilisé le Endpoint ci-dessus
  
  ### Dictionnaire des données PAYS
  **Étape 2** : récuperer les données sous forme JSON Object et création des différents dictionnaires 
  
  En transformant le code en _Python JSON Object_, nous obtenons des données structurés (un extrait) :
  
  ![JSON_PAYS](https://user-images.githubusercontent.com/74513460/103439918-7d144e00-4c41-11eb-9bec-5c7749220dab.PNG)
  
  À partir de cela, nous avons donc fait la liste des tables que nous allons créer sur SQL :
  
  ![CODE_DIFFERENTES_TABLES PAYS](https://user-images.githubusercontent.com/74513460/103439996-53a7f200-4c42-11eb-9159-345a6db26d6d.PNG)
  
  ---
