---
title: "Détails de conception\_: modes évaluation stock"
description: Cette rubrique décrit en quoi le mode évaluation du stock affecte la façon dont les valeurs réelles et budgétées sont capitalisées et prises en compte dans le calcul des coûts.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 05/12/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="design-details-costing-methods"></a>Détails de conception : modes évaluation stock

Le mode évaluation stock détermine si une valeur réelle ou budgétée est capitalisée et prise en compte dans le calcul des coûts. Au même titre que la date de report et la séquence, le mode d’évaluation coût a aussi une incidence sur l’enregistrement du flux des coûts.

> [!NOTE]
> Vous ne pouvez pas modifier le mode évaluation coût d’un article si des écritures article existent pour l’article. Pour plus d’informations, voir [Détails de conception : Modifier le mode évaluation stock des articles](design-details-changing-costing-methods.md).

Les méthodes suivantes sont prises en charge dans [!INCLUDE[prod_short](includes/prod_short.md)] :  

| Mode évaluation du stock | Description | Quand utiliser |
|--|--|--|
| FIFO | Le coût unitaire d'un article est la valeur réelle de toute réception de l'article, sélectionnée par la règle FIFO.<br /><br /> Dans l’évaluation de l’inventaire, nous considérons que les premiers articles placés dans l’inventaire sont vendus en premier. | Dans des environnements commerciaux où le coût de produit est stable.<br /><br /> (Lorsque les prix augmentent, le bilan indique une valeur plus élevée. Cela signifie que les impôts à payer augmentent, mais que les cotes de crédit et la capacité à emprunter de la trésorerie s'améliorent.)<br /><br /> Pour les articles à durée de conservation limitée, car les produits les plus anciens doivent être vendus avant que leur date limite de vente ne soit dépassée. |
| LIFO | Le coût unitaire d'un article est la valeur réelle de toute réception de l'article, sélectionnée par la règle LIFO.<br /><br /> Dans l’évaluation de l’inventaire, nous considérons que les derniers articles placés dans l’inventaire sont vendus en premier. | Interdit dans de nombreux pays/régions, car cela peut être utilisé pour réduire le profit.<br /><br /> (Lorsque les prix augmentent, la valeur de l'état des résultats diminue. Cela signifie que les impôts à payer diminuent, mais que la capacité à emprunter de la trésorerie se détériore.) |
| Moyenne | Le coût unitaire d'un article est calculé comme le coût unitaire moyen à chaque moment après un achat.<br /><br /> Pour l’évaluation de l’inventaire, nous considérons que tous les inventaires sont vendus simultanément. | Dans des environnements commerciaux où le coût de produit est instable.<br /><br /> Lorsque les inventaires sont compilés ou mélangés ensemble et ne peuvent pas être différenciés (par exemple, des produits chimiques). |
| Spécifique | Le coût unitaire d'un article est le coût exact auquel l'unité particulière a été reçue. | Pour la fabrication ou la transaction d'articles facilement identifiables ayant des coûts unitaires assez élevés.<br /><br /> Pour les articles soumis à une régulation.<br /><br /> Pour les articles ayant des numéros de série. |
| Standard | Le coût unitaire d'un article est prédéfini sur la base d'une estimation.<br /><br /> Lorsque le coût réel est réalisé plus tard, le coût standard doit être ajusté au coût réel à l'aide des valeurs d'écart. | Environnement où le contrôle des coûts est primordial.<br /><br /> Pour la fabrication répétitive, afin d'évaluer les coûts matière directs, les frais de main-d'œuvre directs, et les frais généraux matière.<br /><br /> Environnement où il existe une discipline et du personnel pour le maintien des standards. |

L'image suivante montre la manière dont les coûts circulent dans l'inventaire pour chaque mode d'évaluation de l'inventaire.  

![Visualisation des modes évaluation stock.](media/design_details_inventory_costing_7_costing_methods.png "Visualisation des modes évaluation stock")  

Les méthodes d'évaluation de l'inventaire diffèrent dans la façon d'évaluer les diminutions d'inventaire et d'utiliser le coût réel ou le coût standard comme base d'évaluation. Le tableau suivant explique les différentes caractéristiques. (La méthode LIFO est exclue, car elle est presque identique à la méthode FIFO).  
<!--Old  table
|Category|FIFO|Average|Standard|Specific|  
|-|----------|-------------|--------------|--------------|  
|General characteristic|Easy to understand|Based on period options: **Day**/**Week**/**Month**/**Quarter**/**Accounting Period**.<br /><br /> Can be calculated per item or per item/location/variant.|Easy to use, but requires qualified maintenance.|Requires item tracking on both inbound and outbound transaction.<br /><br /> Typically used for serialized items.|  
|Application/Adjustment|Application keeps track of **the remaining quantity**.<br /><br /> Adjustment forwards costs according to quantity application.|Application keeps track of the **remaining quantity**.<br /><br /> Costs are calculated and forwarded per the **valuation date**.|Application keeps track of the **remaining quantity**.<br /><br /> Application is based on FIFO.|All applications are fixed.|  
|Revaluation|Revalues invoiced quantity only.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|Revalues invoiced quantity only.<br /><br /> Can be done per item only.<br /><br /> Can be done backward in time.|Revalues invoiced and un-invoiced quantities.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|Revalues invoiced quantity only.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|  
|Miscellaneous|If you back-date an inventory decrease, then existing entries are NOT reapplied to provide a correct FIFO cost flow.|If you back-date an inventory increase or decrease, then the average cost is recalculated, and all affected entries are adjusted.<br /><br /> If you change the period or calculation type, then all affected entries must be adjusted.|Use the **Standard Worksheet** page to periodically update and roll up standard costs.<br /><br /> Is NOT supported per SKU.<br /><br /> No historic records exist for standard costs.|You can use specific item tracking without using the Specific costing method. Then the cost will NOT follow the lot number, but the cost assumption of the selected costing method.|  
-->
<!--Table flipped for slightly better readability -->

||Caractéristiques générales|Affectation/Ajustement |Réévaluation|Charges diverses de gestion |
|-|---------|---------|---------|---------|
|**FIFO**     |Facile à comprendre|Le lettrage effectue le suivi de **la quantité restante**.<br /><br /> L'ajustement transfère les coûts en fonction de l'affectation de quantité. |Réévalue uniquement la quantité facturée.<br /><br /> Peut être effectué par article ou par écriture du grand livre d’articles.<br /><br /> Peut être fait à une date antérieure.|Si vous antidatez une diminution d'inventaire, les écritures existantes ne sont PAS affectées à nouveau pour présenter un flux de coût FIFO correct.|
|**Moyenne**     |Sur la base des options de période : **Jour**/**Semaine**/**Mois**/**Trimestre**/**Période comptable**.<br /><br /> Peut être calculé par article ou par article/emplacement/variante.|Le lettrage effectue le suivi de la **quantité restante**.<br /><br /> Les coûts sont calculés et transférés par **date d'évaluation**. |Réévalue uniquement la quantité facturée.<br /><br /> Peut être effectué par article uniquement.<br /><br /> Peut être fait à une date antérieure. |Si vous antidatez une augmentation ou une diminution d'inventaire, le coût moyen est recalculé, et toutes les écritures affectées sont ajustées.<br /><br /> Si vous modifiez la période ou un type de calcul, toutes les écritures affectées doivent être ajustées.|
|**Standard**     |Facile à utiliser, mais requiert un entretien qualifié.|Le lettrage effectue le suivi de la **quantité restante**.<br /><br /> L'affectation est basée sur la méthode FIFO.|Réévalue les quantités facturées et non facturées.<br /><br /> Peut être effectué par article ou par écriture du grand livre d’articles.<br /><br /> Peut être fait à une date antérieure.|Utilisez la page **Standard Worksheet** pour régulièrement mettre à jour et rouler les coûts standard.<br /><br /> N'est PAS pris en charge par unité de stock.<br /><br /> Aucun enregistrement historique n'existe pour les coûts standard.|
|**Spécifique**     |Requiert une traçabilité à la fois sur les transactions entrante et sortante.<br /><br /> Généralement utilisé pour les articles fabriqués de série.|Tous les lettrages sont fixes.|Réévalue uniquement la quantité facturée.<br /><br /> Peut être effectué par article ou par écriture du grand livre d’articles.<br /><br /> Peut être fait à une date antérieure.|Vous pouvez utiliser le suivi d'article spécifique sans utiliser le mode d'évaluation spécifique. Alors le coût ne suit PAS le numéro de lot, mais l'acceptation du coût du mode d'évaluation sélectionné.|

## <a name="example"></a>Exemple :

Cette section donne des exemples de la manière dont les divers modes d'évaluation coût affectent la valeur inventaire.  

Le tableau suivant montre les augmentations et diminutions d'inventaire sur lesquelles les exemples sont basés.  

|Date de report|Quantité|N° séquence |  
|------------------|--------------|---------------|  
|01/01/20|1|1|  
|01/01/20|1|2|  
|01/01/20|1|3|  
|01/02/20|-1|4|  
|01/03/20|-1|5|  
|01/04/20|-1|6|  

> [!NOTE]  
> La quantité qui en résulte dans l'inventaire est égale à zéro. Par conséquent, la valeur de l'inventaire doit également être zéro, quel que soit le mode évaluation coût.  

### <a name="effect-of-costing-methods-on-valuing-inventory-increases"></a>Effet des modes évaluation coût sur l'évaluation des augmentations d'inventaire

Pour les articles utilisant les modes évaluation coût qui utilisent le coût réel comme base d'évaluation (**FIFO**, **LIFO**, **Moyenne** ou **Spécifique**), les augmentations d'inventaire sont évaluées au coût d'acquisition de l'article.  

- **Standard**  

    Pour les articles qui utilisent le mode d'évaluation du coût **Standard**, les entrées d'inventaire sont évaluées au coût standard actuel de l'article.  

#### <a name="standard"></a>Standard

Pour les articles qui utilisent le mode d'évaluation du coût **Standard**, les entrées d'inventaire sont évaluées au coût standard actuel de l'article.  

### <a name="effect-of-costing-methods-on-valuing-inventory-decreases"></a>Effet des modes évaluation coût sur l'évaluation des diminutions d'inventaire

- **FIFO**  

    Pour les articles utilisant le mode évaluation stock **FIFO**, les articles achetés en premier sont toujours les premiers vendus (numéros de séquence 3, 2 et 1, dans cet exemple). Par conséquent, les diminutions d'inventaire sont évaluées en prenant en compte la valeur de la première augmentation d'inventaire.  

     La valeur COGS est calculée à l'aide de la valeur des premières acquisitions inventaire.  

     Le tableau suivant montre la manière dont les sorties d’inventaire sont évaluées pour le mode d’évaluation de l’inventaire **FIFO**.  

    |Date de report|Quantité|Coût indiqué (réel)|N° séquence |  
    |------------------|--------------|----------------------------|---------------|  
    |01/02/20|-1|-10,00|4|  
    |01/03/20|-1|-20,00|5|  
    |01/04/20|-1|-30,00|6|  

- **LIFO**  

    Pour les articles utilisant le mode évaluation stock **LIFO**, les articles achetés le plus récemment sont toujours les premiers vendus (numéros de séquence 3, 2 et 1, dans cet exemple). Par conséquent, les diminutions d'inventaire sont évaluées en prenant en compte la valeur de la dernière augmentation d'inventaire.  

     La valeur COGS est calculée à l'aide de la valeur des acquisitions inventaire les plus récentes.  

     Le tableau suivant montre la manière dont les sorties d’inventaire sont évaluées pour le mode d’évaluation de l’inventaire **LIFO**.  

    |Date de report|Quantité|Coût indiqué (réel)|N° séquence |  
    |------------|--------|--------------------|---------|  
    |01/02/20|-1|-30,00|4|  
    |01/03/20|-1|-20,00|5|  
    |01/04/20|-1|-10,00|6|  

- **Moyenne**  

    Pour les articles qui utilisent le mode d’évaluation du stock **Moyen**, les sorties d’inventaire sont évaluées en calculant la moyenne pondérée de l’inventaire restant au dernier jour de la période coût moyen dans laquelle la sortie d’inventaire a été reportée. Pour plus d'informations, voir [Détails de conception : coût moyen](design-details-average-cost.md).  

     Le tableau suivant montre la manière dont les sorties d’inventaire sont évaluées pour le mode d’évaluation de l’inventaire **Moyen**.  

    | Date de report | Quantité | Coût indiqué (réel) | N° séquence  |
    |--|--|--|--|
    | 01/02/20 | -1 | -20,00 | 4 |
    | 01/03/20 | -1 | -20,00 | 5 |
    | 01/04/20 | -1 | -20,00 | 6 |

- **Standard**  

    Pour les articles utilisant le mode évaluation inventaire **Standard**, les sorties d’inventaire sont évaluées de manière similaire au mode évaluation inventaire **FIFO**, sauf que l’évaluation est basée sur un coût standard, pas sur le coût réel.  

    Le tableau suivant montre la manière dont les sorties d’inventaire sont évaluées pour le mode d’évaluation de l’inventaire **Standard**.  

    |Date de report|Quantité|Coût indiqué (réel)|N° séquence |  
    |------------------|--------------|----------------------------|---------------|  
    |01/02/20|-1|-15,00|4|  
    |01/03/20|-1|-15,00|5|  
    |01/04/20|-1|-15,00|6|  

- **Spécifique**  

    Les modes d'évaluation coût partent du principe que les flux de coûts vont de l'augmentation d'inventaire vers la diminution d'inventaire. Toutefois, s'il existe des informations plus précises sur le flux des coûts, vous pouvez remplacer cette supposition en créant une affectation fixe entre les écritures. Une affectation fixe crée un lien entre une diminution d'inventaire et une augmentation d'inventaire spécifique, et supervise le flux des coûts en conséquence.  

    Pour les articles utilisant le mode d’évaluation stock **Spécifique**, les sorties d’inventaire sont évaluées en fonction de l’entrée d’inventaire qui est liée par le lettrage fixe.  

    Le tableau suivant montre la manière dont les sorties d’inventaire sont évaluées pour le mode d’évaluation de l’inventaire **Spécifique**.  

    |Date de report|Quantité|Coût indiqué (réel)|Écriture affectée à|N° séquence |
    |------------|--------|--------------------|----------------|---------|  
    |01/02/20|-1|-20,00|**2**|4|  
    |01/03/20|-1|-10,00|**1**|5|  
    |01/04/20|-1|-30,00|**3**|6|  

## <a name="see-also"></a>Voir aussi

[Détails de conception : évaluation du coût de l’inventaire](design-details-inventory-costing.md)  
[Détails de conception : écart](design-details-variance.md)  
[Détails de conception : coût moyen](design-details-average-cost.md)  
[Détails de conception : affectation d’articles](design-details-item-application.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Glossaire des termes dans les processus métier Dynamics 365](/dynamics365/guidance/business-processes/glossary)  
[Vue d’ensemble Définir les coûts des produits et des services](/dynamics365/guidance/business-processes/product-service-define-cost-overview)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
