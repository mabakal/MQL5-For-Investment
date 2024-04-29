### Les bases de trading

### Ask et bid

En trading financier, notamment sur les marchés boursiers et sur le marché des changes (Forex), "Ask" et "Bid" sont deux termes utilisés pour désigner les prix auxquels les traders peuvent acheter ou vendre un actif financier, comme une paire de devises, une action ou une matière première. Voici ce que chacun de ces termes signifie :

1. **Bid (Offre d'achat) :**
   Le prix "Bid" représente le prix auquel les traders sont prêts à acheter un actif financier. C'est le prix le plus élevé auquel un acheteur est prêt à payer pour acquérir l'actif. Lorsque vous voyez un prix "Bid", cela signifie que c'est le prix auquel vous pouvez vendre l'actif si vous êtes un vendeur sur le marché.

2. **Ask (Offre de vente) :**
   Le prix "Ask" représente le prix auquel les traders sont prêts à vendre un actif financier. C'est le prix le plus bas auquel un vendeur est prêt à vendre l'actif. Lorsque vous voyez un prix "Ask", cela signifie que c'est le prix auquel vous pouvez acheter l'actif si vous êtes un acheteur sur le marché.


La différence entre le prix "Ask" et le prix "Bid" est appelée "spread". Le spread représente le coût de transaction pour les traders et constitue la marge bénéficiaire des courtiers.

Il est important de noter que les prix "Bid" et "Ask" peuvent fluctuer constamment en fonction de l'offre et de la demande sur le marché, et ces prix sont généralement affichés en temps réel sur les plateformes de trading.

### Ordre, Transaction, position

Avant de commencer à étudier les fonctions de trading de la plateforme, vous devez comprendre les termes de base : ordre, transaction et position.

Un ordre est une instruction donnée au courtier d'acheter ou de vendre un instrument financier. Il y a deux principaux types d'ordres : au Marché et en Attente. De plus il y a des niveaux spéciaux de Take Profit et de Stop Loss.
Une transaction est l'échange commercial (achat ou vente) d'un instrument financier. L'Achat est exécuté au prix de la demande (Ask), et la Vente est réalisée au prix de l'offre (Bid). Une transaction peut être ouverte à la suite de l'exécution d'un ordre de marché ou par le déclenchement d'un ordre en attente. Notez que dans certains cas, l'exécution d'un ordre peut donner lieu à plusieures transactions.
Une position est une obligation commerciale, à savoir le nombre de contrats achetés ou vendus d'un instrument financier. Une position longue est un titre acheté en espérant que le prix de l'instrument va augmenter. Une position courte est l'obligation de fournir un titre en attendant que le prix baisse.


### Schéma Général des Opérations de Trading
A partir de la plateforme de trading, un ordre est envoyé au courtier pour exécuter une transaction avec les paramètres spécifiés ;
L'exactitude d'un ordre est vérifiée sur le serveur (exactitude des prix, disponibilité des fonds sur le compte, etc.) ;
Les ordres qui ont passé le contrôle attendent d'être traités sur le serveur de trading. Puis un ordre peut être :
exécuté (dans l'un des modes d'exécution automatique ou par le courtier)
annulé à l'expiration
rejété (par exemple lorsqu'il n'y a pas assez d'argent ou qu'il n'y a pas d'offre correspondante sur le marché ; ou rejeté par le courtier)
annulé par le trader ;
Une transaction est le résultat de l'exécution d'un ordre au marché ou du déclenchement d'un ordre en attente ;
S'il n'y a pas de position pour un symbole, la conclusion d'une transaction se traduit par l'ouverture d'une position. S'il y a une position pour le symbole, la transaction peut augmenter ou réduire le volume de la position, fermer la position ou l'inverser.


### Système de Comptabilisation des Positions
Deux systèmes de comptabilisation des positions sont pris en charge dans la plateforme de trading : Compensation et Couverture. Le système utilisé dépend du compte et est fixé par le courtier.

Système de Compensation
Avec ce système, vous ne pouvez avoir qu'une seule position commune pour un symbole en même temps :

S'il y a une position ouverte pour un symbole, l'exécution d'une transaction dans la même direction augmente le volume de cette position.
Si une opération est exécutée dans le sens inverse, le volume de la position actuelle peut être diminué, la position peut être fermée (lorsque le volume de transaction est égal au volume de la position) ou inversée (si le volume de l'opération inverse est plus grand que la position actuelle).
Peu importe ce qui a cause la transaction opposée - un ordre au marché exécuté ou un ordre en attente déclenché.

### Système de Couverture 
Avec ce système, vous pouvez avoir plusieurs positions ouvertes d'un seul et même symbole, y compris des positions opposées.

Si vous avez une position ouverte pour un symbole, et exécutez une nouvelle transaction (ou un ordre en attente qui se déclenche), une nouvelle position est ouverte. Votre position actuelle ne change pas.

### Impact du Système Sélectionné

En fonction du système de comptabilisation des positions, une partie des fonctions de la plateforme peut avoir un comportement différent :

Pour fermer une position dans le système de compensation, vous devriez effectuer une opération de trading opposée pour le même symbole et le même volume. Pour fermer une position dans le système de couverture, sélectionnez explicitement la commande "Fermer la Position" dans le menu contextuel de la position.
Une position ne peut pas être inversée dans le système de couverture. Dans ce cas, la position actuelle est fermée et une nouvelle position avec le volume restant est ouverte.
Dans le système de couverture, une nouvelle condition pour le calcul de la marge est disponible – Marge couverte.

### Types d'ordres

La plateforme de trading permet de préparer et d'émettre des demandes pour le courtier d'exécuter des opérations de trading. La plateforme permet également de contrôler et de gérer les positions ouvertes. Plusieurs types d'ordres de trading sont utilisés à ces fins. Un ordre est une instruction du trader au courtier pour réaliser une opération de trading. Sur la plateforme, les ordres sont divisés en deux principaux types : au marché et en attente. De plus, il y a des ordres spéciaux Stop Loss et Take Profit.

1. Ordre au Marché

Un ordre au marché est une instruction donnée au courtier pour acheter ou vendre un instrument financier. L'exécution de cet ordre se traduit par l'exécution d'une transaction. Le prix auquel la transaction est exécutée est déterminé par le type d'exécution qui dépend du type du symbole. Généralement, un titre est acheté au prix Ask (prix de la Demande) et vendu au prix Bid (prix de l'Offre).

2. Ordre en attentes

Un ordre en attente est l'instruction du trader à un courtier d'acheter ou de vendre un titre dans le futur à des conditions prédéfinies. Les types d'ordres en attente suivants sont disponibles :

- Buy Limit – une demande de trade pour acheter au prix Ask qui est égal ou inférieur au prix spécifié dans l'ordre. Le niveau actuel du prix est supérieur à la valeur spécifiée dans l'ordre. Habituellement cet ordre est placé par anticipation de sorte que le prix du titre tombera jusqu'à un certain niveau puis remontera ;
- Buy Stop – un ordre pour acheter au prix "Ask" égal ou supérieur à celui spécifié dans l'ordre. Le niveau actuel du prix est inférieur à la valeur spécifiée dans l'ordre. Habituellement cet ordre est placé par anticipation de sorte que le prix atteindra un certain niveau et continuera à monter ;
- Sell Limit – un ordre pour vendre au prix "Bid" égal ou supérieur à celui spécifié dans l'ordre. Le niveau actuel du prix est inférieur à la valeur spécifiée dans l'ordre. Habituellement cet ordre est placé par anticipation de sorte que le prix du titre augmentera jusqu'à un certain niveau puis retombera ;
- Sell Stop – un ordre pour vendre au prix "Bid" égal ou inférieur à celui spécifié dans l'ordre. Le niveau actuel du prix est supérieur à la valeur spécifiée dans l'ordre. Habituellement cet ordre est placé par anticipation de sorte que le prix du titre atteindra un certain niveau et va continuer à tomber.
- Buy Stop Limit – ce type est la combinaison des deux premiers types, c'est un ordre stop pour placer un ordre Buy Limit. Dès que le futur prix Ask atteindra le niveau de stop indiqué dans l'ordre (le champ Prix), un ordre Buy Limit sera placé au niveau spécifié au niveau spécifié dans le champ du prix Stop Limit. Un niveau de stop est fixé au-dessus du prix Ask en cours, tandis que le prix Stop Limit est fixé en dessous du niveau de stop.
- Sell Stop Limit – cet ordre est un ordre stop pour placer un ordre Sell Limit. Dès que le futur prix Bid atteindra le niveau de stop indiqué dans l'ordre (le champ Prix), un ordre Sell Limit sera placé au niveau spécifié dans le champ du prix Stop Limit. Un niveau de stop est fixé en dessous du prix Bid en cours, tandis que le prix Stop Limit est fixé au-dessus du niveau de stop.


### Les stops

1. Takes profit

L'ordre de Take Profit est destiné à obtenir le profit lorsque le prix du titre atteint un certain niveau. L'exécution de cet ordre se traduit par la fermeture complète de la position entière. Il est toujours lié à une position ouverte ou à un ordre en attente. L'ordre ne peut être demandé que conjointement avec un ordre au marché ou un ordre en attente. Cette condition d'ordre pour les positions longues est vérifiée avec le prix Bid (l'ordre est toujours fixé au-dessus du prix Bid en cours), et le prix Ask est utilisé pour les positions courtes (l'ordre est toujours fixé en dessous du prix Ask en cours).

2. Stop loss

Cet ordre est utilisé pour minimiser les pertes si le prix du titre se déplace dans la mauvaise direction. Si le prix du titre atteint ce niveau, la position entière est fermée automatiquement. De tels ordres sont toujours associés à une position ouverte ou à un ordre en attente. Ils ne peuvent être demandés que conjointement avec un ordre au marché ou un ordre en attente. Cette condition d'ordre pour les positions longues est vérifiée à l'aide du prix Bid (l'ordre est toujours fixé en dessous du prix Bid en cours), et le prix Ask est utilisé pour les positions courtes (l'ordre est toujours fixé au-dessus du prix Ask en cours).

### État des ordres

Après qu'un ordre a été formé et envoyé au serveur, il peut passer par les étapes suivantes :

Démarré – l'exactitude de l'ordre a été vérifiée, mais il n'a pas encore été accepté par le courtier ;
Placé – le courtier a accepté l'ordre ;
Rempli partiellement – l'ordre est rempli partiellement ;
Rempli – l'ensemble de l'ordre est rempli ;
Annulé – l'ordre est annulé par le client ;
Rejeté – l'ordre est rejeté par le courtier ;
Expiré – l'ordre est annulé en raison de son expiration.


### Types d'exécution

Quatre modes d'exécution d'ordres sont disponibles sur la plateforme de trading :

- Exécution Instantanée
Dans ce mode, un ordre est exécuté au prix offert au courtier. Lors de l'envoi d'un ordre à exécuter, la plateforme ajoute automatiquement les prix courants à l'ordre. Si le courtier accepte le prix, l'ordre est exécuté. Si le courtier n'accepte pas le prix demandé, un "Requote" ("Recotation") est envoyé – le courtier renvoie les prixs auxquels cet ordre peut être exécuté.
- Exécution de la Demande
Dans ce mode, un ordre au marché est exécuté au prix déjà reçu par le courtier. Les prix pour un certain ordre au marché sont demandés au courtier avant que la commande ne soit envoyée. Après que les prix aient été reçus, l'exécution de l'ordre au prix donné peut être soit confirmé ou rejeté.
- Exécution au Marché
Dans ce mode d'exécution de l'ordre, un courtier prend une décision sur le prix d'exécution de l'ordre sans discussion supplémentaire avec un trader. L'envoi d'un ordre dans un tel mode signifie le consentement préalable du prix pour son exécution.
- Bourse
Dans ce mode, les opérations de trading menées sur la plateforme de trading sont envoyées à un système de trading extérieur (bourse). Les opérations de trading sont exécutées aux prix des offres actuelles du marché.


### Politique de remplissage

Rempli ou Détruit (Fill or Kill - FOK)
Cette politique de remplissage signifie que l'ordre peut être rempli uniquement avec le volume spécifié. Si le montant nécessaire à l'instrument financier est actuellement indisponible sur le marché, l'ordre ne sera pas exécuté. Le volume requis peut être rempli par plusieurs offres disponibles sur le marché à l'heure actuelle.
Immédiat ou Annulé (Immediate Or Cancel - IOC)
Dans ce cas, un trader accepte d'exécuter une transaction avec le volume maximum disponible sur le marché jusqu'à celui indiqué dans l'ordre. Dans le cas où l'ordre ne peut pas être complètement rempli, le volume disponible de l'ordre sera rempli, et le volume restant sera annulé. La possibilité d'utiliser les ordres IOC est déterminé sur le serveur.
Réserver ou Annuler (Book Or Cancel - BOC)
La politique BOC indique que l'ordre ne peut être placé que dans le Depth of Market (le carnet d'ordres). Si lordre peut être exécuté immédiatement après avoir été passé, cet ordre est annulé. Cette politique garantit que le prix de lordre passé sera inférieur au marché actuel. Le BOC est utilisé pour mettre en uvre le trading passif : il est garanti que l'ordre ne peut pas être exécuté immédiatement lorsqu'il est passé et qu'il n'affecte donc pas la liquidité actuelle. Cette politique de remplissage n'est prise en charge que pour les ordres à cours limité et stop à cours limité.
Retour
Cette politique n'est utilisée que pour les ordres au marché (Buy et Sell), limit et stop limit. S'il est rempli partiellement, un ordre avec le volume restant n'est pas annulé, et est traité ultérieurement. Pour les ordres au marché, la politique Retour n'est utilisée que pour le mode d'Exécution Boursière, tandis que pour les ordres limit et stop limit, elle est appliquée dans les modes Exécution Boursière et Exécution au Marché.