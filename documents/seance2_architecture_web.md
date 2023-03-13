# 1. **Méthodes GET et POST**

   
   La requête GET permet de demander au serveur d'nevoyer des informations à afficher dans le navigateur. Cette requête est affichée en clair dans l'URL par exemple avec un moteur de recherche elle peut être sous la forme `search?`
   La requête POST permet d'envoyer des informations au serveur web, elle n'est pas visible dans l'URL et son utilisation la plus courante est pour des formulaires.
   Par exemple sur le site de Framasoft lors de la création d'un Framaste à l'URL: [](https://framadate.org/create_date_poll.php) nous povons observer grâce à la console de débugage de Firefox que la méthode POST est utilisée pour créer le formulaire sur le serveur. 
    
   Elle envoie la requête suivante:

   ```
   name=Toto
   mail=toto@toto.fr
   title=Sondage pour analyse formulaire
   description
   ValueMax
   customized_url
   password
   password_repeat
   editable=1
   type=$poll_type
   gotostep2=date
   ```
   
   La methode GET de son côté permet d'envoyer les données nécéssaire à l'affichage correcte dans le navigateur comme:

   - le type de navigateur, 
   - sa version
   - le système d'exploitation utilisé 
   - La langue du navigateur
   - Le type de contenu demandé

   Dans la requête faite ci-après nous voyions que ce qui est demandé à l'affichage est une image.

   ```
   curl 'https://framasoft.org/nav/img/icons/favicon/sites/date.png' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/110.0' -H 'Accept: image/avif,image/webp,*/*' -H 'Accept-Language: fr-FR,en;q=0.5' -H 'Accept-Encoding: gzip, deflate, br' -H 'Connection: keep-alive' -H 'Referer: https://framadate.org/' -H 'Sec-Fetch-Dest: image' -H 'Sec-Fetch-Mode: no-cors' -H 'Sec-Fetch-Site: cross-site'
   ```
   
# 2. **Comparaison méthodes**
   
   Le tableau ci-après compare les deux méthodes GET et POST:
   
   |                                                                           | GET                                                           | POST                                                                        |
   | ------------------------------------------------------------------------- | ------------------------------------------------------------- |           ---------------------------------------------------------------------------    |
   | Visibilité                                                                | Visible pour l’utilisateur dans le champ d’adresse            | Invisible pour l’utilisateur                                                             |
   | Marque-page et historique de navigation                                   | Les paramètres de l’URL sont stockés en même temps que l’URL. | L’URL est enregistrée sans paramètres URL.                                               |
   | Cache et fichier log du serveur                                           | Les paramètres de l’URL sont stockés sans chiffrement         | Les paramètres de l’URL ne sont pas enregistrés automatiquement.            |
   | Comportement lors de l’actualisation du navigateur / Bouton « précédent » | Les paramètres de l’URL ne sont pas envoyés à nouveau.        | Le navigateur avertit que les données du formulaire doivent être renvoyées. |
   | Type de données                                                           | Caractères ASCII uniquement.                                  | Caractères ASCII mais également données binaires.                              |
   | Longueur des données                                                      | Limitée - longueur maximale de l’URL à 2 048 caractères.      | Illimité              
  
   [Source IONOS comparaison entre GET et POST](https://www.ionos.fr/digitalguide/sites-internet/developpement-web/get-vs-post/)
   
# 3. **Extensible**
      
   C'est un protocole extensible car il peut évoluer au fil du temps et on peut y a jouter plus de nouvelles fonctionnalités, méthodes et moyens d'authentifications. C'est pour cela qu'on a pu l'adapter pour gérer des images, de la vidéo, de l'envoie de données tels que les formulaires par exemple.
   Le protocole HTTP est une couche de transport agnostic de son contenu, on peut lui ajouter de nouveaux Header qui serait par exemple traités par une couche logiciel supplémentaire au serveur.
      
# 4. **Protocole sans état**

   On dit que le protocole HTTP est sans état car il n'y pas de dispositif pour vérifier si les trames envoyées sont bien arrivées. Elles sont envoyées par paires requêtes-réponses. Cela a pour avantage de simplifier le designe des serveurs et de les alléger. Le serveur ne sait donc pas si une requête POST ou GET par exemple est déjà arrivée avec la même demande de la part d'un client. Le serveur s'occupe de répondre aux requêtes peu importe l'ordre d'arrivée des requêtes et peu importe si elles ont déjà été demandées précédemment.
   Cela a pour inconvénients d'empiler les couches de proctocoles car un protocoles sans état s'appuier généralement sur un protocole avec état. Cela oblige également des données des informations supplémentaires qui doivent être interprétées par le serveur ce qui peut ralentir la navigation. Avec un protocole sans état, si une requête est perdue, ni le client, ni le serveur le savent et la requête demandée n'est pas executée. Cela peut entraîner un problème de reception de données incomplètes. 
  
# 5. **URL**

   Par exemple l'URL: https://www.qwant.com/?client=brz-moz&q=d%C3%A9composition+URL&t=web
   
   - HTTPS:// correspond au protocole utilisé, ici le HTTPS qui signifie protocole chiffré TLS
   - www.qwant.com corrsepond au nom de dommaine www signifiant Wolrd Wide Web.
   - ?client=brz-moz&q=d%C3%A9composition+URL&t=websont des paramètres supplémentaires fournis au serveur web. Ces paramètres sont construits sous la forme d'une liste de paires de clé/valeur dont chaque élément est séparé par une esperluette (&). Le serveur web pourra utiliser ces paramètres pour effectuer des actions supplémentaires avant d'envoyer la ressource. Ici ce sont les paramètres liés à ma recherche sur le moteur de rcherche QWANT.

# 6. **Codes Status**

   Les codes de statut de réponse HTTP indiquent si une requête HTTP a été exécutée avec succès ou non. Il en existe plusieurs familles:
   
   - 100 à 199 sont des codes de réponse informatifs
   - 200 à 299 sont des codes de réponses de succès
   - 300 à 399 sont les messages redirection
   - 400 à 499 sont les messages d'erreur côté client
   - 500 à 599 sont les messages d'erreur côté serveur

   L'ensemble des code status sont détaillés sur [cette page](https://developer.mozilla.org/fr/docs/Web/HTTP/Status)
   
# 7. **Négociation de contenu**

   La négociation de contenu est un mécanisme qui permet de proposer une même ressource sous plusieurs formes différentes. En HTTP les variations permises concernent la langue de la ressource et son type MIME (les ressources multimédias). Le navigateur choisi lui même la langue par exemple ou encore le format de l'image affichée soit en fonction de la langue pour laquelle il est configuré et dans le cas d'une image le format qu'il est capable d'afficher.

# 9. **CURL**

   Résultat de la requête GET vers l'url http://dev.local:
   
   ```
   HTTP/1.1 304 Not Modified
   Date: Fri, 10 Mar 2023 14:51:09 GMT
   Server: Apache/2.4.54 (Unix) OpenSSL/1.1.1s PHP/8.2.0 mod_perl/2.0.12 Perl/v5.34.1
   Last-Modified: Fri, 10 Mar 2023 12:46:19 GMT
   ETag: "150-5f68b25d32dab"
   Accept-Ranges: bytes
   Keep-Alive: timeout=5, max=100
   Connection: Keep-Alive
   ```
   Résultat de la requête GET vers l'url http://dev.local/notExisting
   
   ```
   HTTP/1.1 404 Not Found
   Date: Fri, 10 Mar 2023 14:56:57 GMT  
   Server: Apache/2.4.54 (Unix) OpenSSL/1.1.1s PHP/8.2.0 mod_perl/2.0.12 Perl/v5.34.1
   Vary: accept-language,accept-charset
   Accept-Ranges: bytes
   Keep-Alive: timeout=5, max=100
   Connection: Keep-Alive
   Transfer-Encoding: chunked
   Content-Type: text/html; charset=utf-8
   Content-Language: en
   ```
# 10. **Header**

  Les en-têtes HTTP permettent au client et au serveur de transmettre des informations supplémentaires avec la requête ou la réponse. Un en-tête de requête est constitué de son nom (insensible à la casse) suivi d'un deux-points :, puis de sa valeur (sans saut de ligne). L'espace blanc avant la valeur est ignoré.
  Source [Mozilla developper](https://developer.mozilla.org/fr/docs/Web/HTTP/Headers)



  | Type En-tête       | Principales en-tête | Fonction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   | ------------------ | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | En-tête générale   | Date                | Contient la date et l'heure du messsage d'origine                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                    | Cache-Control       | Contient les instructions concernant la mise en cache dans les navigateurs                                                                                                                                                                                                                                                                                                                                                                                                                            |
  |                    | Connection          | Contrôle comment la connexion reste ouverte ou non après que qu'une transaction soit terminée. Keep-alive permet de laisser ouverte une session  pour permettre aux requêtes qui e quivent d'être adressées au serveur.                                                                                                                                                                                                                                                                               |
   | En-tête de requête | Cookie              | L'en-tête de requête HTTP Cookie contient des cookies HTTP stockés associés au serveur .                                                                                                                                                                                                                                                                                                                                                                                                              |
   |                    | Accept              | Le paramètre d'entête de requête HTTP Accept indique quels sont les types de contenu, exprimés sous la forme de types MIME, que le client sera capable d'interpréter.                                                                                                                                                                                                                                                                                                                                 |
   |                    | User-Agent          | L'en-tête de requête User-Agent est une chaîne de caractères qui permet aux serveurs et aux homologues du réseau d'identifier l'application, le système d'exploitation, le fournisseur et/ou la version de l'agent utilisateur demandeur.                                                                                                                                                                                                                                                             |
   |                    | Referer             | L'en-tête de requête Referer contient l'adresse de la page web précédente à partir de laquelle un lien a été suivi pour demander la page courante. L'en-tête Referer permet aux serveurs d'identifier la provenance des visiteurs d'une page.                                                                                                                                                                                                                                                         |
   |                    | If                  | L'entête de requête HTTP If-Modified-Since rend la requête conditionnelle : le serveur renverra la ressource demandée, avec un status 200, seulement si elle a été modifiée pour la dernière fois après la date donnée. Si la ressource n'a pas été modifiée depuis, la réponse sera un 304 sans aucun contenu; le header Last-Modified contiendra la date de la dernière modification. À l'inverse de If-Unmodified-Since (en-US), If-Modified-Since ne peut être utilisé qu'avec un GET ou un HEAD. |
   | En-tête de réponse | Age                 | L'entête HTTP Age indique le temps en secondes pendant lequel la ressource a été stockée dans un cache proxy.                                                                                                                                                                                                                                                                                                                                                                                         |
   |                    | Location            | L'en-tête de réponse Location indique l'URL vers laquelle rediriger une page. Il a un sens seulement lorsqu'il est servi avec une réponse d'état 3xx (redirection) ou 201 (créé).                                                                                                                                                                                                                                                                                                                     |
   |                    | Server              | Le paramètre d'entête Server contient des informations à propos du système (ou sous-système) en place sur le serveur qui s'occupe de la requête.                                                                                                                                                                                                                                                                                                                                                      |
   | En-tête d'entité   | Content length      | L'en-tête (header) Content-Length indique la taille en octets (exprimée en base 10) du corps de la réponse envoyée au client.                                                                                                                                                                                                                                                                                                                                                                         |
   |                    | Content-Language    | L'en-tête Content-Language est utilisé pour décrire quels langages sont destinés au public, de sorte que cela permette à l'utilisateur de se différencier en fonction de la langue préférée des utilisateurs.                                                                                                                                                                                                                                                                                         |
   |                    | Content-Encoding    | L'en-tête Content-Encoding indique la compression utilisée sur le média contenu dans le corps de la requête. Il permet au client de savoir comment décoder le contenu afin d'obtenir le type de média référencé par l'entête Content-Type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
