## Exercice 1: Création d'un module

Créez un module qui expose une fonction qui prend deux nombres en entrée et retourne leur somme.

**Solution:**


```javascript
// dans le fichier sum.js
export function sum(a, b) {
	return a + b;
}
```

## Exercice 2: Importation d'un module

Importez le module de l'exercice précédent dans un autre fichier et utilisez la fonction `sum()` pour ajouter deux nombres.

**Solution:**

```javascript
// dans le fichier main.js
import { sum } from './sum.js';
console.log(sum(2, 3)); // affiche 5
```

## Exercice 3: Exportation multiple

Créez un module qui expose deux fonctions: une fonction qui calcule la surface d'un cercle en fonction de son rayon et une fonction qui calcule le périmètre d'un cercle en fonction de son rayon.

**Solution:**

```javascript
// dans le fichier circle.js
export function computeCircleArea(radius) {
	return Math.PI * radius ** 2;
}
export function computeCirclePerimeter(radius) {
	return 2 * Math.PI * radius;
}
```

## Exercice 4: Importation multiple

Importez le module de l'exercice précédent dans un autre fichier et utilisez les deux fonctions pour calculer la surface et le périmètre d'un cercle.

**Solution:**


````javascript
// dans le fichier main.js
import { computeCircleArea, computeCirclePerimeter } from './circle.js';
const radius = 5;
console.log(`La surface du cercle est: ${computeCircleArea(radius)}`);
console.log(`Le périmètre du cercle est: ${computeCirclePerimeter(radius)}`);
````

## Exercice 5: Gestion des dépendances avec npm

Installez le package `axios` à l'aide de `npm` et utilisez-le pour effectuer une requête GET sur une API publique de votre choix.

**Solution:**

```javascript
// dans le fichier main.js
import axios from 'axios';
axios.get('https://jsonplaceholder.typicode.com/posts/1')
.then(response => console.log(response.data))
.catch(error => console.error(error));
```

Cet exercice suppose que vous avez accès à internet et que l'API publique `https://jsonplaceholder.typicode.com` est en ligne.