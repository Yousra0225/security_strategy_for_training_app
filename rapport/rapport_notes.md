# Notes pour le Rapport
## Author : Yousra Chbib
## Projet de plateforme de formation :
![Architecture](src/architecture.drawio.png)

## Notes à mettre dans le rapport : 
### Mesure et mécanisme de sécurité par défaut ou Global: 
1. Same Origin Policy `(SOP)`.
2. Cross-Origin Ressource Sharing `(CORS)`
3. ...

## Partie Front
1. Composants :
    - Page de Connexion/inscription
        - Connexion
            1. ![Sécurisation du nom d’utilisateur ](src/username.md)
            2. ![Politique de mots de passe sécurisés](src/password.md)
            3. Sécurisation du Formulaire d'Authentification
        - Authentification
    - Tableau de Bord : 
        - Les roles
        - Les actions
    - Formation
        - Permissions (limitées)
        - Protection contre les **scrapers**
    - Mesure global pour sécurisé le coté client
## Partie Back-End
1. Sécurisation des composants
    - API
        - Réception des requetes
        - Authentification et validation
        - Traitement des requetes
        - Chiffrement des données
        - Gesttion des sessions et des tokens
    - Base de Données
    - Gestion des Permissions
    - Logs et Monitoring 
    - Gestion des utilisateurs
    - Stockage des fichiers
## Sécurisation des échanges
1. Echange Front/back
    - Authentification
    - Sessions 
    - Protocol de communication
    - Protection des requetes 
    -  Validation des entrées
























.
## Annexes : 
Bases d'authetification  
https://laconsole.dev/formations/authentification

Sécurité de connexion   
https://www.microsoft.com/fr-fr/security/business/security-101/what-is-login-security

La méthode la plus sécurisée pour se connecter  
https://safety.google/intl/fr_fr/authentication/

Sécurité par Mot de Passe  
https://www.proofpoint.com/fr/threat-reference/password-protection

Regex (expression régulière)  
https://datascientest.com/regex-tout-savoir

Bien gérer son mot de passe   
https://www.cybermalveillance.gouv.fr/tous-nos-contenus/bonnes-pratiques/mots-de-passe

Créer un mot de passe sécurisé  
https://www.economie.gouv.fr/particuliers/creer-mot-passe-securise

Conseils pour créer et gérer les mots de passe  
https://www.priv.gc.ca/fr/sujets-lies-a-la-protection-de-la-vie-privee/technologie/protection-de-la-vie-privee-en-ligne-surveillance-et-temoins/protection-de-la-vie-privee-en-ligne/tips_pw/

Choisir un bon mot de passe  
https://cri.centrale-med.fr/fr/faq/choisir-un-bon-mot-passe

Gestion des sessions d'authentication: 
https://www.vaadata.com/blog/fr/comment-securiser-les-systemes-dauthentification-de-gestion-de-sessions-et-de-controle-dacces-de-vos-applications-web/

csp:
https://www.writesoftwarewell.com/content-security-policy/