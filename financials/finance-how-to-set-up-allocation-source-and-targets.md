---
title: "Procédure : configurer la source d'affectation et ses cibles | Microsoft Docs"
description: "Chaque affectation comporte une source et au moins une cible. La source d'affectation définit les coûts à affecter. Les cibles d'affectation déterminent où affecter ces coûts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: d4dcf5f95d5fc44d4b8fb72b55d905c876989a56
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="set-up-allocation-source-and-targets"></a>Configurer la source d'affectation et ses cibles
Chaque affectation comporte une source et au moins une cible. La source d'affectation définit les coûts à affecter. Les cibles d'affectation déterminent où affecter ces coûts.  

## <a name="to-set-up-cost-allocations"></a>Pour configurer les affectations de coûts  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Affectation des coûts**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Affectation des coûts**, sélectionnez l'action **Modifier**.  
3.  Dans le champ **ID**, entrez un ID pour la source d’affectation.  
4.  Définissez un niveau compris entre les chiffres 1 et 99 dans le champ **Niveau**. Le report de l’affectation suit l’ordre des niveaux.  
5.  Entrez un type de coût pour définir les types de coût à affecter dans le champ **Plage type de coûts**. Si tous les coûts pour un type donné sont affectés, aucune plage n'est définie.  
6.  Entrez un centre de coûts avec des coûts à affecter dans le champ **Code centre de coûts**.  
7.  Entrez un coût associé avec des coûts à affecter dans le champ **Code coûts associés**. Ce champ reste vide la plupart du temps car les coûts associés sont rarement affectés à d'autres coûts associés.  
8.  Entrez un type de coût dans le champ **Type de crédit\\\/coût**. Les coûts affectés sont crédités dans le type de coût d’origine. Le report des crédits est reporté sur le type de coût spécifié ici.  
9. Sur le raccourci **Lignes**, définissez les cibles d’affectation. Sur la première ligne, entrez un type de coût dans le champ **Type coût cible**. Il définit le type de coût à partir duquel l'affectation est débitée.  
10. Sur la première ligne, saisissez la première cible d'affectation dans le champ **Centre de coûts cible** ou **Objet de coûts cible**. Ces deux champs définissent le centre de coûts ou l'objet de coûts à partir desquels l'affectation est débitée. Vous pouvez renseigner uniquement l'un de ces champs, mais pas les deux.  
11. Répétez les mêmes étapes sur la deuxième ligne pour configurer les cibles d'affectation supplémentaires.  
12. Après avoir paramétré la cible et les sources d’affectation, sélectionnez **Calculer la clé d'affectation** pour calculer le total des valeurs d'action.  

> [!NOTE]  
>  Cochez la case **Bloqué** pour désactiver la configuration de l'affectation.  

## <a name="see-also"></a>Voir aussi  
[Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
 [Définition de filtres pour les bases d'affectation dynamique](finance-setting-filters-for-dynamic-allocation-bases.md)   
 [Exemple de scénario : Définition des affectations statiques en fonction du ratio d'affectation](finance-scenario-example-defining-static-allocations-based-on-allocation-ratio.md)   
 [Exemple de scénario : Définition des ventilations dynamique sur la base des articles vendus](finance-scenario-example-defining-dynamic-allocations-based-on-items-sold.md)   
 [Définition et répartition des coûts](finance-define-and-allocate-costs.md)   
 [Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

