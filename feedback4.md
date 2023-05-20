## Correction

Globalement, je pense que tu devrais aborder ton projet de manière plus linéaire.

Tu as tendance à vouloir aller trop vite et tu te retrouves avec des fichiers inexistants (exemple: CoreController.php), inutiles (exemple: data.sql et structure.sql dans le dossier Utils) ou incomplets .
Je te conseille de commencer par la mise en place de l'architecture du projet (dossiers et fichiers indispensables pour démarrer ton projet en respectant l'architecture MVC comme tu l'as vu en saison 04). Puis, de ne traiter qu'une seule fonctionnalité à la fois (Par exemple, tu commences par la gestion d'\*une route dans le fichier index.php, puis tu passes à sa gestion de son controller, idem pour la gestion de son model, et enfin à son affichage dans sa vue). Cela te permettra de mieux structurer ton code et de ne pas te perdre dans les différents fichiers de ton projet.
Attention, c'est inportant de vérifier avant de passer à la fonctionnalité suivante, que celle que tu viens de créer fonctionne correctement et veiller à ce qu'elle reste fonctionnelle tout au long de l'écriture de ton projet.

J'ai remarqué que tu avais tendance à faire des copier/coller de code. Je te conseille de faire attention à cela car tu risques de te retrouver avec des erreurs qui seront difficiles à débugger et des morceaux de code inutiles ou qui ne correspondent pas au projet (ex: 'method' => 'products' dans le fichier routes.php). Il faut que tu prennes le temps de bien comprendre ce que tu fais et relire tes copier/coller pour les adapter.

Enfin, j'ai remarqué que tu avais un fichier composer.phar dans ton répertoire racine de ton projet. Peux-être as-tu dû reinstaller composer ? Je te conseille de supprimer ce fichier et de recommencer l'installation de composer en suivant les instructions de la documentation officielle : https://getcomposer.org/download/ dans le répertoire /home/student/ de la VM. Si tu as des questions là dessus, n'hésite pas à me contacter en MP.

<hr>

## En résumé

je te conseille de prendre ton temps et de bien comprendre ce que tu fais. Cela te permettra de mieux structurer ton code et de ne pas te perdre dans les différents fichiers de ton projet.

N'hésite pas à poser des questions en cockpit et à demander à reformuler si tu n'as pas compris quelque chose. Je t'invite à suivre la correction dans un groupe d'ECP et de refaire le parcours en t'aidant de la correction étape par étape (comme je te l'ai suggéré plus haut).

Au boulot, courage ! 💪
