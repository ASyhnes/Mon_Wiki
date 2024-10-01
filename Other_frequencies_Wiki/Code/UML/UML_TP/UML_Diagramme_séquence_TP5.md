L'utilisateur est représenté par un acteur nommé "Utilisateur".
Le système de gestion de bibliothèque est représenté par un objet nommé "Bibliothèque".
La base de données est représentée par un objet nommé "BaseDeDonnees". 
Le service de notification (queue) est représenté par un objet nommé "Notification".

L'utilisateur commence par envoyer une requête de recherche pour un livre spécifique. La bibliothèque traite la requête et recherche le livre dans sa base de données. Si le livre est disponible, la bibliothèque envoie une réponse positive à l'utilisateur. 

L'utilisateur choisit alors de demander l'emprunt du livre. 
La bibliothèque vérifie à nouveau si le livre est disponible et effectue l'emprunt s'il est disponible.
La bibliothèque enregistre ensuite les détails de l'emprunt dans la base de données.
Le service de notification par e-mail envoie une notification à l'utilisateur pour confirmer l'emprunt du livre. 
L'utilisateur, après avoir lu le livre, décide de le retourner.
L'utilisateur informe la bibliothèque de son intention de retourner le livre.
La bibliothèque enregistre le retour du livre dans la base de données et envoie une confirmation au service de notification par e-mail.
Le service de notification par e-mail envoie une notification de retour au propriétaire du livre.