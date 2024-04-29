### Données historique

Cette structure stocke les informations des prix, des volumes et du spread.

La structure `MqlRates` est utilisée en MQL5 pour stocker les données d'une seule barre de prix historique d'un instrument financier sur un graphique. Voici une description détaillée de chaque membre de cette structure :

1. **`time` :**
   - Type : `datetime`
   - Description : Ce membre spécifie l'heure de début de la période de la barre de prix. Il représente le moment où cette barre de prix a commencé à se former.

2. **`open` :**
   - Type : `double`
   - Description : Ce membre spécifie le prix d'ouverture de la barre de prix. C'est le prix auquel la première transaction de la période a été exécutée.

3. **`high` :**
   - Type : `double`
   - Description : Ce membre spécifie le prix le plus haut atteint pendant la période de la barre de prix. Il représente le prix le plus élevé auquel la transaction a été effectuée pendant cette période.

4. **`low` :**
   - Type : `double`
   - Description : Ce membre spécifie le prix le plus bas atteint pendant la période de la barre de prix. Il représente le prix le plus bas auquel la transaction a été effectuée pendant cette période.

5. **`close` :**
   - Type : `double`
   - Description : Ce membre spécifie le prix de clôture de la barre de prix. C'est le prix auquel la dernière transaction de la période a été exécutée.

6. **`tick_volume` :**
   - Type : `long`
   - Description : Ce membre spécifie le volume de ticks (transactions) pour la barre de prix. Il représente le nombre de transactions effectuées pendant cette période.

7. **`spread` :**
   - Type : `int`
   - Description : Ce membre spécifie le spread pour la barre de prix. Le spread est la différence entre les prix ask et bid à un moment donné, et ce membre représente cette différence pour cette période.

8. **`real_volume` :**
   - Type : `long`
   - Description : Ce membre spécifie le volume réel des trades pour la barre de prix. Il représente le volume total des lots négociés pendant cette période.

### Difference entre tick volume et real volume

1. **`tick_volume` :**
   - Le membre `tick_volume` représente le nombre total de ticks (ou transactions) qui ont eu lieu pendant la période de la barre de prix.
   - Chaque fois qu'un nouveau tick (changement de prix) est reçu, le volume de ticks est incrémenté de 1, indépendamment de la taille de la transaction.
   - Par conséquent, `tick_volume` est simplement un compteur du nombre de ticks ou de transactions qui se sont produits pendant la période de la barre de prix.

2. **`real_volume` :**
   - Le membre `real_volume` représente le volume réel des trades (ou des transactions) qui ont eu lieu pendant la période de la barre de prix.
   - Contrairement à `tick_volume`, le volume réel des trades prend en compte la taille de chaque transaction.
   - Il représente la somme des volumes de toutes les transactions qui ont eu lieu pendant la période de la barre de prix.
   - Ainsi, `real_volume` donne une indication du volume total des lots négociés pendant la période de la barre de prix.


#### Copiez les données historique des prix

##### CopyRates

Retourne dans le tableau rates_array les données historiques de la structure MqlRates pour un symbole et une période spécifiés. L'ordre des éléments des données copiées est du présent au passé, c'est à dire que la position de départ de 0 signifie la barre courante.

La fonction `CopyRates()` en MQL5 permet de copier les données historiques des prix depuis le terminal client vers un tableau d'objets `MqlRates`. Il existe trois variantes d'appel à cette fonction, chacune permettant de spécifier les paramètres de début et de fin de l'intervalle de temps pour lequel vous souhaitez obtenir les données historiques. Voici les trois variantes d'appel avec leurs paramètres :

1. **Appel avec la première position et le nombre d'éléments désirés :**
```mql5
int CopyRates(
    string symbol_name,        // Nom du symbole
    ENUM_TIMEFRAMES timeframe, // Période de temps
    int start_pos,             // Position de départ
    int count,                 // Nombre d'éléments à copier
    MqlRates rates_array[]     // Tableau de destination pour la copie
);
```

2. **Appel avec la date de début et le nombre d'éléments désirés :**
```mql5
int CopyRates(
    string symbol_name,        // Nom du symbole
    ENUM_TIMEFRAMES timeframe, // Période de temps
    datetime start_time,      // Date et heure de début
    int count,                 // Nombre d'éléments à copier
    MqlRates rates_array[]     // Tableau de destination pour la copie
);
```

3. **Appel avec les dates de début et de fin d'un intervalle de temps désiré :**
```mql5
int CopyRates(
    string symbol_name,        // Nom du symbole
    ENUM_TIMEFRAMES timeframe, // Période de temps
    datetime start_time,      // Date et heure de début
    datetime stop_time,       // Date et heure de fin
    MqlRates rates_array[]     // Tableau de destination pour la copie
);
```

Dans chacune de ces variantes, vous spécifiez le nom du symbole, la période de temps, et le tableau de destination `rates_array` où les données historiques des prix seront stockées. La fonction renvoie le nombre d'éléments copiés avec succès dans le tableau `rates_array`, ou -1 en cas d'erreur.

#### D'autre fonction qui permette le copy des données historique

Vous pouvez également opter pour la copie des données spécifique. fonction ne renvoie par une structure complete regroupant plusieurs variables, mais uniquement les ou la données d'une seul variables.

`CopyOpen, CopyClose etc` qui retourne les tableaux de valeurs ou `iClose, iOpen etc` qui retourne une valeur données.