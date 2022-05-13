## Javascript - Obfuscation 3

L'orsque l'on lance le challenge une page s'ouvre avec un popup demandant un mot de passe. l'objectif est tout simplement de trouver le mot de passe sur la page en question. Cependant pour le moment nous ne connaissont pas le dis mot de passe, nous pouvons donc fermer le popup.

On se tourne alors très vite vers le code source de la page. une ligne en particulier attire très vite l'oeuil : 

![rootme6](https://user-images.githubusercontent.com/81105172/168317778-0897091c-1b9e-43a4-962d-5680d2e694e4.PNG)

cette ligne appel à se faire décoder, cela sans aucun doute. Cependant elle n'est pas utilisiable dans l'état, on peut voir plus haut dans le code qu'il nous faudrait plustôt une suite de chiffres. Alors comment allons nous traduire cette ligne? 
En la copiant dans la console entre deux guillemets voila notre ligne de chiffres qui s'affiche :

![rootme7](https://user-images.githubusercontent.com/81105172/168318612-2e672f48-8609-4e18-84f8-aa095afabd57.PNG)

on peut donc procoder à la suite du processus. Comme dans le code, nous allons utiliser la fonction String.fromCharCode pour récupérer le mot de passe :

![rootme8](https://user-images.githubusercontent.com/81105172/168319073-56433355-6943-4757-891b-2f81147bf64d.PNG)

et voila notre mot de passe est "786OsErtk12", nous pouvons donc completer le challenge.
