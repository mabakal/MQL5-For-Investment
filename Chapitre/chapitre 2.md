En MQL5, les opérateurs sont des symboles spéciaux qui permettent d'effectuer des opérations sur des variables et des valeurs. Voici une liste des opérateurs couramment utilisés en MQL5 :

### Opérateurs arithmétiques :

Un opérateur arithmétique est un symbole ou un mot-clé utilisé pour effectuer des opérations mathématiques sur des valeurs ou des variables.

- `+` : Addition
- `-` : Soustraction
- `*` : Multiplication
- `/` : Division
- `%` : Modulo (reste de la division entière)

Exemple :
```mql5
int resultat = 10 + 5; // résultat vaut 15
```

### Opérateurs de comparaison :
Ces opérateurs sont utilisé pour effectuer la comparaison entre des variables et des valeurs
- `==` : Égal à
- `!=` : Différent de
- `<` : Inférieur à
- `>` : Supérieur à
- `<=` : Inférieur ou égal à
- `>=` : Supérieur ou égal à

Exemple :
```mql5
bool estSuperieur = 10 > 5; // estSuperieur vaut true
```

### Opérateurs logiques :
Ce sont des opérateur utilisé pour combiné plusieurs comparaison

- `&&` : ET logique
- `||` : OU logique
- `!` : NON logique

Exemple :
```mql5
bool condition = (10 > 5) && (10 < 20); // condition vaut true
```

### Opérateurs d'affectation :
Il sont utilisè pour affecter des valeurs á des variables

- `=` : Affectation simple
- `+=` : Affectation avec addition
- `-=` : Affectation avec soustraction
- `*=` : Affectation avec multiplication
- `/=` : Affectation avec division
- `++` : Incrémentation
- `--` : Décrémentation

Exemple :
```mql5
int a = 10;
a += 5; // a vaut maintenant 15
```

#### Les structures décisionnelles

En MQL5, comme dans de nombreux langages de programmation, vous pouvez utiliser des structures de décision pour prendre des décisions en fonction de conditions spécifiques. Les structures de décision les plus couramment utilisées sont les instructions `if`, `if-else`, `if-else if-else`, et `switch`.

- Il permet d'éffectuer un ensemble d'opération si une ou un ensemble de condition est vérifié

### Structure `if` :
La structure `if` est utilisée pour exécuter un bloc de code si une condition est vraie.

```mql5
if (condition)
{
    // Bloc de code à exécuter si la condition est vraie
}
```

### Structure `if-else` :
La structure `if-else` est utilisée pour exécuter un bloc de code si une condition est vraie et un autre bloc de code si la condition est fausse.

```mql5
if (condition)
{
    // Bloc de code à exécuter si la condition est vraie
}
else
{
    // Bloc de code à exécuter si la condition est fausse
}
```

### Structure `if-else if-else` :
La structure `if-else if-else` est utilisée pour tester plusieurs conditions en cascade.

```mql5
if (condition1)
{
    // Bloc de code à exécuter si la condition1 est vraie
}
else if (condition2)
{
    // Bloc de code à exécuter si la condition2 est vraie
}
else
{
    // Bloc de code à exécuter si aucune des conditions précédentes n'est vraie
}
```

### Structure `switch` :
La structure `switch` est utilisée pour sélectionner l'exécution parmi plusieurs blocs de code en fonction de la valeur d'une expression.

```mql5
switch (expression)
{
    case valeur1:
        // Bloc de code à exécuter si l'expression est égale à valeur1
        break;
    case valeur2:
        // Bloc de code à exécuter si l'expression est égale à valeur2
        break;
    default:
        // Bloc de code à exécuter si l'expression ne correspond à aucune des valeurs précédentes
        break;
}
```


### Les structures répétitifs

Vous disposez de plusieurs structures de répétition (boucles) pour exécuter un bloc de code plusieurs fois. Les structures de répétition les plus couramment utilisées sont les boucles `for`, `while` et `do-while`.

### Boucle `for` :
La boucle `for` est utilisée lorsque le nombre d'itérations est connu à l'avance. Elle est composée de trois parties : l'initialisation, la condition de continuation et l'expression d'itération.

```mql5
for (initialisation; condition; expression d'itération)
{
    // Bloc de code à répéter
}
```

Exemple :
```mql5
for (int i = 0; i < 5; i++)
{
    Print("Valeur de i :", i);
}
```

### Boucle `while` :
La boucle `while` est utilisée lorsque la condition de continuation est vérifiée avant chaque itération. Tant que la condition est vraie, le bloc de code est exécuté.

```mql5
while (condition)
{
    // Bloc de code à répéter
}
```

Exemple :
```mql5
int i = 0;
while (i < 5)
{
    Print("Valeur de i :", i);
    i++;
}
```

### Boucle `do-while` :
La boucle `do-while` est similaire à la boucle `while`, mais la condition est évaluée après chaque itération. Cela garantit que le bloc de code est exécuté au moins une fois, même si la condition est fausse dès le départ.

```mql5
do
{
    // Bloc de code à répéter
}
while (condition);
```

Exemple :
```mql5
int i = 0;
do
{
    Print("Valeur de i :", i);
    i++;
}
while (i < 5);
```
