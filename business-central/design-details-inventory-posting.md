---
title: Détails de conception - Report inventaire | Microsoft Docs
description: Chaque transaction inventaire, par exemple une réception achat ou une livraison vente, reporte deux écritures de différents types.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: edff39ccb01cc7da7e8a0387a4737088b0be231d
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8138658"
---
# <a name="design-details-inventory-posting"></a>Détails de conception : report inventaire

Chaque transaction inventaire, par exemple une réception achat ou une livraison vente, reporte deux écritures de différents types.  

|Type d'écriture|Description|  
|----------|-----------|  
|Quantité|Reflète la modification de la quantité en inventaire. Ces informations sont stockées dans les écritures du grand livre d'articles.<br /><br /> Accompagné des écritures d'affectation article.|  
|Valeur|Reflète la modification de la valeur inventaire. Ces informations sont stockées dans les écritures valeur.<br /><br /> Chaque écriture article ou écriture de capacité peut posséder une ou plusieurs écritures du grand livre de capacité.<br /><br /> Pour plus d'informations sur les écritures de valeur de capacité liées à l'utilisation des ressources de production ou d'assemblage, reportez\-vous à [Détails de conception : validation d'ordre de fabrication](design-details-production-order-posting.md).|  

 En rapport avec les reports de quantité, les écritures d'affectation article existent pour lier augmentation de l'inventaire avec la diminution de l'inventaire. Cela permet au moteur d'évaluation de transférer les cous des augmentations aux diminutions liées et vice versa. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-application.md).  

 Les écritures article, les écritures valeur, ainsi que les écritures affectation article sont créées suite au report d'une ligne journal article, soit indirectement lors du report d'une ligne commande, soit directement sur la page journal article.  

 À intervalles réguliers, les écritures valeur créées parmi les écritures du grand livre d'inventaire sont reportées dans le grand livre pour rapprocher les deux grands livres à des fins de contrôle financier. Pour plus d'informations, voir [Détails de conception : rapprochement de comptabilité](design-details-reconciliation-with-the-general-ledger.md).  

 ![Flux d’écriture lors de la conciliation de l’inventaire avec le grand livre.](media/design_details_inventory_costing_1_entry_flow.png "Flux d'écriture lors du rapprochement de l'inventaire avec le grand livre")  

## <a name="example"></a>Exemple :

L'exemple suivant indique comment les écritures article, les écritures valeur et les écritures d'affectation article créent des écritures dans le grand livre.  

 Vous reportez un bon de commande comme reçu et facturé pour 10 articles avec un coût unitaire direct de 7 $ et des frais généraux d'1 $. La date de report est le 01/01/20. Les écritures suivantes sont créées.  

### <a name="item-ledger-entries-1"></a>Écritures article (1)

|Date de report|Type écriture|Coût indiqué (réel)|Quantité|N° séquence |  
|------------|----------|--------------------|--------|---------|  
|01/01/20|Achat|80.00|10|1|  

### <a name="value-entries-1"></a>Écritures valeur (1)

|Date de report|Type écriture|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------|----------|--------------------|---------------------|---------|  
|01/01/20|Coût direct|70.00|1|1|  
|01/01/20|Coût indirect|10.00|1|2|  

### <a name="item-application-entries-1"></a>Écritures affectation article (1)

|N° séquence |N° écriture article gr. livre|N° écriture article entrant|N° écriture article sortant|Quantité|  
|---------|---------------------|----------------------|-----------------------|--------|  
|1|1|1|0|10|  

 Ensuite, vous reportez une vente de 10 unités de l'article avec une date de report de 15/01/20.  

### <a name="item-ledger-entries-2"></a>Écritures article (2)

|Date de report|Type écriture|Coût indiqué (réel)|Quantité|N° séquence |  
|------------|----------|--------------------|--------|---------|  
|15/01/20|Vente|-80,00|-10|2|  

### <a name="value-entries-2"></a>Écritures valeur (2)

|Date de report|Type écriture|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------|----------|--------------------|---------------------|---------|  
|15/01/20|Coût direct|-80,00|2|3|  

### <a name="item-application-entries-2"></a>Écritures affectation article (2)

|N° séquence |N° écriture article gr. livre|N° écriture article entrant|N° écriture article sortant|Quantité|  
|---------|---------------------|----------------------|-----------------------|--------|  
|2|2|1|2|-10|  

À la fin de la période comptable, vous exécutez le traitement en lot **Reporter le coût de l'inventaire au grand livre** pour effectuer un rapprochement entre ces transactions d'inventaire et le grand livre.  

 Pour plus d'informations, voir [Détails de conception : comptes du grand livre](design-details-accounts-in-the-general-ledger.md).  

 Les tables suivantes indiquent le résultat du rapprochement des mouvements d'inventaire de cet exemple avec le grand livre.  

### <a name="value-entries-3"></a>Écritures valeur (3)  

|Date de report|Type écriture|Coût indiqué (réel)|Coût reporté dans grand livre|N° écriture article gr. livre|N° séquence |  
|------------|----------|--------------------|------------------|---------------------|---------|  
|01/01/20|Coût direct|70.00|70.00|1|1|  
|01/01/20|Coût indirect|10.00|10.00|1|2|  
|15/01/20|Coût direct|-80,00|-80,00|2|3|  

### <a name="general-ledger-entries-3"></a>Écritures de grand livre (3)

|Date de report|Compte du grand livre|N° compte (démonstration Fr-FR)|Montant|N° séquence |  
|------------|-----------|------------------------|------|---------|  
|01/01/20|[Compte inventaire]|2130|70.00|1|  
|01/01/20|[Compte coût direct affecté]|7291|-70,00|2|  
|01/01/20|[Compte inventaire]|2130|10.00|3|  
|01-01-07|[Compte frais généraux affectés]|7292|-10,00|4|  
|15/01/20|[Compte inventaire]|2130|-80,00|5|  
|15/01/20|[Compte variation stock]|7290|80.00|6|  

> [!NOTE]  
> La date de report des écritures est la même que pour les écritures valeur associées.  
> 
> Le champ **Coût reporté dans grand livre** de la table **Écriture valeur** est renseigné.  

 La relation entre les écritures valeur et les écritures est stockée dans la table **Relation GL - Grand livre article**.  

### <a name="relation-entries-in-the-gl--item-ledger-relation-table-3"></a>Liens écritures dans le grand livre – Table liens grand livre article (3)

|N° écriture comptable|N° écriture valeur|N° registre GL|  
|-------------|---------------|----------------|  
|1|1|1|  
|2|1|1|  
|3|2|1|  
|4|2|1|  
|5|3|1|  
|6|3|1|  

## <a name="assembly-and-production-posting"></a>Report d'assemblage et de production

Les écritures capacité et ressource représentent le délai qui est reporté comme étant consommé dans la production ou l'assemblage. Ces coûts capacité sont reportés comme écritures valeur dans le grand livre en même temps que les coûts matière impliqués dans une structure similaire telle que décrite pour les écritures de cette rubrique.  

Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-assembly-order-posting.md).  

## <a name="see-also"></a>Voir aussi

 [Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
 [Détails de conception : comptes de la comptabilité](design-details-accounts-in-the-general-ledger.md)  
 [Détails de conception : Composantes des coûts](design-details-cost-components.md) [Gestion des coûts inventaire](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]