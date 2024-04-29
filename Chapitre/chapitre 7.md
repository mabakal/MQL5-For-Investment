### Un indicateur

Un indicateur fait référence à une formule mathématique appliquée aux données de prix d'un actif financier afin de fournir des informations supplémentaires sur la direction future des prix, la force de la tendance, les niveaux de support et de résistance, la volatilité, et d'autres aspects du marché.
Les indicateurs sont largement utilisés par les traders et les analystes techniques pour prendre des décisions de trading éclairées. 

### Objectifs 

- Nous allons apprendre à utilisé les indicateurs dans notre programme
- À développer notre propre indicateur personnalisé

### Les catégories d'indicateur

1. **Indicateurs de tendance :** Ces indicateurs aident à déterminer la direction générale du marché. Par exemple, les moyennes mobiles, l'indicateur de convergence/divergence de moyennes mobiles (MACD) et l'indicateur de force relative (RSI) sont des exemples d'indicateurs de tendance.

2. **Indicateurs de momentum :** Ces indicateurs mesurent la vitesse et l'ampleur des mouvements de prix. Par exemple, le MACD et l'oscillateur stochastique sont des indicateurs de momentum populaires.

3. **Indicateurs de volatilité :** Ces indicateurs mesurent la volatilité du marché, c'est-à-dire la variabilité des prix. Par exemple, les bandes de Bollinger et l'indicateur de plage moyenne réelle (ATR) sont des indicateurs de volatilité couramment utilisés.

4. **Indicateurs de volume :** Ces indicateurs analysent le volume des transactions pour fournir des informations sur la force d'une tendance ou la probabilité d'un retournement de tendance. Par exemple, l'indice de volume et l'oscillateur de volume sont des indicateurs de volume.

5. **Indicateurs de support et de résistance :** Ces indicateurs identifient les niveaux de prix où le marché a historiquement réagi, ce qui peut aider à anticiper les futurs mouvements de prix. Par exemple, les points pivots et les lignes de tendance sont des indicateurs de support et de résistance.

### Metatrader et les indicateurs

MetaTrader met á notre disposition des indicateurs deja proprammé qu'on peut utilisé. Il facilite les táches des développeur mettant en place les outils pour utiliser les indicateurs. 
Les fonctions comme ``iMa`` qui commence généralement par `i` sont destiné aux indicateur à l'aide de ces fonctions vous pouvez accéder au données de l'indicateure et recevoir le valeur. Cette fonction ne retorune pas directement la valeur de l'indicateur en question, mais plutot un accesseur qui permet d'accéder aux differente valeur de l'indicateur. Ce accesseur est transmis á la une fonction qui s'appèle ``CopyBuffer`` qui est utilisé pour copier les copier les données de l'indicateurs.


### La fonction copyBuffer()
La fonction `CopyBuffer()` est une fonction clé en MQL5 qui est utilisée pour copier les données stockées dans les buffers d'un indicateur personnalisé dans un tableau de données dans votre programme MQL5. Cela vous permet d'accéder aux valeurs de l'indicateur calculées à différentes périodes de temps et de les utiliser dans votre script pour effectuer des calculs supplémentaires, prendre des décisions de trading ou afficher les valeurs de l'indicateur sur le graphique.

Voici la syntaxe de la fonction `CopyBuffer()` :

```mql5
int CopyBuffer(
   int           indicator_handle,  // Handle de l'indicateur personnalisé
   int           buffer_num,        // Numéro du buffer
   int           start_pos,         // Position de départ dans le tableau de destination
   int           count,             // Nombre d'éléments à copier
   double&       buffer_array[]     // Tableau de destination pour les données copiées
   );
```

Paramètres de la fonction :
- `indicator_handle` : Le handle (identifiant) de l'indicateur personnalisé dont vous voulez copier les données de buffer. Ce handle est généralement obtenu à l'aide de la fonction `iCustom()` ou `iIndicatorCreate()`.
- `buffer_num` : Le numéro du buffer que vous souhaitez copier. Les données tampons sont numérotées à partir de zéro, donc le premier buffer a le numéro 0, le deuxième buffer a le numéro 1, etc.
- `start_pos` : La position de départ dans le tableau de destination où vous souhaitez commencer à copier les données.
- `count` : Le nombre d'éléments à copier depuis le buffer de l'indicateur.
- `buffer_array[]` : Le tableau de destination où les données du buffer seront copiées. Ce tableau doit être déclaré avant d'appeler la fonction `CopyBuffer()`.

La fonction `CopyBuffer()` retourne le nombre d'éléments copiés avec succès dans le tableau de destination. Si une erreur se produit, elle retourne -1.


### Créer un indicateur avec IndicatorCreate()


La fonction `IndicatorCreate()` est une fonction en MQL5 utilisée pour créer un indicateur personnalisé dans un programme MQL5. Cette fonction est utilisée dans les scripts, les expert advisors (robots de trading) et les indicateurs personnalisés pour créer un nouvel indicateur basé sur une formule mathématique ou un algorithme spécifique.

Voici la syntaxe générale de la fonction `IndicatorCreate()` :

```mql5
int IndicatorCreate(
   int         handle,            // Handle (identifiant) de l'indicateur personnalisé
   string      name,              // Nom de l'indicateur personnalisé
   ENUM_INDICATOR_TYPE    type,   // Type de l'indicateur
   int         sub_window        // Numéro de sous-fenêtre pour l'affichage de l'indicateur
   );
```

Paramètres de la fonction :
- `handle` : Le handle (identifiant) de l'indicateur personnalisé qui sera utilisé pour faire référence à cet indicateur dans d'autres parties du programme MQL5. Si vous ne spécifiez pas de handle, la fonction en générera automatiquement un pour vous.
- `name` : Le nom de l'indicateur personnalisé qui sera affiché dans le navigateur d'indicateurs de la plateforme de trading MetaTrader 5 (MT5).
- `type` : Le type de l'indicateur, spécifié en utilisant une des valeurs de l'énumération `ENUM_INDICATOR_TYPE`. Les types d'indicateurs courants incluent `IND_CUSTOM` pour les indicateurs personnalisés et divers autres types pré-définis tels que `IND_MA`, `IND_RSI`, etc.
- `sub_window` : Le numéro de la sous-fenêtre dans laquelle l'indicateur sera affiché sur le graphique de trading. Une valeur de zéro signifie que l'indicateur sera affiché dans la même fenêtre que le graphique des prix principal.

La fonction `IndicatorCreate()` renvoie un entier qui représente le handle (identifiant) de l'indicateur créé. Ce handle peut être utilisé ultérieurement dans le programme pour faire référence à cet indicateur, par exemple pour obtenir des valeurs de l'indicateur ou le supprimer du graphique.

En résumé, `IndicatorCreate()` est utilisée pour créer un nouvel indicateur personnalisé dans un programme MQL5, en spécifiant son nom, son type et sa configuration d'affichage sur le graphique de trading.


### Indicator release

La fonction `IndicatorRelease()` est une fonction en MQL5 utilisée pour libérer les ressources utilisées par un indicateur personnalisé. Lorsqu'un indicateur personnalisé n'est plus nécessaire dans un programme MQL5, il est recommandé de libérer ses ressources en appelant cette fonction.

Voici la syntaxe de la fonction `IndicatorRelease()` :

```mql5
bool IndicatorRelease(
   int   indicator_handle    // Handle (identifiant) de l'indicateur personnalisé
   );
```

Paramètre de la fonction :
- `indicator_handle` : Le handle (identifiant) de l'indicateur personnalisé que vous souhaitez libérer. Ce handle doit correspondre à celui qui a été retourné lors de la création de l'indicateur à l'aide de la fonction `IndicatorCreate()`.

La fonction `IndicatorRelease()` retourne `true` si les ressources de l'indicateur ont été libérées avec succès, sinon elle retourne `false`. Il est important de libérer les ressources des indicateurs personnalisés lorsque vous avez fini de les utiliser dans votre programme pour éviter les fuites de mémoire et optimiser les performances de votre script.
