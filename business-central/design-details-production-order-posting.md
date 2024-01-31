---
title: "Détails de conception\_: report de bon de production | Microsoft Docs"
description: 'Comme pour le report d''ordre d''assemblage, les composantes consommées et le temps du poste utilisé sont convertis et sortis en tant qu''article produit lorsque le bon de production est terminé.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 06/08/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Détails de conception : validation d'ordre de fabrication
Comme pour le report d'ordre d'assemblage, les composantes consommées et le temps du poste utilisé sont convertis et sortis en tant qu'article produit lorsque le bon de production est terminé. Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-assembly-order-posting.md). Toutefois, le flux des coûts des ordres d'assemblage est moins complexe, notamment parce que le report du coût d'assemblage ne se produit qu'une fois et ne génère donc pas d'inventaire travaux en cours.


Les transactions se produisant pendant le processus de fabrication peuvent être suivies au fil des phases suivantes :  

1.  Achat de matériels et autres entrées de fabrication.  
2.  Conversion en travaux en cours.  
3.  Conversion en inventaire de produits finis.  
4.  Vente des produits finis.  

Par conséquent, outre les comptes inventaire réguliers, une compagnie manufacturière doit déterminer trois comptes inventaire distincts pour enregistrer les transactions à différentes phases de la production.  

|Compte inventaire|Description|  
|-----------------------|---------------------------------------|  
|**Compte matières premières**|Inclut le coût de matières premières achetées mais pas encore transférées vers la production. Le solde dans le compte de matières premières indique le coût des matières premières disponibles.<br /><br /> Lorsque les matières premières entrent dans le service de production, le coût des matières est transféré du compte Matières premières au compte TEC.|  
|**Compte Travaux en cours (TEC)**|Additionne les coûts exposés pendant la production dans la période comptable. Le compte TEC est débité du coût de matières premières qui sont transférées à partir de l'entrepôt des matières premières, le coût du travail direct effectué, et les frais généraux de fabrication encourus.<br /><br /> Le compte TEC est crédité pour le coût de fabrication total d'unités qui sont renseignées dans l'usine et transférées vers l'entrepôt des produits finis.|  
|**Compte de produits finis**|Ce compte inclut le coût total de fabrication d'unités qui sont renseignées mais pas encore vendues. Au moment de la vente, le coût des unités vendues est transféré du compte de produits finis sur le compte coût des biens vendus.|  

La valeur de l'inventaire est calculée en suivant les coûts de toutes les augmentations et diminutions, comme exprimé par l'équation suivante :  

* valeur d'inventaire = solde d'ouverture de l'inventaire + valeur de toutes les augmentations - valeur de toutes les diminutions  

Selon le type d'inventaire, les augmentations et diminutions sont représentées par des transactions différentes.  

||Entrées|Sorties|  
|-|---------------|---------------|  
|**Inventaire de matières premières**|-   Achats nets de matériel<br />-   Production de produits semi-finis<br />-   Consommation négative|Consommation matière|  
|**Inventaire TEC**|-   Consommation matière<br />-   Consommation de capacité<br />-   Frais généraux matière|Production de produits finis (coût de produits fabriqués)|  
|**Inventaire de produits finis**|Production de produits finis (coût de produits fabriqués)|-   Ventes (coût des biens vendus)<br />-   Production négative|  
|**Inventaire de matières premières**|-   Achats nets de matériel<br />-   Production de produits semi-finis<br />-   Consommation négative|Consommation matière|  

Les valeurs des augmentations et des diminutions sont enregistrées dans les différents types d'inventaire manufacturé de la même manière que pour l'inventaire acheté. Chaque fois qu'une transaction d'augmentation ou de diminution de stock a lieu, une écriture article et une écriture GL correspondante sont créées pour le montant. Pour plus d'informations, voir [Détails de conception : comptabilisation stock](design-details-inventory-posting.md).  

Bien que les valeurs des transactions qui sont liées aux marchandises achetées soient reportées uniquement en tant qu'écritures article comportant des écritures valeur associées, les transactions liées aux articles produits sont reportées en tant qu'écritures capacité comportant des écritures valeur associées, en plus des écritures article.  

## Structure de report  
Le report des bons de production sur l'inventaire TEC implique la production, la consommation et la capacité.  

Le schéma suivant montre les routines de report impliquées dans le codeunit 22.  

![Routines de report des bons de production.](media/design_details_inventory_costing_14_production_posting_1.png "Routines de report des bons de production")  

Le schéma suivant montre les associations entre les écritures générées et les objets de coûts.  

![Flux d’écritures de production.](media/design_details_inventory_costing_14_production_posting_2.png "Flux d'écritures de production")  

L'écriture capacité décrit la consommation de la capacité en termes d'unités de temps, alors que l'écriture valeur associée décrit la valeur de la consommation de capacité spécifique.  

L'écriture article décrit la consommation ou la production de matière en termes de quantités, alors que l'écriture valeur associée décrit la valeur de consommation ou production de cette matière spécifique.  

Une écriture valeur qui décrit la valeur de l'inventaire TEC peut être associée à l'une des combinaisons suivantes d'objet de coûts :  

-   Une ligne bon de production, un atelier ou une unité de production, et une écriture capacité.  
-   Une ligne bon de production, un article et une écriture article.  
-   Uniquement une ligne O.F.  

Pour plus d'informations sur la manière dont les coûts de fabrication et d'assemblage sont reportés dans le grand livre, reportez-vous à [Détails de conception : report inventaire](design-details-inventory-posting.md).  

## Report de capacité  
Le report de la production à partir de la dernière ligne itinéraire bon de production a pour résultat la création d'une écriture capacité pour le produit fini, en plus de son augmentation d'inventaire.  

 L'écriture capacité est un enregistrement du temps passé à fabriquer l'article. L'écriture valeur liée décrit l'augmentation de la valeur inventaire TEC, qui est la valeur du coût de conversion. Pour plus d'informations, voir « À partir du grand livre de capacité » dans [Détails de conception : Comptes du grand livre](design-details-accounts-in-the-general-ledger.md).  

## Évaluation des coûts de l'ordre de fabrication  
 Pour contrôler l'inventaire et les coûts de production, une compagnie manufacturière doit mesurer le coût des bons de production, car le coût standard prédéterminé de chaque article produit est capitalisé dans le bilan. Pour plus d'informations sur la raison pour laquelle les articles produits utilisent le mode évaluation stock Standard, reportez-vous à [Détails de conception : modes évaluation stock](design-details-costing-methods.md).  

> [!NOTE]  
>  Dans des environnements qui n'utilisent pas le mode évaluation stock standard, le coût réel plutôt que le coût standard des articles produits est capitalisé sur le bilan.  

Le coût réel d'un bon de production comprend les composantes coût suivantes :  

-   Coût matière réel  
-   Coût capacité ou coût de sous-traitance réel  
-   Frais généraux matière  

Ces coûts réels sont reportés sur la commande de production et comparés au coût standard pour calculer les variations. Les écarts sont calculés pour chaque composante des coûts article : matières premières, capacité, sous-traitant, utilisation fixe de capacité et frais généraux de fabrication. Les écarts peuvent être analysés pour déterminer les problèmes, comme les déchets excessifs en traitement.  

Dans des environnements de coût standard, l'évaluation du stock d'un ordre de fabrication est basée sur le mécanisme suivant :  

1.  Lorsque la dernière opération d'itinéraire est reportée, le coût du bon de production est reporté dans le grand livre article et défini sur le coût prévu.  

    Ce coût correspond à la quantité produite reportée dans le journal de production multipliée par le coût standard qui est copié à partir de la fiche article. Le coût est traité en tant que coût prévu jusqu'à ce que l'ordre de fabrication soit terminé. Pour plus d'informations, voir [Détails de conception : validation du coût prévu](design-details-expected-cost-posting.md).  

    > [!NOTE]  
    >  Cela diffère du report d'ordre d'assemblage, qui reporte toujours les coûts réels. Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-assembly-order-posting.md).  
2.  Lorsque le bon de production est défini sur **Terminé**, la commande est facturée en exécutant le traitement en lot **Ajuster coûts - Écr. article**. Par conséquent, le coût total de la commande est calculé en fonction du coût standard des matières et de la capacité consommées. Les écarts entre les coûts standard calculés et les coûts de production réels sont calculés et reportés.  

## Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : Report d'ordre d'assemblage](design-details-assembly-order-posting.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md) [Finance](finance.md)  
 [Utiliser Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]