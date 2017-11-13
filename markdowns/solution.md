Définition de la solution

- plusieurs "composantConcret" peuvent hériter de Composant
- Etendre fonctionnalité = décorateur
- decorateur = classe abstraite qui herite de Composant
             = a pour attribut un Composant
             = declare abstraite les methodes dont on veut étendre les fonctionnalités
- ajouter des fonctionnalite à ComposantConcret -> créer DécorateurConcret hérite de Décorateur
- DecorateurConcret redefinie les methodes de Décorateur


Explication détaillée de la solution
- ComposantConcret est emballe dans DecorateurConcret
 
 
Conséquences
- A utiliser lorsque l'application a besoin de beaucoup evoluer
