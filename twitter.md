# Réseau - Autentification Twitter

### Problème
Un ami a perdu son mot de passe. J'ai réussi à capturer sa session d’authentification twitter. 
Comment est-ce que je peux retrouver son mot de passe ?

### Méthode

La capture de sa session est traduite sous forme d'un fichier, plus précisement un fichier `ch3.pcap`. Après quelques recherches, je sais que cette extension indique que j'ai un fichier détenant à l'interieur des paquets venant du réseau de cette session d'authentification de Twitter ainsi je sais que je trouverai surement les informations du compte de mon ami !

![twitter_image_1](https://user-images.githubusercontent.com/91453740/168303961-648a5af6-12b3-470f-a957-16738ec81a26.jpg)

Mais comment avoir accès à ces informations ? Eh bien il suffit d'utiliser WireShark : ce logiciel est un analyseur de protocole réseau et aussi le plus utilisé au monde. On pourra donc alors regarder, grâce à lui, les informations dans ce fichier et pouvoir déduire le mot de passe.

Ouvrons le fichier dans WireShark

![twitter_image_2](https://user-images.githubusercontent.com/91453740/168304175-e5104e93-0c96-4fe9-ac88-48966c8569da.jpg)

Suivons son flux TCP (clique droit. Pourquoi ? Car ce flux TCP est le processus qui établie les règles de connection et transmet donc les donnés de ce fichier `ch3.pcap`. Voyons alors ce qui il a dedans...

![twitter_image_3](https://user-images.githubusercontent.com/91453740/168304628-2c67a6d6-db95-420f-8d36-604246604249.jpg)

![twitter_image_4](https://user-images.githubusercontent.com/91453740/168304643-89dd528b-45a9-408c-9e1b-9db903f0a04f.jpg)

Il n'y à pas l'air d'avoir de mot de passe... Cependant, le mot de passe est bien présent dans ce fichier ! Si on regarde bien son contenu en partant de la requête `GET /statuses/replies.xml HTTP/1.1`, il esr organiser de façon `key: value`. La clé qui nou intéresse est forcement celle `Authorization` qui détient comme valeur `Basic dXNlcnRlc3Q6cGFzc3dvcmQ=`. 

![twitter_image_5](https://user-images.githubusercontent.com/91453740/168304967-2d3316cc-772f-4616-ae2c-67bdff29c032.jpg)

Mmmmhh, cela ne ressemble toujours pas à un mot de passe... Mais partant de cette information, on peut se demander si le `Basic` ne corresponderait pas au codage Basic 64 et que donc l'information serait en Basic 64. Décodons alors  `dXNlcnRlc3Q6cGFzc3dvcmQ=` :

![twitter_image_6](https://user-images.githubusercontent.com/91453740/168305203-9f97844a-0487-49ab-a0f4-d6d2e2bbf904.jpg)

Et voilà, le secret est enfin révélé !

### Solution 

Le code de cet exercice est donc : **password**.




