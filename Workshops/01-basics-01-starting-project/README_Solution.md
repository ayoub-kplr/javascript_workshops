# Workshop : Créer une calculatrice en HTML et JavaScript

Dans cet atelier, nous allons créer une calculatrice en utilisant HTML et JavaScript. Nous allons couvrir les étapes suivantes :

-   Importer JavaScript dans HTML
-   Utiliser des opérateurs
-   Utiliser des constantes
-   Utiliser des littéraux de gabarit
-   Utiliser une fonction de base
-   Fonction avec retour
-   Fonction d'entrée utilisateur
-   Utiliser parseInt
-   Tableau de base avec push
-   Extraire les éléments du tableau
-   Utiliser des objets

## 1. Importer JavaScript dans HTML

Tout d'abord, nous devons importer notre code JavaScript dans notre page HTML. Pour ce faire, nous allons créer un nouveau fichier appelé `app.js` dans notre répertoire `assets/scripts`. Ensuite, nous allons ajouter le code suivant à notre balise `<head>` :


```html
<script src="assets/scripts/app.js"></script>
```

Cela importera notre fichier JavaScript dans notre page HTML.

## 2. Utiliser des opérateurs

Nous allons utiliser les opérateurs arithmétiques de base pour réaliser nos calculs. Voici les opérateurs que nous allons utiliser :

-   Addition (+)
-   Soustraction (-)
-   Multiplication (*)
-   Division (/)

## 3. Utiliser des constantes

Nous allons utiliser des constantes pour stocker les valeurs des boutons d'opérateur et éviter de les répéter dans notre code. Voici les constantes que nous allons utiliser :


```javascript
const ADDITION = '+';
const SUBTRACTION = '-';
const MULTIPLICATION = '*';
const DIVISION = '/';
```

## 4. Utiliser des littéraux de gabarit

Nous allons utiliser des littéraux de gabarit pour construire notre calcul et notre résultat dans notre page HTML. Les littéraux de gabarit sont une fonctionnalité d'ES6 qui nous permet d'insérer des expressions JavaScript dans une chaîne de caractères.


````javascript
const currentCalculationElement = document.querySelector('#current-calculation');
const currentResultElement = document.querySelector('#current-result'); 
function updateResult(value) {
	currentCalculationElement.textContent = value;
	currentResultElement.textContent = value; 
}  
function addToCalculation(value) {
	const currentCalculation = currentCalculationElement.textContent; 
	currentCalculationElement.textContent = `${currentCalculation} ${value}`;
}
````

## 5. Utiliser une fonction de base

Nous allons créer une fonction de base qui prendra deux arguments et effectuera une opération arithmétique sur ces arguments. Cette fonction retournera le résultat de l'opération.


`function calculate(firstNumber, secondNumber, operator) {   let result;   switch(operator) {     case ADDITION:       result = firstNumber + secondNumber;       break;     case SUBTRACTION:       result = firstNumber - secondNumber;       break;     case MULTIPLICATION:       result = firstNumber * secondNumber;       break;     case DIVISION:       result = firstNumber / secondNumber;       break;     default:       break;   }   return result; }`

## 6. Fonction avec retour

Nous allons créer une fonction qui utilise notre fonction `calculate()` pour effectuer une opération sur les valeurs actuelles de notre calcul et stocker le résultat dans notre élément de résultat.

javascriptCopy code

`function calculateResult() {`const inputNumberElement = document.querySelector('#input-number'); const currentCalculation = currentCalculationElement.textContent; const currentCalculationArray = currentCalculation.split(' '); const firstNumber = parseInt(currentCalculationArray[0]); const secondNumber = parseInt(inputNumberElement.value); const operator = currentCalculationArray[1]; const result = calculate(firstNumber, secondNumber, operator); updateResult(result); }

csharpCopy code

## 7. Fonction d'entrée utilisateur
Nous allons créer une fonction qui sera appelée lorsque l'utilisateur cliquera sur l'un de nos boutons d'opérateur. Cette fonction appellera la fonction `addToCalculation()` pour ajouter le bouton d'opérateur à notre calcul.  ```javascript function handleOperatorClick(event) {   const operator = event.target.textContent;   addToCalculation(operator);   inputNumberElement.value = ''; }``

Nous allons également créer une fonction qui sera appelée lorsque l'utilisateur cliquera sur le bouton d'égalité. Cette fonction appellera la fonction `calculateResult()` pour effectuer le calcul.

javascriptCopy code

`function handleEqualClick() {   calculateResult();   inputNumberElement.value = ''; }`

## 8. Utiliser parseInt

Nous allons utiliser la fonction `parseInt()` pour convertir les valeurs de notre calcul en nombres entiers.

javascriptCopy code

`const firstNumber = parseInt(currentCalculationArray[0]); const secondNumber = parseInt(inputNumberElement.value);`

## 9. Tableau de base avec push

Nous allons utiliser un tableau pour stocker les valeurs de notre calcul. Nous allons ajouter les valeurs à notre tableau en utilisant la méthode `push()`.

javascriptCopy code

`const calculationArray = [];  function addToCalculation(value) {   calculationArray.push(value);   currentCalculationElement.textContent = calculationArray.join(' '); }`

## 10. Extraire les éléments du tableau

Nous allons extraire les éléments de notre tableau en utilisant la méthode `split()`. Cette méthode divise une chaîne de caractères en un tableau de sous-chaînes en fonction d'un délimiteur.

javascriptCopy code

`const currentCalculationArray = currentCalculation.split(' '); const firstNumber = parseInt(currentCalculationArray[0]); const operator = currentCalculationArray[1];`

## 11. Utiliser des objets

Nous allons utiliser un objet pour stocker les valeurs de nos boutons d'opérateur. Cela nous permettra de référencer les valeurs de nos boutons en utilisant des clés plutôt qu'en utilisant des chaînes de caractères.

javascriptCopy code

`const operators = {   ADDITION: '+',   SUBTRACTION: '-',   MULTIPLICATION: '*',   DIVISION: '/' };  function handleOperatorClick(event) {   const operator = operators[event.target.id];   addToCalculation(operator);   inputNumberElement.value = ''; }`

Voici le code complet de notre fichier `app.js`