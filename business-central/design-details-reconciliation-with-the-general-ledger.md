---
title: Détails de conception - rapprochement avec le grand livre | Microsoft Docs
description: Cette rubrique décrit le rapprochement avec le grand livre lorsque vous reportez des transactions inventaire, telles que des livraisons vente, des sorties de production ou des ajustements négatifs.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, reconciliation, general ledger, inventory
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 3f3a90142081ad0bc3096bdde1830924c2998d68
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4751240"
---
# <a name="design-details-reconciliation-with-the-general-ledger"></a>Détails de conception : rapprochement de GL
Lorsque vous reportez des mouvements d'inventaire, tels que des livraisons vente, des productions ou des ajustements négatifs, les modifications de quantité et de valeur effectuées dans l'inventaire sont enregistrées respectivement dans les écritures du grand livre article et les écritures valeur. L'étape suivante de ce processus consiste à reporter les valeurs de l'inventaire dans les comptes inventaire du grand livre.  

Il existe deux méthodes pour rapprocher l'écriture inventaire au grand livre :  

* Manuellement, en exécutant le traitement en lot **Reporter le coût de l'inventaire au grand livre**.  
* Automatiquement, chaque fois que vous reportez une transaction d'inventaire.  

## <a name="post-inventory-cost-to-gl-batch-job"></a>Traitement par lots Reporter le coût de l'inventaire au grand livre.  
Lorsque vous lancez le traitement en lot **Reporter le coût de l'inventaire au grand livre**, les écritures sont créés sur la base des écritures valeur. Vous avez le choix de résumer les écritures pour chaque écriture valeur, ou créer des écritures pour chaque combinaison de date de report, code d'emplacement, groupe de reports d'inventaire, groupe de reports commerciaux généraux et groupe de reports produit généraux.  

Les dates de report des écritures sont fixées à la date de report de l'écriture valeur correspondante, sauf si l'écriture valeur se trouve dans une période comptable fermée. Dans ce cas, l'écriture valeur est ignorée et vous devez modifier la configuration du grand livre ou la configuration utilisateur pour activer le report dans la plage de dates.  

Lorsque vous exécutez ce traitement en lot **Reporter le coût de l'inventaire au grand livre**, il se peut que vous receviez des erreurs en raison d'une configuration manquante ou d'une configuration de dimension incompatible. Si le traitement en lot détecte des erreurs dans la configuration de dimension, il les ignore et utilise les dimensions de l'écriture valeur. Pour toute autre erreur, le traitement par lots ignore la validation des écritures valeur et les répertorie à la fin de l'état dans la section intitulée **Écritures ignorées**. Pour reporter ces écritures, vous devez d'abord corriger les erreurs. Pour afficher la liste des erreurs avant d'exécuter le traitement en lot, vous pouvez exécuter le rapport **Reporter le coût de l'inventaire au grand livre - Test**. Ce rapport répertorie toutes les erreurs détectées durant un test de report. Vous pouvez corriger les erreurs, puis exécuter le traitement en lot de report des coûts inventaire sans ignorer aucune entrée.  

## <a name="automatic-cost-posting"></a>Report coûts automatique  
Pour configurer l'exécution automatique du report des coûts dans le grand livre lorsque vous reportez une transaction d'inventaire, activez la case à cocher **Report coûts automatique** sur la page **Configuration de l'inventaire**. La date de report de l'écriture est identique à la date de report de l'écriture article.  

## <a name="account-types"></a>Types de compte  
Lors du rapprochement, les valeurs d'inventaire sont reportées sur le compte de l'inventaire dans le bilan. Le même montant, mais avec le signe opposé, est reporté sur le compte de contrepartie approprié. Généralement, le compte de contrepartie est un compte état des résultats. Néanmoins, lorsque vous reportez des coûts directs liés à la consommation ou la production, le compte de solde est un compte de bilan. Le type de l'écriture article et de l'écriture valeur détermine sur quel compte du grand livre reporter.  

Le type d'écriture indique le compte du grand livre sur lequel reporter. Ceci est déterminé par le signe de la quantité de l'écriture du grand livre d'articles ou la quantité évaluée de l'écriture valeur, étant donné que les quantités ont toujours le même signe. Par exemple, une écriture vente avec une quantité positive décrit une diminution d'inventaire due à une vente, et une écriture vente avec une quantité négative décrit une augmentation d'inventaire due à un retour vente.  

### <a name="example"></a>Exemple :  
L'exemple suivant présente une chaîne de vélo qui est fabriquée à partir des liens achetés. Cet exemple montre la manière dont les différents types de compte du grand livre sont utilisés dans un scénario courant.  

La case à cocher **Report coût prévu au GL** de la page **Configuration inventaire** est activée et la configuration suivante est définie.  

Le tableau suivant montre la manière dont le lien est paramétré sur la fiche article.  

|Champ de configuration|Valeur|  
|-----------------|-----------|  
|**Mode évaluation stock**|Standard|  
|**Coût standard**|1,00 $|  
|**Coefficient des frais gén.**|0,02 $|  

Le tableau suivant montre la manière dont la chaîne est paramétrée sur la fiche article.  

|Champ de configuration|Valeur|  
|-----------------|-----------|  
|**Mode évaluation stock**|Standard|  
|**Coût standard**|150,00 $|  
|**Frais généraux**|25,00 $|  

Le tableau suivant montre la manière dont l'atelier est paramétré sur la fiche atelier.  

|Champ de configuration|Valeur|  
|-----------------|-----------|  
|**Coût unitaire direct**|2,00 $|  
|**Pourcentage coût indirect**|10|  

##### <a name="scenario"></a>Scénario  
1. L'utilisateur achète 150 liens et reporte le bon de commande comme reçu. (Achat)  
2. L'utilisateur reporte le bon de commande comme facturé. Cela crée une quantité supplémentaire de 3,00 $ à affecter à une quantité de tolérance de 18,00 $. (Achat)  

    1. Les comptes d'attente sont supprimés. (Achat)  
    2. Le coût direct est reporté. (Achat)  
    3. Le coût indirect est calculé et reporté. (Achat)  
    4. L'écart achat est calculé et reporté (uniquement pour les articles de coût standard). (Achat)  
3. L'utilisateur vend une chaîne et reporte le document de vente comme livré. (Vente)  
4. L'utilisateur reporte le document de vente comme facturé. (Vente)  

    1. Les comptes d'attente sont supprimés. (Vente)  
    2. Le coût des marchandises vendues est reporté. (Vente)  

        ![Résultats du report des ventes sur les comptes généraux](media/design_details_inventory_costing_3_gl_posting_sales.png "Résultats du report des ventes sur les comptes généraux")  
5. L'utilisateur reporte la consommation de 150 liens, qui est le nombre de liens utilisés pour produire une chaîne. (Consommation, Matière)  

    ![Résultats du report des matières sur les comptes généraux](media/design_details_inventory_costing_3_gl_posting_material.png "Résultats du report des matières sur les comptes généraux")  
6. L'atelier a pris 60 minutes pour produire la chaîne. L'utilisateur reporte le coût de conversion. (Consommation, Capacité)  

    1. Les coûts directs sont reportés. (Consommation, Capacité)  
    2. Les coûts indirects sont calculés et reportés. (Consommation, Capacité)  

        ![Résultats du report de la capacité sur les comptes généraux](media/design_details_inventory_costing_3_gl_posting_capacity.png "Résultats du report de la capacité sur les comptes généraux")  
7. L'utilisateur reporte le coût prévu d'une chaîne. (Production)  
8. L'utilisateur termine le bon de production et exécute le traitement en lot **Ajuster coûts - Écr. article**. (Production)  

    1. Les comptes d'attente sont supprimés. (Production)  
    2. Le coût direct est transféré du compte TEC vers le compte inventaire. (Production)  
    3. Le coût indirect (frais généraux) est transféré du compte des coûts indirects vers le compte inventaire. (Production)  
    4. Cela a pour résultat une quantité de tolérance de 157,00 $. Les écarts sont uniquement calculés pour les articles de coût standard. (Production)  

        ![Résultats du report de la production sur les comptes généraux](media/design_details_inventory_costing_3_gl_posting_output.png "Résultats du report de la production sur les comptes généraux")  

        > [!NOTE]  
        >  Pour des raisons de simplicité, un seul compte écart est affiché. En réalité, cinq comptes différents existent :  
        >   
        >  * Écart sur matières  
        >  * Écart sur capacité  
        >  * Capacité - Écart frais génér.  
        >  * Écart sous-traitance  
        >  * Écart frais généraux production  

9. L'utilisateur réévalue la chaîne de 150,00 $ à 140,00 $. (Ajustement/Réévaluation/Arrondissement/Transfert)  

    ![Résultats du report de l'ajustement sur les comptes généraux](media/design_details_inventory_costing_3_gl_posting_adjustment.png "Résultats du report de l'ajustement sur les comptes généraux")  

Pour plus d'informations sur les relations entre les types de compte et les différents types d'écritures valeur, voir [Détails de conception : comptes de la comptabilité](design-details-accounts-in-the-general-ledger.md).  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
[Détails de conception : report du coût prévu](design-details-expected-cost-posting.md)   
[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]