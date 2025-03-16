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
|**XML External Entity (XXE)**|*exploite une mauvaise configuration du traitement XML pour accéder à des fichiers sensibles du serveur ou exécuter d'autres actions malveillantes.*|Envoyer un fichier XML contenant une entité externe pour que le serveur renvoie le contenu d'un fichier sensible.|

## Régles d'hygiène : 
|Principe de sécurité|Description|Exemples|
|--------------------|-----------|--------|
|**Défence en Profondeur**|*Utilisation de plusieurs couches de sécurité indépendantes pour protéger un système.*|Ne pas concentrer toutes les mesures de sécurité au point d’entrée, chaque composant doit intégrer ses propres protections.|
|**Moindre Privilège**|*Limiter les permissions aux seules nécessaires pour minimiser les risques en cas de compromission.*|Définir des rôles précis (lecture seule, écriture…), restreindre les permissions d’accès aux API et aux fichiers système.|
|**Réduction de la surface d'attaque**|*Ne pas exposer de services, accès ou composants inutiles pour limiter les vulnérabilités.*|Filtrage des ports réseau, désactivation des services non nécessaires, suppression des modules inutiles.|

## TLS 
### C'est quoi ?
*TLS (Transport Layer Security) est un protocole de sécurité utilisé pour chiffrer les communications entre un serveur et un client.*
*Lorsque on vois `HTTPS` dans l'URL d'un site, cela signifie que TLS est utilisé pour sécuriser la connexion.*

### Pourquoi l'utiliser ?
- Protège la confidentialité des données échangées entre le site et l'utilisateur.
- Empêche les attaques `Man-In-The-Middle`*, où un attaquant pourrait intercepter ou modifier les informations.

### Bonne Pratiques 
- Utiliser `TLS 1.2` ou `1.3` pour garantir une sécurité optimale.
- Activer `HSTS`* pour forcer l'utilisation de HTTPS et empêcher l'accès en HTTP non sécurisé.
- Surveiller les `CT`* logs pour détecter et révoquer les certificats frauduleux.

|Termes|Définition|
|------|----------|
|**Man-In-The-Middle**|*Une attaque où un attaquant intercepte, modifie ou espionne les communications entre deux parties (par exemple, un utilisateur et un site web) sans qu'elles ne s'en aperçoivent.*|
|**HSTS (HTTP Strict Transport Security)**|*Une mesure de sécurité qui force les navigateurs à n'utiliser que HTTPS pour se connecter à un site web.*|
|**CT Logs (Certificate Transparency Logs)**|*Ce sont des registres publics qui enregistrent tous les certificats SSL/TLS délivrés pour un site web. *|

## Mécanismes de Sécurité Web  

| **Mécanisme de sécurité** |**Explication**|
|---------------------------|---------------|
| **Protection contre les vulnérabilités XSS**   | XSS (Cross-Site Scripting) permet à un attaquant d'injecter du code malveillant dans une page web. Pour s'en protéger, on filtre les entrées utilisateur pour éviter l'injection. |
| **Content Security Policy (CSP)**              | CSP est une politique de sécurité qui permet de contrôler les sources de contenu autorisées (comme les scripts, images, etc.) pour empêcher l'exécution de code malveillant.    |
| **Referrer-Policy**                            | Referrer-Policy définit quelles informations (comme l'URL complète) sont envoyées dans les en-têtes HTTP lors des navigations, pour protéger la vie privée de l'utilisateur.      |
| **Web Storage, IndexedDB, Cookies**            | Ces technologies stockent des données côté client. Web Storage et IndexedDB permettent de stocker des informations locales, tandis que les cookies gardent des informations sur l'utilisateur. |
| **XMLHttpRequest (XHR) et Cross-Origin Resource Sharing (CORS)** | XHR est utilisé pour faire des requêtes HTTP sans recharger la page. CORS est une politique qui définit si un site peut accéder à des ressources d'un autre domaine.            |
| **HTML5 et JavaScript**                        | HTML5 et JavaScript permettent de créer des pages interactives et dynamiques. Ils sont utilisés dans des applications web modernes, mais doivent être sécurisés pour éviter les attaques. |

## Conlusion :
*Ce guide permer de mieux comprendre les différents mécanismes de sécurité à mettre en place pour protéger les applications web. En appliquant des techniques comme la protection contre les attaques XSS, l'utilisation de la CSP, et la gestion des cookies ou du stockage local, on peut renforcer la sécurité des sites. on voit aussi l'importance de mettre en œuvre CORS et la Referrer-Policy pour mieux gérer la confidentialité et l'intégrité des données.Ces mesures doivent être intégrées dès le début du développement pour garantir une sécurité maximale.*

