# Réseau - Ethernet Trame

### Problème
Mon ami a encore perdu son mot de passe... Mais cette fois-ci je suis chez lui, connecté à son wifi et j'ai pu récupérer quelque chose : j'ai réussi à capturer sa trame de son ethernet. Que puis-je faier pour retrouver son mot de passe ?

### Méthode

La capture de sa session est, encore une fois, traduite sous forme d'un fichier, ici un fichier `ch12.txt`. Contrairement à avant et sans recherche, cela indique que j'ai un fichier détenant à l'interieur du texte pur et simple de sa trame ethernet de sa connexion, alors cette fois-ci je me demande si trouver des informations utiles est possible...

Ouvrons le fichier dans Notepad 

![ethernet_image_1](https://user-images.githubusercontent.com/91453740/168312040-a02502eb-8d39-4c90-af48-ab01eeea4068.jpg)

Mais qu'est ce que c'est que ce language des dieux ? Encore une fois, on se doute que c'est un codage spécifique et je sais, grâce à mon cursus de mathématique, que c'est de l'hexadécimal (le fait qu'il y ait deux caractères avec des lettres allant de A à F m'ont donné le flair). Donc il faudrait encore une fois le décoder mais avant faisons attention : nous sommes ici dans le domaine d'une trame ethernet ce qui veux dire que d'après les documents fourni avec l'exercice, nous pouvons enlever certains octets inutile du fichier pour garder seulement les données de la trame.

![ethernet_image_2](https://user-images.githubusercontent.com/91453740/168312313-10775b97-9b64-4c70-9ed0-e488da7c3189.jpg)

En enlevant les 14 octets inutile, sachant que 1 octet = 1 chiffre hexadécimal, nous avons : 

![ethernet_image_3](https://user-images.githubusercontent.com/91453740/168312593-5625a534-5d4f-4c10-a9b1-97aaeaa3a685.jpg)

Maintentant allons le décoder...

![ethernet_image_4](https://user-images.githubusercontent.com/91453740/168312744-ed1f9c35-e597-43ac-9780-79e808f71c04.jpg)

Nous prenons la clé `Autentification` et le tour est joué :

![ethernet_image_5](https://user-images.githubusercontent.com/91453740/168312962-dd3dbcc5-e03f-400b-9bfb-9992764fa5c0.jpg)

Et voilà, le secret est enfin révélé !

### Solution 

Le code de cet exercice est donc : **confi:dential**.




