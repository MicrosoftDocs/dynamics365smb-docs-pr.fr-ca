---
author: brentholtorf
ms.topic: include
ms.date: 03/15/2022
ms.author: bholtorf
---
Lorsque vous recevez une facture d’une compagnie dans une devise étrangère, il est assez facile de calculer la valeur en devise locale ($) de la facture en fonction du taux de change du jour. Cependant, la facture est souvent accompagnée de modalités de paiement afin que vous puissiez reporter le paiement à une date ultérieure, ce qui implique un taux de change potentiellement différent. Ce problème, combiné au fait que les taux de change bancaires diffèrent toujours des taux de change officiels, rend impossible l’anticipation du montant exact en devise locale ($) requis pour couvrir la facture. Si la date d’échéance de la facture s’étend au mois suivant, vous devrez peut-être également réévaluer le montant en devise locale ($) à la fin du mois. L’ajustement de la devise est nécessaire, car la nouvelle valeur $ requise pour couvrir le montant de la facture peut être différente et la dette de la compagnie envers le fournisseur a potentiellement changé. Le nouveau montant $ peut être supérieur ou inférieur au montant précédent et représentera donc un gain ou une perte. Cependant, comme la facture n’a pas encore été payée, le gain ou la perte est considéré comme *non réalisé*. Ultérieurement, la facture est réglée et la banque est revenue au taux de change réel pour le paiement. Ce n’est que maintenant que le gain ou la perte *réalisé(e)* est calculé(e). Ce gain ou cette perte non réalisé(e) est ensuite inversé(e) et le gain ou la perte réalisé(e) est reporté(e) à sa place.

Dans l’exemple suivant, une facture est reçue le 1er janvier avec le montant en devise 1 000. À ce moment là, le taux de change est 1,123.

|Date|Action|Montant devise|Taux document|Montant en $ sur le document|Taux ajustement|Montant gains non réalisés|Taux règlement|Montant pertes constatées report|  
|-----|----------|------------|-----------|---------|-----------|-------------|---------|---------|
|1/1|**Facture**|1000|1,123|1123|||||
|1/31|**Ajustement**|1000||1125|1,125|2|||
|2/15|**Ajustement Contrepassation sur paiement**|1000||||-2|||
|2/15|**Règlement**|1000||1120|||1,120|-3|

À la fin du mois, un ajustement de devise est effectué lorsque le taux de change d’ajustement a été fixé à 1,125, ce qui déclenche un gain non réalisé de 2.

Au moment du paiement, le taux de change réel enregistré sur la transaction bancaire indique un taux de change de 1,120.

Ici, il y a une transaction non réalisée. Elle sera donc inversée avec le paiement.

Enfin, le paiement est enregistré et la perte réelle est reportée sur le compte des pertes réalisées.
