---
title: Exporter des données | Invoicing
description: Découvrez comment exporter des données, par exemple supprimer des contacts dans le cadre d'une demande de sujet de données.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/12/2018
ms.author: edupont
ms.openlocfilehash: 384791aeadaaa4c374607ec529955171456ab7e4
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "826243"
---
# <a name="export-or-delete-data-from-included365invlongincludesd365invlongmd"></a>Exporter ou supprimer des données de [!INCLUDE[d365inv_long](includes/d365inv_long.md)]

Si vous voulez supprimer un contact ou un client de [!INCLUDE[d365inv](includes/d365inv.md)], il est facile de le faire.  

## <a name="to-delete-an-existing-customer"></a>Pour supprimer un client existant

1. Sur la page d'accueil, choisissez **Clients** pour ouvrir la liste des clients.
2. Recherchez le contact, puis choisissez le nom pour ouvrir les détails.
3. Cliquez sur l'action **Supprimer**.

> [!NOTE]
> Si vous lui avez déjà envoyé une facture, vous ne pouvez pas supprimer le client. À la place, [!INCLUDE[d365inv](includes/d365inv.md)] peut marquer le client comme bloqué pour toute activité ultérieure. Cela signifie que vous ne pouvez pas lui envoyer de nouvelles factures, par exemple.  

Si le contact n'a pas été ajouté comme client, vous pouvez l'ajouter en créant une facture provisoire.

## <a name="to-add-a-contact-as-a-customer-and-then-delete-the-customer"></a>Pour ajouter un contact comme client et supprimer le client

1. Sur la page Accueil, choisissez **Nouvelle facture**
2. Dans le champ **Nom du client**, commencez à saisir le nom du contact.
3. Sélectionnez votre contact dans la recherche, puis fermez la fenêtre.
4. Supprimez la facture provisoire qui vient d'être créée.
5. Suivez les étapes pour supprimer le client comme décrit ci-dessus.

## <a name="responding-to-requests-about-personal-data"></a>Réponse aux demandes relatives aux données personnelles

Les sujets des données peuvent demander plusieurs types d'actions concernant leurs données personnelles. Par exemple, en vertu du Règlement général sur la protection des données (RGPD), les résidents de l'UE ont le droit de demander l'exportation, la suppression et la modification de leurs données personnelles. Cela est appelé *Demande du sujet des données*.  

### <a name="requests-for-deletion"></a>Demandes de suppression

Un sujet des données peut demander la suppression de ses données personnelles. Si un contact ou un client vous demande de le supprimer dans le cadre d'une demande de sujet de données, vous pouvez suivre les étapes décrites ci-dessus.  

### <a name="requests-for-exporting-privacy-data"></a>Demandes d'exportation des données de confidentialité

Un sujet des données peut faire une demande de portabilité des données, ce qui signifie que vous devez exporter les données personnelles du sujet des données à partir de vos systèmes et les fournir dans un format couramment utilisé et structuré.  Si un contact ou un client vous demande de lui envoyer ses informations à partir de [!INCLUDE[d365inv](includes/d365inv.md)], vous pouvez vous envoyer ses informations de contact par courriel.  

#### <a name="to-export-privacy-data"></a>Pour exporter les données de confidentialité

1. Sur la page d'accueil, choisissez **Clients** pour ouvrir la liste des clients.
2. Recherchez le contact approprié, puis choisissez le nom pour ouvrir les détails.
3. Développez l'onglet **Confidentialité**, puis choisissez **Exporter les données de confidentialité du client**.
4. Dans la page **Exporter les données du client**, vérifiez que vous êtes sur le point d'envoyer le courriel à vous-même, puis cliquez sur le bouton OK.

Le courriel que vous recevez contient un classeur Excel avec des informations sur le client, notamment les factures que vous lui avez envoyées. Selon la demande d'origine, vous pouvez choisir de supprimer une partie des informations avant de transférer le courriel au client.  

### <a name="requests-for-correction"></a>Demandes de correction

Un sujet des données peut demander la correction des données personnelles incorrectes. Si un contact ou un client vous demande de mettre à jour les informations le concernant dans [!INCLUDE[d365inv](includes/d365inv.md)], vous pouvez le faire dans les détails du client.  

## <a name="see-also"></a>Voir aussi .

[Configurer les informations sur votre entreprise](set-up-business-profile.md)  
[Envoyer une facture à un nouveau client](send-invoice.md)  
[Dépannage](about-troubleshooting.md)  
