### Obtenir les informations de ton compte

MétaTrader á facilité l'obtention des informations du compte d'un client. Des fonctions très facile sont mis á votre disposition pour avoir ces information. 

Trois fonction sont mis a votre disposition, il ont la même structure la difference est le type de valeur que ces fonction renvoie une fonction renvoi un entier, un autre une valeur flottante et l'autre une chaine de caractère. Ces fonctions sont :

```AccountInfoDouble, AccountInfoInteger, AccountInfoString```

##### Utilisation

Chaque information que vous souhaiter obtenir á une propriété qui est définie dans un énumeration nommé `` ENUM_ACCOUNT_INFO_X`` (le `X` peux être `String Long, Integer`). Par exemple `ENUM_ACCOUNT_INFO_String`. Toutes ces énumeration peux être trouver á l'address [Account info](https://www.mql5.com/en/docs/constants/environment_state/accountinformation#enum_account_info_string)

#### Exemple de propriété

1. **Informations de base :**
   - `ACCOUNT_BALANCE`: Solde du compte.
   - `ACCOUNT_EQUITY`: Équité du compte.
   - `ACCOUNT_MARGIN`: Marge utilisée.
   - `ACCOUNT_MARGIN_LEVEL`: Niveau de marge en pourcentage.
   - `ACCOUNT_LEVERAGE`: Effet de levier du compte.
   - `ACCOUNT_CURRENCY`: Devise du compte.

2. **Informations sur les trades :**
   - `ACCOUNT_TRADE_ALLOWED`: Autorisation des opérations de trading (1 si autorisé, 0 sinon).
   - `ACCOUNT_TRADE_EXPERT`: Autorisation des opérations d'expert advisor (1 si autorisé, 0 sinon).
   - `ACCOUNT_TRAILING_STOP`: Autorisation du trailing stop (1 si autorisé, 0 sinon).
   - `ACCOUNT_TRAILING_STOP_LIMIT`: Limite du trailing stop en points.

3. **Informations sur le compte :**
   - `ACCOUNT_COMPANY`: Nom de la société de courtage.
   - `ACCOUNT_SERVER`: Nom du serveur de trading.
   - `ACCOUNT_NAME`: Nom du compte de trading.
   - `ACCOUNT_LOGIN`: Numéro de compte de trading.
   - `ACCOUNT_EXPIRATION`: Date d'expiration du compte (en secondes depuis l'Épiphanie).

4. **Informations sur les paramètres du compte :**
   - `ACCOUNT_FIFO`: Méthode de comptabilité FIFO (1 si activée, 0 sinon).
   - `ACCOUNT_NFA`: Conformité avec les règles NFA (1 si activée, 0 sinon).
   - `ACCOUNT_MARGIN_SO_MODE`: Mode de déclenchement du stop-out de marge.

5. **Informations sur le trading :**
   - `ACCOUNT_TRADE_MODE`: Mode de trading (TRADE_OPERATION_BUY seulement, TRADE_OPERATION_SELL seulement, etc.).
   - `ACCOUNT_TRADE_EXPERT`: Autorisation du trading automatique (1 si autorisé, 0 sinon).

Ce ne sont que quelques exemples d'énumérations disponibles pour obtenir des informations sur un compte de trading en MQL5. Vous pouvez consulter la documentation officielle de MQL5 pour obtenir une liste complète des énumérations disponibles et des informations qu'elles fournissent.


### Rappel

La marge (ou "margin" en anglais) dans le trading fait référence à la quantité de fonds requise pour maintenir une position ouverte sur le marché. Elle est utilisée par les courtiers comme garantie pour couvrir les pertes potentielles des traders.

Il existe plusieurs types de marges utilisées dans le trading, notamment :

1. **Marge initiale (Initial Margin) :** C'est la quantité de fonds requise pour ouvrir une nouvelle position. Elle est basée sur la taille de la position et sur les exigences de marge fixées par le courtier ou la bourse.

2. **Marge de variation (Variation Margin) :** C'est la quantité de fonds nécessaire pour maintenir une position ouverte en fonction des fluctuations des prix du marché. Si la valeur de la position diminue, la marge de variation doit être augmentée pour maintenir la position ouverte.

3. **Marge de maintenance (Maintenance Margin) :** C'est le niveau minimum de marge requis pour maintenir une position ouverte. Si la marge disponible tombe en dessous de ce niveau, le courtier peut émettre un appel de marge (Margin Call) et demander au trader de déposer des fonds supplémentaires pour maintenir la position ouverte.

4. **Marge libre (Free Margin) :** C'est la quantité de fonds disponibles dans le compte de trading qui peut être utilisée pour ouvrir de nouvelles positions ou maintenir des positions ouvertes. Elle est calculée en soustrayant la marge utilisée et les pertes flottantes (pertes potentielles sur les positions ouvertes) du solde du compte.

5. **Marge utilisée (Used Margin) :** C'est la quantité de fonds utilisée pour maintenir des positions ouvertes sur le marché. Elle est calculée en fonction de la taille de la position et des exigences de marge du courtier.

Ces différents types de marges sont essentiels pour gérer le risque dans le trading et sont utilisés par les traders et les courtiers pour s'assurer que les positions sont maintenues dans des limites de risque acceptables. Il est important pour les traders de comprendre comment ces marges fonctionnent et comment elles affectent leurs comptes de trading.