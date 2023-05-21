## **Spoiler Alert !**

_La notion de fetch sera abordée dans la prochaine saison pour récupérer une ressource en JS alors fais preuve de patience..._
_- ...Non ? Tu tiens vraiment en savoir plus maintenant, c'est sûr ? Très bien, c'est parti pour un petit teasing ! 😎_

## Fetch, c'est quoi ?

<hr>

`Fetch` est une fonction JavaScript utilisée pour récupérer ou envoyer des données (comme une liste de professeurs par exemple 😛).

Cette méthode permet à ton application Web de faire une demande à un serveur via une requête HTTP (mais pas que !) pour aller chercher une donnée en fonction d’une URL (et d'autres paramètres) et de recevoir une réponse que tu pourras traiter ensuite !

## Comment ça marche ?

<hr>

Avant de t'expliquer comment fonctionne cette méthode, il faut d'abord que je te parle de façon synchrone, ce que signifie l'**asynchrone** et de ce qu'est une **promesse**.

### ➕ Synchrone vs Asynchrone

<hr>

Quand un programme est **synchrone**, il lit et exécute les instructions les unes après les autres, dans l'ordre où elles sont écrites, un peu comme si tu lisais un livre (ou cette explication, du moins je l'espère 😅).
Certaines parties du code peuvent être plus longues à s'exécuter que d'autres, voir bloquantes (😱 pas de panique, je t'explique ce que c'est juste après !), et le programme ne passera pas à l'instruction suivante tant que la précédente n'est pas terminée. Et des fois ça peut être long, très long... 😴

par exemple :

```js
/**
 * Fonction synchrone : Simulation d'une tâche longue et bloquante
 */
function tacheBloquante() {
  let debut = Date.now();
  while (Date.now() - debut < 5000) {
    // attendre pendant 5 secondes
  }
  console.log("Fini d'attrendre !");
}

tacheBloquante();
console.log("Je suis la dernière instruction !");

// "Fini d'attrendre !", s'affiche après 5 secondes. Puis s'affiche "Je suis la dernière instruction !" dans la foulée
```

De la même manière, le fait de demander et de récupérer des ressources sur un serveur peut être une tâche longue (quantité de données à récupérer, puissance du serveur, distance entre les machines, ...). Et si tu as plusieurs requêtes à faire, ça peut vite poser un problème ou pire faire fuir ton utilisateur...

Heureusement, il existe une solution : l'**asynchrone** !

Tu l'as compris, à l'inverse du programme synchrone, l'asyncrone ne va pas attendre la fin d'une instruction pour passer à la suivante. Il va lancer l'instruction asynchrone, passer à l'instruction suivante, et revenir à la première instruction quand elle sera terminée.

Par exemple :

```js
/**
 * Fonction asynchrone : Simulation d'une tâche longue et non bloquante
 */
async function tacheNonBloquante() {
  let debut = Date.now();
  while (Date.now() - debut < 5000) {
    // attendre pendant 5 secondes
  }
  console.log("Fini d'attrendre !");
}

tacheNonBloquante();
console.log("Je suis la dernière instruction !");

// "Je suis la dernière instruction !" s'affiche tout de suite, puis "Fini d'attrendre !" s'affiche après 5 secondes
```

**- bon ok du coup "Je suis la dernière instruction !" s'affiche en premier... Mais ce n'est pas grave, tu as compris le principe !**

**- C'est tout ?**

**- Non pas du tout, il y a encore mieux c'est promis !**

### ➕ Les Promesses

<hr>

Une [promesse](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Using_promises) est ce qui va représenter la fin d'une tâche asynchrone. Tu te souviens dans l'explication "Il va lancer l'instruction asynchrone, passer à l'instruction suivante, et revenir à la première instruction quand elle sera terminée." ? Et bien la promesse va permettre de savoir quand la tâche asynchrone est terminée, et de récupérer le résultat de cette tâche. 😎

Pour utiliser une promesse, il faut utiliser la méthode `.then()` qui va prendre en paramètre une fonction qui sera exécutée quand la promesse sera terminée (Allez juste pour la beauté du mot, c'est ce qu'on appelle une fonction **[callBack](https://developer.mozilla.org/fr/docs/Glossary/Callback_function)** ).

par exemple :

```js
/**
 * Fonction asynchrone : Simulation d'une tâche longue et non bloquante
 */
async function tacheNonBloquante() {
  let debut = Date.now();
  while (Date.now() - debut < 5000) {
    // attendre pendant 5 secondes
  }
  console.log("Fini d'attrendre !");
}

tacheNonBloquante().then(() => {
  console.log("Je suis la dernière instruction !");
});

// "Je suis la dernière instruction !" s'affiche après 5 secondes, puis "Fini d'attrendre !" s'affiche dans la foulée
```

**- Ok, mais ce n'est pas encore ça...**

**- Oui, je sais, je sais...**

**- Allez, encore un petit effort !**

### ➕ Fetch

<hr>

Maintenant que l'on a parlé des principes de l'asynchrone et des promesses, je peux enfin t'expliquer le fonctionnement de la méthode `fetch` ! 🙌

Comme je te l'ai écrit plus haut, mais avec maintenant les connaissances que tu as acquises, on peut écrire que : `fetch` est une méthode qui va te permettre de faire une requête HTTP (ou HTTPS !) vers un serveur pour récupérer des données. Elle va retourner une réponse (sous la forme d'une promesse) qui sera résolue quand la requête sera terminée. Tu pourras ensuite utiliser la méthode `.then()` pour traiter le résultat de la requête !

Un exemple ?

```js
fetch("http://localhost:8080/api/teachers")
  .then((response) => response.json())
  .then((data) => {
    // Manipulez les données ici
    console.log(data);
  })
  .catch((error) => {
    // Gérer l'erreur ici
    console.error(error);
  });
```

**- Hey ! Mais c'est quoi ce code !? Ce n'est pas du tout ce qu'on a dit !**

**- En partie si... Sur le principe en tout cas. Allez, encore un petit effort !**

### ➕ Les Promesses (bis)

<hr>

Tu te souviens de la fonction `tacheNonBloquante` ? Et bien, c'est exactement ce que fait `fetch` ! Elle va lancer une tâche asynchrone (la requête HTTP), et retourner une promesse qui sera résolue quand la requête sera terminée. Et comme on l'a vu, on peut utiliser la méthode `.then()` pour traiter le résultat de la requête !

**- Ok, mais pourquoi on a écrit `.then((response) => response.json())` ?**

**- Aaaah...!**

Il faut comprendre que la méthode fetch va renvoyer une promesse qui sera résolue quand la requête sera terminée. Mais cette promesse ne va pas contenir directement les données de la réponse 😱. Elle va contenir un objet de type `Response` qui va contenir des informations sur la réponse (code HTTP, headers, ...). Pour récupérer les données de la réponse, il faut utiliser la méthode `.json()`, qui va retourner une promesse qui sera résolue quand les données seront disponibles.

**- Ok, mais pourquoi on a écrit `.then((data) => { console.log(data); })` ?**

### ➕ Les Promesses (ter) et fin promis !

<hr>

Comme je te l'ai expliqué plus haut, la méthode `json()` également va retourner une promesse ! Et comme on l'a vu, on peut utiliser la méthode `.then()` pour traiter le résultat de la requête ! 😎

**- Euh... on a écrit `.catch((error) => { console.error(error); })` ?**

**- Oui, c'est pour gérer les erreurs !**

### ➕ Catch moi si tu peux ! 🏃‍♂️

<hr>

On va d'abord revoir l'ensemble du cheminement de la méthode `fetch` :

- `fetch` va retourner une réponse sous la forme d'une promesse
- On va utiliser la méthode `.then()` pour traiter le résultat de la requête
- On va utiliser la méthode `.json()` pour récupérer les données de la réponse
- On va utiliser la méthode `.then()` pour traiter les données de la réponse

Nous voilà donc avec une promesse qui va contenir les données de la réponse 💪. Mais il se peut que la requête ne se termine pas correctement (serveur injoignable, erreur de code, ...). Dans ce cas, la promesse sera rejetée et on pourra utiliser la méthode `.catch()` pour gérer l'erreur ! C'est aussi simple que ça ! 😎

**- Ok, mais pourquoi on a écrit `.catch((error) => { console.error(error); })` ?**

Ah oui ! J'ai oublié de te préciser que la méthode `fetch` renvoie un objet `Response` quand la requête est terminée, et un objet `Error` quand la requête a échouée !

## En résumé

<hr>

> Le processus de la méthode fetch() implique :
>
> - d'appeler fetch() avec l'URL de la ressource,
> - d'envoyer une requête asynchrone au serveur,
> - de recevoir la réponse (ou l'erreur),
> - de traiter la réponse et d'utiliser les données dans votre application (ou de gérer l'erreur !).
>
> FINI !

**J'aurais pu te le résumer directement comme ça, mais je n'aurais pas tenu ma promesse !! 😂😂**

<hr>

## Pour aller plus loin quelques ressources :

- https://developer.mozilla.org/fr/docs/Web/API/Fetch_API/Using_Fetch
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing
- https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Using_promises
- https://developer.mozilla.org/en-US/docs/Web/API/Response/json
- https://developer.mozilla.org/fr/docs/Glossary/Callback_function

Et bien sûr, la documentation kourou disponible dans la prochaine saison, à bientôt ! 😎

```
Q: "how do javascript developers break up ?"
A: "They always promise to callback"
```
