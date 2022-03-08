---
title: Procédure de suivi des relations entre l'offre et la demande | Microsoft Docs
description: À partir d'un document d'approvisionnement ou de demande dans le réseau d'ordres, vous pouvez suivre la demande de commande (quantité suivie), les prévisions, les commandes permanentes ventes ou les paramètres de planification (quantité non suivie) qui ont donné lieu à la ligne planification en question.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 3d053de6193593256e404803d61b14f4681dc771
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3921550"
---
# <a name="track-relations-between-demand-and-supply"></a>Suivre les relations entre l'offre et la demande
À partir d'un document d'approvisionnement ou de demande dans le réseau d'ordres, vous pouvez suivre la demande de commande (quantité suivie), les prévisions, les commandes permanentes ventes ou les paramètres de planification (quantité non suivie) qui ont donné lieu à la ligne planification en question.

Les feuilles planification incluent également des informations de planification sur les entités sans rapport avec les commandes pour aider le gestionnaire à obtenir un programme d'approvisionnement optimal. Pour plus d'informations, voir [Éléments planification sans suivi](production-how-track-demand-supply.md#untracked-planning-elements).

## <a name="to-track-linked-items"></a>Pour chaîner des articles liés
Par l'intermédiaire des systèmes de planification et de réservation, le suivi de commande montre de quelle manière les documents de vente, les bons de production et les bons de commande sont reliés aux ordres de fabrication.

La procédure suivante décrit comment chaîner des articles liés sur un ordre de fabrication planifié ferme. La procédure est similaire pour tous les autres types de commande, et à partir des lignes feuille planification.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bon de production planifié ferme**, puis sélectionnez le lien associé.
2. Ouvrez le bon de production planifié ferme approprié dans la liste.
3. Sur le raccourci **Lignes**, choisissez l'action **Fonctions**, puis l'action **Chaînage**.

Les lignes de la fenêtre **Chaînage** affichent les documents liés à la ligne de l'ordre de fabrication en cours.

## <a name="untracked-planning-elements"></a>Éléments de planification sans traçabilité
La page **Éléments planification sans suivi** s'affiche lorsque vous cliquez sur le champ **Qté sans suivi** sur la page **Planification commande**. Elle a deux objectifs :

1. Stockage d'informations sur les quantités non chaînées qui s'affichent lorsque l'utilisateur affiche la page Chaînage.
2. Stockage des messages d'avertissement qui s'affichent lorsque l'utilisateur clique sur l'icône **Avertissement** sur la page **Feuille planification**.

la page inclut les écritures représentant une quantité excédentaire non chaînée du réseau de chaînage. Ces écritures sont générées au cours de l'exécution de la planification et expliquent la provenance de la quantité excédentaire non chaînée des lignes chaînage. Cet excédent non chaîné peut provenir des lignes suivantes :

- Prévisions production ;
- Commandes permanentes
- Stock de sécurité ;
- Point de commande ;
- Inventaire maximum
- Quantité de réappro. ;
- Qté maximum commande ;
- Qté minimum commande ;
- Commandé par ;
- Seuil (% taille lot).

## <a name="see-also"></a>Voir aussi  
[Planification](production-planning.md)   
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : réservation, chaînage et message d'action](design-details-reservation-order-tracking-and-action-messaging.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
