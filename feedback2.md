Tu as bien compris l'architecture MVC et tu respectes la séparation des responsabilités, bravo ! 👏

Tu as pensé à ajouter un fichier .htaccess pour la réécriture d'url, c'est très bien ! Mais pourquoi ne pas en avoir profité pour en ajouter un également dans ton dossier app, pour empêcher l'accès direct à tes fichiers php ? 😁

```apacheconf
// app/.htaccess
Deny from all
```

Tu as correctement su faire l'intégration des templates et tu as pensé à les séparer en plusieurs fichiers. Cela participe à la maintenabilité de ton code ! En prime, tu as également ajouté un dossier assets pour y stocker tes fichiers css et js, c'est très bien ! 👏

💡 Juste une petite amélioration à ce sujet, tu utilises un chemin relatif dans ton fichier `app/views/layout/header.tpl.php` pour charger tes fichiers css (`href="./assets/css/style.css"`). Pourquoi ne pas plutôt faire le choix d'utiliser un chemin absolu ? 😁

> Cela permet une meilleure portabilité, flexibilité... Définir dynamiquement la base de l'URL de tes ressources permet d'utiliser ton code dans différents environnements (dev, test, pré-prod, production) où les chemins peuvent varier.
> Alors pourquoi s'en passer ? 😁

... D'autant que tu l'as défini dans ton fichier CoreController.php :

```php
// définir l'url absolue pour nos assets
$viewData['assetsBaseUri'] = $_SERVER['BASE_URI'] . 'assets/';
```

💡 Maintenant que tu as amélioré la portabilité de ton code, pourquoi ne pas aller plus loin et faire en sorte que ton code soit plus maintenable ?
La manière d'écrire du code est propre à chaque développeur, on a tous nos petites habitudes, nos préférences... Mais si l'écrire est personnel, bien souvent d'autres développeurs vont devoir le lire (code review...), voir y écrire (pull request...), et il est donc important de faire en sorte que le code soit facilement compréhensible par tous. C'est important de respecter le fond **ET** la forme grâce à l'**indentations** ou aux **commentaires**... 😁

🎁 Pour en savoir plus sur les commentaires, je t'invite à lire cet article : https://itexpert.fr/blog/commentaires-parfaits/

💡 Dans le même ordre d'idée, il est important de respecter les conventions de nommage pour que le code reste homogène même si plusieurs développeurs travaillent dessus. 😁
Par exemple, tu as nommé tes controllers au pluriel (StudentsController.php) et tes models (Students.php). La convention de nommage courante (mais pas obligatoire certe) pour les controllers et les modèles est de les nommer au singulier (StudentController.php et Student.php) et d'utiliser pour les controllers le UpperCamelCase et pour les modèles le CamelCase.

🎁 Tu pourras retrouver tout ça ici > [Conventions generales nommage](https://www.alsacreations.com/outils/guidelines/Conventions-generales-nommage.md)

Tu as pensé à utliser l'abstraction pour ton CoreModel et rendu des méthodes statiques dans tes modèles, bravo ! 👏

Dommage que tu ne sois pas allé plus loin dans le projet, qu'est-ce qui t'a bloqué ?

N'hésite pas à m'expliquer la raison en MP ou si tu préfères en discuter de vive voix, je suis disponible sur Discord. 😁

<hr>

## En **résumé**... 😁

## Dans tous les cas, le code que tu as rendu est correct. 👏

Tu devrais l'améliorer avec les points que j'ai relevé et essayer de le terminer en utilisant le moins possible la correction et t'inscrire dans un groupe d'ECP pour comparer ton code avec celui des autres apprenants 😁

Bonne continuation ! 👋
