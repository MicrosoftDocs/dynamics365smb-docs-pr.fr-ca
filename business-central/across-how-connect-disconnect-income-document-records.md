---
title: Créer des document entrants depuis Documents| Microsoft Docs
description: Vous pouvez créer des enregistrements de documents entrants, tels que des factures électroniques, et gérer des tâches OCR, du e-Commerce et l'échange de documents.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 1cc239f02dc0b278afd11c8e9ecdf48af1170a91
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5776082"
---
# <a name="create-incoming-document-records-directly-from-documents-and-entries"></a>Créer des enregistrements document entrant directement à partir de documents et d'écritures
Vous pouvez enregistrer des documents commerciaux externes dans [!INCLUDE[prod_short](includes/prod_short.md)] en liant des fichiers document aux enregistrements document entrant associées. Si le document, une facture achat par exemple, n'était pas dès le départ un enregistrement document entrant, vous pouvez toujours créer et le lier à un enregistrement document entrant ultérieurement. Vous pouvez également joindre des fichiers document entrant à des documents achat et vente reportés et à des écritures fournisseur, client et GL à l'aide du récapitulatif **Fichiers document entrant** dans, par exemple, les pages **Factures achat reportées** et **Écritures fournisseur**.

Depuis les pages **Plan comptable** et **Écritures**, vous pouvez utiliser la fonction de recherche pour rechercher les écritures pour des documents achat et vente reportés qui n'ont pas d'enregistrement de document entrant, puis les lier de façon centralisée à des enregistrements existants ou en créer de nouveaux avec des fichiers joints. Pour plus d'informations, voir [Rechercher des enregistrements reportés sans enregistrements document entrant](across-how-find-posted-documents-without-income-document-records.md).

Les procédures suivantes indiquent comment joindre un fichier à une facture achat existante qui n'a pas été créée à partir d'un enregistrement document entrant et comment joindre un fichier à une écriture fournisseur. La même tâche permet de joindre un fichier à des documents achat ou vente reportés.

## <a name="to-create-and-connect-an-incoming-document-record-from-a-purchase-invoice"></a>Créer et lier un enregistrement document entrant à partir d'une facture achat
1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Factures achat**, puis sélectionnez le lien associé.
2. Sélectionnez la ligne de la facture achat à laquelle vous souhaitez joindre un fichier, puis sélectionnez l'action **Créer un document entrant à partir d'un fichier**.
3. Vous pouvez également sélectionner la ligne de la facture achat à laquelle vous souhaitez joindre un fichier, puis sélectionner l'action **Joindre fichier**.
4. Sur la page **Insérer un fichier**, sélectionnez le fichier qui représente le document entrant concerné, puis choisissez le bouton **Ouvrir**.

## <a name="to-create-and-connect-an-incoming-document-record-from-a-vendor-ledger-entry"></a>Créer et lier un enregistrement document entrant à partir d'une écriture fournisseur
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Écritures fournisseur**, puis choisissez le lien associé.
2. Sélectionnez une ligne d'une écriture comptable fournisseur à laquelle vous souhaitez joindre un fichier, puis sélectionnez l'action **Créer un document entrant à partir d'un fichier**.
3. Vous pouvez également sélectionner une ligne d'une une écriture comptable fournisseur à laquelle vous souhaitez joindre un fichier, puis sélectionner l'action **Joindre fichier**.
4. Sur la page **Insérer un fichier**, sélectionnez le fichier qui représente le document entrant concerné, puis choisissez le bouton **Ouvrir**.

## <a name="to-remove-a-connection-from-an-incoming-document-record-to-a-posted-document"></a>Pour supprimer la connexion d'un enregistrement document entrant à un document reporté
Vous pouvez supprimer des fichiers joints de documents non reportés à tout moment en supprimant l'enregistrement document entrant associé. Si le document est reporté, vous devez d'abord supprimer la connexion de l'enregistrement document entrant.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents entrants**, puis sélectionnez le lien associé.
2. Sélectionnez la ligne correspondant à un enregistrement document entrant lié à un document validé que vous souhaitez supprimer, puis sélectionnez **Supprimer la référence à l'enregistrement**.

La connexion au document reporté est supprimée. Vous pouvez maintenant connecter un autre enregistrement document entrant au document reporté, comme cela est décrit dans cette rubrique.

## <a name="see-also"></a>Voir aussi
[Traiter les documents entrants](across-process-income-documents.md)  
[Documents entrants](across-income-documents.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]