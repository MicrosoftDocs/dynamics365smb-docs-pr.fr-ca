---
title: Configurer des promotions marketing dans Business Central | Microsoft Docs
description: Décrit la manière dont vous pouvez configurer et mener des promotions marketing dans Business Central afin de vous aider à identifier et attirer des prospects et à fidéliser les clients.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'marketing, campaign, promo, prospect'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="managing-marketing-campaigns" />Gestion de campagnes marketing
Disposer d'une solide stratégie marketing permet d'identifier, d'attirer et de fidéliser les clients. Une stratégie marketing est composée de diverses campagnes ainsi que d'interactions en relation avec vos activités de vente et de marketing. Lors de la planification d'une promotion, vous devez choisir les contacts à cibler, le type de promotion (salon, courriel direct) et le représentant chargé de chaque tâche.

Chaque promotion est composée de diverses activités ou tâches. Vous pouvez combiner plusieurs tâches, par exemple les tâches qui représentent chacune une étape, dans les activités. Les tâches d'activité sont liées entre elles par une formule de date. Les tâches individuelles peuvent être affectées uniquement à des représentants. Les activités peuvent être affectées aux opportunités, représentants, groupes de représentants et contacts. Pour plus d'informations, voir [Configurer des cycles de vente opportunité et des phases de cycle](marketing-how-setup-opportunity-sales-cycles-stages.md).

## <a name="defining-individual-campaigns" />Définition de campagnes individuelles
Pour pouvoir créer une campagne, vous devez configurer des *codes statut campagne*. Ceux-ci permettent de gérer vos promotions en affectant un état à la promotion. Lorsque vous travaillez sur les phases d'une promotion, vous pouvez voir où en est la promotion et visualiser l'étape suivante. Vous devez configurer des codes état promotion sur la page **État promotion**.

Vous pouvez créer une fiche campagne pour toutes les campagnes que vous voulez suivre. Vous pouvez également afficher ces fiches promotion pour visualiser des informations générales sur vos promotions.
Vous pouvez supprimer des écritures promotion, par exemple si elles enregistrent une action qui a été annulée. Vous ne pouvez supprimer que les écritures promotion annulées.

### <a name="selecting-the-target-audience" />Sélection du public cible
Après avoir créé une promotion, vous pouvez commencer à créer les segments qui spécifient le public cible de la promotion. Pour plus d'informations, voir [Gestion des segments](marketing-segments.md).

### <a name="registering-discount-percentages" />Enregistrement des pourcentages escompte
Lorsque vous avez défini votre promotion, que vous avez déterminé les segments que la promotion doit couvrir et défini les dates de début et dates de fin, vous enregistrez le pourcentage d'escompte auquel le client a droit pour chaque article dans les lignes de la page **Escomptes de ligne de vente**. Vous pouvez également enregistrer les prix de vente pour des articles individuels sur les lignes de la page **Prix vente**. Vous pouvez accéder aux deux pages à partir de la fiche promotion.

 Lorsque vous avez configuré les prix vente/escomptes ligne et les segments dans la fiche promotion, vous devez les activer afin que les lignes reflètent les prix/escomptes de la promotion.

> [!NOTE]  
>   Afin que vous puissiez activer les prix vente/escomptes ligne, vous devez spécifier si le segment entier ou une partie seulement des contacts sont des cibles de la promotion. Si les prix vente/remises ligne couvrent tous les contacts du segment, sélectionnez le champ **Cible campagne** sur le raccourci **Campagne** de la fiche **Segment**.

Si les prix vente/remises ligne ne sont pas offerts à tous les contacts du segment, vous pouvez désélectionner le champ **Cible campagne** pour les contacts appropriés. Si vous ne pouvez pas visualiser ce champ, vous pouvez l'ajouter à votre affichage. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

## <a name="conducting-campaigns" />Mise en place de campagnes
Au cours de la promotion, toutes les interactions avec vos contacts (ou le segment) sont enregistrées afin que vous puissiez obtenir des statistiques et autres informations sur les coûts et le taux de réussite de la promotion.

Les promotions sont conduites par les représentants, vous devez créer des activités pour représenter chaque tâche et les affecter aux représentants appropriés. Pour plus d'informations, voir [Configurer des cycles de vente opportunité et des phases de cycle](marketing-how-setup-opportunity-sales-cycles-stages.md).

## <a name="see-also" />Voir aussi
[Gestion de contacts](marketing-contacts.md)  
[Gestion des segments](marketing-segments.md)  
[Gestion des opportunités de ventes](marketing-manage-sales-opportunities.md)  
[Utiliser Business Central](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
