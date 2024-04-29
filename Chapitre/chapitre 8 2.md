### Les principaux object intervenant dans les trade

1. MqlTradeRequest

La structure `MqlTradeRequest` est une structure clé en MQL5 utilisée pour envoyer des demandes de trading au serveur de trading. Cette structure contient toutes les informations nécessaires pour placer un ordre sur le marché financier. Voici une description détaillée des membres de la structure `MqlTradeRequest` :

-  **Type d'ordre (`type`) :**
   C'est un membre de type énumération (`ENUM_TRADE_REQUEST_ACTIONS`) qui spécifie le type d'action à effectuer. Les valeurs possibles sont :
   - `TRADE_ACTION_DEAL` : Exécuter une transaction (achat ou vente).
   - `TRADE_ACTION_PENDING` : Placer un ordre en attente (achat limité, vente limitée, achat stop, vente stop, etc.).
   - `TRADE_ACTION_SLTP` : Modifier le niveau de stop loss ou take profit d'une position existante.
   - `TRADE_ACTION_MODIFY` : Modifier les paramètres d'un ordre en attente.
   - `TRADE_ACTION_REMOVE` : Annuler un ordre en attente.
   - `TRADE_ACTION_CLOSE_BY` : Fermer une position par une autre position opposée.

-  **Identifiant de la demande (`magic`) :**
   C'est un membre de type `ulong` qui est utilisé pour identifier de manière unique la demande de trading. Cela peut être utile pour suivre les demandes spécifiques dans le journal des événements de trading.

-  **Symbole (`symbol`) :**
   C'est une chaîne de caractères qui spécifie le symbole de l'instrument financier sur lequel l'action de trading doit être effectuée.

-  **Volume (`volume`) :**
   C'est un membre de type `double` qui spécifie le volume de l'ordre ou de la transaction à effectuer. Pour les transactions, le volume représente la taille de la position. Pour les ordres en attente, le volume représente la taille de l'ordre.

-  **Prix (`price`) :**
   C'est un membre de type `double` qui spécifie le prix auquel l'ordre doit être placé. Pour les ordres en attente, il s'agit du prix auquel l'ordre sera activé. Pour les transactions, il s'agit du prix auquel la transaction sera exécutée.

-  **Prix de stop (`stoplimit`) :**
   C'est un membre de type `double` utilisé pour spécifier le prix de déclenchement d'un ordre stop. Il est utilisé uniquement pour les ordres en attente de type stop.

-  **Prix de limite (`limitprice`) :**
   C'est un membre de type `double` utilisé pour spécifier le prix de déclenchement d'un ordre limite. Il est utilisé uniquement pour les ordres en attente de type limite.

- **Prix stop loss (`sl`) :**
   C'est un membre de type `double` utilisé pour spécifier le niveau de stop loss pour une transaction ou une position existante.

-  **Prix take profit (`tp`) :**
   C'est un membre de type `double` utilisé pour spécifier le niveau de take profit pour une transaction ou une position existante.

- **Commentaire (`comment`) :**
    C'est une chaîne de caractères utilisée pour ajouter des commentaires ou des annotations à la demande de trading. Cela peut être utile pour suivre et identifier les différentes transactions ou ordres.

La structure `MqlTradeRequest` permet aux traders de spécifier toutes les informations nécessaires pour placer un ordre ou effectuer une transaction sur le marché financier en utilisant les fonctions de trading en MQL5. Elle est largement utilisée dans le développement d'algorithmes de trading automatisé et dans la création de robots de trading en MQL5.

2. MQLTradeResult

La structure `MqlTradeResult` est utilisée en MQL5 pour stocker les résultats d'une demande de trading qui a été envoyée au serveur de trading. Elle est généralement utilisée pour récupérer des informations sur le résultat de l'exécution d'un ordre ou d'une transaction. Voici une description des membres de la structure `MqlTradeResult` :

- **Code de résultat (`retcode`) :**
   C'est un membre de type entier qui indique le code de résultat de l'opération de trading. Les valeurs possibles sont spécifiées dans l'énumération `ENUM_TRADE_RESULT`.
   
   - `TRADE_RETCODE_DONE` : L'opération de trading a été effectuée avec succès.
   - `TRADE_RETCODE_REQUOTE` : Une requête de nouveau prix est nécessaire.
   - `TRADE_RETCODE_REJECT` : L'opération de trading a été rejetée.
   - `TRADE_RETCODE_CANCEL` : L'opération de trading a été annulée.
   - `TRADE_RETCODE_PLACED` : L'ordre en attente a été placé avec succès.
   - `TRADE_RETCODE_DONE_PARTIAL` : L'opération de trading a été partiellement exécutée.
   - `TRADE_RETCODE_TIMEOUT` : La demande de trading a expiré en raison d'un délai d'attente.
   - `TRADE_RETCODE_INVALID` : La demande de trading est invalide.

- **Identifiant de la demande (`deal`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant de la transaction (deal) associée à la demande de trading. Cet identifiant peut être utilisé pour suivre la transaction dans le journal des événements de trading.

- **Ordre ou transaction (`order`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant de l'ordre ou de la transaction associé à la demande de trading.

- **Prix (`price`) :**
   C'est un membre de type `double` qui spécifie le prix auquel l'ordre a été exécuté ou la transaction a été effectuée.

- **Volume (`volume`) :**
   C'est un membre de type `double` qui spécifie le volume de l'ordre ou de la transaction qui a été exécutée.

- **Volume restant (`volume_remain`) :**
   C'est un membre de type `double` qui spécifie le volume restant de l'ordre ou de la transaction qui n'a pas été exécuté.

- **Prix de remplissage (`price_fill`) :**
   C'est un membre de type `double` qui spécifie le prix de remplissage de l'ordre ou de la transaction.

- **Commentaire (`comment`) :**
   C'est une chaîne de caractères qui contient des informations supplémentaires sur le résultat de l'opération de trading.

La structure `MqlTradeResult` est utilisée pour récupérer des informations détaillées sur le résultat d'une demande de trading après son exécution. Ces informations peuvent être utilisées pour suivre l'état des transactions, analyser les résultats des opérations de trading et prendre des décisions en conséquence dans un programme MQL5.


3. MQLTradeTransaction

Lors de l'exécution de certains actions définies sur un compte de trading, son état change. De telles actions incluent :

L'envoi d'une demande de trading depuis n'importe application MQL5 dans le terminal client avec les fonctions OrderSend et OrderSendAsync et son exécution ;
L'envoi d'une demande de trading vie l'interface graphique du terminal et son exécution ;
L'activation des ordres en attente et des stops sur le serveur ;
Effectuer des opérations du côté du serveur de trades.
Les transactions de trading suivantes sont effectuées suite à ces actions :

traitement d'une demande de trading ;
changement des ordres ouverts ;
changement de l'historique des ordres ;
changement de l'historique des transactions ;
changement des positions.
Par exemple, lors de l'envoi d'un ordre d'achat, il est pris en compte par le gestionnaire, un ordre d'achat correspondant est créé pour le compte, l'ordre est ensuite exécuté et supprimé de la liste des ordres ouverts, puis il est ajouté à l'historique des ordres, une transaction correspondante est ajoutée à l'hisorique et une nouvelle position est créée. Toutes ces actions sont des transactions de trading.


La structure `MqlTradeTransaction` est utilisée en MQL5 pour stocker des informations sur les transactions effectuées sur le compte de trading. Elle contient des détails sur les ordres exécutés, les modifications d'ordres, les annulations d'ordres, les opérations de dépôt/retrait, etc. Voici une description des membres de la structure `MqlTradeTransaction` :

- **Identifiant de la transaction (`deal`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant unique de la transaction.

- **Identifiant de l'ordre (`order`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant de l'ordre associé à la transaction. Si la transaction est liée à un ordre, cet identifiant indique l'ordre correspondant.

- **Identifiant du client (`client`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant unique du client (trader) associé à la transaction.

- **Identifiant du symbole (`symbol`) :**
   C'est un membre de type `ulong` qui spécifie l'identifiant unique du symbole (instrument financier) associé à la transaction.

- **Type de transaction (`type`) :**
   C'est un membre de type énumération (`ENUM_TRADE_TRANSACTION_TYPE`) qui spécifie le type de la transaction. Les valeurs possibles sont :
   - `TRADE_TRANSACTION_ORDER_ADD` : Ajout d'un nouvel ordre.
   - `TRADE_TRANSACTION_ORDER_UPDATE` : Modification d'un ordre existant.
   - `TRADE_TRANSACTION_ORDER_DELETE` : Suppression d'un ordre.
   - `TRADE_TRANSACTION_DEAL_ADD` : Ajout d'une nouvelle transaction.
   - `TRADE_TRANSACTION_DEAL_UPDATE` : Modification d'une transaction existante.
   - `TRADE_TRANSACTION_DEAL_DELETE` : Suppression d'une transaction.
   - `TRADE_TRANSACTION_POSITION` : Ouverture, augmentation, réduction ou fermeture d'une position.
   - `TRADE_TRANSACTION_HISTORY_ADD` : Ajout d'une transaction dans l'historique.

- **Résultat de la transaction (`retcode`) :**
   C'est un membre de type entier qui indique le code de résultat de la transaction. Les valeurs possibles dépendent du type de transaction.

- **Temps (`time`) :**
   C'est un membre de type `datetime` qui spécifie l'heure à laquelle la transaction a été effectuée.

- **Prix (`price`) :**
   C'est un membre de type `double` qui spécifie le prix auquel la transaction a été effectuée.

- **Volume (`volume`) :**
   C'est un membre de type `double` qui spécifie le volume de la transaction.

- **Commission (`commission`) :**
    C'est un membre de type `double` qui spécifie le montant de la commission facturée pour la transaction.

- **Commentaire (`comment`) :**
    C'est une chaîne de caractères qui contient des informations supplémentaires sur la transaction.

La structure `MqlTradeTransaction` est utilisée pour récupérer des détails sur les transactions effectuées sur le compte de trading. Ces informations peuvent être utilisées pour suivre l'historique des transactions, analyser les performances de trading et prendre des décisions en conséquence dans un programme MQL5.


