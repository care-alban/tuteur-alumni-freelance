# Retours à l’équipe pédagogique Parcours S06

🟢 RAS
🟡 Des Choses à Travailler
🟠 Insuffisant pour Valider
🔴 Non Rendu ou Très Insuffisant

| Tâches à réaliser                    | Apprenant 1 | Apprenant 2 | Apprenant 3 | Apprenant 4 |
| ------------------------------------ | ----------- | ----------- | ----------- | ----------- |
| Lister tous les profs                | 🟢          | 🟢          | 🟢          | 🟠          |
| Lister tous les étudiants            | 🟢          | 🟢          | 🟢          | 🟠          |
| Ajout d'un prof                      | 🟢          | 🔴          | 🟠          | 🟠          |
| Ajout d'un étudiant                  | 🟢          | 🔴          | 🟠          | 🟠          |
| Restreindre l'accès aux utilisateurs | 🟢          | 🔴          | 🔴          | 🟠          |
| Mettre en place les permissions      | 🟡          | 🔴          | 🔴          | 🔴          |
| ----- BONUS -----                    | ----------- | ----------- | ----------- | ----------- |
| Validation des données               | 🟡          | 🔴          | 🟡          | 🟡          |
| Mise à jour d'un prof                | 🟡          | 🔴          | 🔴          | 🟠          |
| Mise à jour d'un étudiant            | 🟡          | 🔴          | 🔴          | 🟠          |
| Suppression d'un prof                | 🟢          | 🔴          | 🔴          | 🔴          |
| Suppression d'un étudiant            | 🟢          | 🔴          | 🔴          | 🔴          |
| ----- SUPER BONUS -----              | ----------- | ----------- | ----------- | ----------- |
| Gestion des utilisateurs en BO       | 🟠          | 🔴          | 🔴          | 🟠          |
| CSRF                                 | 🔴          | 🔴          | 🔴          | 🟠          |

## Analyse globale :

D'une manière générale, je pense que la qualité du code produit est en deçà de ce que l'on pourrait attendre à ce stade de la formation.

- Il persiste pour tous les apprenants quelques maladresses qui n'ont rien de rédhibitoire comme la pertinence de commentaires (plus des notes que des commentaires), ou la mise en forme d'un code qui manque de clarté, ou des conventions de nommage qui ne sont pas respectées.

- Les apprenants semblent avoir compris globalement le principe de l'architecture MVC, il reste des fragilités sur le découpage du code (CoreController, abstraction...).

- Les modèles ont posé moins de problèmes, bien que l'utilisation de requêtes préparées ne soit pas encore systématique. **Il me semble important de faire un point sur ce sujet avec les apprenants.**

- Plusieurs apprenants (ou au moins une fois chaque apprenant 😱) n'ont pas suivi les indications données dans le fichier docs/routes.md, concernant l'URL des routes. **Il est nécessaire de refaire un point sur ce sujet et/ou de vérifier la compréhension sur ce point dans l'énoncé.**

- L'intégration des vues est globalement correcte.

- La majorité des apprenants se sont arrêtés après à la liste des étudiants, sans aller plus loin dans les fonctionnalités demandées. (est-ce que l'intégration leur a pris plus de temps que nécessaire ?) **il me semble important de faire rapidement un point sur ce sujet avec eux.**

- ⛔ **Un rappel sur l'utilisation du fichier .gitignore** semble également le bienvenu pour éviter de pusher des fichiers compromettants sur le repo. (fichier config.ini)

**_Les autres notions n'ayant pas été abordées par tous les apprenants, j'y ferai référence dans les retours individuels. 🙏_**

## Analyse individuelle :

<hr>

### **Apprenant 1** :

Le tableau des tâches parle de lui-même pour cet apprenant qui a presque réalisé toutes les fonctionnalités demandées. Il persiste cependant quelques _points à améliorer_ :

(+) Qualité du code :

1. Architecture du code

- pas de fichier .htaccess
- pas de mise en place des assets
- pas de mise à jour du fichier .gitignore pour le fichier config.ini

2. Maintenabilité et scalabilité

- organisation du code (des méthodes dans les classes)
- convention de nommage

(+) Notions Principales :

3. MVC : 👌

4. Gestion des routes : 👌 (erreur sur 1 route)

5. Affichage des listes (profs et/ou étudiants) : 👌

6. Ajout d'un prof et/ou d'un étudiant :

- l'id n'est pas passé avec la route

```html
<form
  action="<?= $router->generate('teacher_update_post') ?>"
  method="POST"
  class="mt-5"
></form>
```

- pas de requêtes préparées

7. Mise en place de l'authentification

- utilisation de `FILTER_SANITIZE_EMAIL` vs `FILTER_VALIDATE_EMAIL`
- n'a pas utilisé la méthode `bindValue()` sur l'email dans le model

(+) Notions transversales :

8. POO :

Mise en place de méthodes statiques mais il ne les utilise pas forcément dans ses controllers.

```php
$newstudent = new Student();
$studentFromDb = $newstudent->find($studentid);
```

9. ACL :

- plusieurs routes inutiles commentées
- oublie de la route `main-home` et des droits pour l'user sur la route `teacher_list`

10. Validation des données :

les champs de formulaire sont filtrés mais pas d'utilisation systématiques des filtres PHP (ex: `$firstname = filter_input(INPUT_POST, 'firstname');`)

(+) Notions supplémentaires :

11. Héritage : non réalisé 😔

12. Protection CSRF : non réalisée 😔

<hr>

### **Apprenant 2** :

La production rendue par l'apprenant est très incomplète et ne permet pas une évaluation de compétences objectives, toutefois les notions qu'il a abordées semblent plutôt bien maîtrisées. Il persiste cependant quelques _points à améliorer_ :

(+) Qualité du code :

(+) Qualité du code :

1. Architecture du code

- pas de fichier .htaccess
- pas de mise à jour du fichier .gitignore pour le fichier config.ini

2. Maintenabilité et scalabilité

- utilisation d'un chemin relatif pour les assets
- problème de présentation du code
- convention de nommage pas toujours respectée
- peu ou pas de commentaire, beaucoup "notes" inutiles

(+) Notions Principales :

3. MVC : 👌

4. Gestion des routes : 👌

5. Affichage des listes (profs et/ou étudiants) : 👌

6. Ajout d'un prof et/ou d'un étudiant : non réalisé 😔

7. Mise en place de l'authentification : non réalisée 😔

(+) Notions transversales :

8. POO : 👌

9. ACL : non réalisée 😔

10. Validation des données : non réalisée 😔

(+) Notions supplémentaires :

11. Héritage :

- mise en place correct mais partiel de l'abstraction compte-tenu de l'avancement des modèles

12. Protection CSRF : non réalisée 😔

<hr>

### **Apprenant 3** :

L'apprenant fait preuve de bonne volonté mais ses connaissances sont fragiles. Il ne semble pas maîtriser toutes les notions qu'il utilise (copier/coller ?).

(+) Qualité du code :

1. Architecture du code

- pas de fichier .htaccess
- pas de mise en place des assets
- pas de mise à jour du fichier .gitignore pour le fichier config.ini

2. Maintenabilité et scalabilité

- problème de présentation du code et de passages à la ligne
- peu ou pas de commentaire, beaucoup "notes" inutiles

(+) Notions Principales :

3. MVC :

- l'intégration HTML n'a pas été réalisée. L'intégralité du fichier à été ajouté. 😔
- pas de mise en place de CoreController (methode show() dans le MainController)

4. Gestion des routes :

- plusieurs routes ne respectent pas le fichier de routes fourni

5. Affichage des listes (profs et/ou étudiants) : 👌

6. Ajout d'un prof et/ou d'un étudiant :

- informations sur les profs n'ont passées dans la vue du formulaire d'ajout d'un étudiant
- requête SQL incomplète pour l'ajout d'un étudiant (manque le teacher_id)
- pas de requêtes préparées
- oublies de modification du code copier/coller de l'ajout d'un étudiant dans le TeacherController
- fonctionalité non terminée

7. Mise en place de l'authentification : non réalisée 😔

(+) Notions transversales :

8. POO : 👌 (mise en place et utilisation de l'abstraction pour la méthode findAll())

9. ACL : non réalisée 😔

10. Validation des données : 👌

(+) Notions supplémentaires :

11. Héritage : 👌 (pour la méthode findAll())

12. Protection CSRF : non réalisée 😔

<hr>

### **Apprenant 4** :

Il y a un manque d'organisation dans le code de l'apprenant. J'ai le sentiment qu'il a copié/collé du code sans forcément le comprendre. J'aimerai penser que c'est du à un souci récent de compréhension mais plusieurs éléments me font penser que ce n'est pas le cas.

**⚠ Je souhaiterai pouvoir faire un point pour déterminer ensemble la raison ou le moment du "décrochage". ⚠**

(+) Qualité du code :

1. Architecture du code

- pas de fichier .htaccess
- pas de mise en place des assets
- pas de mise à jour du fichier .gitignore pour le fichier config.ini
- présence de fichiers inutiles et compromettants dans le App/Utils (data.sql, structure.sql)
- fichier composer.phar à la racine du projet **A réinstallé composer ou ne maitrise pas l'installation des dépendances ?**
- absence de fichiers qui sont appelés dans le code (MainController.php, ...)

2. Maintenabilité et scalabilité

- Présence de commentaires/notes issus de C/C sans rapport avec le projet
- convention de nommage pas toujours respectée
- Adaptation des méthodes C/C incomplète (ex : `teachersEdit`dans StudentsController)

(+) Notions Principales :

3. MVC :

- l'ensemble des controllers étendent du CoreController qui n'existe pas

4. Gestion des routes :

- plusieurs routes ne respectent pas le fichier de routes fourni
- toutes les routes sont définies dans le fichier index.php mais les fonctionnalités ne sont pas toutes implémentées

5. Affichage des listes (profs et/ou étudiants) :

- commentaire inapproprié
- Instanciation incorrecte des modèles

```php
$teachersModel = new Teachers
teachers();
```

6. Ajout d'un prof et/ou d'un étudiant :

- récupération des données du formulaire incomplète (juste le prénom est récupéré pour l'ajout d'un étudiant)
- la vue pour l'ajout d'un professeur n'a pas été dynamisée

7. Mise en place de l'authentification

- copier/coller ?

(+) Notions transversales :

8. POO : 🤔

9. ACL : non réalisée 😔

10. Validation des données : 👌 (complète dans l'UserController)

(+) Notions supplémentaires :

11. Héritage : 👌 (mise en place de l'abstraction complète)

12. Protection CSRF : non réalisée 😔
