---
title: Exécuter en lot la sortie de production et les temps d'exécution
description: La quantité de sortie représente l'avancement du travail sous la forme de la quantité finie et de la capacité utilisée de l'atelier ou de l'unité de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 923f68b13619013dd54062438c66192a682868bc
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5787887"
---
# <a name="batch-post-output-and-run-times"></a>Exécuter en lot la production et les temps d'exécution
La quantité de sortie représente l'avancement du travail sous la forme de la quantité finie et de la capacité utilisée de l'atelier ou de l'unité de production.

Vous pouvez utiliser le journal de sortie pour :
*  Ajustez l'inventaire en fonction de la production des articles finis émanant de la production.
*  Enregistrez les quantités et les rebuts pour chaque opération dans l'itinéraire de production.
*  Enregistrez la configuration et le temps d'exécution pour les ateliers et les unités de production.

> [!NOTE]
> Si l'itinéraire de production est utilisé, l'inventaire est mis à jour uniquement lorsque vous reportez la quantité produite durant la dernière opération.

La fenêtre **Journal production** vous permet d’exécuter les mêmes tâches que celles de la fenêtre **Journal de sortie** et d'exécuter en même temps les tâches connexes de report de la consommation. Pour plus d'informations, voir [Enregistrer la consommation et la production pour une ligne bon de production libéré](production-how-to-register-consumption-and-output.md).

## <a name="to-post-output-quantities-andor-register-run-times-for-one-or-more-production-order-lines"></a>Pour reporter les quantités produites et/ou enregistrer le temps d’exécution pour une ou plusieurs lignes bon de production
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.  
2. Renseignez les champs en indiquant les données relatives au bon de production et/ou le temps d’exécution. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
  
    Vous pouvez utiliser la fonction **Éclater itinéraire** pour générer des lignes journal à partir des bons de production.
  
4. Si l'opération est achevée, sélectionnez le champ **Terminé**.  
5. Choisissez l’action **Reporter** pour reporter les opérations. 
 
Les écritures capacité sont mises à jour pour les unités de production ou les ateliers utilisés avec des informations sur le temps et la quantité de production et de rebut. Si vous avez reporté la dernière opération, l'article sera ajouté à l'inventaire. 

## <a name="see-also"></a>Voir aussi  
[Reporter la mise au rebut manuellement](production-how-to-post-scrap.md)
[Report de sortie inversée](production-how-to-reverse-output-posting.md)
[Fabrication](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Inventaire](inventory-manage-inventory.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
