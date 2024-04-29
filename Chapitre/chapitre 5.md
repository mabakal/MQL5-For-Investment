### Les fonctions

Une fonction est un bloc de code autonome qui effectue une tâche spécifique lorsqu'elle est appelée. En programmation, les fonctions sont utilisées pour organiser et réutiliser le code, ce qui permet de le rendre plus modulaire, plus lisible et plus facile à maintenir.

Voici quelques caractéristiques des fonctions :

1. **Nom :** Chaque fonction a un nom qui l'identifie. Ce nom est utilisé pour appeler la fonction à partir d'autres parties du code.

2. **Paramètres :** Une fonction peut accepter des paramètres en entrée qui fournissent des valeurs pour être utilisées dans le corps de la fonction. Ces paramètres sont également appelés arguments.

3. **Corps :** Le corps de la fonction contient les instructions et les opérations qui sont exécutées lorsque la fonction est appelée.

4. **Valeur de retour :** Certaines fonctions peuvent retourner une valeur calculée ou un résultat une fois qu'elles ont terminé leur exécution. Cette valeur de retour peut être utilisée dans le reste du programme.

5. **Portée :** Les variables déclarées à l'intérieur d'une fonction sont généralement locales à cette fonction, ce qui signifie qu'elles ne sont accessibles que dans le cadre de cette fonction.

6. **Réutilisation :** Les fonctions peuvent être appelées à partir de différentes parties du programme, ce qui permet de réutiliser le même code pour effectuer des tâches similaires dans différentes situations.

En résumé, une fonction en programmation est un outil puissant qui permet d'organiser et de réutiliser le code de manière efficace. Elle permet d'encapsuler des séquences d'instructions pour effectuer des tâches spécifiques, ce qui contribue à la modularité et à la lisibilité du code.


### Créer une fonction

Pour créer une fonction en MQL5, vous devez suivre ces étapes :

1. **Définir le prototype de la fonction :** Vous devez spécifier le nom de la fonction, les types et les noms des paramètres (le cas échéant) et le type de la valeur de retour (le cas échéant). Le prototype de la fonction est généralement défini en dehors de toute fonction ou bloc de code, souvent juste en dessous des directives de préprocesseur.

2. **Écrire le corps de la fonction :** Vous devez écrire le corps de la fonction entre des accolades `{}`. C'est là que vous mettez les instructions et les opérations que la fonction doit effectuer lorsqu'elle est appelée.

3. **Définir les paramètres (le cas échéant) :** Si votre fonction prend des paramètres en entrée, vous devez les déclarer dans le prototype de la fonction et les utiliser dans le corps de la fonction pour effectuer des calculs ou des opérations.

4. **Spécifier la valeur de retour (le cas échéant) :** Si votre fonction retourne une valeur, vous devez inclure un `return` dans le corps de la fonction pour renvoyer cette valeur. Assurez-vous que le type de la valeur de retour correspond au type spécifié dans le prototype de la fonction.

Voici un exemple simple de création d'une fonction en MQL5 qui calcule la somme de deux nombres :

```mql5
// Prototype de la fonction
double Somme(double a, double b);

// Définition de la fonction
double Somme(double a, double b)
{
    // Corps de la fonction
    double resultat = a + b;
    return resultat;
}

```

### Appel d'une fonction

Pour appeler une fonction en MQL5, vous devez utiliser son nom suivi de parenthèses contenant les arguments nécessaires (s'il y en a). Voici un exemple simple :

Supposons que vous avez une fonction nommée `MaFonction` qui prend deux paramètres, `parametre1` et `parametre2`, et qui ne retourne rien (type de retour `void`). Voici comment vous l'appelleriez :

```mql5
// Déclaration de la fonction
void MaFonction(int parametre1, double parametre2)
{
    // Corps de la fonction
    // Faites quelque chose avec parametre1 et parametre2
}

// Appel de la fonction
int variable1 = 10;
double variable2 = 3.5;
MaFonction(variable1, variable2); // Appel de la fonction avec les valeurs de variable1 et variable2 comme arguments
```

Dans cet exemple, nous définissons d'abord la fonction `MaFonction`, puis nous l'appelons en passant deux variables (`variable1` et `variable2`) comme arguments.

Si la fonction retourne une valeur, vous pouvez la stocker dans une variable. Par exemple, si `MaFonction` renvoie un `double`, vous pouvez écrire :

```mql5
double resultat = MaFonction(variable1, variable2);
```

Cela stockera la valeur renvoyée par `MaFonction` dans la variable `resultat`. Assurez-vous que le type de la variable `resultat` correspond au type de retour de la fonction `MaFonction`.

C'est ainsi que vous appelez une fonction en MQL5, en spécifiant son nom suivi des arguments nécessaires entre parenthèses.

### Paramètres des fonctions


3. **Appeler la fonction avec les arguments appropriés :** Appelez la fonction à partir d'un autre endroit de votre programme en fournissant les valeurs des paramètres requis.

Voici un exemple simple illustrant ces étapes :

```mql5
// Prototype de la fonction
void MaFonction(int parametre1, double parametre2);

// Définition de la fonction
void MaFonction(int parametre1, double parametre2)
{
    // Corps de la fonction
    Print("Valeur de parametre1 :", parametre1);
    Print("Valeur de parametre2 :", parametre2);
}

// Appel de la fonction avec les arguments appropriés
void OnStart()
{
    int variable1 = 10;
    double variable2 = 3.5;
    MaFonction(variable1, variable2); // Appel de la fonction avec les valeurs de variable1 et variable2 comme arguments
}
```

2. Deuxième methode de transmission de paramètre

La deuxième méthode est de passer par référence. Dans c cas, la référence à un paramètre (et pas sa valeur) est passée au paramètre d'une fonction. Dans la fonction, elle est utilisée pour se référer au paramètre actuel spécifié dans l'appel. Cela signifie qu'un changement du paramètre affectera l'argument utilisé pour appeler la fonction.

```mql5
double SecondMethod(int &i,int &j)
  {
   double res;
   i*=2;
   j/=2;
   res=i+j;
   return(res);
  }

void OnStart()
{

   int a=14,b=8;
   Print("a et b avant l'appel :",a," ",b);
   double d=SecondMethod(a,b);
   Print("a et b après l'appel :",a," ",b);
  }

```

### Surcharge de fonction

La surcharge de fonction est une fonctionnalité de la programmation qui permet de définir plusieurs fonctions avec le même nom mais avec des listes de paramètres différentes.


```mql5
  double moyenne(const double & array[],int size)
  {
   if(size<=0) return 0.0;
   double sum=0.0;
   double aver;

   for(int i=0;i<size;i++)
     {
      sum+=array[i];    // Somme des double
     }
   aver=sum/size;       // Divise la somme par le nombre

   Print("Calcul de la moyenne d'un tableau de doubles");
   return aver;
  }

double moyenne(const int & array[],int size)
  {
   if(size<=0) return 0.0;
   double aver=0.0;
   int sum=0;

   for(int i=0;i<size;i++)
     {
      sum+=array[i];     // Somme des entiers
     }
   aver=(double)sum/size;// Division de la somme par la taille
   Print("Calcul de la moyenne d'un tableau d'entiers");
   return aver;
  }
```

### Orgnaiser vos code

Organiser le code est une pratique importante dans le développement de logiciels pour plusieurs raisons :

- **Lisibilité :** Un code bien organisé est plus facile à lire et à comprendre pour vous-même et pour les autres développeurs qui peuvent travailler sur le projet. La structure claire du code facilite la navigation et la compréhension de sa logique.

- **Maintenance :** L'organisation du code facilite la maintenance à long terme. Lorsque le code est bien organisé, il est plus simple d'apporter des modifications, d'ajouter de nouvelles fonctionnalités ou de corriger des bogues sans perturber le fonctionnement du programme.

- **Réutilisabilité :** Un code bien organisé est plus modulaire, ce qui signifie que vous pouvez réutiliser des parties du code dans d'autres projets ou sections du même projet. Cela permet d'économiser du temps et des efforts en évitant de réécrire du code déjà existant.

- **Débogage :** Lorsque le code est organisé de manière logique et structurée, il est plus facile de repérer et de corriger les erreurs (bugs). Les fonctions bien définies et les sections de code clairement séparées permettent de cibler rapidement les problèmes.

- **Collaboration :** Si vous travaillez en équipe sur un projet, une bonne organisation du code facilite la collaboration. Les autres membres de l'équipe peuvent comprendre rapidement votre code, travailler efficacement dessus et contribuer au projet de manière cohérente.

- **Performance :** Bien que l'organisation du code en soi n'ait pas d'impact direct sur les performances d'un programme, elle peut indirectement contribuer à une meilleure performance en permettant une meilleure gestion des ressources et une écriture de code plus efficace.


1. Les includes

Les projet ***includes*** sont destinés à la création de code qui vont vous permettre d'organiser vos code, de les réutilisé ou des les partagés avec d'autre programmeurs. Pour créer un projet include, suivez ces étapes.

