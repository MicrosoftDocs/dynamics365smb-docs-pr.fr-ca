---
title: Planification avec/sans emplacement | Microsoft Docs
description: Il est important de comprendre le fonctionnement de la planification avec/sans codes d'emplacement sur les lignes demande.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: dd86568c87a9cbb66214ae88b75fcdae8e85b59d
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5383185"
---
# <a name="planning-with-or-without-locations"></a>Planification avec/sans emplacement
En ce qui concerne la planification avec ou sans code magasin sur les lignes demande, le système opère directement lorsque :  

-   Les lignes demande indiquent systématiquement le code d'emplacement et le système exploite intégralement les unités de stock, y compris la configuration d'emplacement pertinente.  
-   Les lignes demande n'indiquent jamais le code d'emplacement et le système n'utilise ni les unités de stock ni la configuration d'emplacement (reportez-vous au dernier scénario ci-dessous).  

Toutefois, si les lignes demande indiquent parfois le code magasin, mais pas de manière systématique, le système de planification suit certaines règles en fonction de la configuration.  

## <a name="demand-at-location"></a>Demande à l'emplacement  
Lorsque le système de planification détecte une demande dans un emplacement (identifiée par une ligne avec code d'emplacement), il peut procéder de plusieurs manières en fonction de 3 valeurs de configuration critiques.  

Lors de l'exécution de la planification, le système recherche ces 3 valeurs de configuration l'une après l'autre et effectue la planification en conséquence :  

1.  Le champ **Magasin obligatoire** est-il activé ?  

    Si oui :  

2.  Existe-t-il une unité de stock pour l'article ?  

    Si oui :  

    L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.  

    Si non :  

3.  Le champ **Mag. composant par déf** contient-il le code magasin demandé ?  

    Si oui :  

    L'article est planifié en fonction des paramètres de planification de la fiche article.  

    Si non :  

    L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot*, Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide. (Les articles qui suivent l’*ordre* de la méthode réapprovisionnement continuent à  *le* suivre, tout comme les autres paramètres.)  

> [!NOTE]  
>  Cette solution minimale couvre strictement la demande. Tout paramètre de planification défini est ignoré.  

Consultez les variantes des cas de figure ci-dessous.  

## <a name="demand-at-blank-location"></a>Demande à un emplacement vide  
Même si la case **Emplacement obligatoire** est cochée, le système autorise la création de lignes demande sans code d'emplacement, ce que l'on appelle également « emplacement *VIDE* ». Il s'agit d'un écart pour le système, car il a plusieurs valeurs de configuration accordées pour gérer les emplacements (voir ci-dessus) et, par conséquent, le moteur de planification ne crée pas de ligne planification pour une telle ligne demande. Si le champ **Emplacement obligatoire** n'est pas sélectionné alors qu'une des valeurs de configuration d'emplacement existe, c'est également considéré comme un écart et le système de planification réagira en proposant la « solution minimale » :   
L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour lot* (l' *ordre* conserve la valeur *Ordre)*, Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

Consultez les variantes des scénarios de configuration ci-dessous.  

### <a name="setup-1"></a>Configuration 1 :  

-   Emplacement obligatoire = *Oui*  
-   Le point de stock a pour valeur *ROUGE*  
-   Composante à l'emplacement =  *BLEU*  

#### <a name="case-11-demand-is-at--red-location"></a>Situation 1.1 : la demande concerne un magasin *ROUGE*  

L'article est planifié en fonction des paramètres de planification de la fiche unité de stock (y compris, un éventuel transfert).  

#### <a name="case-12-demand-is-at--blue-location"></a>Situation 1.2 : la demande concerne un magasin *BLEU*  

L'article est planifié en fonction des paramètres de planification de la fiche article.  

#### <a name="case-13-demand-is-at--green-location"></a>Situation 1.3 : la demande concerne un magasin *VERT*  

L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour Lot* (l' *ordre* conserve la valeur  *Ordre*), Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

#### <a name="case-14-demand-is-at--blank-location"></a>Situation 1.4 : la demande concerne un magasin *BLANC*  

L'article n'est pas planifié, car aucun emplacement n'est défini sur la ligne de réquisition.  

### <a name="setup-2"></a>Configuration 2 :  

-   Emplacement obligatoire = *Oui*  
-   Il n'existe pas d'unité de stock  
-   Composante à l'emplacement =  *BLEU*  

#### <a name="case-21-demand-is-at--red-location"></a>Situation 2.1 : la demande concerne un magasin *ROUGE*  

L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour Lot* (l' *ordre* conserve la valeur  *Ordre*), Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

#### <a name="case-22-demand-is-at--blue-location"></a>Situation 2.2 : la demande concerne un magasin *BLEU*  

L'article est planifié en fonction des paramètres de planification de la fiche article.  

### <a name="setup-3"></a>Configuration 3 :  

-   Emplacement obligatoire = *Non*  
-   Il n'existe pas d'unité de stock  
-   Composante à l'emplacement =  *BLEU*  

#### <a name="case-31-demand-is-at--red-location"></a>Situation 3.1 : la demande concerne un magasin *ROUGE*  

L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour Lot* (l' *ordre* conserve la valeur  *Ordre*), Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

#### <a name="case-32-demand-is-at--blue-location"></a>Situation 3.2 : la demande concerne un magasin *BLUE*  

L'article est planifié en fonction des paramètres de planification de la fiche article.  

#### <a name="case-33-demand-is-at--blank-location"></a>Situation 3.3 : la demande concerne un magasin *BLANC*  

L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour Lot* (l' *ordre* conserve la valeur  *Ordre*), Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

### <a name="setup-4"></a>Configuration 4 :  

-   Emplacement obligatoire = *Non*  
-   Il n'existe pas d'unité de stock  
-   Composante à l'emplacement =  *VIDE*  

#### <a name="case-41-demand-is-at--blue-location"></a>Situation 4.1 : la demande concerne un magasin *BLEU*  

L'article est planifié comme suit : Stratégie réapprovisionnement =  *Lot pour Lot* (l' *ordre* conserve la valeur  *Ordre*), Inclure inventaire =  *Oui*. Tous les autres paramètres de planification ont la valeur Vide.  

#### <a name="case-42-demand-is-at--blank-location"></a>Situation 4.2 : la demande concerne un magasin *BLANC*  

L'article est planifié en fonction des paramètres de planification de la fiche article.  

Comme vous pouvez le voir au dernier cas de figure, le seul moyen d'obtenir des résultats corrects pour une ligne de demande sans code d'emplacement consiste à désactiver toutes les valeurs de configuration relatives aux emplacements. De la même manière, le seul moyen d'obtenir des résultats de planification stables pour les demandes dans des magasins consiste à utiliser des points de stock.  

Par conséquent, si vous planifiez souvent des demandes dans des magasins, il est fortement recommandé d'utiliser la fonctionnalité des points de stock.  

## <a name="see-also"></a>Voir aussi
[Planification](production-planning.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]