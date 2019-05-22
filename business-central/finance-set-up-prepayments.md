---
title: Configurer des paiements anticipés | Microsoft Docs
description: Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. La fonctionnalité d'acomptes vous permet de facturer et de collecter les acomptes requis des clients ou de régler des acomptes aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: prepayment
ms.date: 04/01/2019
ms.author: edupont
ms.openlocfilehash: e8a6e0834b259358de5c07d3f83a7b5477a0d3a7
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1244709"
---
# <a name="set-up-prepayments"></a>Configuration des acomptes
Si vous voulez que vos clients fassent des paiements avant de leur livrer une commande ou si votre fournisseur exige que vous fassiez un paiement avant de vous livrer une commande, vous pouvez utiliser la fonctionnalité Paiement anticipé. Cette fonctionnalité vous permet de facturer et de collecter les dépôts requis des clients ou de régler des dépôts aux fournisseurs, et de vous assurer que tous les paiements partiels sont reportés sur une facture. Pour plus d'informations, voir [Créer des factures de paiement anticipé](finance-how-to-create-prepayment-invoices.md).

Avant de reporter des factures paiement anticipé, vous devez configurer les comptes de report dans le grand livre et configurer des séries de numéros pour les documents paiement anticipé.  

Vous pouvez définir le pourcentage du montant ligne qui sera facturé pour paiement anticipé, pour un client ou un fournisseur, pour tous les articles ou pour une sélection d'articles. Une fois la configuration terminée, vous pouvez générer des factures paiement anticipé à partir des documents de vente et des bons de commande. Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou, au besoin, modifier les montants de la facture. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

Puisque le montant prépayé appartient à l'acheteur jusqu'à ce qu'il ait reçu les biens ou les services, vous devez configurer des comptes du grand livre pour recevoir les montants de paiement anticipé jusqu'au report de la facture finale. Les paiements anticipés vente doivent être enregistrés dans un compte passif jusqu'à la livraison des articles. Les acomptes achat doivent être enregistrés dans un compte immobilisations jusqu'à la réception des articles. En outre, vous devez configurer un compte du grand livre séparé pour chaque identificateur TVA.  

[!INCLUDE[local-func-setup-link](includes/local-func-setup-link.md)]

## <a name="to-add-prepayment-accounts-to-the-general-posting-setup"></a>Ajouter des comptes paiement anticipé à la configuration de report générale  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration du report général**, puis sélectionnez le lien associé.
2. Sur la page **Configuration du report général**, vous devez renseigner les champs suivants :  

    - **Compte de paiements anticipés de vente**  
    - **Compte de paiements anticipés d'achat**  

Si vous n'avez pas encore configuré de comptes GL pour les paiements anticipés, vous pouvez le faire sur la page **Liste compte GL**.  

## <a name="to-set-up-number-series-for-prepayment-documents"></a>Configurer des séries de numéros pour des documents paiement anticipé  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration ventes et à recevoir**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes et à recevoir**, renseignez les champs suivants :  

   - **N° factures pour paiement anticipé reporté**
   - **N° notes de crédit pour paiement anticipé reporté**

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration achats et à payer**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes et à recevoir**, renseignez les champs suivants :

    - **N° factures pour paiement anticipé reporté**
    - **N° notes de crédit pour paiement anticipé reporté**

> [!NOTE]  
>  Vous pouvez utiliser les mêmes séries de numéros pour des factures paiement anticipé et des factures normales, ou utiliser des séries de numéros différentes. Si vous utilisez des souches différentes, elles ne doivent pas se chevaucher car vous ne pouvez pas avoir des numéros identiques dans les deux souches.  

## <a name="to-set-up-prepayment-percentages-for-items-customers-and-vendors"></a>Pour configurer des pourcentages de paiement anticipé pour des articles, des clients et des fournisseurs  
Pour un article, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les clients, pour un client spécifique ou pour un groupe prix client.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.
2. Sélectionnez un article, puis cliquez sur l'action **Pourcentages paiement anticipé**.  
3. Sur la page **Pourcentages paiement anticipé vente**, renseignez autant de champs que nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pour un client ou un fournisseur, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les articles et tous les types de lignes vente. Vous entrez cette valeur dans la fiche client ou fournisseur.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Clients**, puis sélectionnez le lien associé.
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
[Calculer la taxe sur les biens et services pour les paiements anticipés en Australie](LocalFunctionality/Australia/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Calculer la taxe sur les biens et services pour les paiements anticipés en Nouvelle-Zélande](LocalFunctionality/NewZealand/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Familiarisation avec les écritures comptables et les COA](finance-general-ledger.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
