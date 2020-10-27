---
title: Procédure de sous-traitance de la production | Microsoft Docs
description: Une fois que le bon de commande a été créée à partir de la feuille sous-traitant, il peut être reporté.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 0b8c0acb51467d8320a6ebe91ee6dbf6827f8e85
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3915395"
---
# <a name="subcontract-manufacturing"></a>Sous-traiter la production
La sous-traitance des opérations sélectionnées au fournisseur est courante dans de nombreuses compagnies manufacturières. La sous-traitance peut être occasionnelle ou faire partie intégrante des processus de production.

[!INCLUDE[d365fin](includes/d365fin_md.md)] fournit plusieurs outils pour gérer le travail de sous-traitance :  

- Ateliers avec fournisseur affecté : cette fonctionnalité permet de configurer un atelier associé à un fournisseur (sous-traitant). Il s'agit d'un atelier sous-traitant. Vous pouvez spécifier un atelier sous-traitant sur une opération d'itinéraire, ce qui permet de traiter aisément l'activité sous-traitée. En outre, le coût de l'opération peut être indiqué au niveau de l'itinéraire ou de l'atelier.  
- Coût de l'atelier basé sur des unités de temps : cette fonctionnalité permet de spécifier si les coûts associés à l'atelier sont basés sur le temps de fabrication ou un coût unitaire. Bien que les sous-traitants utilisent généralement un coût unitaire pour facturer leurs services, l'application peut gérer les deux options (temps de fabrication et coût unitaire).  
- Feuille de sous-traitance : cette fonctionnalité vous permet de rechercher les bons de production dont les matériaux sont prêts pour envoi à un sous-traitant et de créer automatiquement des bons de commande pour sous-traiter des opérations à partir d'itinéraires de bon de production. L'application reporte automatiquement les frais de bon de commande dans le bon de production durant le report du bon de commande. Seuls les bons de production dont l'état est libéré sont accessibles et utilisables à partir d'une feuille de sous-traitance.  

## <a name="subcontract-work-centers"></a>Centres de charge sous-traitants  
Les centres de charge sous-traitants sont configurés de la même manière que les centres de charge ordinaires avec des informations supplémentaires. Ils sont affectés à des gammes de la même manière que d'autres centres de charge.  

### <a name="subcontract-work-center-fields"></a>Champs Atelier sous-traitant  
Le champ **N° sous-traitant** désigne l'atelier comme atelier sous-traitant. Vous pouvez entrer le numéro d'un sous-traitant qui fournit l'atelier. Ce champ permet d'administrer des ateliers qui ne sont pas internes mais effectuent un traitement sous contrat.  

Si vous sous-traitez avec le fournisseur à un taux différent pour chaque traitement, sélectionnez le champ **Coût unitaire spécifique** . Cela vous permet de configurer un coût sur chaque ligne itinéraire et vous évite de devoir entrer à nouveau chaque bon de commande. Le coût d'une ligne itinéraire est utilisé dans le cadre du traitement au lieu du coût des champs de coût de l'atelier. La sélection du champ **Coût unitaire spécifique** permet de calculer des coûts pour le fournisseur par opération de gamme.  

Si vous sous-traitez à un coût unique par fournisseur, laissez le champ **Coût unitaire spécifique** vide. Configurez les coûts en renseignant les champs **Coût unitaire direct** , **% coût indirect** et **Frais généraux** .  

### <a name="routings-that-use-subcontract-work-centers"></a>Gammes qui utilisent des centres de charge sous-traitants  
Vous pouvez utiliser des centres de charge sous-traitants pour des opérations de gamme de la même manière que des centres de charge ordinaires.  

Vous pouvez configurer un itinéraire utilisant un atelier externe comme étape opérationnelle standard. Vous pouvez également modifier l'itinéraire pour un bon de production particulier afin d'inclure une opération externe. Cela peut être nécessaire en cas d'urgence, par exemple pour un serveur défaillant, ou durant une période temporaire de demande accrue, où le travail généralement traité en interne doit être délégué à un sous-traitant.  

Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).  

## <a name="calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders"></a>Calculer des feuilles de sous-traitance et créer des bons de commande de sous-traitance  
Après le calcul des feuilles de sous-traitance, le document approprié, en l'occurrence un bon de commande, est créé.  

La page **Feuille sous-traitance** fonctionne comme la **Feuille planification** en calculant les approvisionnements nécessaires (dans ce cas, les bons de commande) que vous vérifiez dans la feuille puis créez à l'aide de la fonction **Traiter message d'action** .  

> [!NOTE]  
>  Seuls les ordres de fabrication dont l'état est **Lancé** sont accessibles et utilisables à partir d'une proposition sous-traitance.  

### <a name="to-calculate-the-subcontracting-worksheet"></a>Pour calculer des propositions sous-traitance  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Propositions sous-traitance** , puis sélectionnez le lien associé.  
2.  Pour calculer la feuille, choisissez l'action **Générer sous-traitances** .  
3.  Sur la page **Générer sous-traitances** , définissez des filtres pour les opérations de sous-traitance, ou les ateliers où celles-ci sont effectuées, pour ne calculer que les bons de production appropriés.  
4.  Cliquez sur le bouton **OK** .  

    Examinez les lignes de la page **Propositions sous-traitance** . Les informations de cette feuille proviennent des lignes du bon de production et de l'itinéraire du bon de production et sont insérées dans le bon de commande lors de la création de ce document. Vous pouvez supprimer une ligne de la feuille sans toucher aux informations d'origine, tout comme vous pouvez le faire avec les autres feuilles. Les informations réapparaissent à la prochaine exécution de la fonction **Générer sous-traitances** .  

### <a name="to-create-the-subcontract-purchase-order"></a>Pour créer le bon de commande de sous-traitance  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Propositions sous-traitance** , puis sélectionnez le lien associé.  
2.  Choisissez l'action **Traiter message d'action** .  
3.  Sélectionnez le champ **Imprimer commandes** pour imprimer la commande achat lors de sa création.  
4.  Cliquez sur le bouton **OK** .  

Si toutes les opérations de sous-traitance sont envoyées au même emplacement fournisseur, un seul bon de commande est créé.  

La ligne feuille transformée en bon de commande est supprimée de la feuille. Une fois qu'un bon de commande est créé, il n'apparaît plus dans la feuille.  

## <a name="posting-subcontract-purchase-orders"></a>Report de bons de commande de sous-traitance  
Une fois les commandes achat de sous-traitant créées, il est possible de les valider. La réception de la commande reporte une écriture du grand livre de capacité dans le bon de production et la facturation de ce dernier reporte le coût direct du bon de commande dans le bon de production.  

## <a name="to-post-a-subcontract-purchase-order"></a>Pour reporter un bon de commande de sous-traitance  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Bons de commande** , puis sélectionnez le lien associé.  
2.  Ouvrez un bon de commande créé à partir de la feuille de sous-traitance.  

    Sur les lignes du bon de commande, vous pouvez visualiser les mêmes informations que celles figurant sur la feuille. Les champs **N° ordre de fabrication** , **N° ligne O.F.** , **N° opération** et **N° centre de charge** sont renseignés avec les informations du bon de production source.  

3.  Sélectionnez l'action **Valider** .  

Lorsque l'achat est reporté comme reçu, une écriture journal de sortie est automatiquement reportée pour le bon de production. Ceci est valable uniquement si l'opération de sous-traitance est la dernière opération sur l'itinéraire du bon de production.  

> [!CAUTION]  
>  Le report automatique de la production pour un bon de production en cours lorsque des articles sous-traités reçus ne sont peut-être pas souhaités. Les raisons à cela peuvent être une différence entre la quantité produite prévue reportée et la quantité réelle, et l'inexactitude de la date de report de la production automatique.  
>   
>  Pour éviter que la production prévue d'un bon de production ne soit reportée lorsque les achats de sous-traitance sont réceptionnés, veillez à ce que l'opération sous-traitée ne soit pas la dernière. Sinon, insérez une dernière opération pour la quantité produite finale.  

Lorsque le bon de commande est reporté comme facturé, son coût direct est reporté dans le bon de production.  

## <a name="see-also"></a>Voir aussi  
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
