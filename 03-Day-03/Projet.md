Le tableau `users` contient les données des utilisateurs sous forme d'objets. Chaque objet a une propriété `id` qui est un nombre entier et une propriété `name` qui est une chaîne de caractères.

1.  Utilisez Postman ou un autre outil similaire pour envoyer une requête GET à l'URL `http://localhost:3000/users`. Quel est le résultat renvoyé ?
    
2.  Modifiez la requête GET précédente pour ajouter un paramètre de requête `name` qui permet de filtrer les utilisateurs par nom. Par exemple, la requête `http://localhost:3000/users?name=Bob` devrait renvoyer l'utilisateur dont le nom est "Bob". Testez votre nouvelle requête avec Postman.
    
3.  Ajoutez une nouvelle route à votre API pour permettre la création d'un nouvel utilisateur. La route doit écouter les requêtes POST à l'URL `/users` et prendre en charge un corps de requête JSON contenant les propriétés `id` et `name` du nouvel utilisateur. Le serveur doit ajouter le nouvel utilisateur au tableau `users` et renvoyer une réponse JSON contenant le tableau mis à jour. Testez votre nouvelle route avec Postman.
    
4.  Ajoutez une nouvelle route à votre API pour permettre la mise à jour d'un utilisateur existant. La route doit écouter les requêtes PUT à l'URL `/users/:id` et prendre en charge un corps de requête JSON contenant les propriétés `name` du nouvel utilisateur. Le serveur doit mettre à jour le nom de l'utilisateur correspondant à l'ID spécifié et renvoyer une réponse JSON contenant le tableau mis à jour. Testez votre nouvelle route avec Postman.
    
5.  Ajoutez une nouvelle route à votre API pour permettre la suppression d'un utilisateur existant. La route doit écouter les requêtes DELETE à l'URL `/users/:id`. Le serveur doit supprimer l'utilisateur correspondant à l'ID spécifié du tableau `users` et renvoyer une réponse JSON contenant le tableau mis à jour. Testez votre nouvelle route avec Postman.
    

Note : Assurez-vous de gérer les erreurs et de renvoyer des codes de statut HTTP appropriés dans chaque cas.