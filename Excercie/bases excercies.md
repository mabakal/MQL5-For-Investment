D'accord, voici quelques exercices liés au trading pour pratiquer la manipulation de variables en MQL5 :

### Exercice 1 : Calcul du profit potentiel
Écrivez un programme en MQL5 qui calcule le profit potentiel d'une position en fonction du prix d'entrée, du prix de sortie et du nombre de lots échangés. Affichez le résultat.

```mql5
void OnStart()
{
    // Déclarez et initialisez les variables
    double prixEntree = 1.2000;
    double prixSortie = 1.2500;
    double lots = 1.5;
    
    // Calculez le profit potentiel
    double profit = (prixSortie - prixEntree) * lots * 100000; // 1 lot standard = 100 000 unités de la devise de base
    
    // Affichez le résultat
    Print("Profit potentiel :", profit, " USD");
}
```

### Exercice 2 : Calcul du risque
Écrivez un programme en MQL5 qui calcule le montant du risque en fonction du prix d'entrée, du prix de stop-loss et du nombre de lots échangés. Affichez le résultat.

```mql5
void OnStart()
{
    // Déclarez et initialisez les variables
    double prixEntree = 1.2000;
    double prixStopLoss = 1.1900;
    double lots = 2.0;
    
    // Calculez le montant du risque
    double risque = (prixEntree - prixStopLoss) * lots * 100000; // 1 lot standard = 100 000 unités de la devise de base
    
    // Affichez le résultat
    Print("Montant du risque :", risque, " USD");
}
```

### Exercice 3 : Calcul de la taille de la position
Écrivez un programme en MQL5 qui calcule la taille de la position en fonction du montant du risque, du prix de stop-loss et du prix d'entrée. Affichez le résultat.

```mql5
void OnStart()
{
    // Déclarez et initialisez les variables
    double montantRisque = 100.0; // Montant du risque en USD
    double prixEntree = 1.2000;
    double prixStopLoss = 1.1900;
    
    // Calculez la taille de la position
    double taillePosition = montantRisque / ((prixEntree - prixStopLoss) * 100000); // 1 lot standard = 100 000 unités de la devise de base
    
    // Affichez le résultat
    Print("Taille de la position :", taillePosition, " lots");
}
```
