# Bonjour !

Bienvenue sur notre tech.io ! Dans cette presentation nous allons vous parler du **design pattern Decorator**.

# Problematique

On connait tous la manière classique d'ajouter des méthodes à un objet ou modifier son comportement sans toucher à la classe mère : l'héritage !

![Image Heritage](herit2.jpg)

Mais on peut vite se retrouver avec un modele complexe avec beaucoup de classes.
![Classes](Classes.PNG)

De plus on ne pourra pas ajouter de fonctionnalités de façon dynamique. En effet, une fois le programme compile on ne peut pas le modifier.


Comment faire pour ajouter des fonctionnalités de façon dynamique à un de nos objets sans utiliser autant de classes ?
