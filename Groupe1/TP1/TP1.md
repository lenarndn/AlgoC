Année: 2021-2022
----------------

# Travaux pratiques 1 Renaudin Léna et Reure Antoine

## Objectifs

-   Ecrire, compiler et exécuter les programmes C.

### Exercice 1.1 [★]

 
Créez un fichier *bonjour.c* et écrivez un programme qui affiche
**"bonjour le monde!"** à l'écran. Compilez ce fichier en utilisant
gcc et exécutez le code.

```c
#include <stdio.h>
int main(){
    printf("Bonjour tout le monde!\n");
    return 0;
}
```

### Exercice 1.2 [★]

 
Ecrivez un programme *cercle.c* qui calcule l'aire et le périmètre d'un
cercle

a.  l'aire: Utilisez une variable **rayon** : float ou double

b.  le périmètre: Utilisez une variable **rayon** : float ou double

c.  Compilez *cercle.c* et créez un fichier éxecutable nommé cercle

d.  Exécutez 'cercle'

```c

#include <stdio.h>
#include <math.h>

int main(){
    float rayon = 1;
    printf("Mesure rayon? ");
    scanf("%f",&rayon); //scanf = rend la main ; &=@var ; https://openclassrooms.com/fr/courses/19980-apprenez-a-programmer-en-c/14118-un-monde-de-variables
    float pi = M_PI;
    float aire = rayon * rayon * pi;
    float perim = 2 * rayon * pi;
    printf("%f\n",aire);
    printf("%f\n",perim);
    return 0;
}
```


### Exercice 1.3 [★]

 
Ecrivez un programme *sizeof_types.c* qui affiche la taille des
différents types de base (en octets) :

```c
#include <stdio.h>
//enum type {char,short,int,long int,long long int, float, double, long double};

int main(){
    printf("char: %lu octets\n", sizeof(char));
    printf("int: %lu octets\n", sizeof(int));
    printf("long: %lu octets\n", sizeof(long));
    printf("long long: %lu octets\n", sizeof(long long));
    printf("float: %lu octets\n", sizeof(float));
    printf("double: %lu octets\n", sizeof(double));
    printf("long double: %lu octets\n", sizeof(long double));
return 0;
}
```

### Exercice 1.4 [★★]

 
Ecrivez un programme *variables.c* qui affecte et affiche les valeurs
des variables des différents types de base :

```c
#include <stdio.h>

int main(){
    char str[] = "Hello";
    printf("STR = '%s' Changer string? ",str);
    scanf("%s",str);
    printf("%s\n",str);

    int a = 1;
    short b = 44;
    long c = 1983248;
    float d = 3.14;
    char e = 'E';
    long long int f = 1561561561;
    double h = 6564;
    long double i = 46464;

    printf("char = %c\n", e);
    printf("short = %hd\n", b);
    printf("int = %i\n", a);
    printf("long int = %li\n", c);
    printf("long long int = %lli\n", f);
    printf("float = %f\n", d);
    printf("double = %lf\n", h);
    printf("long double = %Lf\n", i);
return 0;
}

```

### Exercice 1.5 [★★]

 
Ecrivez un programme *opérateurs.c* qui utilise deux variables
suivantes:

i.  **a** = 16

ii. **b** = 3

et testez les différents opérateurs arithmétiques et logiques.

```c

#include <stdio.h>
#include <math.h>

int main(){
    int val1 = 1;
    int val2 = 1;
    printf("Valeure 1? ");
    scanf("%i",&val1);
    printf("Valeure 2? ");
    scanf("%i",&val2);
    int somme = val1 + val2;
    int produit = val1 * val2;
    int puissance = round(pow(val1,val2));
    printf("Somme : %d\n",somme);
    printf("Produit : %d\n",produit);
    printf("Puissance : %d\n", puissance);
 return 0;
}
    

```

### Exercice 1.6 [★★]

 
Ecrivez un programme *boucles.c* qui utilise **for**, # et * et qui
affiche un triangle rectangle. La taille du triangle est dependent de la
valeur de la variable **compter** (**compter** < 4 inacceptable).
Exemple, si **compter** = 5, le programme affiche

```c
#include <stdio.h>

int main(){
    int ligne = 0;
    int x;
    int y;
    printf("Hauteur du sapingue? ");
    scanf("%d",&ligne);
    ligne=ligne-3;
    
    if (ligne == 0-3) {printf("PAS DE SAPIN\n");}
    else if (ligne == 1-3) {printf("*\n");}
    else if (ligne > 1-3) {
        printf("*\n**\n");
        for (y=0 ; y<=ligne ; y++){
            printf("*");
            if (y==ligne) {for(x=0 ; x<=y ; x++){printf("*");}}
            else {for(x=0 ; x<=y ; x++) {printf("#");}}
            printf("*\n");
        }
    }
    return 0;
}
```

Testez le code avec les différentes valeurs de compter. Ecrivez une
nouvelle version du code en utilisant **while** ou **do..while**.


### Exercice 1.7 [★★]

 
Ecrivez un programme *conditions.c* qui utilise les boucles (**for**,
**while** ou **do..while**) et les branchements inconditionnels (break
ou continue) pour l'affichage de numéros <= 1000 qui sont divisible par
:

a.  2 et 15

b.  103 ou 107

c.  7 ou 5, mais pas par 3



### Exercice 1.8 [★★★]

 
Ecrivez un programme *opérateurs2.c* qui utilise trois variables

1.  **num1** (entier)
2.  **num2** (entier)
3.  **op** (un caractère)

La variable **op** contient un de ces différents opérateurs. (+, -, \*,
/, %, &, |, ~). Utilisez **switch** et réutilisez le code de votre
premier exercice. Si c est égal à '+', le programme fait l'addition de
deux variables **num1** et **num2**, si **op** est égal à '&', le
programme fait l'opération ET etc. Rappelez-vous bien que l'on ne peut
pas utiliser chaine de caractères comme condition en **switch**. Testez
votre programme avec différents valeurs de **num1**, num2, **op**

```c
#include <stdio.h>
#include <math.h>

int main(){
    int num1 = 6;
    printf("Num1? "); scanf("%i",&num1);
    int num2 = 5;
    printf("Num2? "); scanf("%i",&num2);
    char ope;
    printf("Opérateur? "); scanf("%c",&ope);
    int res1=num1+num2;
    int res2=num1-num2;
    int res3=num1*num2;
    int res4=num1/num2;
    int res5=num1%num2;

    switch(ope){
        case '+':
            printf("%i",res1); break;
        case '-':
            printf("%i",res2); break;
        case '*':
            printf("%i",res3); break;
        case '/':
            printf("%i",res4); break;
        case '%':
            printf("%i",res5); break;
//        default:
//            printf("Erreur"); break;
    }
    printf("\n");
    return 0;
}

```
#### Exercice 1.9 [★★★]

 
Ecrivez un programme *binaire.c* qui utilise **for** pour l'affichage
d'une variable int en format binaire. Rappelez-vous bien que printf n'a
pas de code de conversion comme x (l'affichage d'un numéro en notation
hexadécimale) ou o (l'affichage d'un numéro en notation octale) pour
l'affichage en notation binaire. Testez votre code avec les 5 numéros
suivants : 0, 4096, 65536, 65535, 1024

```c

#include <stdio.h>

int main()

{
    int n;

    int binary[100];  //tableau
 
    int i=0;

    printf("\nEntrez votre nombre decimal : "); 

    scanf("%d",&n);

    if(n==0){  //si le n est egale a 0 alors...

        printf("Le nombre binaire est : 0");

return 0;

    }


    while(n){   //tant que  n different de 0

      binary[i] = n%2; //modulo

      n = n/2; 

      i++; 

    }
    
    for(i=i-1;i>=0;i--)

    {   

        printf("%d",binary[i]);  //commence par la fin du tableau  

    }

return 0; 

}


```

#### Astuce

-   Utilisez les boucles dans une boucle et **if** (Exercice 1.6)
-   Pour l'exercice 1.9, pensez à utiliser les opérateurs pour la
    manipulation de bits (&, | ou ~)

#### Fichiers

*binaire.c, bonjour.c, boucles.c, cercle.c, conditions.c, opérateurs2.c,
opérateurs.c, sizeof_types.c, variables.c*

#### Instructions

-   Ne pas oubliez les commentaires (nom de fichier, objectif, auteurs
    etc.)
-   Créez README et ajoutez les détails concernant votre premiez
    exercice.

#### Exemple

 
**CONTRIBUTORS**

```             
 1. RENAUDIN Léna
 2. REURE Antoine
`


