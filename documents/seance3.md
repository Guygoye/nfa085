# 1. Web statique et web dynamique
##  Expliquez la différence entre les deux.
   
   Un site web statique est un site dont le contenu est figé. Chaque page affichées correspond à un fichier HTML. Un site web dynamique peu comprendre du HTML, du CSS et du JavaScript. Tout le code la page se trouve dans le fichier HTML. Peut importe l'utilisateur, ce sera toujours la même page qui sera générée. La modification du site web se fait directement sur la page web, l'ajout ou le retrait d'élèments oblige à modifier toutes les pages où cet élèment apparaît.
   
   Un site web dynamique est généré en fonction des paramètres choisis comme la langue, la région géographique ou l'heure de la journée ou encore d'autres paramètes défini par le webmaster. La page générée n'est donc pas la même pour tous les utilisateurs et utilise des technologie comme PHP, HTML, CSS, JSP, ASP.
   
## Comment identifier qu’une ressource Web est statique ou dynamique ?

   On peut l'identifer en affichant le code source de la page, si la page contient le code et ne renvoie pas à des scripts tel que PHP par exemple on dire qu'elle est statique. Inversement si le code source de la page est quasiment vide et ne renvoie qu'à des liens vers des scripts on peut se dire que la page est dynamique.

## Les sites suivants sont t-ils statiques ou dynamiques ?

  http://www.rleonardi.com/interactive-resume/ est un site statique on peut observer dans la page HTML qu'il n'y pas de balise php, ajs, jsp ou d'autres qui mettent en œuvre des scripts. Le contenu de la page d'index fait appel à une page HTML pour chaque élément affichés. Ils ne sont pas générés à la volée lors de l'ouverture de la page.
 
 https://www.je-change-de-metier.com/ est également un site statique on peut observer sur la page d'index tout le code HTML, nous ne retrouvons pas non plus de balises php, ajs, jsp. Le contenu chargé par chaque utilisateur est identique. Il existe une page HTML qui est appellée pour chaque contenu demandé sur la page d'index.

# 2. Langages

## Front-end
   
   Le développement front-end c'est la couche regroupant le logiciel et le hardware faisant partie de l'interface utilisateur. Il consiste à créer des applications, des logiciels ou des sites web dont le rendu s’effectue côté client.Le développeur front-end crée des logiciels ou des sites web sans aucun développement back-end. Un site web ainsi créé est un site statique. Il peut s’agir par exemple d’un site web pour un restaurant ou un salon de coiffure.
   
   Les langages Front-end sont par exemple: HTML, CSS ou JavaScript
   
   [source data scientest](https://datascientest.com/front-end-vs-back-end)
   
## Back-end

   Le back-end désigne les parties du codes ou logicielles qui ne sont pas accessibles par l'utilisateurs. Cela concerne des logiciels dont le rendu s'effectue côté serveur.
   Les sites web dynamique sont des application back-end.
   
   Les langages Back-end sont par exemple: PHP, Node.js, le Python, le Java...
   
   [source data scientest](https://datascientest.com/front-end-vs-back-end)
   
# 3. Technologies

## Ajax

   Asynchronous Javascript And Xml est la combinaison des technologies HTML/CSS, Javascript/DOM, XML et les requêtes HTTP, il permet d'actualiser les données en cours de navigation sans avoir à recharger la page du navigateur. Par exmple l'affichage de la suggestion de mots dans une barre de recherche lorque l'utilisateur est en train de taper.
   
   ## Single-page application
   
   Single-page application est une application monopage qui évite d'avoir à recharger l'ensemble d'une page web à achque action utilisateur. Ceci afin de rendre plus fluide la navigation.Des exemples connus sont des sites comme FaceBook, Google Maps, Gmail etc.
   
## API

   Application Programming Interface est un ensemble de fonctionnalités et de règles existant dans un logiciel permettant d'intéragir avec celui-ci de manière automatisée.L'API peut être vue comme un contrat simple passé entre le logiciel qui la propose et d'autres entités, telles que des logiciels ou matériels tiers.
   Par exemple: L'API getUserMedia peut être utilisée pour capturer l'audio et la vidéo de la webcam d'un utilisateur.
   
   [Source Mozilla](https://developer.mozilla.org/fr/docs/Glossary/API)
   
   
# 4. Librairie et framework

   Le framework permet de donner une structure de base à programme sans avoir à le réecrire complétement. Il offre une base de programme à paramètrer selon ses besoins que l'ont peut intégrer dans une architecture logicielle. C'est un cadre applicatif qui donne une structure, un cadre à une application.
   Pour python nous avons les framework Jango et Flask qui sont sur la partie back-end, pour Javascript Angular sur la partie Front-end.
   
   La librairie offre des fonctionnalités souvent décorrélées les unes des autres. C'est une collection de routines (ou de méthodes), pouvant être appelées par le code d’un développeur pour exécuter des actions spécifiques. Un framework peut contenir des bibliothèques. 
   Jquery, Bootstrap et Tailwin sont des bibliothèques font-end. 
   
## 5. Architecture

   Une architecture 3 tiers est une architecture en web qui s'appuie sur 3 couches logicielles:
   - présentation des données, correspondant à l'affichage, la restitution sur le poste de travail, le dialogue avec l'utilisateur
   - traitement des données, correspondant à la mise en œuvre de l'ensemble des règles de gestion et de la logique applicative 
   - accés aux données, correspondant aux données qui sont destinées à être conservées sur la durée, voire de manière définitive

   Les 3 couches communiquent entre elles, au travers d'un model d'échanges, chacune d'entre elles proposent un model de service et ne peut accéder qu'àl couche  qui lui est immédiatement inférieure. Donc chaque couche met à disposition ses services à la couche supérieur.

   ![exemple de schéma d'architecture à 3 couches, source Wikipédia](https://user-images.githubusercontent.com/58706637/225900714-d156aa57-9340-4759-9cb0-38cdf1256fca.png)

# 6. Interrogation d’API Web- lecture

   **API dadjokes**
   
   ```
   curl https://api.api-ninjas.com/v1/dadjokes?limit=3 -H "X-Api-Key: FPshQKwI3BFpU45yW641IQ==8FwDddgiAo3fGZsR"
[{"joke": "What do you call someone who tells dad jokes but isn't a dad? A faux pa."}, {"joke": "I don't trust stairs because they're always up to something."}, {"joke": "Five out of four people admit they\u2019re bad at fractions."}]
   
   ```
   
   **API textsimilary**
   
   ```
   curl -X POST https://api.api-ninjas.com/v1/textsimilarity -H "X-api-Key: FPshQKwI3BFpU45yW641IQ==8FwDddgiAo3fGZsR" -H "Content-Type: application/json" -d "{\"text_1\": \"Nous le savons, et pas seulement de Marseille\", \"text_2\": \"Le savon de Marseille\"}"
   ```
   Le score est de 0.7752714157104492
   
   **API urllookup**
   
   - Le Parisien
   
   ```
   curl -X GET https://api.api-ninjas.com/v1/urllookup?url=www.leparisien.fr  -H "X-Api-Key: FPshQKwI3BFpU45yW641IQ==8FwDddgiAo3fGZsR"  {"is_valid": true, "country": "United States", "country_code": "US", "region_code": "WA", "region": "Washington", "city": "Seattle", "zip": "98160", "lat": 47.6034, "lon": -122.3414, "timezone": "America/Los_Angeles", "isp": "Akamai International, BV", "url": "www.leparisien.fr"}
   ```
   L'ISP est "Akamai International, BV"
   
   La localisation est aux Etats-Unis dans l'Etat de Washington à Seattle
   
   - Le Bon Coin

   ```
   curl -X GET https://api.api-ninjas.com/v1/urllookup?url=www.leboncoin.fr -H "X-Api-Key: FPshQKwI3BFpU45yW641IQ==8FwDddgiAo3fGZsR" 
{"is_valid": true, "country": "United States", "country_code": "US", "region_code": "OR", "region": "Oregon", "city": "Portland", "zip": "97207", "lat": 45.5051, "lon": -122.675, "timezone": "America/Los_Angeles", "isp": "Amazon Technologies Inc.", "url": "www.leboncoin.fr"}  
   ```
   L'ISP est "Amazon Technologies Inc."
   
   La localisation est au USA dans l'Oregon dans la ville de Portland
   
   - Cdiscount

   ```
   curl -X GET https://api.api-ninjas.com/v1/urllookup?url=www.cdiscount.fr -H "X-Api-Key: FPshQKwI3BFpU45yW641IQ==8FwDddgiAo3fGZsR" ~
{"is_valid": true, "country": "United States", "country_code": "US", "region_code": "VA", "region": "Virginia", "city": "Sterling", "zip": "20166", "lat": 39.0297, "lon": -77.4088, "timezone": "America/New_York", "isp": "NeuStar, Inc.", "url": "www.cdiscount.fr"}
   ```
   L'ISP est "NeuStar, Inc."
   
   La localisation est au USA en Virginie dans la ville de Sterling
   
   # 7.  Interrogation d’API Web – opérations multiples
   
   - Token :  
   ```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTUsInVzZXJuYW1lIjoia21pbmNoZWxsZSIsImVtYWlsIjoia21pbmNoZWxsZUBxcS5jb20iLCJmaXJzdE5hbWUiOiJKZWFubmUiLCJsYXN0TmFtZSI6IkhhbHZvcnNvbiIsImdlbmRlciI6ImZlbWFsZSIsImltYWdlIjoiaHR0cHM6Ly9yb2JvaGFzaC5vcmcvYXV0cXVpYXV0LnBuZyIsImlhdCI6MTY3OTIyNDU4NiwiZXhwIjoxNjc5MjI4MTg2fQ.gBE469GbBzeZwsbBQ77jp48hjG_JTWlQkET-IeWLmBM
   ```

   - Lister les produits du caddie de l'utilisateur ID 15
   
   ```
   curl -X GET https://dummyjson.com/carts/user/15 -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTUsInVzZXJuYW1lIjoia21pbmNoZWxsZSIsImVtYWlsIjoia21pbmNoZWxsZUBxcS5jb20iLCJmaXJzdE5hbWUiOiJKZWFubmUiLCJsYXN0TmFtZSI6IkhhbHZvcnNvbiIsImdlbmRlciI6ImZlbWFsZSIsImltYWdlIjoiaHR0cHM6Ly9yb2JvaGFzaC5vcmcvYXV0cXVpYXV0LnBuZyIsImlhdCI6MTY3OTIyNDU4NiwiZXhwIjoxNjc5MjI4MTg2fQ.gBE469GbBzeZwsbBQ77jp48hjG_JTWlQkET-IeWLmBM" 
   
   {
    "carts": [{
        "id": 16,
        "products": [{
            "id": 3,
            "title": "Samsung Universe 9",
            "price": 1249,
            "quantity": 3,
            "total": 3747,
            "discountPercentage": 15.46,
            "discountedPrice": 3168
        }, {
            "id": 50,
            "title": "Women Shoes",
            "price": 36,
            "quantity": 3,
            "total": 108,
            "discountPercentage": 16.87,
            "discountedPrice": 90
        }, {
            "id": 67,
            "title": "Fashion Magnetic Wrist Watch",
            "price": 60,
            "quantity": 2,
            "total": 120,
            "discountPercentage": 16.69,
            "discountedPrice": 100
        }, {
            "id": 86,
            "title": "Bluetooth Aux",
            "price": 25,
            "quantity": 1,
            "total": 25,
            "discountPercentage": 10.56,
            "discountedPrice": 22
        }, {
            "id": 12,
            "title": "Brown Perfume",
            "price": 40,
            "quantity": 1,
            "total": 40,
            "discountPercentage": 15.66,
            "discountedPrice": 34
        }],
        "total": 4040,
        "discountedTotal": 3414,
        "userId": 15,
        "totalProducts": 5,
        "totalQuantity": 10
    }],
    "total": 1,
    "skip": 0,
    "limit": 1
}

   ```
   - Afficher un produit

   ```
   https://dummyjson.com/products/50
   
   {
    "id": 50,
    "title": "Women Shoes",
    "description": "2020 New Arrivals Genuine Leather Fashion Trend Platform Summer Women Shoes",
    "price": 36,
    "discountPercentage": 16.87,
    "rating": 4.33,
    "stock": 46,
    "brand": "Arrivals Genuine",
    "category": "womens-shoes",
    "thumbnail": "https://i.dummyjson.com/data/products/50/thumbnail.jpg",
    "images": ["https://i.dummyjson.com/data/products/50/1.jpeg", "https://i.dummyjson.com/data/products/50/2.jpg", "https://i.dummyjson.com/data/products/50/3.jpg"]
}

   ```
   
   - Ajouter un produit

  ```
  curl -X POST https://dummyjson.com/products/add -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTUsInVzZXJuYW1lIjoia21pbmNoZWxsZSIsImVtYWlsIjoia21pbmNoZWxsZUBxcS5jb20iLCJmaXJzdE5hbWUiOiJKZWFubmUiLCJsYXN0TmFtZSI6IkhhbHZvcnNvbiIsImdlbmRlciI6ImZlbWFsZSIsImltYWdlIjoiaHR0cHM6Ly9yb2JvaGFzaC5vcmcvYXV0cXVpYXV0LnBuZyIsImlhdCI6MTY3OTIyNDU4NiwiZXhwIjoxNjc5MjI4MTg2fQ.gBE469GbBzeZwsbBQ77jp48hjG_JTWlQkET-IeWLmBM" -H "Content-Type: application/json" --data-binary @- <<DATA
{    "title": "produit ajouté NFA085"
  
  }
DATA

{
    "id": 101,
    "title": "produit ajouté NFA085"
}
   ```
   - Supprimer un produit

   ```
   curl -X DELETE https://dummyjson.com/products/2 -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTUsInVzZXJuYW1lIjoia21pbmNoZWxsZSIsImVtYWlsIjoia21pbmNoZWxsZUBxcS5jb20iLCJmaXJzdE5hbWUiOiJKZWFubmUiLCJsYXN0TmFtZSI6IkhhbHZvcnNvbiIsImdlbmRlciI6ImZlbWFsZSIsImltYWdlIjoiaHR0cHM6Ly9yb2JvaGFzaC5vcmcvYXV0cXVpYXV0LnBuZyIsImlhdCI6MTY3OTIyNDU4NiwiZXhwIjoxNjc5MjI4MTg2fQ.gBE469GbBzeZwsbBQ77jp48hjG_JTWlQkET-IeWLmBM" 

   
   {
    "id": 2,
    "title": "iPhone X",
    "description": "SIM-Free, Model A19211 6.5-inch Super Retina HD display with OLED technology A12 Bionic chip with ...",
    "price": 899,
    "discountPercentage": 17.94,
    "rating": 4.44,
    "stock": 34,
    "brand": "Apple",
    "category": "smartphones",
    "thumbnail": "https://i.dummyjson.com/data/products/2/thumbnail.jpg",
    "images": ["https://i.dummyjson.com/data/products/2/1.jpg", "https://i.dummyjson.com/data/products/2/2.jpg", "https://i.dummyjson.com/data/products/2/3.jpg", "https://i.dummyjson.com/data/products/2/thumbnail.jpg"],
    "isDeleted": true,
    "deletedOn": "2023-03-19T19:38:19.909Z"
}
   ```
   - Modifier un produit

   ```
   curl -X PUT https://dummyjson.com/products/2 -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTUsInVzZXJuYW1lIjoia21pbmNoZWxsZSIsImVtYWlsIjoia21pbmNoZWxsZUBxcS5jb20iLCJmaXJzdE5hbWUiOiJKZWFubmUiLCJsYXN0TmFtZSI6IkhhbHZvcnNvbiIsImdlbmRlciI6ImZlbWFsZSIsImltYWdlIjoiaHR0cHM6Ly9yb2JvaGFzaC5vcmcvYXV0cXVpYXV0LnBuZyIsImlhdCI6MTY3OTIyNDU4NiwiZXhwIjoxNjc5MjI4MTg2fQ.gBE469GbBzeZwsbBQ77jp48hjG_JTWlQkET-IeWLmBM" -H "Content-Type: application/json" -d "{ \"title\": \"Produit NFA085\"}"
   
   {
    "id": 2,
    "title": "Produit NFA085",
    "price": 899,
    "stock": 34,
    "rating": 4.44,
    "images": ["https://i.dummyjson.com/data/products/2/1.jpg", "https://i.dummyjson.com/data/products/2/2.jpg", "https://i.dummyjson.com/data/products/2/3.jpg", "https://i.dummyjson.com/data/products/2/thumbnail.jpg"],
    "thumbnail": "https://i.dummyjson.com/data/products/2/thumbnail.jpg",
    "description": "SIM-Free, Model A19211 6.5-inch Super Retina HD display with OLED technology A12 Bionic chip with ...",
    "brand": "Apple",
    "category": "smartphones"
}

   ```
   
