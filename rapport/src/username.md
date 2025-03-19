# Sécurisation du nom d’utilisateur
## Validation des entrées avec des expressions régulières (Regex) :
*Une expression régulière est une séquence de caractères utilisée pour définir un motif (pattern). Ce motif permet de rechercher, extraire ou modifier des chaînes de caractères spécifiques au sein d’un texte.*  
`Exemple : La regex \d{5} correspond à une suite de cinq chiffres.`
### À quoi sert une expression régulière ?
**Valider des entrées utilisateur : Vérification d’adresses email, de mots de passe ou de formats spécifiques.**  
Exemple :     
Adresses email : `^[a-zA-Z0-9._%+-]+@gmail\.com$`  
Numéros de téléphone : `^\+?[1-9]\d{1,14}$`  

## Filtrage et nettoyage des entrées (Sanitization)
- Supprimer les espaces inutiles avant/après l’entrée.
- Échapper ou refuser les caractères spéciaux potentiellement dangereux pour éviter les injections (SQL, XSS).

## Longueur minimale et maximale 
Exiger un minimum de 6 caractères et un maximum de 50 pour éviter les entrées trop courtes ou trop longues.

## Protection contre l’énumération des utilisateurs
Réponse générique en cas d’échec : ne pas dire "Cet email n'existe pas", mais plutôt "Identifiants incorrects", cela empêche un attaquant de deviner quels emails sont enregistrés.
