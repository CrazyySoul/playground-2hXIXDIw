# Welcome!

This Java template lets you get started quickly with a simple one-page playground.

```java runnable
import java.text.NumberFormat;

//Classe abstraite dessert.
public abstract class Dessert
{
private String libelle;// Libellé du dessert.
private double prix;// Prix du dessert.

// Accesseurs en lecture pour le libellé et le prix.
public String getLibelle() {
	return libelle;
}
public double getPrix()
{
	return prix;
}

// Accesseurs en écriture pour le libellé et le prix.
protected void setLibelle(String libelle)
{
	this.libelle = libelle;
}
protected void setPrix(double prix)
{
	this.prix = prix;
}

// Méthode utilisée pour l'affichage d'un dessert.
public String toString()
{
	NumberFormat format=NumberFormat.getInstance();
	format.setMinimumFractionDigits(2);// 2 chiffres après la virgule suffisent pour l'affichage.
	return getLibelle()+" : "+format.format(getPrix())+"€";
}
}

public class Crepe extends Dessert {
	// Constructeur qui initialise le libellé et le prix.
    public Crepe()
    {
            setLibelle("Crêpe");
            setPrix(1.50);
    }
}

public class Gaufre extends Dessert {
	 // Constructeur qui intialise le libellé et le prix.
    public Gaufre()
    {
            setLibelle("Gaufre");
            setPrix(1.80);
    }
}

public abstract class DecorateurIngredient extends Dessert {
	protected Dessert dessert;// Dessert sur leuquel on applique l'ingrédient.
    
    // On oblige les ingrédients à implémenter la méthode getLibelle().
    public abstract String getLibelle();
    // On oblige les ingrédients à implémenter la méthode getPrix().
    public abstract double getPrix();
}

public class Chocolat extends DecorateurIngredient {

	 // Constructeur qui prend en paramètre le dessert.
    public Chocolat(Dessert d)
    {
            dessert = d;
    }
    
    // On affiche le libellé du dessert et on rajoute le libellé de l'ingrédient chocolat.
    public String getLibelle()
    {
            return dessert.getLibelle()+", chocolat";
    }
    
    // On additionne le prix du dessert et le prix de l'ingrédient chocolat.
    public double getPrix()
    {
            return dessert.getPrix()+0.20;
    }

}

public class Chantilly extends DecorateurIngredient {
	// Constructeur qui prend en paramètre le dessert.
    public Chantilly(Dessert d)
    {
            dessert = d;
    }
    
    // On affiche le libellé du dessert et on rajoute le libellé de l'ingrédient chantilly.
    public String getLibelle()
    {
            return dessert.getLibelle()+", chantilly";
    }
    
    // On additionne le prix du dessert et le prix de l'ingrédient chantilly.
    public double getPrix()
    {
            return dessert.getPrix()+0.50;
    }

}

//Classe principale de l'application.
public class Main
{
     // Méthode principale.
     public static void main(String[] args)
     {
             // Création et affichage d'une gaufre au chocolat.
             Dessert d1 = new Gaufre();
             d1 = new Chocolat(d1);
             System.out.println(d1);
             // Création et affichage d'une crêpe au chocolat et chantilly.
             Dessert d2 = new Crepe();
             d2 = new Chocolat(d2);
             d2 = new Chantilly(d2);
             System.out.println(d2);
             
             Dessert d3 = new Crepe();
             d3 = new Chocolat(d3);
             System.out.println(d3);
     }
}




```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Java template](https://tech.io/select-repo/385)
