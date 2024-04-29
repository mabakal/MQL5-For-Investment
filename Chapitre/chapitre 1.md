#### Les concepts de bases en programmation

En MQL5, les types de données sont similaires à ceux que l'on trouve dans d'autres langages de programmation comme C++ ou Java. Voici une liste des types de données les plus couramment utilisés en MQL5:

#### Les types primitifs

1. **Entiers** :
   - `int` : Entier signé de 32 bits. Peut être positif, négatif ou nul.
   - `uint` : Entier non signé de 32 bits. Ne peut être que positif ou nul.
   - `long` : Entier signé de 64 bits. Utilisé pour des valeurs plus grandes que ce que `int` peut contenir.
   - `ulong` : Entier non signé de 64 bits.

2. **Flottants** :
   - `double` : Nombre à virgule flottante de 64 bits selon la norme IEEE 754. Utilisé pour stocker des nombres réels.
   - `float` : Nombre à virgule flottante de 32 bits.

3. **Booléens** :
   - `bool` : Type booléen. Peut être `true` (vrai) ou `false` (faux).

4. **Caractères et chaînes de caractères** :
   - `char` : Caractère ASCII unique.
   - `string` : Chaîne de caractères. En MQL5, les chaînes de caractères sont des tableaux de caractères terminés par un caractère nul (`'\0'`).

5. **Tableaux** :
   - Les tableaux sont des collections ordonnées d'éléments du même type de données.
   - Ils peuvent être unidimensionnels, bidimensionnels ou multidimensionnels.

6. **Énumérations (Enumérations)** :
   - `enum` : Type de données permettant de définir un ensemble de constantes nommées.
   - Utile pour définir des états, des modes, des signaux, etc.


7. **Date et heure** :
   - `datetime` : Type de données permettant de stocker des informations sur la date et l'heure.
   - Il s'agit d'un entier non signé de 64 bits représentant le nombre de secondes écoulées depuis le 1er janvier 1970.

#### Les types complexes

En MQL5, comme dans de nombreux langages de programmation modernes, vous pouvez également utiliser des types de données plus complexes pour organiser et manipuler des données de manière plus structurée. Voici quelques types de données complexes couramment utilisés en MQL5 :

1. **Tableaux (Arrays)** :
   - Les tableaux sont des collections ordonnées d'éléments du même type de données. Ils peuvent être unidimensionnels, bidimensionnels ou multidimensionnels. Les éléments d'un tableau sont accessibles via leur indice.
   - Exemple : 
     ```mql5
     int myArray[5]; // Déclare un tableau d'entiers de taille 5
     ```

2. **Structures (Structs)** :
   - Les structures permettent de regrouper plusieurs variables de types différents dans une seule unité. Chaque variable dans une structure est appelée un membre. Les structures sont utiles pour représenter des objets complexes avec plusieurs propriétés.
   - Exemple :
     ```mql5
     struct Point {
         double x;
         double y;
     };
     ```
   
3. **Classes (Classes)** :
   - MQL5 prend en charge la programmation orientée objet avec la définition de classes et d'objets. Les classes sont des modèles pour créer des objets qui contiennent à la fois des données (membres) et des fonctions (méthodes) qui agissent sur ces données.
   - Exemple :
    ```mql5
    class Person {
    private:
        string name;
        int age;

    public:
        void setName(string newName) {
            name = newName;
        }
        void setAge(int newAge) {
            age = newAge;
        }
    };
    ```

4. **Énumérations (Enums)** :
   - Les énumérations permettent de définir un ensemble de constantes nommées. Elles sont utiles pour définir des états, des modes, des options, etc.
   - Exemple :
     ```mql5
     enum Colors {
         RED,
         GREEN,
         BLUE
     };
     ```

### Les types primitifs

En MQL5, vous pouvez déclarer et affecter des valeurs à des variables en même temps. Voici comment vous pouvez le faire :

### Déclaration et affectation de variables :

La déclaration et l'affectation sont deux concepts fondamentaux en programmation, utilisés pour créer des variables et leur attribuer des valeurs, respectivement.

### Déclaration :
La déclaration d'une variable consiste à informer au compilateur que vous allez utiliser une variable avec un certain nom et un certain type de données dans votre programme. Cela réserve un espace mémoire pour la variable. La déclaration se fait en spécifiant le type de données de la variable suivi de son nom.

Exemple:
```mql5
int age; // Déclaration d'une variable nommée 'age' de type entier (int)
```

### Affectation :
L'affectation consiste à attribuer une valeur à une variable déjà déclarée. Cela initialise ou modifie la valeur stockée dans la variable. L'affectation se fait en utilisant l'opérateur d'affectation (`=`) qui prend la valeur à droite de l'opérateur et la stocke dans la variable à gauche de l'opérateur.

Exemple:
```mql5
age = 30; // Affectation de la valeur 30 à la variable 'age'
```

### Les énumérations

Une énumération (enum) est un type de données qui permet de définir un ensemble de valeurs nommées. Ces valeurs sont généralement utilisées pour représenter des options ou des états spécifiques dans un programme. Voici comment déclarer et utiliser une énumération en MQL5 :

### Déclaration d'une énumération :
Pour déclarer une énumération, vous utilisez le mot-clé `enum` suivi du nom de l'énumération et de la liste des valeurs possibles entre accolades `{}`.

```mql5
enum Couleur {
    Rouge,
    Vert,
    Bleu
};
```

Dans cet exemple, nous avons déclaré une énumération appelée `Couleur` avec trois valeurs possibles : `Rouge`, `Vert` et `Bleu`. Chaque valeur est associée à un entier, qui commence par défaut à zéro pour la première valeur, et s'incrémente de un pour chaque valeur suivante.

### Utilisation d'une énumération :
Vous pouvez utiliser une énumération pour déclarer des variables et des paramètres de fonction, et vous pouvez également accéder aux valeurs de l'énumération directement.

```mql5
Couleur maCouleur = Rouge;
Print("Ma couleur préférée est : ", maCouleur); // Affiche "Ma couleur préférée est : 0"
```

Dans cet exemple, nous avons déclaré une variable `maCouleur` de type `Couleur` et lui avons assigné la valeur `Rouge`. Lorsque nous imprimons la valeur de `maCouleur`, elle est affichée comme `0`, car c'est la position de la valeur `Rouge` dans l'énumération (zéro-indexée).

### Attribution de valeurs personnalisées :
Vous pouvez attribuer des valeurs personnalisées aux membres de l'énumération.

```mql5
enum JourDeLaSemaine {
    Lundi = 1,
    Mardi = 2,
    Mercredi = 3,
    Jeudi = 4,
    Vendredi = 5,
    Samedi = 6,
    Dimanche = 7
};
```

Les énumérations sont utiles pour rendre votre code plus lisible, en remplaçant les valeurs numériques arbitraires par des noms significatifs, ce qui facilite la compréhension de votre code.


### Dates

En MQL5, les dates sont représentées par le type de données `datetime`. Le type `datetime` est un entier 64 bits qui représente le nombre de secondes écoulées depuis le 1er janvier 1970 à 00:00:00 heure UTC (temps universel coordonné). Les dates sont largement utilisées dans le trading algorithmique pour effectuer des calculs temporels et pour identifier les moments précis dans le temps.

Voici quelques concepts importants liés aux dates en MQL5 :

1. **Récupération de la date actuelle :**
   Vous pouvez obtenir la date actuelle en utilisant la fonction `TimeCurrent()`, qui renvoie la date et l'heure actuelles sous forme de valeur `datetime`.

   ```mql5
   datetime dateActuelle = TimeCurrent();
   Print("Date actuelle : ", dateActuelle);
   ```

2. **Conversion de la date en chaîne de caractères :**
   Vous pouvez convertir une valeur `datetime` en une chaîne de caractères représentant la date et l'heure à l'aide de la fonction `TimeToString()`.

   ```mql5
   datetime dateActuelle = TimeCurrent();
   string chaineDate = TimeToString(dateActuelle, TIME_DATE);
   Print("Date actuelle : ", chaineDate);
   ```

3. **Opérations sur les dates :**
   Vous pouvez effectuer des opérations arithmétiques sur les dates, telles que l'ajout ou la soustraction d'un certain nombre de secondes, minutes, heures, jours, etc.

   ```mql5
   datetime dateActuelle = TimeCurrent();
   datetime dateDansTroisJours = dateActuelle + 3 * 24 * 60 * 60; // Ajoute trois jours (3 * 24 heures * 60 minutes * 60 secondes)
   ```

4. **Comparaison de dates :**
   Vous pouvez comparer les valeurs `datetime` pour déterminer si une date est antérieure, postérieure ou égale à une autre.

   ```mql5
   datetime date1 = TimeCurrent();
   datetime date2 = date1 + 24 * 60 * 60; // Ajoute un jour à date1
   if (date1 < date2) {
       Print("date1 est antérieure à date2");
   }
   ```

5. **Conversion de chaîne de caractères en date :**
   Vous pouvez convertir une chaîne de caractères représentant une date en une valeur `datetime` à l'aide de la fonction `StringToTime()`.

   ```mql5
   string chaineDate = "2022.01.01 12:00:00";
   datetime date = StringToTime(chaineDate);
   ```
