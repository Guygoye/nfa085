1. **Méthodes GET et POST**

   
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
   
2. **Comparaison méthodes**
   
   Le tableau ci-après compare les deux méthodes GET et POST:
   
   > GET > POST
   ---
   
