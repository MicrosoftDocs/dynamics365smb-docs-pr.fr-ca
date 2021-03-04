---
title: Créer un document de vente et vendre des produits | Microsoft Docs
description: Décrit comment créer un document de vente pour enregistrer votre entente avec un client pour vendre ou commercialiser des produits à des conditions spécifiques.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: f6d913681967bbe609a03d7d6a2736e9c86b4ce0
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4758177"
---
# <a name="sell-products"></a>Vendre des produits

Vous créez un document de vente ou une facture vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines méthodes de livraison et de paiement.

> [!NOTE]  
> Utilisez des documents de vente si votre processus de vente requiert que vous livriez des parties d'une quantité de commande, par exemple, si la quantité totale est pas disponible d'un coup. Si vous utilisez des factures vente, alors [!INCLUDE [prod_short](includes/prod_short.md)] suppose que vous livrez la quantité complète lorsque vous reportez la facture. Si vous commercialisez des articles en les livrant directement du fournisseur au client, vous devez également utiliser les documents de vente. Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md). Pour tous les autres aspects, les commandes vente fonctionnent de la même manière que les factures vente. Pour plus d'informations, reportez-vous à [Facturer des ventes](sales-how-invoice-sales.md).

Vous pouvez négocier avec le client en créant d'abord un devis, que vous pouvez convertir en document de vente lorsque vous êtes d'accord sur la vente. Pour plus d'informations, voir [Créer des devis](sales-how-make-offers.md).

Une fois que le client a confirmé l'entente, par exemple après une procédure de devis, vous pouvez envoyer une confirmation de commande pour enregistrer votre obligation de fournir les produits comme convenu.

Lorsque vous livrez les produits, entièrement ou partiellement, vous reportez le document de vente comme étant livré ou livré et facturé pour créer les écritures article et client associées dans votre système. Lorsque vous reportez le document de vente, vous pouvez également envoyer par courriel le document en pièce jointe au format PDF. Vous pouvez faire en sorte que le corps du message soit prérempli avec un résumé des informations de commande et de paiement, par exemple un lien vers Paypal. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).

Dans les environnements d'entreprise où le client paie un certain temps après la livraison, conformément aux conditions de paiement, une facture vente reportée reste ouverte (impayée) jusqu'à ce que le département Comptabilité client vérifie la réception du paiement et affecte le paiement à la facture vente reportée. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

Dans les environnements d'entreprise où le client paie immédiatement, par exemple par PayPal ou en espèces, le paiement est enregistré immédiatement lorsque vous reportez le document de vente comme facturé, c'est-à-dire la facture vente reportée est fermée comme entièrement affectée. Vous sélectionnez la méthode appropriée dans le champ **Code mode de paiement** du document de vente. Voir l'étape 8. Pour les paiements électroniques, tels que PayPal, vous devez également renseigner le champ **Service de paiement**. Pour plus d'informations, voir [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).

Vous pouvez même créer des commandes à paiement direct pour les clients non enregistrés en configurant une fiche « client en espèces », vers laquelle vous pointez sur le document de vente. Pour plus d'informations, reportez-vous à [Configurer des clients effectuant un achat au comptoir](finance-how-to-set-up-cash-customers.md).

Vous pouvez facilement corriger ou annuler une facture vente reportée qui résulte d'un document de vente avant qu'elle soit payée. Cela est utile si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande. Pour plus d'informations, voir [Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md). Si la facture vente reportée est payée, vous devez créer une note de crédit vente pour inverser la vente. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).

La fiche article peut être de type **Inventaire**, **Service** et **Hors inventaire** pour spécifier si l'article est une unité d'inventaire physique, une unité de temps de travail ou une unité physique qui n'est pas conservée dans l'inventaire. Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md). Le processus de document de vente est identique pour les trois types d'article.

Vous pouvez remplir les champs relatifs au client sur la document de vente de deux façons selon que le client est déjà enregistré ou non. Reportez-vous aux étapes 2 et 3 de la procédure ci-dessous.

## <a name="to-create-a-sales-order"></a>Pour créer un document de vente
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Dans le champ **Client**, entrez le nom d'un client existant.

    D'autres champs de la page **Document de vente** sont désormais renseignés avec les informations standard sur le client sélectionné. Si le client n'est pas enregistré, procédez comme suit :
3. Dans le champ **Client**, entrez le nom du nouveau client.
4. Dans la boîte de dialogue d'enregistrement du nouveau client, cliquez sur le bouton **Oui**.
5. Sur la page **Sélectionnez un modèle pour un nouveau client**, sélectionnez un modèle sur lequel baser la nouvelle fiche client, puis cliquez sur le bouton **OK**.

    Une nouvelle fiche client préremplie avec les informations sur le modèle client sélectionné s'ouvre. Le champ **Nom** est prérempli avec le nom du nouveau client que vous avez saisi sur le document de vente.
6. Renseignez les autres champs de la fiche client. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  
7. Lorsque vous avez terminé la fiche client, cliquez sur le bouton **OK** pour revenir à la page **Document de vente**.

    Plusieurs champs du document de vente sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.
8. Renseignez les champs restants de la page **Document de vente**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > Si vous autorisez le client à payer immédiatement, par exemple, par carte de crédit ou par PayPal, renseignez le champ **Code mode de règlement**. Le paiement est ensuite enregistré dès que vous reportez le document de vente comme facturé. Si vous sélectionnez ESPÈCES, le paiement est enregistré dans un compte de contrepartie spécifié.

    Vous êtes maintenant prêt à renseigner les lignes document de vente avec les articles en inventaire ou les services que vous voulez vendre au client.

    Si vous avez défini des lignes vente récurrentes pour le client, tel qu'un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l'intermédiaire de l'action **Extraire les lignes vente récurrentes**.
9. Dans le raccourci **Lignes**, dans le champ **Article**, entrez le numéro d'un article en stock ou d'un service.  
10. Dans le champ **Quantité**, saisissez le nombre d'articles à vendre.

    > [!NOTE]  
    >   Pour les articles de type Service, la quantité est une unité de temps, telle que les heures, comme indiqué dans le champ **Code unité de la ligne**.

    Le champ **Montant ligne** est mis à jour pour indiquer la valeur du champ **Prix unitaire** multipliée par la valeur du champ **Quantité**.

    Le prix et les montants ligne sont affichés avec ou sans la Sales Tax en fonction de la valeur que vous avez sélectionné dans le champ **Prix incluant les taxes** de la fiche client.
11. Dans le champ **% remise ligne**, saisissez un pourcentage si vous souhaitez accorder au client une remise sur le produit. La valeur du champ **Montant ligne** est mise à jour en conséquence.

    Si vous avez défini des prix article spéciaux sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne devis sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).
12. Pour ajouter un commentaire sur la ligne devis que le client peut afficher dans le devis vente imprimé, saisissez un texte dans le champ **Description** sur une ligne vierge.  
13. Répétez les étapes 9 à 12 pour chaque article que vous souhaitez à vendre au client.

    Les totaux sous les lignes sont calculés automatiquement au fur et à mesure que vous créez ou modifiez des lignes.
14. Une nouvelle fiche client affiche des informations sur le modèle client sélectionné. Renseignez les champs restants. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  
15. Lorsque vous avez terminé la fiche client, cliquez sur le bouton **OK** pour revenir à la page **Document de vente**.

    Plusieurs champs du document de vente sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.
16. Renseignez les champs restants de la page **Document de vente**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Vous êtes maintenant prêt à renseigner les lignes document de vente pour les produits que vous vendez au client ou pour toute transaction avec le client que vous souhaitez enregistrer dans un compte du grand livre.   

    Si vous avez défini des lignes vente récurrentes pour le client, tel qu'un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l'intermédiaire de l'action **Extraire les lignes vente récurrentes**.  
17. Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à valider pour le client avec la ligne vente.

18. Dans le champ **N°**, sélectionnez un enregistrement à valider en fonction de la valeur du champ **Type**.

    Laissez le champ **N°** vide dans les cas suivants :

    * Si la ligne est destinée à un commentaire. Saisissez le commentaire dans le champ **Description**.
    * Si la ligne est destinée à un article de catalogue. Sélectionnez l'action **Sélectionner articles de catalogue**. Pour en savoir plus, voir [Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md).

19. Dans le champ **Quantité**, entrez le nombre d'unités du produit, de frais ou de la transaction que la ligne enregistre pour le client.  

    > [!NOTE]  
    > Si l'article est de type **Service** ou si le champ **Type** contient **Ressource**, la quantité est une unité de temps, par exemple heures, comme indiqué dans le champ **Code unité de mesure** de la ligne. Pour plus d'informations, voir [Configurer des unités de mesure article](inventory-how-setup-units-of-measure.md).

    La valeur du champ **Montant ligne** est calculée comme suit : *Prix unitaire* x *Quantité*.  

    Le prix et les montants ligne sont affichés avec ou sans la taxe de vente en fonction de la valeur que vous avez sélectionnée dans le champ **Prix incluant les taxes** de la fiche client.  
20. Si vous souhaitez accorder une remise, saisissez un pourcentage dans le champ **% remise ligne**. La valeur du champ **Montant ligne** est mise à jour en conséquence.  

    Si des prix article spéciaux sont définis sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne vente sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).  
21. Répétez les étapes 9 à 12 pour chaque produit ou frais que vous souhaitez vendre au client.  

    Les champs totaux sous les lignes sont automatiquement mis à jour lorsque vous créez ou modifiez des lignes pour afficher les montants qui seront reportés dans les livres.

    > [!NOTE]
    > Dans de très rares cas, les montants reportés peuvent différer de ce qui est affiché dans les champs des totaux. Cela est généralement dû aux calculs d'arrondissement par rapport à la TVA ou à la taxe de vente.<br /><br />Pour vérifier les montants qui seront réellement reportés, vous pouvez utiliser la page **Statistiques**, qui tient compte des calculs d'arrondissement. Aussi, si vous choisissez l'action **Libérer**, les champs de totaux seront mis à jour pour inclure les calculs d’arrondissement.  
22. Dans le champ **Montant d'escompte de la facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.

    Si vous avez défini des remises facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% remise facture** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant remise facture sans TVA**. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).
23. Pour expédier seulement une partie de la quantité commandée, entrez la quantité dans le champ **Qté à expédier**. La valeur est copiée dans le champ **Qté à facturer**.
24. Pour facturer seulement une partie de la quantité expédiée, entrez la quantité dans le champ **Qté à facturer**. La quantité doit être inférieure à la valeur du champ **Qté à expédier**.   
25. Lorsque les lignes commande vente sont renseignées, sélectionnez l'action **Valider et envoyer**.

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode de réception de documents par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).

Les écritures article et client associées sont à présent créées dans votre système, et le document de vente est sorti en tant que document au format PDF. Lorsque le document de vente est entièrement reporté, il est supprimé de la liste des documents de vente et remplacé par de nouveaux documents dans la liste des factures vente reportées et la liste des livraisons vente reportées.

## <a name="see-also"></a>Voir aussi
[Vente](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Imprimer la liste des prélèvements](sales-how-print-picking-list.md)  
[Inventaire](inventory-manage-inventory.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]