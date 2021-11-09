Année: 2021-2022
----------------

### Travaux pratiques 2

#### Objectifs

-   Comprendre les opérateurs, les tableaux, les pointeurs et les
    structures.

#### Exercice 2.1 [★]


Écrivez le code *puissance.c* qui prend deux entiers **a** et **b** et
qui affiche la valeur du nombre **a** élevé à une puissance **b**. Par
exemple, puissance(2,3) affiche la valeur 8. N'utilisez pas la fonction
*pow()* (math.h).

```c
#include <stdio.h>
#include <math.h>

int main(){
    int val1;
    int val2;
    printf("Valeure 1? ");
    scanf("%i",&val1);
    printf("Valeure 2? ");
    scanf("%i",&val2);
    int puissance = round(pow(val1,val2));
    printf("Puissance : %d\n", puissance);
    return 0;
}


```
#### Exercice 2.2 [★]


Considérez un entier d (**int d ;**). Écrivez le code *bits.c* qui
vérifie si les 4eme et 20eme bits de **gauche** sont 1 (en binaire). Si
les deux bits sont 1, il affiche 1 sinon 0.


#### Exercice 2.3 [★]


La suite de Fibonacci est une suite d'entiers définie comme suit :

-   U0=1
-   U1=1
-   Un= Un-1 + Un-2

Écrivez le code *fibonacci.c* qui affiche les n termes de la suite de
Fibonacci U0, U1, U2,...Un.


#### Exercice 2.4 [★★]


Sans utiliser les bibliothèques standards ou externes (par exemple
string.h), écrivez le code *chaine.c* qui

1.  calcule le nombre de caractères dans une chaine de caractères
2.  copie une chaine de caractères dans une autre chaine de caractère
3.  concatène deux chaines de caractères


#### Exercice 2.5 [★★]


Imaginez que vous gérez les notes de cinq étudiant.e.es. En utilisant
seulement des tableaux, écrivez un programme *etudiant.c* qui déclare,
initialise et affiche les détails de ces cinq étudiant.e.es. Pour chaque
étudiant.e, on est intéressé par son nom, son prénom, son adresse, et
ses notes dans 2 modules (Programmation en C, Système d'exploitation).

```c

#include<stdio.h>
#include<string.h>

struct student
{
    int note_progC;
    char nom[100];
    char prenom[100];
    char adresse[100];
    int note_systeme;
};
int main(void)
{
    int counter;
    struct student student_fiche[5];

    printf("fiche etudiant : \n");

    for(counter=0; counter<5; counter++)
    {
        printf("\n nom:");
        scanf("%s",&student_fiche[counter].nom);
        printf("\n prenom:");
        scanf("%s",&student_fiche[counter].prenom);
printf("\n adresse:");
        scanf("%s",&student_fiche[counter].adresse);
        printf("\n note en systeme exploitation:");
        scanf("%d",&student_fiche[counter].note_systeme);
        printf("\n note en prog en C:");
        scanf("%d",&student_fiche[counter].note_progC);
    }

    printf("\n La liste des etudiants:");

    for(counter=0; counter<5; counter++)
    {
        printf("\n L'etudiant  nom:%s\t prenom:%s\t Adresse :%s\t systeme exploitation: %d\t programation : %d\n ",
               student_fiche[counter].nom,student_fiche[counter].prenom,student_fiche[counter].adresse,student_fiche[counter].note_systeme,student_fiche[counter].note_progC);
    }
    return 0;
}
```


#### Exercice 2.6 [★★]


Écrivez un programme *etudiant2.c* pour la gestion de données
étudiant.e.es (5 étudiant.e.es) en utilisant struct. Les détails pour
chaque étudiant.e restent les mêmes comme pour l'exercice précédente
(nom, prénom etc.). Vous pouvez utiliser strcpy pour initialiser les
noms, prénoms etc.

```c

#include <stdio.h>
#include <string.h>
 
struct Student {
   char  nom[50];
   char  prenom[50];
   char  adresse[100];
   int   note_C;
   int   note_systeme;
} student;
 
int main( ) {

   struct Student eleve1;        /* Déclare student de type eleve 1 */
   
   strcpy (eleve1.nom,"re\t");
   strcpy (eleve1.prenom,"lena\t");
   strcpy (eleve1.adresse,"rue de fire\t\n");
   eleve1.note_C=12;
   eleve1.note_systeme=8;

   /* afficher les informations du eleve 1 */
   printf( "nom: %s", eleve1.nom);
   printf( "prenom: %s", eleve1.prenom);
   printf( "adresse: %s", eleve1.adresse);
   printf( "note en C: %d\t", eleve1.note_C);
   printf( "note en systeme exp: %d\t\n", eleve1.note_systeme);
   printf("----------------------------\n");

 struct Student eleve2;        /* Déclare student de type eleve2 */
   
   strcpy (eleve2.nom,"dupont\t");
   strcpy (eleve2.prenom,"jean\t");
   strcpy (eleve2.adresse,"rue de la feuille\t\n");
   eleve2.note_C=6;
   eleve2.note_systeme=18;

   /* afficher les informations du eleve 2 */
   printf( "nom: %s", eleve2.nom);
   printf( "prenom: %s", eleve2.prenom);
   printf( "adresse: %s", eleve2.adresse);
   printf( "note en C: %d\t", eleve2.note_C);
   printf( "note en systeme exp: %d\t\n", eleve2.note_systeme);
printf("----------------------------\n");

struct Student eleve3;        /* Déclare student de type eleve3 */
   
   strcpy (eleve3.nom,"roy\t");
   strcpy (eleve3.prenom,"lola\t");
   strcpy (eleve3.adresse,"allee montmartre\t\n");
   eleve3.note_C=14;
   eleve3.note_systeme=10;

   /* afficher les informations du eleve 3 */
   printf( "nom: %s", eleve3.nom);
   printf( "prenom: %s", eleve3.prenom);
   printf( "adresse: %s", eleve3.adresse);
   printf( "note en C: %d\t", eleve3.note_C);
   printf( "note en systeme exp: %d\t\n", eleve3.note_systeme);
        printf("----------------------------\n");

struct Student eleve4;        /* Déclare student de type eleve4 */
   
   strcpy (eleve4.nom,"vanns\t");
   strcpy (eleve4.prenom,"adrien\t");
   strcpy (eleve4.adresse,"avenue duman\t\n");
   eleve4.note_C=10;
   eleve4.note_systeme=11;

   /* afficher les informations du eleve 4 */
   printf( "nom: %s", eleve4.nom);
   printf( "prenom: %s", eleve4.prenom);
   printf( "adresse: %s", eleve4.adresse);
   printf( "note en C: %d\t", eleve4.note_C);
   printf( "note en systeme exp: %d\t\n", eleve4.note_systeme);
        printf("----------------------------\n");

struct Student eleve5;        /* Déclare student de type eleve5 */
   
   strcpy (eleve5.nom,"LORIS\t");
   strcpy (eleve5.prenom,"jeanne\t");
   strcpy (eleve5.adresse,"avenue vauxis\t\n");
   eleve5.note_C=4;
   eleve5.note_systeme=15;

   /* afficher les informations du eleve 5 */
printf( "nom: %s", eleve5.nom);
   printf( "prenom: %s", eleve5.prenom);
   printf( "adresse: %s", eleve5.adresse);
   printf( "note en C: %d\t", eleve5.note_C);
   printf( "note en systeme exp: %d\t\n", eleve5.note_systeme);
        printf("----------------------------\n");

   return 0;
}

```


#### Exercice 2.7 [★★]


Une couleur en format RGBA contient 4 valeurs : rouge (R), vert (G),
bleu (B) et alpha (A). Chaque valeur est un octet. Créez un programme
*couleurs.c* en utilisant struct. Ensuite, créer et initialiser un
tableau de 10 couleurs. Pensez à initialiser les coleurs en notation
hexadécimale (r : 0xef, g : 0x78 etc.).


#### Exercice 2.8 [★★]


Réutiliser le programme *variables.c* et créez un programme
*ptrvariables.c* qui affecte et affiche les valeurs des variables de
différents types de base (char, short, int, long int, long long int,
float, double, long double) en utilisant leurs adresses. N'oubliez pas
d'afficher l'adresse et la valeur de ces variables avant ou après la
manipulation par leurs adresses (en utilisant les pointeurs).


#### Exercice 2.9 [★★★]


Créez un programme *tableauptr.c* et écrivez le code pour créer deux
tableaux différents : int et float. Remplissez les valeurs aléatoires.
Pour les deux tableaux, si l'indice est divisible par 2, multipliez la
valeur à cette position par 3. N'utilisez pas la notation indicielle
pour parcourir les tableaux (par exemple, i [3], i [5] etc.).
Utilisez les pointeurs.


#### Astuce

-   Pour l'exercice 2.5, pensez à utiliser *(s+i) etc (e.g, si s est
    un pointeur de type int *).

#### Fichiers

*bits.c, chaine.c, couleurs.c, etudiant2.c, etudiant.c, fibonacci.c,
ptrvariables.c, puissance.c, tableauptr.c*

#### Instructions

-   Ne pas oublier les commentaires (nom de fichier, objectif, auteurs,
    , les lignes importantes de code etc.). Les commentaires sont notés.
-   N'oublier pas de mettre à jour le fichier README et ajouter les
    détails concernant votre deuxième exercice.
-   Compte rendu en format .zip en un seul fichier.


