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

D'une manière générale, je pense que la qualité du code produit est en deça des attentes qu'on l'on pourrait attendre à ce stade de la formation.

- Il persiste pour tous les apprenants quelques maladresses qui n'ont rien de rédhibitoire comme la pertinence de commentaires, ou la mise en forme d'un code qui manque de clarté, ou des conventions de nommage qui ne sont pas respectées.

- Les apprenants semblent avoir compris globalement le principe de l'architecture MVC, il reste des fragilités sur découpage du code (coreController, abstraction...).

- Les modèles ont posé moins de problèmes, bien que l'utilisation de requêtes préparées ne soit pas encore systématique. **Il me semble important de faire un point sur ce sujet avec les apprenants.**

- Plusieurs apprenants (ou au moins une fois chaque apprenant 😱) n'ont pas suivi les indications données dans le fichier docs/routes.md, concernant l'URL des routes. **Il est nécessaire de refaire un point sur ce sujet et/ou de vérifier la compréhension sur ce point dans l'énoncé.**

- L'intégration des vues est globalement correcte.

- La majorité des apprenants se sont arrêtés après à la liste des étudiants, sans aller plus loin dans les fonctionnalités demandées. (est-ce que l'intégration leur a pris plus de temps que nécessaire ?) **il me semble important de faire rapidement un point sur ce sujet avec eux.**

- ⛔ **Un rappel sur l'utilisation du fichier .gitignore** semble également le bienvenu pour éviter de pusher des fichiers comprometants sur le repo. (fichier config.ini)

**_Les autres notions n'ayant pas été abordées par tous les apprenants, j'y ferai référence dans les retours individuels. 🙏_**
