On voit dans le travail que tu m'as rendu que tu as bien compris le concept général du **MCD** 💪 !

C'est une très bien d'avoir pensé à ajouter la contextualisation de ton projet, cela permet de mieux suivre ton schéma et de comprendre ta réflexion 👍

> 🎁 Tips : tu pourrais l'écrire sous forme de tableau, ou de liste et y ajouter de la mise en forme (mettre en italique les entités, en majuscule les verbes et en gras les cardinalités par exemple) pour en **faciliter la lecture**, mais ce n'est pas obligatoire.
>
> Par exemple : Un _utilisateur_ peut PASSER **aucune ou plusieurs** _commandes_.
>
> Et n'hésite pas à écrire également la relation dans l'autre sens :
>
> Une _commande_ peut être PASSEE **un et un seul** _utilisateur_.

<hr>

J'ai remarqué que tu as ressenti le besoin d'y faire figurer la fonctionnalité correspondante, c'est une bonne idée, mais tu peux le faire dans une partie à part, pour ne pas surcharger ta contextualisation ou :

> 🎁 Tips : ...En introduction.
>
> Par exemple :
>
> Un utilisateur pourra liker un mug en cliquant sur le bouton "j'aime" sur la page du produit.
>
> - Un _utilisateur_ peut AIMER **aucun ou plusieurs** _produit_.
> - Un _produit_ peut être AIMÉ par **aucun ou plusieurs** _utilisateur_.
>
> (...)

<hr>

Tu as su trouver les bonnes entités et les bonnes relations, c'est très bien 👍 !
Comme tu l'as appris en formation, on définit une relation en utilisant un VERBE, le top serait d'utiliser un VERBE D'ACTION et de ne pas le conjuguer (ça laisse la possibilité de lire la relation dans les deux sens 😉). Par exemple, on ne dira pas "Un utilisateur peut avoir une adresse", mais "Un utilisateur peut AJOUTER une adresse".

> 🎁 Tips : si tu manques d'inspiration, tu peux utiliser ton moteur de recherche préféré, en tapant "verbe d'action" ou "liste de verbes d'action" et tu trouveras des listes de verbes d'action qui pourront t'aider à trouver les bons verbes pour tes relations. Voilà un exemple que j'utilise personnellement : [liste de verbes d'actions](https://www.acsoe.com/liste-verbes-action/)

<hr>

😱 Cachez cet ID que je ne saurais voir ! 😱

Le **MCD** est un schéma **C**onceptuel, il ne doit donc pas contenir de données techniques (comme les id, les dates de création, etc.). Il doit être le plus générique possible.

Mais ne t'inquiète pas, l'ID n'a pas disparu, il reviendra plus tard quand les données techniques seront ajoutées dans le **MLD**.

> 🎁 Tips : Si ton entité à besoin d'une propriété pour avoir des enregistrements "uniques", tu peux par exemple utiliser la nomenclature `CODE_PRODUCT`.

> 🎁 Plus de tips 😱 ? Ok...
>
> Tu pourrais indiquer dans ton schéma la propriété qui a cette particularité (**le déterminant**) en la soulignant pour la distinguer plus rapidement. Par exemple dans le cas d'un utilisateur, on pourrait ne pas mettre de propriété supplémentaire et souligner son email 😉

<hr>

Puisqu'on discute des propriétés des entités, même si elles sont très intimement liées au projet que tu développes, elles doivent être les plus exhaustives (complètes) possibles. C'est pourquoi il faut te poser le maximum de question et imaginer tous les scénarios possibles.

Par exemple :

Quelles sont les informations présentent dans une adresse de livraison ? (nom et prénom, rue, etc...)

💡 A ce sujet, il y a quelques fautes d'orthographe dans ton entité adresse, n'hésites pas à bien relire et à utiliser un traducteur en ligne si besoin.

D'autres exemples :

- Est-ce que l'utilisateur va forcément se faire livrer le mug chez lui, donc est-ce que le nom de l'utilisateur est obligatoirement celui dans l'adresse de livraison ?
- Du coup comment faire le lien entre l'adresse de livraison et la commande ?
- ...

> 🎁 Tips : je te conseille de faire une liste de toutes les propriétés que tu imagines pour chaque entité au brouillon au fur et à mesure de tes interrogations, et de t'inspirer d'exemple de la vie courante (autres sites d'Ecommerce).

<hr>

Tu as bien indiqué des cardinalités pour chaque relation, c'est très bien 👍 !
Si tu suivis les conseils précédents (écrire les relations dans les deux sens sous forme de liste, imaginer/lister tous les cas de figure,...), tu remarqueras que certaines relations n'ont pas la bonne cardinalité 🤔. Tu veux un indice ? On peut traduire "Many To Many" par "plusieurs à plusieurs"😉

<hr>

**En résumé :**

Tu as compris le concept général du **MCD**, tu as su trouver les bonnes entités et mettre en place les relations, c'est très bien 👍 ! Il faut maintenant que tu travailles sur les propriétés de tes entités et sur les cardinalités de tes relations.
Je te laisse améliorer ton travail et je reste disponible si tu as besoin de plus d'explication, n'hésite pas à me contacter en MP, je serai ravi de t'aider 😊

Tu peux aussi, avant de te lancer, relire la fiche Kourou pour t'aider : [MCD / Modèle Conceptuel de Données](https://kourou.oclock.io/ressources/fiche-recap/mcd-modele-conceptuel-de-donnees/)

> 🎁 Tu reprendras bien un dernier tips : tout refaire à la main est un bon exercice, mais il vaut mieux s'habituer à utiliser des outils spécialisés pour être paré à affronter des gros projets, alors tu peux aussi utiliser un outil en ligne pour t'aider 😅. Voici quelques exemples :
>
> - [draw.io](https://www.draw.io/)
> - [Mocodo](https://mocodo.net/)
> - [GitMind](https://gitmind.com/fr/)
> - [Lucidchart](https://www.lucidchart.com/pages/fr)
> - [Visual Paradigm](https://www.visual-paradigm.com/)

Bon courage pour la suite 💪 !
