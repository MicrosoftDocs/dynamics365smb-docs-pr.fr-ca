---
title: Traiter les transactions IC entrantes et sortantes | Microsoft Docs
description: "Les transactions intersociétés que vous recevez de vos partenaires intersociétés sont stockées dans la boîte de réception Intersociétés où vous pouvez les traiter manuellement ou automatiquement."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: incoming document
ms.date: 07/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: d1a901cee7a80e9a1690f665df4a79a59fa7bc12
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="manage-the-intercompany-inbox-and-outbox"></a>Gérer la boîte de réception et la boîte d'envoi intersociétés
Toutes les transactions intersociétés que vous recevez par voie électronique de vos partenaires intersociétés sont stockées dans la boîte de réception Intersociétés.  

## <a name="organizing-the-inbox"></a>Organisation de la boîte de réception  
 Les champs de filtre, situés en haut de la fenêtre de la boîte de réception, permettent de déterminer les transactions qui apparaissent dans la fenêtre. Par exemple, si vous souhaitez uniquement consulter les transactions créées par un partenaire précis, vous pouvez définir les filtres **Source de la transaction** et **Code Partenaire Intercompagnie**.  

### <a name="transaction-source"></a>Source de transaction  
Vous pouvez utiliser une transaction différemment selon qu'elle a été :  

- Créé par votre partenaire intercompagnie  
- Rejeté par votre partenaire intercompagnie et renvoyé vers vous  

Vous pouvez utiliser le champ **Afficher la source de la transaction** pour filtrer la fenêtre **Transactions boîte de réception Intersociétés**, afin qu'elle n'affiche qu'un seul des types de transaction suivants. (Vous pouvez également filtrer la fenêtre en fonction du partenaire intercompagnie ou de la valeur du champ **Action de la ligne**.)  

#### <a name="created-by-intercompany-partner"></a>Créé par votre partenaire intercompagnie  
 Lorsque vous recevez une nouvelle transaction créée par votre partenaire, vous pouvez soit :

- Accepter la transaction  
- Rejeter la transaction (et la renvoyer à votre partenaire)  
- Annuler la transaction (et la supprimer sans la renvoyer à votre partenaire)  

#### <a name="returned-from-intercompany-partner"></a>Renvoyé par le partenaire intercompagnie  
 Si la transaction a été rejetée par votre partenaire intercompagnie, vous n'avez pas d'autre choix que d'annuler la transaction dans la boîte de réception. Vous devez créer des lignes de correction ou inverser le journal ou le document de votre compagnie.  

## <a name="re-creating-inbox-entries"></a>Recréation d'écritures boîte de réception  
 Si vous acceptez une transaction de votre boîte de réception, mais que vous avez supprimé le journal ou le document au lieu de le reporter, vous pouvez recréer l'écriture boîte de réception et l'accepter à nouveau.  

## <a name="getting-an-overview-of-intercompany-transactions-for-a-period"></a>Affichage d'un aperçu des transactions intersociétés sur une période donnée  
 Vous pouvez afficher un aperçu des transactions intersociétés envoyées et reçues sur une période donnée. Le rapport **Transactions intercompagnies** répertorie toutes les écritures GL intercompagnies, les écritures client et les écritures fournisseur.

 > [!NOTE]  
 > Si les partenaires intercompagnies sont exprimés dans la même base de données, les transactions sont transférées sans recourir à un fichier ou un courriel. Voir le champ **Type de transfert** dans la fenêtre **Partenaire intercompagnie**. <br /><br />
Dans ce cas, vous pouvez configurer le système pour qu'il ignore la boîte de réception et la boîte d'envoi en sélectionnant la case à cocher **Auto. Accepter les transactions** dans la fenêtre **Partenaire Intercompagnie** et la case à cocher **Auto. Envoyer des transactions** dans la fenêtre **Configuration intercompagnie** respectivement.

## <a name="to-import-intercompany-transactions-from-a-file"></a>Pour importer des transactions intersociétés à partir d'un fichier  
Si l'un de vos partenaires intercompagnies ne figure pas dans la même base de données que votre compagnie, vous pouvez recevoir de lui des transactions intercompagnies dans un fichier .xml. Vous devez ensuite importer ces transactions dans votre boîte de réception.  

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Informations compagnie**, puis sélectionnez le lien associé.
2. Enregistrez le fichier à l'emplacement spécifié dans le champ **Détails boîte réception intercompagnie** de la fenêtre **Informations compagnie**.  
3. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Transactions Boîte de réception intercompagnies**, puis sélectionnez le lien associé.
4. Dans la fenêtre **Transactions boîte de réception Intersociétés**, choisissez l'action **Importer le fichier de transaction**.  
5. Dans la fenêtre qui apparaît, sélectionnez le fichier .xml qui contient les transactions, puis cliquez sur le bouton **Ouvrir**.  

Les transactions sont importées dans la boîte de réception. Vous pouvez alors les traiter.

## <a name="to-process-incoming-intercompany-transactions"></a>Pour traiter les transactions intersociétés entrantes  
Lorsque vos partenaires intersociétés vous envoient des transactions intersociétés, celles-ci arrivent dans votre boîte de réception intersociété. Vous devez évaluer chaque transaction qu'elle contient et prendre les mesures nécessaires.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Transactions Boîte de réception intercompagnies**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Transactions boîte de réception Intersociétés**, sélectionnez une ligne, puis choisissez une action **Accepter** pour traiter la ligne.
3. Dans la fenêtre **Terminer action boîte récep IC**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Cliquez sur le bouton **OK**.  

Pour les lignes que vous avez traitées avec l'action **Accepter**, des lignes document ou journal sont créées dans votre compagnie. Ouvrez chaque document ou journal, apportez les modifications nécessaires, puis reportez-les.  

Les lignes que vous avez traitées avec l'action **Renvoyer au partenaire** sont déplacées vers la boîte d'envoi d'où vous pouvez ensuite les envoyer à votre partenaire.

Pour les lignes que vous avez traitées avec l'action **Renvoyé par le partenaire**, vous devez à présent reporter une correction sur la transaction initiale reportée dans votre compagnie.

## <a name="to-process-outgoing-intercompany-transactions"></a>Pour traiter les transactions intersociétés sortantes  
Lorsque vous reportez un journal ou un document intercompagnie, ou que vous envoyez une confirmation de commande intercompagnie, les transactions sont envoyées à votre boîte d'envoi intercompagnie. Pour qu'elles soient envoyées à vos partenaires intersociétés, vous devez ouvrir la boîte d'envoi et les traiter.  

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Transactions Boîte de réception intercompagnies**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Transactions boîte d'envoi Intersociétés**, sélectionnez une ligne, puis choisissez une action **Retourner à la boîte de réception** pour traiter la ligne.

Les lignes que vous avez traitées avec l'action **Envoyer au partenaire intercompagnie** sont transmises à la boîte de réception du partenaire concerné.

Les lignes que vous avez traitées avec l'action **Retourner à la boîte de réception** sont déplacées vers la boîte de réception où vous pouvez les accepter pour créer des documents ou des lignes journal dans votre compagnie.  

Pour les lignes que vous avez traitées avec l'action **Annuler**, vous devez à présent reporter une correction sur la transaction initiale reportée dans votre compagnie.  

## <a name="to-recreate-intercompany-inbox-transactions"></a>Pour recréer des transactions boîte de réception intersociétés  
À l'occasion, vous pouvez recréer une transaction dans la boîte de réception ou d'envoi. Par exemple, si vous avez accepté une transaction dans votre boîte de réception, mais que vous avez supprimé le journal ou le document au lieu de le reporter, vous pouvez recréer l'écriture boîte de réception et l'accepter à nouveau.  

La procédure suivante décrit comment recréer des transactions de boîte de réception. Le processus est le même pour la boîte d'envoi.

  1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Transactions Boîte de réception intercompagnies**, puis sélectionnez le lien associé.  

  2.  Dans la fenêtre **Transactions boîte de réception IC gérées**, sélectionnez la ligne contenant la transaction à recréer dans la boîte de réception, puis choisissez l'action **Recréer la transaction boîte de réception**.  

## <a name="see-also"></a>Voir aussi
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

