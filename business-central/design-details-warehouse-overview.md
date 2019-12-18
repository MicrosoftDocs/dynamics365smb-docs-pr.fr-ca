---
title: Détails de conception - Vue d'ensemble d'entrepôt | Microsoft Docs
description: Pour prendre en charge la manipulation physique des articles au niveau des zones, toutes les informations doivent être suivies pour chaque transaction ou mouvement dans l'entrepôt. Ceci est géré dans la table **Écriture entrepôt**. Chaque transaction est enregistrée dans un registre entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 20e2d2529ab84184bb55366434b41126703c5107
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2879954"
---
# <a name="design-details-warehouse-overview"></a>Détails de conception : vue d'ensemble d'entrepôt
Pour prendre en charge la manipulation physique des articles au niveau des zones, toutes les informations doivent être suivies pour chaque transaction ou mouvement dans l'entrepôt. Ceci est géré dans la table **Écriture entrepôt**. Chaque transaction est enregistrée dans un registre entrepôt.  

Les documents entrepôt et un journal entrepôt sont utilisés pour enregistrer des mouvements article dans l'entrepôt. Chaque fois qu'un article dans l'entrepôt est déplacé, reçu, rangé, prélevé, livré ou ajusté, les écritures entrepôt sont enregistrées pour stocker les informations physiques sur les zones et la quantité.

La table **Contenu de la zone** est utilisée pour gérer l'ensemble des dimensions du contenu d'un d'une zone par article, par exemple, l'unité de mesure, la quantité maximum et la quantité minimum. La table **Contenu de la zone** affiche également des champs de flux vers les écritures entrepôt, des instructions entrepôt et des lignes journal entrepôt, ce qui garantit que la disponibilité d'un article par zone et d'une zone pour un article peut être calculée rapidement. Pour plus d'informations, voir [Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md).  

Lorsque les reports article se produisent en dehors du module d'entrepôt, une zone d'ajustement par défaut par emplacement est utilisée pour synchroniser des écritures d'entrepôt avec les écritures d'inventaire. Au cours de l'inventaire physique de l'entrepôt, toutes les différences entre les quantités calculées et comptées sont enregistrées dans la zone d'ajustement, puis reportées comme correction des écritures articles. Pour plus d'informations, voir [Détails de conception : intégration avec l'inventaire](design-details-integration-with-inventory.md).  

La figure suivante présente les flux d'entrepôt courants.  

![Vue d'ensemble des processus entrepôt](media/design_details_warehouse_management_overview.png "Vue d'ensemble des processus entrepôt")  

## <a name="basic-or-advanced-warehousing"></a>Entreposage de base ou avancé  
La fonctionnalité d'entrepôt dans [!INCLUDE[d365fin](includes/d365fin_md.md)] peut être implémentée à différents niveaux de complexité, selon les processus d'une compagnie et le volume de commande. La principale différence est que les activités sont effectuées par commande dans l'entreposage de base, alors qu'elles sont regroupées pour plusieurs commandes dans l'entreposage avancé.  

 Pour différencier les différents niveaux de complexité, ces documents font référence à deux dénominations générales de base, Basic et Advanced Warehousing. Cette différenciation simple couvre plusieurs niveaux de complexité différents tels que définis par les granules produit et la configuration de l'emplacement, chacun étant pris en charge par différents documents d'interface utilisateur. Pour plus d'informations, reportez\-vous à [Détails de conception : Paramètres entrepôt](design-details-warehouse-setup.md).  

> [!NOTE]  
>  Le niveau le plus avancé de l'entreposage est appelé « Installations WMS » dans cette documentation, étant donné que ce niveau requiert le granule le plus avancé, Warehouse Management Systems (systèmes de gestion d'entrepôt).  

 Les différents documents de l'interface utilisateur suivants sont utilisés dans l'entreposage de base et avancé.  

## <a name="basic-ui-documents"></a>Documents de base de l'interface utilisateur  

-   **Article dans l'inventaire à classer**  
-   **Article en inventaire à prélever**  
-   **Mouvement d'inventaire**  
-   **Journal article**  
-   **Journal de reclassements d'articles**  
-   (Divers rapports)  

## <a name="advanced-ui-documents"></a>Documents d'interface utilisateur avancés  

-   **Réception de l'entrepôt**  
-   **Feuille rangement**  
-   **Rangement magasin**  
-   **Feuille prélèvement**  
-   **Prélèvement magasin**  
-   **Feuille mouvement**  
-   **Mouvement d'entrepôt**  
-   **Prélèvement interne entrepôt**  
-   **Rangement interne entrepôt**  
-   **Feuille de création de zone**  
-   **Feuille de création du contenu de la zone**  
-   **Journal article entrepôt**  
-   **Journal reclassement article entrepôt**  
-   (Divers rapports)  

Pour plus d'informations sur chaque document, reportez-vous aux rubriques correspondantes de la page.  

### <a name="terminology"></a>Terminologie  
Pour s'aligner avec les concepts financiers d'achats et de ventes, la documentation d'entrepôt [!INCLUDE[d365fin](includes/d365fin_md.md)] fait référence aux termes suivants pour la circulation des articles dans l'entrepôt.  

|Terme|Description|  
|----------|---------------------------------------|  
|Flux entrant|Articles qui se déplacent dans l'emplacement entrepôt, par exemple les achats et les transferts entrants.|  
|Flux interne|Articles qui se déplacent au sein de l'emplacement entrepôt, par exemple les composantes de production et leur résultat.|  
|Flux sortant|Articles qui se déplacent hors de l'emplacement entrepôt, par exemple les ventes et les transferts sortants.|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)
