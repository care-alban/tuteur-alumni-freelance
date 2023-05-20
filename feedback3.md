## Home sweet home... 🏠

Quelle surprise j'ai eu en arrivant sur ta page d'accueil : 404 not found ! 😱

Heureusement, j'ai toujours un GPS de développeur sur moi et en consultant ton fichier index.php, j'a pu retrouver mon chemin.

```php
$router->map(
    'GET',
    '/home',  //<-- Ici, tu as indiqué la route "/home"
    [
        'method' => 'home',
        'controller' => MainController::class // On indique le FQCN de la classe
    ],
    'main-home'
);
```

Mais du coup, je me suis demandé si tu avais bien vu la consigne "la liste des routes du projet est fournie : docs/routes.md" dans l'énoncé ? 🤔

💡 Lis bien les consignes, elles sont là pour t'aider à ne rien oublier et prendront encore plus d'importance quand tu devras travailler en équipe.

## Je code...

### ... je commente ✍

J'ai vu que tu avais commentaire dans ton code, c'est une bonne pratique 👍 ! Mais tout ne doit pas être commenté, et les commentaires ne servent pas à expliquer ce que fait ton code, mais pourquoi tu l'as fait.

Les commentaires comme : "Le formulaire a été soumis, les données sont envoyées", sont des commentaires qui ont un but pédagogique, ils servent à laisser une trace des explications faites en cockpit. Ils ne doivent pas être présents dans le code final d'un projet.

A l'inverse, c'est une bonne pratique de commenter une méthode, pour expliquer qu'elle est son rôle, quels sont les arguments qu'elle attend, et ce qu'elle retourne. Comme par exemple :

```php
/**
* Méthode gérant l'affichage de la page 404
*
* @return void
 */
public function err404()
{...}
```

💡 L'idéal serait même d'écrire des commentaires en anglais pour t'habituer.

🎁 Pour en savoir plus sur les commentaires, je t'invite à lire cet article : https://itexpert.fr/blog/commentaires-parfaits/

### Et je fais du ménage ? 🧹

💡 Attention, tu as tendance à laisser des lignes vides dans ton code ou à ne pas respecter les indentations, il faut t'habituer à ce que ton code soit le plus lisible possible, et les lignes vides ne servent pas à grand chose 😂.

## Allo Houston, we have a problem... 🚀

... j'ai perdu ma navbar et mon footer en route 😱! Tu vois où je veux en venir ?

N'oublie pas que pour pouvoir réutiliser la barre de navigation et les scripts (dans le footer), il faut qu'ils aient leur propre template. Et pour pouvoir les utiliser, tu dois les appeler dans la méthode show() de ton MainController.

## MainController, vous avez dit MainController ? 🤔

La méthode show() est une méthode commune à plusieurs controllers (elle est utilisé dans ton mainController, teacherController et studentController, errorController).

💡 Ne serait-il pas mieux de la déplacer dans un fichier plus global comme le CoreController, et de faire hériter tes controllers de ce fichier plutôt que du mainController (qui contient ta méthode home()) ?

C'est toujours intéresant de séparer les différentes responsabilités des composants de l'application et de les organiser de manière claire et cohérente.

## fonctionnalités !

Tu as correctement su mettre en place les fonctionnalites d'affichage de la liste des professeurs et des étudiants et tu as même pensé à utiliser l'abstraction et les fonctions statiques (dans tes modèles), c'est top ! 👍

💡 Cependant pourquoi ne pas avoir inclus l'id dans ton fichier coreModel, c'est une propriété commune à tous tes modèles ?

💡 Attention au choix du nom de tes méthodes, `public function getCreated_at()` (dans ton coreModel) n'est pas conforme à la convention de nommage des méthodes en PHP. Il faut utiliser le camelCase : `public function getCreatedAt()`.

🎁 Tu pourras retrouver tout ça ici > [Conventions generales nommage](https://www.alsacreations.com/outils/guidelines/Conventions-generales-nommage.md)

## Copier/coller... ou ne pas être ! 🤔

C'est super que tu aies réussi à mettre en place la fonctionnalité d'ajout d'un étudiant, mais je me suis rendu compte que tu avais copié/collé ton code pour l'ajout d'un professeur, et que tu l'avais modifié pour l'adapter.

Et comme je suis un peu curieux (et téméraire), j'ai voulu tester ton formulaire d'ajout d'un professeur, et là... surprise 😱 ! Je suis redirigé vers le formulaire d'ajout d'un étudiant. "student/add" (J'avoue il y a pire comme prise de risque ! 😂)

💡 Attention, c'est une mauvaise habitude de faire des copier/coller, car tu risques d'oublier de modifier certaines parties du code, et de te retrouver avec des bugs.

🎁 Pour en savoir plus wikipédia à un très bon article sur cette pratique, je t'invite à y jeter un petit coup d'oeil : [Programmation par copier-coller](https://fr.wikipedia.org/wiki/Programmation_par_copier-coller)

## je contrôle, donc je suis... (sûr que ça fonctionne !) 🥳!

Tant qu'à être sur le formulaire d'ajout d'un étudiant, j'ai voulu le tester, et là... impossible de choisir un professeur dans la liste déroulante. 😱

```html
<select name="teacher" id="teacher" class="form-control">
  <option value="0">-</option>
  <option value="1">Prénom Prof - Formateur PHP/MySQL</option>
  <option value="2">Prénom2 Prof2 - Formateur PHP/MySQL</option>
  <option value="5">sgsg fsgfsg - sg</option>
</select>
```

Est-ce que tu n'aurais pas oublié ou rencontré des difficultés pour récupérer et transmettre la liste des professeurs à ton formulaire ?

🎁 Si c'est le cas, dis-toi que c'est la même logique que générer la liste des professeurs, et que les données tramsmises ne te serviront que dans les options de ta balise select.

## NOT NULL is not null ! 🤔

Pour finir avec cette fonctionnalité, j'ai remarqué dans la méthode insert() de ton modèle Student.php que ta requête SQL ne prenait pas en compte l'id de l'enseignant (teacher_id) :

```sql
$sql = "
    INSERT INTO `student` (firstname, lastname, status)
    VALUES ('{$this->firstname}','{$this->lastname}','{$this->status}')
";
```

J'imagine que si tu as rencontré des difficultés avec la liste déroulante, tu as peut-être voulu faire la requête SQL sans l'id de l'enseignant, pour pouvoir tester ton formulaire.

💡 Mais dans le cas présent, ce n'est pas possible de l'omettre car il est défini comme NOT NULL dans ta base de données :

```sql
`teacher_id` INT UNSIGNED NOT NULL
```

C'est un sécurité qui permet de s'assurer que chaque étudiant ait un enseignant "référent".

💡 Je pense que tu devrais reprendre cette partie là calmement (en essayant de la faire sans la correction), récupérer la liste des enseignants et mettre à jour ton formulaire, puis modifier ta requête SQL pour qu'elle soit cohérente avec les données que l'on souhaites insérer.

## Et si on sécurisait un peu tout ça ? 🔒

Je me suis rendu compte que tu avais mis en place la vérification des données saisies dans tes formulaires et d'avoir utilisé des filtres (ex: FILTER_SANITIZE_SPECIAL_CHARS pour supprimer ou échapper les caractères spéciaux dans la valeur récupérée 🙏). C'est une étape importante pour sécuriser ton application. Bravo pour avoir pensé ! 💪

Et si on poussait un peu plus loin la sécurité ?

💡 Quand ta fonctionnalité d'ajout d'un étudiant sera terminé, et que ta requête fonctionnera correctement, pourquoi ne pas l'améliorer en utilisant des requêtes préparées ?

🎁 Tu pourras retrouver tout ça ici sur la documentation officielle de php : [Requêtes préparées](https://www.php.net/manual/fr/pdo.prepared-statements.php) et biensûr sur kourou : [Requêtes préparées](https://kourou.oclock.io/ressources/fiche-recap/pdo/#requ%c3%aates-pr%c3%a9par%c3%a9es)

<hr>

## En **résumé**... 😁

Tu devrais pouvoir améliorer ton code existant avec les points que je t'ai indiqué. Mais ce n'est pas suffisant il faut aussi que tu essayes de le terminer en utilisant le moins possible la correction.
J'invite à t'inscrire dans un groupe d'ECP pour pouvoir discuter et comparer ton code avec celui des autres apprenants 😁

Bonne continuation ! 👋
