---
title: "Configurer des paiements anticipés | Microsoft Docs"
description: "Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. La fonctionnalité d'acomptes vous permet de facturer et de collecter les acomptes requis des clients ou de régler des acomptes aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 11aef4cb4b1d40568b63662239a26993782201a3
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-prepayments"></a>Procédure : configurer des paiements anticipés
Si vous voulez que vos clients fassent des paiements avant de leur livrer une commande ou si votre fournisseur exige que vous fassiez un paiement avant de vous livrer une commande, vous pouvez utiliser la fonctionnalité Paiement anticipé. Cette fonctionnalité vous permet de facturer et de collecter les dépôts requis des clients ou de régler des dépôts aux fournisseurs, et de vous assurer que tous les paiements partiels sont reportés sur une facture. Pour plus d'informations, consultez la [Procédure : créer des factures de paiement anticipé](finance-how-to-create-prepayment-invoices.md).

Avant de reporter des factures paiement anticipé, vous devez configurer les comptes de report dans le grand livre et configurer des séries de numéros pour les documents paiement anticipé.  

Vous pouvez définir le pourcentage du montant ligne qui sera facturé pour paiement anticipé, pour un client ou un fournisseur, pour tous les articles ou pour une sélection d'articles. Une fois la configuration terminée, vous pouvez générer des factures paiement anticipé à partir des documents de vente et des bons de commande. Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou, au besoin, modifier les montants de la facture. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

Puisque le montant prépayé appartient à l'acheteur jusqu'à ce qu'il ait reçu les biens ou les services, vous devez configurer des comptes du grand livre pour recevoir les montants de paiement anticipé jusqu'au report de la facture finale. Les paiements anticipés vente doivent être enregistrés dans un compte passif jusqu'à la livraison des articles. Les acomptes achat doivent être enregistrés dans un compte immobilisations jusqu'à la réception des articles. En outre, vous devez configurer un compte du grand livre séparé pour chaque identificateur TVA.

## <a name="to-add-prepayment-accounts-to-the-general-posting-setup"></a>Ajouter des comptes paiement anticipé à la configuration de report générale  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration report général**, puis sélectionnez le lien associé.
2. Dans la fenêtre **Configuration report général**, vous devez renseigner les champs suivants :  

    - **Compte de paiements anticipés de vente**  
    - **Compte de paiements anticipés d'achat**  

## <a name="to-set-up-number-series-for-prepayment-documents"></a>Configurer des séries de numéros pour des documents paiement anticipé  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône"), entrez **Paramètres ventes**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Paramètres ventes**, renseignez les champs suivants :  

   - **N° factures pour paiement anticipé reporté**
   - **N° notes de crédit pour paiement anticipé reporté**

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres achats**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Paramètres achats**, renseignez les champs suivants :

    - **N° factures pour paiement anticipé reporté**
    - **N° notes de crédit pour paiement anticipé reporté**

> [!NOTE]  
>  Vous pouvez utiliser les mêmes séries de numéros pour des factures paiement anticipé et des factures normales, ou utiliser des séries de numéros différentes. Si vous utilisez des souches différentes, elles ne doivent pas se chevaucher car vous ne pouvez pas avoir des numéros identiques dans les deux souches.  

## <a name="to-set-up-prepayment-percentages-for-items-customers-and-vendors"></a>Pour configurer des pourcentages de paiement anticipé pour des articles, des clients et des fournisseurs  
Pour un article, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les clients, pour un client spécifique ou pour un groupe prix client.  

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.
2. Sélectionnez un article, puis cliquez sur l'action **Pourcentages paiement anticipé**.  
3. Dans la fenêtre **Pourcentages paiement anticipé vente**, renseignez autant de champs que nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pour un client ou un fournisseur, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les articles et tous les types de lignes vente. Vous entrez cette valeur dans la fiche client ou fournisseur.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche d'un client.
3. Remplissez le champ **% paiement anticipé**.
4. Répétez les étapes pour d'autres clients ou fournisseurs.  

### <a name="to-determine-which-prepayment-percentage-has-first-priority"></a>Pour déterminer quel pourcentage de paiement anticipé a la priorité  
Une commande peut présenter un pourcentage de paiement anticipé dans l'en-tête vente et un autre pourcentage pour les articles figurant dans les lignes. Pour déterminer quel pourcentage de paiement anticipé s'applique à chaque ligne vente, le système recherche le pourcentage de paiement anticipé dans l'ordre suivant et applique la première valeur par défaut qu'il trouve :  
1. Un pourcentage de paiement anticipé pour l'article figurant dans la ligne et le client auquel la commande est destinée ;  
2. un pourcentage de paiement anticipé pour l'article figurant dans la ligne et le groupe prix client auquel le client appartient ;  
3. un pourcentage de paiement anticipé pour l'article figurant dans la ligne pour tous les clients ;  
4. le pourcentage de paiement anticipé figurant dans l'en-tête vente ou achat.  

Autrement dit, le pourcentage de paiement anticipé figurant dans la fiche client ne s'applique que si aucun pourcentage de paiement anticipé n'est configuré pour l'article. Toutefois, si vous modifiez le contenu du champ **% acompte** dans l'en\-tête vente ou achat après avoir créé les lignes, le pourcentage d'acompte figurant dans toutes les lignes est mis à jour. Cela facilite la création d'une commande avec un pourcentage de paiement anticipé fixe, quel que soit le pourcentage configuré pour les articles.

## <a name="see-also"></a>Voir aussi  
[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

