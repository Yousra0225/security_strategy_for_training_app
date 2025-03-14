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