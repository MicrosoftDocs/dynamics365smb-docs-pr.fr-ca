---
title: 'Procédure : reporter des capacités | Microsoft Docs'
description: Le journal capacité vous permet de reporter les capacités consommées qui ne sont pas affectées au bon de production. Par exemple, les travaux d'entretien doivent être affectés à une capacité, mais non à un bon de production.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: d580fe2513e245b7105342c3d795ae122c151317
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2313286"
---
# <a name="post-capacities"></a>Reporter des capacités
Le journal capacité vous permet de reporter les capacités consommées qui ne sont pas affectées au bon de production. Par exemple, les travaux d'entretien doivent être affectés à une capacité, mais non à un bon de production.  

## <a name="to-post-capacities"></a>Pour reporter les capacités  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux capacité**, puis sélectionnez le lien associé.  
2.  Renseignez les champs **Date de report** et **N° document**.  
3.  Dans le champ **Type**, entrez le type de capacité, **Poste de charge** ou **Centre de charge**, que vous validez.  
4.  Dans le champ **N°**, saisissez le numéro de l'unité de production ou de l'atelier.  
5.  Entrez les données nécessaires dans les autres champs, tels que **Heure début**, **Heure fin**, **Quantité**, et **Rebut**.  
6.  Choisissez l'action **Reporter** pour reporter les capacités.  

## <a name="to-view-work-center-ledger-entries"></a>Pour afficher les écritures de l'atelier  
Sur les pages **Fiche atelier** et **Fiche unité de production**, vous pouvez afficher les capacités reportées en tant que résultat des bons de production terminés.    
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Ateliers**, puis sélectionnez le lien associé.  
2.  Ouvrez la fiche **Atelier** appropriée dans la liste, puis choisissez l'action **Écritures du grand livre de capacité**.  

La page **Écritures capacité** affiche les écritures reportées relatives à l'atelier dans l'ordre de leur report.   

## <a name="see-also"></a>Voir aussi  
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
