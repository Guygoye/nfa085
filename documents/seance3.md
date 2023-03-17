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
