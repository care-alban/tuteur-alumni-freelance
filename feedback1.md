Bravo 👏 ! Tu as produit un code d'une grande qualité ! Tu as su aborder le projet dans sa globalité et tu maîtrises la majorité des concepts !

Attention toutefois aux détails, c'est ce qui fera la différence entre un bon et un très bon développeur ! 😉

## N'oublie pas : la **maintenabilité** et la **scalabilité** sont tes amis !! 😁

Je pense notamment à l'organisation de ton code où tu as tendance à mettre les méthodes dans le désordre (ou du moins à suivre l'ordre de l'énoncé 😝).

Le souci est que si tu as besoin de modifier une méthode, tu dois la chercher dans le fichier et si tu as 50 méthodes dans un fichier, ça va vite devenir compliqué de s'y retrouver. Imagine si un autre développeur doit intervenir sur ton code, il va vite être perdu !

> Par exemple pour les fonctionnalités liées aux profs :
>
> - dans ton fichier index.php, tu pourrais lister les routes comme ceci :
>
>   - lister tous les profs
>   - ajouter un prof
>   - modifier un prof
>   - supprimer un prof
>
> - dans un controller, il est plus courant de trouver les méthodes dans l'ordre suivant : teachers, addGet, addPost, editGet, editPost, delete.
>
> - du coup dans le model correspondant, on les retrouve dans le même ordre : findAll, find, insert, update, delete.

Dans le même ordre d'idées, tu as tendance à utiliser des noms de méthodes qui sont très longs comme par exemple `teacherUpdatePost` ou pas suffisamment adapté comme `teacher` (pour une liste). Il serait plus parlant de l'appeler `teachers` ou mieux puisqu'on est dans un controller qui gère les profs, pourquoi ne pas l'appeler juste : `teacherList`. 😏 (⛔ attention à l'utilisation d'une methode `list()`, il existe déjà une fonction `list()` en PHP qui "assigne des variables comme si elles étaient un tableau")

Cette remarque fonctionne également pour tes paramètres de méthodes ! Dans ta méthode `teacherUpdatePost`, tu attends un paramètre que tu nommes `$teacherid`. Pourquoi ne pas l'appeler `$id` tout simplement ? 😁 (Au passage, n'oublie pas les conventions de nommage, si tu dois utiliser plusieurs éléments dans un nom, il convient d'utiliser le cas présent le **camelCase** ce qui donnerait `$teacherId`)

Tu pourras retrouver tout ça ici > [Conventions generales nommage](https://www.alsacreations.com/outils/guidelines/Conventions-generales-nommage.md)

❤ C'est un peu hors sujet, mais je suis certain que tu vas adorer ce lien aussi : [PHP Standards Recommendations](https://www.php-fig.org/psr/psr-12/)! 😍

<hr>

## Choisir la meilleur **route**... celle qui est dans la doc ! 😁

Au fait, tu utilises un GPS parfois ? 🤔 C'est pratique n'est-ce pas ? Surtout si on suit la route qu'il nous indique ! 😁

Et bien, c'est pareil pour ton code ! Il faut suivre les routes qui sont indiquées sinon tu vas perdre des développeurs en route ! 😁

Je t'invite à vérifier tes routes en les comparant avec celles qui sont indiquées dans le fichier /docs/routes.md ! 😉

<hr>

## Les **méthodes statiques** peuvent être appelées directement depuis la classe elle-même, sans avoir besoin d'instancier un objet. 😁

Tes modèles (après un soupçon de rangement) sont très bien !

Tu as choisi d'utiliser les méthodes statiques pour les méthodes qui ne nécessitent pas d'instancier un objet, bravo. 👍
Mais du coup, pourquoi ne pas les avoir utilisées dans tes controllers ? 😁

```php
class MaClass {
    public static function maMethodeStatic() {
        // ...
    }
}

$monAppelDeLaMethodStatique = MaClass::maMethodeStatic();
```

Tu pourras retrouver tout ça ici : [Méthodes statiques](https://www.php.net/manual/fr/language.oop5.static.php) (comment ça mon exemple ressemble à celui de la doc ??? 😤) et biensûr sur Kourou : [Les objets en php](https://kourou.oclock.io/ressources/fiche-recap/les-objets-en-php/#m%c3%a9thodes-et-propri%c3%a9t%c3%a9s-statiques)

<hr>

## L'**abstraction** c'est DRY et le DRY c'est bien ! 🥳

Au fait ? Est-ce que l'abstraction est un concept concret pour toi ? 🤔
J'ai remarqué que tu n'as pas utilisé l'abstraction dans tes modèles. C'est loin d'être une erreur, mais c'est un concept qui peut être très utile dans certains cas et je t'invite à essayer de le mettre en place avec la correction 💪
D'autant que je suis sûr que tu vas aimer rendre ton code plus DRY (Don’t Repeat Yourself) !

Tu peux te remettre tout ça en tête ici : [L'abstraction](https://kourou.oclock.io/ressources/fiche-recap/heritage/#anchor-polymorphisme) et si tu as besoin n'hésite pas à me demander en MP ! 😉

<hr>

## Et si on parlait un peu **Sécurité** ? 😁

Tu as su très bien gérer la validation des données dans tes formulaires et la mise en place de l'authentification (utilisation des sessions), bravo ! 👏

Une petite remarque concernant les ACL (Access Control List)... Notamment ta liste d'ACL dans le fichier CoreController.php. Vérifie bien que toutes les routes qui ont besoin d'être "contrôlées" sont listées dans ce fichier et que tu la mets à jour après chaque ajout de fonctionnalité !
Ça serait dommage qu'un admin ou un user reste coincé devant la porte de la maison ! Ou de privé un utilisateur d'une fonctionnalité comme la liste des profs ! 😁

Tu n'as pas utilisé de requêtes préparées dans tous tes modèles, c'est dommage, c'est une vulnérabilité de sécurité majeure. D'autant que tu les as utilisées dans ton modèle AppUser.php 😔

J'imagine que tu n'as pas eu le temps de t'attaquer à la protection CSRF (Cross-Site Request Forgery) ? 😁

Pas de pression 🍺, il est déjà très impressionnant d'être arrivé jusque-là 👏 ! Et il est toujours temps de le faire avec la correction ! 💪

<hr>

## Je **contrôle**, donc je suis... (sûr !) 🥳

As-tu testé toutes tes fonctionnalités ? 🤔 TOUTES ? 😁

Je t'invite à tester régulière toutes tes fonctionnalités et à vérifier que tout fonctionne comme toujours prévu ! 😁

Tu as écrit ce commentaire dans ton fichier TeacherController.php dans ta méthode `eacherUpdatePost` :

```php
// aucune erreur détectée
// j'ai soumis mon formulaire et je n'ai pas d'erreur
```

Certes, mais est-ce que tu as vérifié que tout fonctionne comme prévu ? 😁

Je te propose de relire le code de ta vue teacher_update.tpl.php et de vérifier que tu as bien pensé à tout (y compris récupérer les options pour le statut du prof 😝) ! 😁

Je peux te donner un indice 🎁 si tu n'as aucun(e) 👉id👈 de ce qui est attendu par ta méthode `teacherUpdatePost` ?

Et si tu ne trouves toujours pas, n'hésite pas à me demander en MP, je te donnerai plein d'autres indices compliqués ! 💪

<hr>

## En **résumé**... 😁

## Tu peux être fier de toi ! C'est un très bon travail que tu as réalisé ! 👏

Il te reste à améliorer les points suivants :

(+) utiliser les conventions de nommage

(+) vérifier que les routes sont conformes à la doc

(+) vérifier le bon fonctionnement des fonctionnalités <= “C'est pas faux !” 🏆

(+) utiliser les méthodes statiques de tes modèles dans tous les controllers

(+) bien mettre à jour la liste des ACL au fur et à mesure des ajouts de fonctionnalités

(+) utiliser les requêtes préparées (partout !)

(+) utiliser l'abstraction dans les modèles

(+) Mettre en place la protection CSRF

## Oups j'ai failli oublier ! 😅

### (+) T'inscrire comme ECP pour partager tes connaissances avec les autres apprenants ! 🥳💪
