---
title: Configurer la connexion à la messagerie | Microsoft Docs
description: Apprenez à transformer les interactions de messagerie entre les représentants et les clients en véritables opportunités de vente.
services: project-madeira
documentationcenter: ''
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect, opportunity, email
ms.date: 10/01/2019
ms.author: bholtorf
ms.openlocfilehash: e325cce98256b723c6fcfdf4d16068f852a2b032
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2308750"
---
# <a name="track-email-message-exchanges-between-salespeople-and-contacts"></a>Suivre les échanges de courriels entre les représentants et les contacts
Tirez le meilleur parti des communications entre les représentants et vos clients existants ou potentiels en suivant les échanges de courriels, puis en les transformant en opportunités exploitables. [!INCLUDE[d365fin](includes/d365fin_md.md)] peut utiliser Exchange Online pour conserver un journal des messages entrants et sortants. Vous pouvez afficher et analyser le contenu de chaque message sur la page **Écritures journal interaction**.

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085401]

## <a name="setting-up-included365finincludesd365fin_mdmd-to-log-email-messages"></a>Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)] pour enregistrer les courriels
Pour démarrer la connexion à la messagerie, effectuez deux étapes simples :

1. Connectez [!INCLUDE[d365fin](includes/d365fin_md.md)] à Exchange Online pour votre abonnement Office 365. Exchange Online gère vos courriels. Nous avons facilité cette étape en fournissant un guide de configuration assisté. Vous avez juste besoin de vos identifiants d’administrateur pour votre compte d’administrateur dans Office 365. Pour commencer le guide, accédez à **Configuration assistée**, puis choisissez **Configurer la connexion à la messagerie**. 
2. Assurez-vous que des adresses de courriel valides ont été entrées dans [!INCLUDE[d365fin](includes/d365fin_md.md)] pour vos représentants et vos contacts, selon qu’il s'agisse de clients potentiels ou existants. Pour ce faire, pour chaque client ou représentant, ouvrez la fiche **Contact** ou **Représentant/Acheteur** et regardez le champ **Courriel**.

> [!Tip]
> Une fois les étapes du guide terminées, vous pouvez vérifier si la connexion a réussi. Recherchez **Configuration marketing**, choisissez **Traiter**, puis **Fonctions** et **Valider la configuration de la connexion à la messagerie**.

## <a name="viewing-email-message-exchanges-in-the-interaction-log"></a>Affichage des échanges de courriels dans le journal des interactions
[!INCLUDE[d365fin](includes/d365fin_md.md)] crée une entrée sur la page **Journal des interactions** chaque fois qu'un représentant et un contact échangent un courriel. Pour afficher le journal des interactions, ouvrez la fiche **Contact** ou **Représentant/Acheteur** pour la personne, puis choisissez **Naviguer**, **Historique**, puis **Écritures journal interaction**. Nous pouvons faire certaines choses avec chaque entrée du journal, par exemple :

* Affichez le contenu du courriel échangé en cliquant sur l'action **Afficher les pièces jointes**.
* Transformez un échange de courriels en opportunité de vente. Si une entrée semble prometteuse, vous pouvez la transformer en opportunité, puis gérer son évolution vers une vente. Pour cela, sélectionnez l'entrée, puis cliquez sur l'action **Créer une opportunité**. Pour plus d'informations, voir [Gérer des opportunités de vente](marketing-manage-sales-opportunities.md).

## <a name="see-also"></a>Voir aussi
[Gestion des relations](marketing-relationship-management.md)

