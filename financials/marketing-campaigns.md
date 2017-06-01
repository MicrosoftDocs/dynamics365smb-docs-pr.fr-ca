---
title: Configuration des campagnes marketing dans Financials | Microsoft Docs
description: "Décrit la manière dont vous pouvez configurer et mener des campagnes marketing dans Dynamics 365 for Financials"
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: marketing, campaign, promo, prospect
ms.date: 03/08/2017
ms.author: edupont
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 8f616382e28e29aab1ce7d9b45b8efb4ad374b96
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="managing-marketing-campaigns"></a>Gestion de campagnes marketing
Disposer d'une solide stratégie marketing permet d'identifier, d'attirer et de fidéliser les clients. Une stratégie marketing est composée de diverses campagnes ainsi que d'interactions en relation avec vos activités de vente et de marketing. Lors de la planification d'une promotion, vous devez choisir les contacts à cibler, le type de promotion (salon, courriel direct) et le représentant chargé de chaque tâche.

<!-- Each campaign consists of various activities or to-dos. Activities are large tasks that can be broken down into several smaller tasks or to-dos. To-dos are individual or team tasks that can be created within activities or individually and then be assigned to individual salespeople or groups of salespeople.-->

## <a name="defining-individual-campaigns"></a>Définition de campagnes individuelles
Pour pouvoir créer une campagne, vous devez configurer des *codes statut campagne*. Ceux-ci permettent de gérer vos promotions en affectant un état à la promotion. Lorsque vous travaillez sur les phases d'une promotion, vous pouvez voir où en est la promotion et visualiser l'étape suivante. Vous devez configurer des codes statut campagne dans la fenêtre **Statut campagne**.

Vous pouvez créer une *fiche campagne* pour toutes les campagnes que vous voulez suivre. Vous pouvez également afficher ces fiches promotion pour visualiser des informations générales sur vos promotions.
Vous pouvez supprimer des écritures promotion, par exemple si elles enregistrent une action qui a été annulée. Vous ne pouvez supprimer que les écritures promotion annulées.

### <a name="selecting-the-target-audience"></a>Sélection du public cible
Après avoir créé une promotion, vous pouvez commencer à créer les segments qui spécifient le public cible de la promotion. Pour plus d'informations, voir [Gestion des segments](marketing-segments.md).

### <a name="registering-discount-percentages"></a>Enregistrement des pourcentages escompte
Lorsque vous avez défini votre campagne, que vous avez déterminé les segments que la campagne doit couvrir et défini les dates début et dates de fin, vous enregistrez le pourcentage de la remise auquel le client a droit pour chaque article dans les lignes de la fenêtre **Remises ligne vente**. Vous pouvez également enregistrer les prix de vente pour des articles individuels sur les lignes de la fenêtre **Prix vente**. Vous pouvez accéder aux deux fenêtres à partir de la fiche promotion.

 Lorsque vous avez configuré les prix vente/escomptes ligne et les segments dans la fiche promotion, vous devez les activer afin que les lignes reflètent les prix/escomptes de la promotion.

> [!NOTE]  
>  Afin que vous puissiez activer les prix vente/escomptes ligne, vous devez spécifier si le segment entier ou une partie seulement des contacts sont des cibles de la promotion. Si les prix vente/remises ligne couvrent tous les contacts du segment, sélectionnez le champ **Cible campagne** sur le raccourci **Campagne** de la fiche **Segment**.
Si les prix vente/remises ligne ne sont pas offerts à tous les contacts du segment, vous pouvez désélectionner le champ **Cible campagne** pour les contacts appropriés. Si vous ne pouvez pas visualiser ce champ, vous pouvez l'ajouter à votre affichage. Pour plus d'informations, voir [Personnalisation utilisateur](ui-user-personalization.md).

<!-- ## Conducting campaigns
As a campaign runs, all interactions with your contacts, or segment, are recorded so that you can get statistics and other information about the costs and success rates of the campaign.

Campaigns are conducted by salespeople, and you must create activities to represent each task and assign them to the relevant salespeople.  -->

## <a name="see-also"></a>Voir aussi
[Gestion de contacts](marketing-contacts.md)  
[Gestion des segments](marketing-segments.md)  
[Gestion des opportunités de ventes](marketing-manage-sales-opportunities.md)  
[Utilisation de Financials](ui-work-product.md)  

