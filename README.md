# API-PROJECT
### Olivia MESSINA & Nassriat YOUSSOUF
 Créer une BDD et la remplir des données venant d'une API 

# Table of Contents
  * [SUPERHEROS](#SUPERHEROS)
     - [Info API](#Info-API)
  * [MARVEL](#MARVEL)
     - [Info API](#Info-API)
  * [PAYS](#PAYS)
  
  
  ## SUPERHEROS
  ![Capture](https://user-images.githubusercontent.com/74513460/103438065-0ff7bd00-4c2f-11eb-80ee-e2814fca8078.PNG)
  
  ### Info API
  Endpoint utilisé : **https://superheroapi.com/api/access-token/search/name**
  
  **Étape 1** : récupérer l'_access-token_ en se connectant avec un compte FACEBEOOK. 
  
  Pour cette API, il y a 2 manières d'obtenir les données des Superheros :
  + À partir de l'**id**
  + À partir du **nom**
  
  Pour récupérer un maximum de données, nous avons cherché à partir du nom : **https://superheroapi.com/api/access-token/search/a**.
  
  Nous avons fait **'search/a'** car logiquement, plusieurs Superheros ont la lettre 'a' dans le prénom. 
  
  ---
  
   ## MARVEL
  ![PAGE DE GARDE](https://user-images.githubusercontent.com/74513460/103438125-b6dc5900-4c2f-11eb-90c2-972255a1aaa5.PNG)

   ### Info API
   Endpoint utilisé : **http(s)://gateway.marvel.com/**
   
   **Étape 1** : récupérer la _public key_ & la _private key_ en se connectant avec un compte MARVEL. 
   
   Après avoir créer le compte, il faut utiliser ces deux clés (_public key_ & _private key_) pour obtenir les deux autres paramètres obligatoires :
   
  + **ts** : correspond au premier chiffre de la _public key_
  + **hast** : correspond au codage md5( _ts_+ _public key_ + _private key_ )
   
  Cela va donc nous donner pour les paramètres : '''params={"apikey":"_public key_","ts": "_ts_","hash": "_hash_"}'''
  
  Pour cette API, il y a plusieurs manières d'obtenir les données des Superheros :
  + À partir de '**characters**
  + À partir de **comics**
  + À partir de '**creators**
  + À partir de **events**
  + À partir de **stories**
  
  Pour récupérer les données, nous avons utilisé : **http://gateway.marvel.com/v1/public/characters**.
  
  Il faut savoir que le nombre de données est limité à 100. 
   

  ---
  
   ## PAYS
  ![PAGE DE GARDE1](https://user-images.githubusercontent.com/74513460/103438112-acba5a80-4c2f-11eb-9f9d-d9cbecfdab6f.PNG)
  ---
