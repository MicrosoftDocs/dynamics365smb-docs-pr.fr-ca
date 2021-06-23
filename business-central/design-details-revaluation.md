---
title: Détails de conception - Réévaluation | Microsoft Docs
description: Vous pouvez réévaluer l'inventaire en fonction de la base d'évaluation reflétant le plus précisément la valeur d'inventaire. Vous pouvez également antidater une réévaluation, afin que le coût des biens vendus (COGS) soit correctement mis à jour pour les articles qui ont déjà été vendus. Les articles utilisant le mode évaluation stock standard qui n'ont pas été entièrement facturés peuvent également être réévalués.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: a052f726169fde9e09e83aeb690169580eaee948
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6215788"
---
# <a name="design-details-revaluation"></a>Détails de conception : réévaluation
Vous pouvez réévaluer l'inventaire en fonction de la base d'évaluation reflétant le plus précisément la valeur d'inventaire. Vous pouvez également antidater une réévaluation, afin que le coût des biens vendus (COGS) soit correctement mis à jour pour les articles qui ont déjà été vendus. Les articles utilisant le mode évaluation stock standard qui n'ont pas été entièrement facturés peuvent également être réévalués.  

Dans [!INCLUDE[prod_short](includes/prod_short.md)], la flexibilité suivante est prise en charge sur la réévaluation :  

-   La quantité réévaluable peut être calculée pour n'importe quelle date, également dans le passé.  
-   Pour les articles utilisant le mode évaluation stock standard, les écritures coût prévu sont incluses dans la réévaluation.  
-   Des diminutions d'inventaire affectées par la réévaluation sont détectées.  

## <a name="calculating-the-revaluable-quantity"></a>Calcul de la quantité réévaluable  
 La quantité réévaluable est la quantité restante en inventaire qui est disponible pour la réévaluation à une date donnée. Elle est calculée comme la somme totale des quantités des écritures article entièrement facturées qui ont une date de report égale ou antérieure à la date de report de réévaluation.  

> [!NOTE]  
>  Les articles utilisant le mode évaluation coût standard sont traités de façon différente lors du calcul de la quantité réévaluable par article, emplacement et variante. Les quantités et les valeurs des écritures articles qui ne sont pas entièrement facturées sont incluses dans la quantité réévaluable.  

Une fois qu'une réévaluation a été reportée, vous pouvez reporter une diminution ou une augmentation d'inventaire avec une date de report antérieure à la date de report de la réévaluation. Cependant, cette quantité n'est pas affectée par la réévaluation. Pour équilibrer l'inventaire, seule la quantité réévaluable initiale est considérée.  

Étant donné que la réévaluation peut être effectuée à n'importe quelle date, vous devez avoir des conventions pour le moment où un article est considéré comme une partie de l'inventaire du point de vue financier. Par exemple, lorsque l'article figure dans l'inventaire et lorsque l'article est un travail en cours (TEC).  

### <a name="example"></a>Exemple :  
L'exemple suivant montre à quel moment un article TEC se transforme pour devenir une partie de l'inventaire. L'exemple est basé sur la production d'une chaîne de 150 liens.  

![Inventaire et réévaluation TEC](media/design_details_inventory_costing_10_revaluation_wip.png "Inventaire et réévaluation TEC")  

**1Q** : l'utilisateur valide les maillons achetés comme étant reçus. Le tableau suivant montre l'écriture article résultante.  

|Date de report|Article|Type écriture|Quantité|N° séquence |  
|------------------|----------|----------------|--------------|---------------|  
|01/01/20|LIEN|Achat|150|1|  

> [!NOTE]  
>  À présent un article utilisant le mode évaluation stock standard est disponible pour la réévaluation.  

**1V** : l'utilisateur reporte les maillons achetés comme étant facturés et les maillons font alors partie de l'inventaire, d'un point de vue financier. Le tableau suivant montre les écritures valeur résultantes.  

|Date de report|Type écriture|Date évaluation|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|15/01/20|Coût direct|01/01/20|150.00|1|1|  

 **2Q + 2V** : l'utilisateur valide les maillons achetés comme étant consommés pour la production de la chaîne en fer. Du point de vue financier, les liens deviennent une partie de l'inventaire TEC.  Le tableau suivant montre l'écriture article résultante.  

|Date de report|Article|Type écriture|Quantité|N° séquence |  
|------------------|----------|----------------|--------------|---------------|  
|01/02/20|LIEN|Consommation|-150|1|  

Le tableau suivant montre l'écriture valeur résultante.  

|Date de report|Type écriture|Date évaluation|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|01/02/20|Coût direct|01/02/20|-150,00|2|2|  

La date d'évaluation est définie sur la date du report de la consommation (02-01-20), en tant que diminution d'inventaire classique.  

**3Q** : l'utilisateur valide la chaîne comme étant en production et finit l'ordre de fabrication. Le tableau suivant montre l'écriture article résultante.  

|Date de report|Article|Type écriture|Quantité|N° séquence |  
|------------------|----------|----------------|--------------|---------------|  
|02-15-20|CHAÎNE|Sortie|1|3|  

**3V** : l'utilisateur exécute le traitement en lot **Ajuster coûts - Écr. article**, qui reporte la chaîne comme facturée pour indiquer que toute la consommation de matériel a été entièrement facturée. Du point de vue financier, les liens ne font plus partie de l'inventaire TEC lorsque la production est entièrement facturée et ajustée. Le tableau suivant montre les écritures valeur résultantes.  

|Date de report|Type écriture|Date évaluation|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|15/01/20|Coût direct|01/01/20|150.00|2|2|  
|01/02/20|Coût direct|01/02/20|-150,00|2|2|  
|15/02/20|Coût direct|15/02/20|150.00|3|3|  

## <a name="expected-cost-in-revaluation"></a>Coût prévu de la réévaluation  
La quantité réévaluable est calculée comme la somme de la quantité des écritures article entièrement facturées avec une date de report égale ou antérieure à la date de réévaluation. Cela signifie que lorsque certains articles sont reçus/livrés mais pas facturés, leur valeur d'inventaire ne peut pas être calculée. Les articles utilisant le mode évaluation stock standard ne sont pas limités à cet égard.  

> [!NOTE]  
>  L'inventaire TEC est un autre type de coût prévu qui peut être réévalué, dans le cadre de certaines règles. Pour plus d’informations, voir [Réévaluation de l'inventaire TEC](design-details-revaluation.md#wip-inventory-revaluation).  

Lors du calcul de la quantité réévaluable pour les articles utilisant le mode d’évaluation Standard, les écritures article n’ayant pas été complètement facturées sont incluses dans le calcul. Les écritures sont ensuite réévaluées lorsque vous reportez la réévaluation. Lorsque vous facturez l'écriture réévaluée, les écritures valeur suivantes sont créées :  

-   L'écriture valeur facturée habituelle avec un type d'écriture **Coût direct**. Le coût indiqué de cette écriture est le coût direct de la ligne source.  
-   Une écriture valeur avec le type d'écriture **Écart**. Cette écriture enregistre la différence entre le coût facturé et le coût standard réévalué.  
-   Une écriture valeur avec le type d'écriture **Réévaluation**. Cette écriture enregistre l'inversion de la réévaluation du coût prévu.  

### <a name="example"></a>Exemple :  
L'exemple suivant, basé sur la production de la chaîne dans l'exemple précédent, illustre la manière dont les trois types d'écritures sont créés. Il est basé sur le scénario suivant :  

1.  L'utilisateur reporte les liens achetés comme reçus avec un coût unitaire de 2,00 $.  
2.  L'utilisateur reporte ensuite une réévaluation des liens avec un nouveau coût unitaire de 3,00 $, mettant à jour le coût standard à 3,00 $.  
3.  L'utilisateur valide l'achat d'origine des liens comme facturés, ce qui crée ce qui suit :  

    1.  Une écriture valeur facturée avec le type d'écriture **Coût direct**.  
    2.  Une écriture valeur avec le type d'écriture **Réévaluation** pour enregistrer la contrepassation de la réévaluation du coût prévu.  
    3.  Une écriture valeur avec le type d'écriture Écart, qui enregistre la différence entre le coût facturé et le coût standard réévalué.  
Le tableau suivant montre les écritures valeur résultantes.  

|Étape|Date de report|Type écriture|Date évaluation|Coût indiqué (prévu)|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|----------|------------------|----------------|--------------------|------------------------------|----------------------------|---------------------------|---------------|  
|1.|15/01/20|Coût direct|15/01/20|300.00|0.00|1|1|  
|2.|20/01/20|Réévaluation|20/01/20|150.00|0.00|1|2|  
|3.a.|15/01/20|Coût direct|15/01/20|-300,00|0.00|1|3|  
|3.b.|15/01/20|Réévaluation|20/01/20|-150,00|0.00|1|4|  
|3.c.|15/01/20|Écart|15/01/20|0.00|450.00|1|5|  

## <a name="determining-whether-an-inventory-decrease-is-affected-by-revaluation"></a>Déterminer si une sortie d'inventaire est liée à la réévaluation  
La date du report ou de la réévaluation est utilisée pour déterminer si une diminution d'inventaire est affectée par une réévaluation.  

Le tableau suivant montre les critères utilisés pour un article qui n'utilise pas le mode évaluation stock moyen.  

|Scénario|N° séquence |Timing|Lié à la réévaluation|  
|--------------|---------------|------------|-----------------------------|  
|A|Antérieur au numéro d'écriture réévaluation.|Antérieur à la date de report de réévaluation|Non|  
|B|Antérieur au n° d'écriture réévaluation.|Égal à la date de report de réévaluation|Non|  
|C|Antérieur au n° d'écriture réévaluation.|Postérieur à la date de report de réévaluation|Oui|  
|J|Ultérieur au n° d'écriture réévaluation.|Antérieur à la date de report de réévaluation|Oui|  
|E|Ultérieur au n° d'écriture réévaluation.|Égal à la date de report de réévaluation|Oui|  
|F|Ultérieur au n° d'écriture réévaluation.|Postérieur à la date de report de réévaluation|Oui|  

### <a name="example"></a>Exemple :  
L'exemple suivant, qui illustre la réévaluation d'un article qui utilise le mode d'évaluation du stock FIFO, est basé sur le scénario suivant :  

1.  Le 01/01/20, l'utilisateur valide un achat de 6 unités.  
2.  Le 01/02/20, l'utilisateur valide une vente de 1 unité.  
3.  Le 01-03-20, l'utilisateur valide une vente de 1 unité.  
4.  Le 01-04-20, l'utilisateur valide une vente de 1 unité.  
5.  Le 01/03/20, l'utilisateur calcule la valeur d'inventaire pour l'article, et reporte une réévaluation du coût unitaire de l'article en $ de 10,00 à 8,00 $.  
6.  Le 01/02/20, l'utilisateur valide une vente de 1 unité.  
7.  Le 01-03-20, l'utilisateur valide une vente de 1 unité.  
8.  Le 01-04-20, l'utilisateur valide une vente de 1 unité.  
9. L'utilisateur exécute le traitement en lot **Ajuster coûts - Écr. article**.  

Le tableau suivant montre les écritures valeur résultantes.  

|Scénario|Date de report|Type écriture|Date évaluation|Quantité valorisée|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|--------------|------------------|----------------|--------------------|---------------------|----------------------------|---------------------------|---------------|  
||01/01/20|Achat|01/01/20|6|60.00|1|1|  
||01/03/20|Réévaluation|01/03/20|4|-8,00|1|5|  
|A|01/02/20|Vente|01/02/20|-1|-10,00|2|2|  
|B|01/03/20|Vente|01/03/20|-1|-10,00|3|3|  
|C|01/04/20|Vente|01/04/20|-1|-10,00|4|4|  
||01/04/20|Vente|01/04/20|-1|2.00|4|9|  
|J|01/02/20|Vente|01/03/20|-1|-10,00|5|6|  
||01/02/20|Vente|01/03/20|-1|2.00|5|10|  
|E|01/03/20|Vente|01/03/20|-1|-10,00|6|7|  
||01/03/20|Vente|01/03/20|-1|2.00|6|11|  
|F|01/04/20|Vente|01/04/20|-1|-10,00|7|8|  
||01/04/20|Vente|01/04/20|-1|2.00|7|12|  

## <a name="wip-inventory-revaluation"></a>Réévaluation de l'inventaire TEC  
La réévaluation de l'inventaire TEC implique de réévaluer les composantes qui sont enregistrées dans le cadre de l'inventaire TEC au moment de la réévaluation.  

Pour cela, il est important d'établir des conventions sur le moment où un article est considéré comme une partie de l'inventaire TEC d'un point de vue financier. Dans [!INCLUDE[prod_short](includes/prod_short.md)], les conventions disponibles sont les suivantes :  

-   Une composante achetée fait partie de l'inventaire de matières premières dès le report d'un achat comme étant facturé.  
-   Une composante achetée/semi-finie fait partie de l'inventaire TEC dès le report de sa consommation par rapport à un bon de production.  
-   Une composante achetée/semi-finie reste dans l'inventaire TEC jusqu’au moment où un bon de production (article fabriqué) est facturé.  

La manière dont la date d'évaluation de l'écriture valeur de la consommation est définie suit les mêmes règles que pour l'inventaire hors TEC. Pour plus d’informations, reportez-vous à la section [Déterminer si une sortie d'inventaire est liée à la réévaluation](design-details-revaluation.md#determining-whether-an-inventory-decrease-is-affected-by-revaluation).  

L'inventaire TEC peut être réévalué tant que la date de réévaluation n'est pas ultérieure à la date de report des écritures article correspondantes de type Consommation et tant que le bon de production correspondant n'a pas encore été facturé.  

> [!CAUTION]  
>  Le rapport **Évaluation de l'inventaire - TEC** affiche la valeur des écritures bon de production reportées et peut donc créer un peu de confusion pour les articles TEC qui ont été réévalués.  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : modes évaluation stock](design-details-costing-methods.md)   
 [Détails de conception : Évaluation de l'inventaire](design-details-inventory-valuation.md) [Gestion des coûts inventaire](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]