---
title: "Détails de conception - Création de traçabilité | Microsoft Docs"
description: "Cette rubrique décrit la conception associée à la traçabilité dans [!INCLUDE[d365fin](includes/d365fin_md.md)]."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, item, tracking, tracing
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 1d47b646b1908987648ebe13f53693f6782f6cdf
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-item-tracking-design"></a>Détails de conception : création de traçabilité
Dans la première version de Traçabilité de [!INCLUDE[d365fin](includes/d365fin_md.md)] 2.60, les numéros de série ou les numéros de lot étaient enregistrés directement sur les écritures article. Ce design a fourni des informations de disponibilité complète et un suivi unique des écritures historiques, mais il a manqué de flexibilité et de fonctionnalité.  

Depuis [!INCLUDE[d365fin](includes/d365fin_md.md)] 3.00, la fonctionnalité de traçabilité se trouve dans une structure d'objet distincte avec des liens complexes à des documents et des écritures article reportés. Ce design était flexible et riche en fonctionnalités, mais les écritures de suivi d'article n'étaient pas entièrement impliquées dans les calculs de disponibilité.  

Depuis [!INCLUDE[d365fin](includes/d365fin_md.md)] 3.60, la fonctionnalité de traçabilité est intégrée au système de réservation, qui traite la réservation, le chaînage et les messages d'action. Pour plus d'informations, voir « Détails de conception : réservations, chaînage et messages d'action » dans « Détails de conception : planification des approvisionnements ».  

Ce dernier design incorpore les écritures de suivi d'article dans les calculs de disponibilité totaux dans tout le système, y compris la planification, la fabrication, et l'entreposage. L'ancien concept consistant à indiquer les numéros de série et de lot des écritures article est réintroduit pour assurer un accès simple aux données historiques pour la traçabilité. En relation avec les améliorations de traçabilité dans [!INCLUDE[d365fin](includes/d365fin_md.md)] 3.60, le système de réservation a été étendu aux entités réseau sans rapport avec les commandes, telles que les journaux, les factures et les notes de crédit.  

Avec l'ajout de numéros de série ou de lot, le système de réservation gère les attributs d'article permanents tout en gérant également les liens intermittents entre l'approvisionnement et la demande sous la forme d'écritures de suivi de commande et d'écritures de réservation. Il existe une autre caractéristique qui différencie les numéros de série ou de lot des données de réservation conventionnelles : leur report peut être effectué partiellement ou en totalité. Par conséquent, la table **Écriture de réservation** (T337) s'exécute à présent avec une table associée, la table **Spécification traçabilité** (T336), qui gère et affiche l'ajout à travers les quantités de suivi article actives et reportées. Pour plus d'informations, voir [Détails de conception : comparaison entre écritures traçabilité actives et historiques](design-details-active-versus-historic-item-tracking-entries.md).  

Le schéma suivant explique la conception de la fonctionnalité de traçabilité dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

![Conception de la traçabilité](media/design_details_item_tracking_design.png "design_details_item_tracking_design")  

L'objet de report principal est remodelé pour gérer la sous-classification unique d'une ligne document sous forme de numéros de série ou de lot, et des tables de lien spéciales sont ajoutées pour créer une relation un à plusieurs entre les documents reportés et leurs écritures article et valeur scindées.  

Codeunit 22, **Journal article – Ligne report**, fractionne alors le report en fonction des numéros traçabilité qui sont indiqués sur la ligne document. Chaque numéro traçabilité unique sur la ligne crée sa propre écriture article pour l'article. Cela signifie que le lien de la ligne document reportée vers les écritures article associées est à présent une relation un à plusieurs. Cette relation est traitée par les tableaux de relation de suivi d'article suivants.  

|Champ|Description|  
|---------------|---------------------------------------|  
|**Lien écriture article** (T6507)|Relie les lignes livrées ou reçues aux écritures article|  
|**Lien écriture valeur** (T6508)|Relie les lignes facturées aux écritures valeur|  

Pour plus d'informations, reportez-vous à [Détails de conception : structure de report de traçabilité](design-details-item-tracking-posting-structure.md).  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : traçabilité](design-details-item-tracking.md)

