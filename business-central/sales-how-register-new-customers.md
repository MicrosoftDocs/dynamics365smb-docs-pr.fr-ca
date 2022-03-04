---
title: Enregistrer de nouveaux clients en créant une fiche client (contient une vidéo)
description: Décrit comment créer une fiche client pour enregistrer des informations sur chaque nouveau client ou client auquel vous vendez.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: client, customer, credit
ms.search.form: 7, 21, 22, 33, 42, 43, 367, 368, 369, 461, 512, 785, 1330, 1380, 1381, 1382, 1627, 2107, 7177, 9080, 9081, 9084, 9301, 9305
ms.date: 09/24/2021
ms.author: edupont
ms.openlocfilehash: f1b37df909e482f9f4102eab70ce82cdef999a12
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8137013"
---
# <a name="register-new-customers"></a>Enregistrer de nouveaux clients

Les clients sont l'origine de vos revenus. Chaque client auquel vous vendez un élément doit être enregistré en tant que fiche client. Les fiches client contiennent les informations nécessaires à la vente de biens au client. Pour plus d'informations, voir [Facturer des ventes](sales-how-invoice-sales.md) et [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).  

Avant de pouvoir enregistrer de nouveaux clients, vous devez configurer divers codes vente que vous pouvez sélectionner lorsque vous renseignez les fiches client. Pour plus d'informations, reportez-vous à [Définition des ventes](sales-setup-sales.md).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3PZsM]

## <a name="adding-new-customers"></a>Ajout de nouveaux clients
Vous pouvez ajouter de nouveaux clients manuellement, en remplissant les champs sur la page **Fiche client**, ou vous pouvez utiliser des modèles contenant des informations prédéfinies. Par exemple, vous pouvez créer des modèles pour différents types de profils de client. L’utilisation de modèles permet de gagner du temps lors de l’ajout de nouveaux clients et permet de garantir que les informations sont correctes à chaque fois. Si vous créez des modèles pour plusieurs types de client, vous pouvez choisir le modèle à utiliser lorsque vous ajoutez un client. Si vous ne créez qu’un seul modèle, il sera utilisé pour tous les nouveaux clients. Après avoir créé un modèle, vous pouvez utiliser l’action **Appliquer le modèle** pour l’appliquer à un ou plusieurs client sélectionnés. Pour créer un modèle, vous remplissez les informations que vous souhaitez réutiliser sur la page Fiche client, puis l’enregistrez en tant que modèle. Pour plus d’informations, consultez [Pour enregistrer la fiche client en tant que modèle](sales-how-register-new-customers.md#to-save-the-customer-card-as-a-template)

> [!TIP]
> Il peut être utile de personnaliser la page **Modèle de client** lorsque vous créez un modèle. Par exemple, vous pouvez ajouter le champ **Limite de crédit** à un modèle. Pour plus d’informations, voir [Personnaliser votre espace de travail](/dynamics365/business-central/ui-personalization-user#to-start-personalizing-a-page-through-the-personalizing-banner).

Vous pouvez également créer un client à partir d'un contact. Pour plus d’informations, reportez-vous à [Pour créer un contact comme client, fournisseur, employé ou compte bancaire à partir d'un contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact).  

### <a name="to-create-a-new-customer-card"></a>Pour créer une fiche client

[!INCLUDE[create_new_customer](includes/create_new_customer.md)]

L'action **Prix et escomptes** fournit des options pour gérer des prix spéciaux ou des escomptes pour le client lorsqu’une commande répond à certains critères. Exemples de critères : moment où ils achètent un certain article, commandent une quantité minimale ou achètent avant une date, par exemple à la fin d’une promotion. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).

Le client est désormais enregistré, et la fiche client est prête à être utilisée sur les documents vente.

Si vous souhaitez utiliser cette fiche client comme modèle lorsque vous créez de nouvelles fiches client, enregistrez-la comme modèle. Pour plus d'informations, reportez-vous à la section suivantes.  

### <a name="to-save-the-customer-card-as-a-template"></a>Pour enregistrer la fiche client en tant que modèle

1. Sur la page **Fiche client**, sélectionnez l'action **Sauvegarder comme modèle**. La page **Modèle client** s'ouvre et affiche la fiche client comme modèle.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour réutiliser les axes analytiques dans les modèles, sélectionnez l'action **Axes analytiques**. La page **Modèles dimension** s'ouvre et affiche tous les codes dimension qui sont configurés pour le client.
4. Modifiez ou entrez les codes dimension s'appliquant aux nouvelles fiches client créées à l'aide du modèle.  
5. Lorsque vous avez terminé le nouveau modèle client, cliquez sur le bouton **OK**.

Le modèle client est ajouté à la liste des modèles client. Vous pouvez ainsi l'utiliser pour créer des fiches client.

## <a name="deleting-customer-cards"></a>Suppression de fiches client

Si vous avez reporté une transaction pour un client, vous ne pouvez pas supprimer la fiche, car les écritures peuvent être nécessaires pour l'audit. Pour supprimer des fiches client avec des écritures, contactez votre partenaire Microsoft pour le faire via le code.  

## <a name="managing-credit-limits"></a>Gestion des limites de crédit

Les limites de crédit, les soldes échus et les modalités de paiement permettent à [!INCLUDE [prod_short](includes/prod_short.md)] d’émettre une alerte limite de crédit ou solde échu lorsque vous entrez un document de vente.  De plus, les options modalités de rappel et modalités de frais financiers vous permettent de facturer des intérêts et des frais supplémentaires.  

Le champ **Limite de crédit** sur une fiche client spécifie le montant maximal de dépassement du solde de paiement que vous autorisez le client à dépasser avant que des alertes ne soient émises. Ensuite, lorsque vous saisissez des informations dans des journaux, des devis, des commandes et des factures, [!INCLUDE [prod_short](includes/prod_short.md)] teste l’en-tête vente et les lignes vente individuelles pour voir si la limite de crédit a été dépassée.

Vous pouvez reporter même si la limite de crédit a été dépassée. Si vous laissez le champ blanc, il n’y a pas de limite de crédit pour ce client.  

Vous pouvez choisir de ne pas afficher les alertes vous indiquant que la limite de crédit du client a été dépassée et vous pouvez spécifier les types d’avertissement que vous souhaitez voir.

### <a name="to-specify-credit-limit-warnings"></a>Pour spécifier les alertes limite de crédit

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration ventes & à recevoir**, puis choisissez le lien associé.

2. Sur le raccourci **Général**, dans le champ **Alertes crédit**, choisissez l’option appropriée comme décrit dans le tableau suivant :

    |Option| Description|
    |------|------------|
    |**Toutes les alertes**| Le programme contrôle à la fois les champs **Limite de crédit** et **Solde dû** de la fiche client, et affiche une alerte si le client a dépassé sa limite de crédit ou si le client a un solde échu.|
    |**Limite de crédit**|Le programme compare la valeur du champ **Limite de crédit** de la fiche client et le solde du client, et affiche une alerte si le solde du client dépasse ce montant.|
    |**Solde échu**|Le champ **Solde dû** de la fiche client est contrôlé et une alerte s’affiche si le client a un solde échu.|
    |**Aucune alerte**|Aucune alerte n’est affichée sur l’état du client.|

## <a name="see-also"></a>Voir aussi

[Définition des modes de règlement](finance-payment-methods.md)  
[Fusionner l'enregistrement des doublons](sales-how-merge-duplicate-records.md)  
[Création des séries de numéros](ui-create-number-series.md)  
[Vente](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
