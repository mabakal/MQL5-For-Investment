### Excercice sur les indicateurs

Reprogrammer ces indicateurs

1. **Moyenne mobile simple (SMA) :**
   
   
   $SMA = \frac{\sum_{i=1}^{n} Close[i]}{n}$

   Où \( Close[i] \) est le prix de clôture de la \( i \)-ème période et \( n \) est le nombre de périodes.

2. **Moyenne mobile exponentielle (EMA) :**
   

   $EMA = \left( Close - EMA_{\text{précédente}} \right) \times \left( \frac{2}{\text{période} + 1} \right) + EMA_{\text{précédente}}$

   
   Où \( Close \) est le prix de clôture actuel, \( EMA_{\text{précédente}} \) est la valeur EMA de la période précédente et la période est le nombre de périodes utilisé pour le calcul.

3. **Indice de force relative (RSI) :**
   
  
   $RSI = 100 - \left( \frac{100}{1 + RS} \right)$

   
   Où \( RS \) est le rapport des moyennes des gains et des pertes sur une période spécifique. Pour calculer \( RS \), vous pouvez utiliser les formules suivantes :
   
 
   $\text{Moyenne des gains} = \frac{\sum_{i=1}^{n} \text{Gain}[i]}{n}$

   

   $\text{Moyenne des pertes} = \frac{\sum_{i=1}^{n} \text{Perte}[i]}{n}$
 
   

   $RS = \frac{\text{Moyenne des gains}}{\text{Moyenne des pertes}}$


   Où \( \text{Gain}[i] \) est la différence entre les prix de clôture actuel et précédent si positive, et \( \text{Perte}[i] \) est la différence entre les prix de clôture actuel et précédent si négative.


5. **Moyenne mobile pondérée (WMA) :**


   $WMA = \frac{\sum_{i=1}^{n} (Close[i] \times i)}{\sum_{i=1}^{n} i}$


   Où \( Close[i] \) est le prix de clôture de la \( i \)-ème période et \( n \) est le nombre de périodes.

6. **Oscillateur stochastique :**


   $\%K = \left( \frac{Close - \text{LowestLow}}{\text{HighestHigh} - \text{LowestLow}} \right) \times 100$
   
   Où \( Close \) est le prix de clôture actuel, \( \text{LowestLow} \) est le plus bas des \( n \) derniers prix les plus bas et \( \text{HighestHigh} \) est le plus haut des \( n \) derniers prix les plus hauts.

 
   $\%D = \text{Moyenne mobile de } \%K$

   Où la moyenne mobile de \( \%K \) est calculée sur une période spécifique.

7. **Average True Range (ATR) :**


   $TR = \max(\text{High} - \text{Low}, |\text{High} - \text{Close précédent}|, |\text{Low} - \text{Close précédent}|)$
   

   $ATR = \frac{\sum_{i=1}^{n} TR[i]}{n}$


   Où \( \text{High} \) et \( \text{Low} \) sont les plus hauts et les plus bas des prix de la période, respectivement, et \( \text{Close précédent} \) est le prix de clôture de la période précédente.

