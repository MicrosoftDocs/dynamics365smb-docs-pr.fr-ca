---
title: "Détails de conception\_:\_réévaluation"
description: Vous pouvez réévaluer l'inventaire en fonction de la base d'évaluation reflétant le plus précisément la valeur d'inventaire.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 07/07/2023
ms.custom: bap-template
---

# Détails de conception : réévaluation

Vous pouvez réévaluer l'inventaire en fonction de la base d'évaluation reflétant le plus précisément la valeur d'inventaire. Vous pouvez également antidater une réévaluation, afin de mettre à jour correctement le coût des biens vendus (COGS) pour les articles qui ont déjà été vendus. Les articles utilisant le mode évaluation stock standard et qui n’ont pas été entièrement facturés peuvent également être réévalués.  

Dans [!INCLUDE[prod_short](includes/prod_short.md)], la flexibilité suivante est prise en charge sur la réévaluation :  

- La quantité réévaluable peut être calculée pour n'importe quelle date, également dans le passé.  
- Pour les articles utilisant le mode évaluation stock standard, les écritures coût prévu sont incluses dans la réévaluation.  
- Des diminutions d'inventaire affectées par la réévaluation sont détectées.  

## Calculer la quantité réévaluable

La quantité réévaluable est la quantité restante en inventaire qui est disponible à une date donnée. La quantité correspond au total des écritures article entièrement facturées que vous reportez à la date de réévaluation ou avant.  

> [!NOTE]  
>  Les articles utilisant le mode évaluation coût standard sont traités de façon différente lors du calcul de la quantité réévaluable par article, emplacement et variante. Les quantités et les valeurs des écritures articles qui ne sont pas entièrement facturées sont incluses dans la quantité réévaluable.  

Une fois qu'une réévaluation a été reportée, vous pouvez reporter une diminution ou une augmentation d'inventaire avec une date de report antérieure à la date de report de la réévaluation. Cependant, cette quantité n'est pas affectée par la réévaluation. Pour équilibrer l'inventaire, seule la quantité réévaluable initiale est considérée.  

Étant donné que vous pouvez effectuer la réévaluation à n’importe quelle date, vous devez avoir des conventions pour le moment où un article est considéré comme faisant partie de l'inventaire. Par exemple, lorsque l'article figure dans l'inventaire et lorsque l'article est un travail en cours (TEC).  

### Exemple :  

L'exemple suivant montre à quel moment un article TEC se transforme pour devenir une partie de l'inventaire. L'exemple est basé sur la production d'une chaîne de 150 liens.  

![Inventaire et réévaluation TEC.](media/design_details_inventory_costing_10_revaluation_wip.png "Inventaire et réévaluation TEC")  

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

## Coût prévu de la réévaluation

La quantité réévaluable est la somme de la quantité des écritures article entièrement facturées avec une date de report égale ou antérieure à la date de réévaluation. Lorsque certains articles sont reçus ou livrés, mais pas facturés, vous ne pouvez pas calculer leur valeur d'inventaire. Les articles utilisant le mode évaluation stock standard ne sont pas limités à cet égard.  

> [!NOTE]  
>  L'inventaire TEC est un autre type de coût prévu qui peut être réévalué, dans le cadre de certaines règles. Pour plus d’informations, voir [Réévaluation de l'inventaire TEC](design-details-revaluation.md#wip-inventory-revaluation).  

Lors du calcul de la quantité réévaluable pour les articles utilisant le mode d’évaluation du coût Standard, le calcul inclut les écritures article qui ne sont pas complètement facturées. Les écritures sont réévaluées lorsque vous reportez la réévaluation. Lorsque vous facturez l’écriture réévaluée, les écritures valeur suivantes sont créées :  

- L'écriture valeur facturée habituelle avec un type d'écriture **Coût direct**. Le coût indiqué de cette écriture est le coût direct de la ligne source.  
- Une écriture valeur avec le type d'écriture **Écart**. Cette écriture enregistre la différence entre le coût facturé et le coût standard réévalué.  
- Une écriture valeur avec le type d'écriture **Réévaluation**. Cette écriture enregistre l'inversion de la réévaluation du coût prévu.

### Exemple :  

L’exemple suivant est basé sur la production de la chaîne dans l’exemple précédent. Cet exemple illustre comment les trois types d’entrées sont créés, sur la base du scénario suivant :  

1.  Vous reportez les liens achetés comme reçus avec un coût unitaire de 2,00 $.  
2.  Vous reportez une réévaluation des liens avec un nouveau coût unitaire de 3,00 $, mettant à jour le coût standard à 3,00 $.  
3.  Vous reportez l’achat d’origine des liens de chaîne comme facturés, ce qui crée les écritures valeur suivantes :  

    1.  Une écriture valeur facturée avec le type d'écriture **Coût direct**.  
    2.  Une écriture valeur avec le type d'écriture **Réévaluation** pour enregistrer la contrepassation de la réévaluation du coût prévu.  
    3.  Une écriture valeur avec le type d'écriture Écart, qui enregistre la différence entre le coût facturé et le coût standard réévalué.  

Le tableau suivant affiche les résultats.  

|Étape|date de report|Type écriture|Date évaluation|Coût indiqué (prévu)|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|----------|------------------|----------------|--------------------|------------------------------|----------------------------|---------------------------|---------------|  
|1.|15/01/20|Coût direct|15/01/20|300.00|0.00|1|1|  
|2.|20/01/20|Réévaluation|20/01/20|150.00|0.00|1|2|  
|3.a.|15/01/20|Coût direct|15/01/20|-300,00|0.00|1|3|  
|3.b.|15/01/20|Réévaluation|20/01/20|-150,00|0.00|1|4|  
|3.c.|15/01/20|Ecart|15/01/20|0.00|450.00|1|5|  

## Déterminer si une réévaluation affecte une diminution d'inventaire  

Utilisez la date du report ou de la réévaluation pour déterminer si une diminution d'inventaire est affectée par une réévaluation.  

Le tableau suivant montre les critères utilisés pour un article qui n’utilise pas le mode évaluation stock moyen.  

|Scénario|N° séquence |Timing|Lié à la réévaluation|  
|--------------|---------------|------------|-----------------------------|  
|A|Antérieur au numéro d'écriture réévaluation.|Antérieur à la date de report de réévaluation|Non|  
|B|Antérieur au n° d'écriture réévaluation.|Égal à la date de report de réévaluation|Non|  
|C|Antérieur au n° d'écriture réévaluation.|Postérieur à la date de report de réévaluation|Oui|  
|J|Ultérieur au n° d'écriture réévaluation.|Antérieur à la date de report de réévaluation|Oui|  
|E|Ultérieur au n° d'écriture réévaluation.|Égal à la date de report de réévaluation|Oui|  
|F|Ultérieur au n° d'écriture réévaluation.|Postérieur à la date de report de réévaluation|Oui|  

### Exemple :  

L’exemple suivant, qui illustre la réévaluation d’un article qui utilise le mode d’évaluation du stock FIFO. L’exemple est basé sur le scénario suivant :  

1.  Le 01/01/20, vous reportez un achat de 6 unités.  
2.  Le 02/01/20, vous reportez une vente de 1 unité.  
3.  Le 03/01/20, vous reportez une vente de 1 unité.  
4.  Le 04/01/20, vous reportez une vente de 1 unité.  
5.  Le 01/03/20, vous calculez la valeur d'inventaire pour l’article, et reportez une réévaluation du coût unitaire de l’article en $ de 10,00 à 8,00 $.  
6.  Le 02/01/20, vous reportez une vente de 1 unité.  
7.  Le 03/01/20, vous reportez une vente de 1 unité.  
8.  Le 04/01/20, vous reportez une vente de 1 unité.  
9. Vous exécutez le traitement en lot **Ajuster coûts - Écr. article**.  

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

## Réévaluation de l'inventaire TEC  

La réévaluation de l'inventaire TEC implique que vous réévaluiez les composantes enregistrées en tant qu'inventaire TEC.  

Il est important d’avoir des conventions qui contrôlent quand un article est un inventaire TEC d’un point de vue financier. Dans [!INCLUDE[prod_short](includes/prod_short.md)], les conventions disponibles sont les suivantes :  

- Une composante achetée fait partie de l'inventaire de matières premières lorsque vous reportez un achat comme étant facturé.  
- Une composante achetée/semi-finie fait partie de l'inventaire TEC lorsque vous reportez sa consommation avec un bon de production.  
- Une composantee achetée/semi-finie reste dans l'inventaire TEC jusqu’au moment où vous facturez un bon de production (article fabriqué).  

La manière dont la date d’évaluation de l’écriture valeur de la consommation est définie suit les mêmes règles que pour l'inventaire hors TEC. Pour en savoir plus, accédez à [Déterminer si une réévaluation affecte une diminution d'inventaire](#determine-whether-revaluation-affects-an-inventory-decrease).  

Vous pouvez réévaluer l'inventaire TEC dans les conditions suivantes :

- La date de réévaluation est antérieure aux dates de report des écritures article correspondantes de type Consommation.
- Vous n’avez pas facturé le bon de production.  

> [!CAUTION]  
> Le rapport **Évaluation de l'inventaire - TEC** affiche la valeur des écritures bon de production reportées et peut donc créer un peu de confusion pour les articles TEC réévalués.  

## Réévaluer les articles avec la méthode du coût moyen

Vous ne pouvez réévaluer les articles qui utilisent la méthode de coût moyen que si **Calculer par** est défini sur *Article*.

Vous ne pouvez effectuer la réévaluation qu’à la fin de la période sélectionnée dans le champ **Période coût moyen** sur la page **Configuration inventaire**.

La réévaluation n’affectera pas les transactions négatives du mois en cours, c’est pourquoi les écritures entrantes entièrement affectées ne sont pas non plus incluses.

### Exemple :

Cet exemple montre ce qui se passe lorsque vous calculez la valeur d'inventaire sur la page **Journal réévaluation article**. Sur la page **Configuration inventaire**, **Article** est choisi dans le champ **Type calcul coût moyen** et **Mois** est choisi dans le champ **Période coût moyen**.

Le tableau suivant répertorie les écritures article pour l’exemple d’article coût moyen, ITEM1.

|date de report|Type écriture article|Quantité|Montant (réel)|N° séquence |
|----|----|----|----|----|
25/04/23|Achats|5|5.00|1
26/04/23|Achats|3|3.00|2
27/04/23|Vente|-5|-5,00|3
28/04/23|Vente|-1|-1,00|4
13/05/23|Achats|2|20.00|5
17/06/23|Vente|-6|-22,00|6

Le tableau suivant montre le résultat de l’exécution du rapport **Calculer valeur inventaire** avec différentes dates de report.

|date de report|Quantité|Commentaire|
|---|---|-------------|
30/04/23|2|Comprend uniquement la quantité restante de l’écriture 2. L’écriture 1 est complètement affectée avant la date de report et l’écriture 5 est après la date de report.
31/05/23|4|Comprend les quantités restantes des écritures 2 et 13.
30/06/23|0|Pas de quantité restante à la date de report.

Le résultat des écritures suivantes sera 0, quelle que soit la date de report.

|date de report|Type écriture article|Quantité|Montant (réel)|N° séquence |
|----|----|----|----|----|
13/05/23|Achats|5|5.00|1
26/04/23|Vente|-5|5.00|2

## Voir aussi  

[Détails de conception : mode d’évaluation de l’inventaire](design-details-inventory-costing.md)   
[Détails de conception : modes évaluation stock](design-details-costing-methods.md)   
[Détails de conception : évaluation de l'inventaire](design-details-inventory-valuation.md)
[Gestion des coûts d'inventaire](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
