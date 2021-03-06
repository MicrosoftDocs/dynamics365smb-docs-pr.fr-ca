---
title: Créer des interactions sur les contacts et les segments| Microsoft Docs
description: Décrit comment créer des interactions pour les communications que vous avez avec vos contacts et segments dans Business Central, par exemple le courriel direct.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: 92965b353dadb78e50b11138a832115885518f4f
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5780717"
---
# <a name="create-interactions-on-contacts-and-segments"></a>Créer des interactions sur les contacts et les segments
Vous pouvez créer des interactions pour enregistrer toutes les interactions et toutes les communications que vous entretenez avec vos contacts et segments, par exemple le courriel direct.

Pour pouvoir créer des interactions, vous devez configurer des modèles interaction. Pour plus d'informations, reportez vous à [Configurer des modèles interaction](marketing-interactions.md).

## <a name="to-create-an-interaction"></a>Pour créer une interaction
1. Ouvrez le contact, le représentant, ou l'écriture journal interaction.
2. Sélectionnez l'action **Créer interaction**.
3. Renseignez les champs, puis cliquez sur le bouton **OK**.

> [!NOTE]  
>   Si vous devez effectuer une autre tâche avant de terminer l'interaction, vous pouvez cliquer sur **Annuler** et choisir de terminer l'interaction à une date ultérieure. Cela permet de reporter l'interaction à plus tard.

## <a name="to-finish-and-delete-postponed-interactions"></a>Pour terminer et supprimer les interactions reportées
1. Ouvrez le contact, le représentant, ou l'écriture journal interaction.
2. Sélectionnez **Interactions reportées**.
3. Sélectionnez l'interaction que vous souhaitez terminer, puis sélectionnez l'action **Reprendre**.

## <a name="to-create-an-interaction-on-a-segment"></a>Pour créer une interaction sur un segment
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Segments**, puis sélectionnez le lien associé.
2. Sur la page **Segment**, dans la section **Interaction**, renseignez les champs pour définir l'interaction à affecter au segment.

    Après avoir affecté une interaction au segment, vous pouvez personnaliser l'interaction pour chaque contact au sein du segment, par exemple en sélectionnant un autre modèle interaction sur les lignes de la page **Segment**.  
3. Pour journaliser le segment et les interactions, sélectionnez l'action **Journal**. La page **Journaliser segment** s’affiche.
4. Si vous souhaitez créer un segment contenant les mêmes contacts, activez la case à cocher **Créer suivi segment**. Pour créer un segment de suivi, vous devez avoir indiqué une série de numéros pour les segments sur la page **Configuration Marketing**.

Une interaction est enregistrée pour chaque contact inclus dans le segment dans la table **Ecriture journal interaction**, et le segment est journalisé. Vous pouvez consulter les segments journalisés sur la page **Segments journalisés**.

Si vous avez activé la case à cocher **Créer suivi segment**, le programme crée automatiquement un segment contenant les mêmes contacts que le segment journalisé.

## <a name="see-also"></a>Voir aussi
[Enregistrement d'interactions](marketing-interactions.md)  
[Gestion de contacts](marketing-contacts.md)  
[Gestion des opportunités de ventes](marketing-manage-sales-opportunities.md)  
[Utilisation de Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]