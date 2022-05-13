## CSFR 0 protection

On cherche à activer notre compte pour activer l'espace privé de l'intranet. Une fois sur la page d'acceuil on se register puis on se login.

![rootme1](https://user-images.githubusercontent.com/81105172/168243766-b06a27cd-ebb5-4d5b-a0aa-4c46f370cfd7.PNG)

une fois cette étape passée nous gagnons l'accès à de nouvelles pages, la page contact :

![rootme2](https://user-images.githubusercontent.com/81105172/168244176-8e8305f7-6fbd-4133-861e-8e211b5f1e9c.PNG)

et la page profile:

![rootme3](https://user-images.githubusercontent.com/81105172/168244236-b5e4105d-4e69-4b7c-bc7e-fbf64920217b.PNG)

en observant le code source de la page profile, on observe que celle-ci correspond à un forms permettant de post des informations à l'intranet, hors nous ne pouvons pas checkez la case de status nous même ni submit le forms. 
On vas alors envoyer le forms directement par message et ce via l'onglet contact. On vas retoucher légèrement le code du forms, mettant l'url complet et en ajoutant l'argument "checked" au chackbox et nous allons rajoutant un element script pour l'appeler.
on as donc le code ci-dessous :

<form id="form" action="http://challenge01.root-me.org/web-client/ch22/?action=profile" method="post" enctype="multipart/form-data">
	<input type="text" name="username" value="zeobuilder10">
	<input type="checkbox" name="status" checked >
	<button type="submit">Submit</button>
</form>
<script>document.getElementById("form").submit()</script>

soit :

![rootme4](https://user-images.githubusercontent.com/81105172/168245319-5246781b-3a23-49e7-8106-cd7e75c7b8c6.PNG)

On appuie alors sur submit et c'est gagnée, il suffit d'aller dans l'onglet Private pour récupérer le code et compléter l'exercice.

![rootme5](https://user-images.githubusercontent.com/81105172/168245509-c41d9ebc-d1e9-4aa6-867a-99297265c611.PNG)
