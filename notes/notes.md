# Mes notes 
## Author : Yousra Chbib
## Attaques
1. **Menaces**

|Menaces|Explication|Exemple|
|-------|-----------|-------|
|**Compromission des ressources**|*Prendre le contrôle des données ou des services d'un site*|accéder à la base de données et/ou modifier des fichiers importants|
|**Le déni de service DoS/DDoS**|*Rendre un site web/app inutilisable en saturant le serveurs de requêtes, ce qui le bloque*|**DDoS**(un grand nombre de machines `botnets` attaquent en même temps) |
|**Le vol de données**|*Accéder à des informations sensible*|accéder à une base de données et voler les données personnelles des utilisateurs|

2. **Classes d'attaques**

|Nom de la classe|Explication|Exemple|
|----------------|-----------|-------|
|**Cross-Site-Scripting (XSS)**|*Attaquer les utilisateurs d'une page web en injectant du code malveillant dans cette page, afin qu'il soit exécuté par leurs navigateurs.*|Injecter du code JavaScript dans un champ de commentaire.|
|**Cross-Site-Request-Foregery (CSRF)**|*Forcer l'utilisateur à faire une action sur un site où il est déja connecter sans qu'il le sache*|L'utilisateur clique sur un lien piégé alors qu'il est connecté à sa banqhue, une requête vas etre envoyer à la banque pour un virement, -comme il est déja connecté- la banque l'accepte|
|**Server-Side-request-Foregery (SSRF)**|*Forcer un serveur à faire des requêtes vers des recources interne et/ou externe*|L'attaquant envoie une requête cencé de récupérer un image, mais il a détourner pour accéder à des ressources internes et récupérer des données sensibles|
|**SQLi**|*Insérer du code SQL malveillant dans une entrée utilisateur pour manipuler une base de donner  des données malveillantes dans un champ de formulaire pour tromper la base de données et lui faire executer des commandes non prévues*|Envoyer une requête SQL malveillante pour se connecter à un site `Select from users WHERE name'toto' and password ='tutu' OR '1'=1` comme 1=1 est toujours vrais, le site donne accés à tous les comptes|
|**Local/Remote file inclusion**|*Forcer un site à charger un fichier provient ou bien du serveur lui même ou d'un serveur externe*|Charger un fichier local sensible (mots de passe...) du serveur|