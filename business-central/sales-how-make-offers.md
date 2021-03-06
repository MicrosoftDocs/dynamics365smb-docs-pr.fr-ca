---
title: Faire une offre vente à un client
description: Décrit comment créer une offre vente offrent ou un document de demande de proposition pour enregistrer votre offre à un client pour vendre des produits dans certaines conditions.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: rfq
ms.date: 05/27/2021
ms.author: edupont
ms.openlocfilehash: a538b7099521b10227bf5aeaefad0a9c60971068
ms.sourcegitcommit: f9a190933eadf4608f591e2f1b04c69f1e5c0dc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115550"
---
# <a name="make-sales-quotes"></a>Créer des devis

Vous créez un devis pour enregistrer votre proposition à un client pour vendre certains biens selon certaines méthodes de livraison et modalités de paiement. Vous pouvez envoyer un devis au client pour communiquer la proposition. Vous pouvez envoyer par courriel le document en pièce jointe au format PDF. Vous pouvez également faire en sorte que le corps du message soit prérempli avec un résumé du devis. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).

Lorsque vous négociez avec le client, vous pouvez modifier et renvoyer autant de devis que nécessaire. Lorsque le client accepte le devis, vous convertissez le devis en facture vente ou en document de vente dans lequel vous traitez la vente. Pour plus d'informations, voir [Facturer des ventes](sales-how-invoice-sales.md) ou [Vendre des produits](sales-how-sell-products.md).

Vous pouvez remplir les champs relatifs au client sur le devis de deux façons selon que le client est déjà enregistré ou non. Reportez-vous aux étapes 2 et 3 de la procédure ci-dessous.

## <a name="to-create-a-sales-quote"></a>Pour créer un devis

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Devis**, puis sélectionnez le lien associé.
2. Dans le champ **Client**, entrez le nom d'un client existant.

   D'autres champs de la page **Devis** contiennent des informations standard sur le client sélectionné.  

    [!INCLUDE [sales-create-customer](includes/sales-create-customer.md)]

    Plusieurs champs du devis sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.  
3. Renseignez les champs restants de la page **Devis**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Vous êtes maintenant prêt à renseigner les lignes document de vente pour les produits que vous vendez au client ou pour toute transaction avec le client que vous souhaitez enregistrer dans un compte du grand livre.  

    Si vous avez défini des lignes vente récurrentes pour le client, tel qu'un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l'intermédiaire de l'action **Extraire les lignes vente récurrentes**.  

4. Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à valider pour le client avec la ligne vente.
5. Dans le champ **N°**, sélectionnez un enregistrement à valider en fonction de la valeur du champ **Type**.

    Laissez le champ **N°** vide dans les cas suivants :
    - Si la ligne est destinée à un commentaire. Saisissez le commentaire dans le champ **Description**.
    - Si la ligne est destinée à un article de catalogue. Sélectionnez l'action **Sélectionner articles de catalogue**. Pour en savoir plus, voir [Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md).

6. Dans le champ **Quantité**, entrez le nombre d'unités du produit, de frais ou de la transaction que la ligne enregistre pour le client.

    > [!NOTE]  
    >  Si l'article est de type **Service** ou si le champ **Type** contient **Ressource**, la quantité est une unité de temps, par exemple heures, comme indiqué dans le champ **Code unité de mesure** de la ligne. Pour plus d'informations, reportez-vous à [Configuration d'unités de mesure article](inventory-how-setup-units-of-measure.md)

    La valeur du champ **Montant ligne** est calculée comme suit : *Prix unitaire* x *Quantité*.  

    Le prix et les montants ligne sont affichés avec ou sans la taxe de vente en fonction de la valeur que vous avez sélectionnée dans le champ **Prix incluant les taxes** de la fiche client.  
7. Si vous souhaitez accorder une remise, saisissez un pourcentage dans le champ **% remise ligne**. La valeur du champ **Montant ligne** est mise à jour en conséquence.  

    Si des prix article spéciaux sont définis sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne vente sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).  
8. Répétez les étapes 4 à 7 pour chaque produit que vous souhaitez proposer au client.

    Les totaux sous les lignes sont calculés automatiquement au fur et à mesure que vous créez ou modifiez des lignes.  
9. Dans le champ **Montant remise facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.

    Si vous avez défini des remises facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% remise facture** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant remise facture sans TVA**. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).

    > [!TIP]
    > Pour que **Devis valide jusqu'à** soit renseigné automatiquement avec un certain nombre de jours après la création du devis, vous pouvez renseigner le champ **Calcul de validité du devis** sur la page **Ventes**.

10. Lorsque les lignes devis sont renseignées, sélectionnez l'action **Envoyer par e-mail**.
11. Sur la page **Envoyer courriel**, renseignez les champs restants et examinez le devis intégré. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).
12. Si le client accepte le devis, sélectionnez l'action **Établir facture** ou **Créer commande**.

Le devis est supprimé de la base de données. Une facture vente ou un document de vente basé sur les informations du devis et dans lequel vous pouvez traiter la vente est créé. Dans le champ **N° devis** de la facture vente ou du document de vente, vous pouvez visualiser le numéro du devis à partir duquel elle a été réalisée. Pour plus d'informations, voir [Facturer des ventes](sales-how-invoice-sales.md) ou [Vendre des produits](sales-how-sell-products.md).  

## <a name="external-document-number"></a>Numéro de document externe

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## <a name="see-also"></a>Voir aussi

[Vente](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]