---
title: Configuration des campagnes marketing dans Financials | Microsoft Docs
description: "Décrit la manière dont vous pouvez configurer et mener des campagnes marketing dans Dynamics 365 for Financials"
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: marketing, campaign, promo, prospect
ms.date: 05/20/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 92c5fb75f4f3d3180ba67b89481beed2e58c3dbe
ms.openlocfilehash: 68359d2dd2c2e07463babda91d86d47998f0912a
ms.contentlocale: fr-ca
ms.lasthandoff: 05/31/2017


---
# <a name="managing-marketing-campaigns"></a>Gestion de campagnes marketing
Disposer d'une solide stratégie marketing permet d'identifier, d'attirer et de fidéliser les clients. Une stratégie marketing est composée de diverses campagnes ainsi que d'interactions en relation avec vos activités de vente et de marketing. Lors de la planification d'une promotion, vous devez choisir les contacts à cibler, le type de promotion (salon, courriel direct) et le représentant chargé de chaque tâche.

Chaque promotion est composée de diverses activités ou tâches. Vous pouvez combiner plusieurs tâches, par exemple les tâches qui représentent chacune une étape, dans les activités. Les tâches d'activité sont liées entre elles par une formule de date. Les tâches individuelles peuvent être affectées uniquement à des représentants. Les activités peuvent être affectées aux opportunités, représentants, groupes de représentants et contacts. Pour plus d'informations, voir [Procédure : configurer des cycles de vente opportunité et des étapes de cycle](marketing-how-setup-opportunity-sales-cycles-stages.md).

## <a name="defining-individual-campaigns"></a>Définition de campagnes individuelles
Pour pouvoir créer une campagne, vous devez configurer des *codes statut campagne*. Ceux-ci permettent de gérer vos promotions en affectant un état à la promotion. Lorsque vous travaillez sur les phases d'une promotion, vous pouvez voir où en est la promotion et visualiser l'étape suivante. Vous devez configurer des codes statut campagne dans la fenêtre **Statut campagne**.

Vous pouvez créer une fiche campagne pour toutes les campagnes que vous voulez suivre. Vous pouvez également afficher ces fiches promotion pour visualiser des informations générales sur vos promotions.
Vous pouvez supprimer des écritures promotion, par exemple si elles enregistrent une action qui a été annulée. Vous ne pouvez supprimer que les écritures promotion annulées.

### <a name="selecting-the-target-audience"></a>Sélection du public cible
Après avoir créé une promotion, vous pouvez commencer à créer les segments qui spécifient le public cible de la promotion. Pour plus d'informations, voir [Gestion des segments](marketing-segments.md).

### <a name="registering-discount-percentages"></a>Enregistrement des pourcentages escompte
Lorsque vous avez défini votre campagne, que vous avez déterminé les segments que la campagne doit couvrir et défini les dates début et dates de fin, vous enregistrez le pourcentage de la remise auquel le client a droit pour chaque article dans les lignes de la fenêtre **Remises ligne vente**. Vous pouvez également enregistrer les prix de vente pour des articles individuels sur les lignes de la fenêtre **Prix vente**. Vous pouvez accéder aux deux fenêtres à partir de la fiche promotion.

 Lorsque vous avez configuré les prix vente/escomptes ligne et les segments dans la fiche promotion, vous devez les activer afin que les lignes reflètent les prix/escomptes de la promotion.

**Remarque** : afin que vous puissiez activer les prix vente/remises ligne, vous devez spécifier si le segment entier ou une partie seulement des contacts sont des cibles de la campagne. Si les prix vente/remises ligne couvrent tous les contacts du segment, sélectionnez le champ **Cible campagne** sur le raccourci **Campagne** de la fiche **Segment**.
Si les prix vente/remises ligne ne sont pas offerts à tous les contacts du segment, vous pouvez désélectionner le champ **Cible campagne** pour les contacts appropriés. Si vous ne pouvez pas visualiser ce champ, vous pouvez l'ajouter à votre affichage. Pour plus d'informations, voir [Personnalisation utilisateur](ui-user-personalization.md).

## <a name="conducting-campaigns"></a>Mise en place de campagnes
Au cours de la promotion, toutes les interactions avec vos contacts (ou le segment) sont enregistrées afin que vous puissiez obtenir des statistiques et autres informations sur les coûts et le taux de réussite de la promotion.

Les promotions sont conduites par les représentants, vous devez créer des activités pour représenter chaque tâche et les affecter aux représentants appropriés. Pour plus d'informations, voir [Procédure : configurer des cycles de vente opportunité et des étapes de cycle](marketing-how-setup-opportunity-sales-cycles-stages.md).

## <a name="see-also"></a>Voir aussi
[Gestion de contacts](marketing-contacts.md)  
[Gestion des segments](marketing-segments.md)  
[Gestion des opportunités de ventes](marketing-manage-sales-opportunities.md)  
[Utilisation de Financials](ui-work-product.md)  

