---
title: Exporter des données | Invoicing
description: Découvrez comment exporter des données, par exemple supprimer des contacts dans le cadre d'une demande de sujet de données.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/08/2019
ms.author: bholtorf
ms.openlocfilehash: aa3e598721a3c0fcfde31ee5edbe2a1fe47e96b9
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3927918"
---
# <a name="export-or-delete-data-from-d365inv_long"></a>Exporter ou supprimer des données de [!INCLUDE[d365inv_long](includes/d365inv_long.md)]
> [!Note]
> [!INCLUDE[d365inv_discont](includes/d365inv_discont.md)]

## <a name="export-all-of-your-data"></a>Exporter toutes vos données
Si vous êtes administrateur, [!INCLUDE[d365inv](includes/d365inv.md)] fournit un guide de configuration assistée qui vous permet d'exporter les données pour les clients, les prix, les factures, les estimations et les paiements vers Excel, le tout en une seule opération, puis d'envoyer le classeur vers une adresse de courriel. Le classeur Excel liste les informations dans des onglets distincts. Vous pouvez démarrer le guide de deux manières :

* Lorsque vous vous connectez, une notification s'affiche. Pour démarrer le guide, choisissez **Exporter**.
* Dans votre Tableau de bord, Sous **Informations importantes**, choisissez **Étapes suivantes**.    

> [!Note]
> Seuls les administrateurs système peuvent exporter des données à partir de [!INCLUDE[d365inv](includes/d365inv.md)].

## <a name="export-invoices-only"></a>Exporter des factures uniquement
Si vous souhaitez simplement exporter des factures, sur la page de liste **Factures**, choisissez **Gérer**, puis **Exporter des factures**. Entrez des dates de début et de fin pour la période pour laquelle exporter des factures et assurez-vous que l'adresse de courriel correcte est entrée. Invoicing exporte les documents vers Excel, puis envoie le classeur vers l'adresse de courriel.

## <a name="delete-an-existing-customer"></a>Supprimer un client existant
Si vous voulez supprimer un contact ou un client de [!INCLUDE[d365inv](includes/d365inv.md)], il est facile de le faire.
1. Sur la page d'accueil, choisissez **Clients** pour ouvrir la liste des clients.
2. Recherchez le contact, puis choisissez le nom pour ouvrir les détails.
3. Cliquez sur l'action **Supprimer**.

> [!NOTE]
> Si vous lui avez déjà envoyé une facture, vous ne pouvez pas supprimer le client. À la place, [!INCLUDE[d365inv](includes/d365inv.md)] peut marquer le client comme bloqué pour toute activité ultérieure. Cela signifie que vous ne pouvez pas lui envoyer de nouvelles factures, par exemple.  

Si le contact n'a pas été ajouté comme client, vous pouvez l'ajouter en créant une facture provisoire.

## <a name="add-a-contact-as-a-customer-and-then-delete-the-customer"></a>Ajouter un contact comme client et supprimer le client
1. Sur la page Accueil, choisissez **Nouvelle facture**
2. Dans le champ **Nom du client**, commencez à saisir le nom du contact.
3. Sélectionnez votre contact dans la recherche, puis fermez la fenêtre.
4. Supprimez la facture provisoire qui vient d'être créée.
5. Suivez les étapes pour supprimer le client comme décrit ci-dessus.

## <a name="see-also"></a>Voir aussi
[Configurer les informations sur votre entreprise](set-up-business-profile.md)  
[Envoyer une facture à un nouveau client](send-invoice.md)  
[Dépannage](about-troubleshooting.md)  
