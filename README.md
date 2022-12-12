# USSI47-TPBonus



### Prérequis
- Cloner le projet sur votre poste dans le repertoire de votre choix
- Ouvrir le projet :
	- Sur l'écran d'accueil d'IntelliJ, cliquer sur **Open**
	- Sélectionner le dossier **tp-xxx** qui a été copié depuis github puis cliqué sur **OK**.
	- Le projet s'ouvre
	- Allez vérifier que le SDK est bien sélectionné dans **File > Project Structure** onglet **Project**

### Utilisation de GIT

- Créer une nouvelle branche **prenomNom**
- Faire **1 commit** par exercice (sauf exercice 0)
- Ouvrir **une seule** *pull request* sur github et **ne pas** la fermer/merger !!

### Exercice

Vous devez réaliser une application de location de véhicules

> Si vous ne l'avez pas encore fait, pensez a créer une nouvelle branche **prenomNom**

Une **Agence** loue 2 types de véhicules :

- des vélos
- des voitures

Une **Voiture** possède :

- une immatriculation (String)
- une marque (String)
- un modele (String)
- un coût fixe à la journée (double)
- Le nom du client qui le loue (String)
- Une puissance

Une voiture doit aussi retourner le coût de location avec la formule : **coût fixe à la journée + (puissance * 10 )**

On doit pouvoir retourner une chaine qui décrit la voiture



Un **Velo** possède :

- une immatriculation (String)
- une marque (String)
- un modele (String)
- un coût fixe à la journée (double)
- Le nom du client qui le loue (String)
- Une indication pour savoir si le velo est électrique ou non (boolean)

Un vélo doit aussi retourner le coût de location avec la formule : **coût fixe à la journée + (10 seulement si le velo est electrique)**

On doit pouvoir retourner une chaine qui décrit le vélo


Une **Agence**, gère donc une 2 collections de véhicules, une pour les véhicules libres et une pour les véhicules louées. On doit pouvoir : 

- Ajouter un nouveau **véhicule**

- Afficher la liste des **véhicules libres** avec leur immatriculation,  marque, modèle, coût fixe à la journée

- Afficher la liste des **véhicules loués** avec leur immatriculation, marque, modèle, coût fixe à la journée et le nom du client qui l'a loué

- Louer un véhicule en fournissant le *nom du client* ainsi que *l'immatriculation du véhicule*. Cette action doit donc :

  - Afficher un message d'erreur si l'immatriculation ne correspond pas a un véhicule libre
  - associer le nom du client au véhicule
  - ajouter le véhicule a la collection des véhicule loués
  - retirer le véhicule de la collection des véhicules libres

- Retourner un véhicule en fournissant *l'immatriculation du véhicule* et le *nombre de jours de location*. Cette action doit donc : 

  - Afficher un message d'erreur si l'immatriculation ne correspond pas a un véhicule loué

  - Afficher le nom du client et le montant total de la location

  - retirer l'association entre le véhicule et le client

  - retirer le véhicule de la collection des véhicules loués

  - ajouter le véhicule a la collection des véhicule libres

    

#### Ecrire sur ordinateur votre proposition de programme pour répondre à ces spécifications

Le code suivant une fois complété doit pouvoir s'exécuter : 

```java
public class Main {
 public static void main(String[] args) {
  Agence a = new Agence();
  a.ajoutNouveauVehicule(new Voiture("ZZ-111-AA", "Renault", "clio", 20, 4));
  a.ajoutNouveauVehicule(new Voiture("XX-222-BB", "Audi", "a4", 80, 10));
  a.ajoutNouveauVehicule(new Voiture("YY-333-CC", "Mercedes", "a4", 300, 11));
  a.ajoutNouveauVehicule(new Velo("123456789", "Gitane", "Verso", 10, false));
  a.ajoutNouveauVehicule(new Velo("223344558", "Gitane", "e-CITY", 10, false));
      
  // Jane Doe loue un véhicule qui n'existe pas
  // Jane Doe loue le véhicule YY-333-CC
  // John Doe loue le véhicule 123456789
  // John Doe ramène le véhicule au bout de 3 jours
  // Jane Doe ramène le véhicule au bout de 7 jours
      
  }
}
```

et afficher le résultat suivant :

```
Cette voiture n'existe pas ou n'est pas disponible
John Doe doit 30.0
Jane Doe doit 2870.0
```
Vous pouvez ajouter d'autres tests dans la classe Main selon vos besoins.

A la fin, n'oublier pas d'envoyer votre travail 

