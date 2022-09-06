---
title: Configuration et facturation de paiements anticipés
description: Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 12/03/2021
ms.author: edupont
ms.openlocfilehash: 1c26882670321a3a2957302413f6f7ebd11a1f6d
ms.sourcegitcommit: 38b1272947f64a473de910fe81ad97db5213e6c3
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/29/2022
ms.locfileid: "9362317"
---
# <a name="walkthrough-setting-up-and-invoicing-sales-prepayments"></a>Procédure pas à pas : configuration et facturation de paiements anticipés vente

Cette procédure pas à pas vous guide tout au long du processus de configuration et d’utilisation des paiements anticipés dans [!INCLUDE [prod_short](includes/prod_short.md)]. [!INCLUDE [prepayment_def](includes/prepayment_def.md)]

[!INCLUDE [prepayment_req](includes/prepayment_req.md)]

Par exemple, vous pouvez également envoyer plus de factures paiement anticipé si davantage d’articles supplémentaires sont ajoutés à la commande.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  

Cette procédure pas à pas présente les scénarios suivants :  

- Configuration des paiements anticipés  
- Création d'une commande nécessitant un paiement anticipé  
- Création d'une facture de paiement anticipé  
- Correction des conditions de paiement anticipé sur une commande  
- Affectation de paiements anticipés à une commande  
- Facturation du montant final sur une commande faisant l'objet d'un paiement anticipé.  

### <a name="roles"></a>Rôles

Cette procédure pas à pas inclut les tâches correspondant aux rôles suivants :  

- responsable de la comptabilité (Phyllis) ;  
- préparatrice de commandes (Susan) ;  
- administrateur Ventes (Arnie).  

## <a name="story"></a>Scénario

 Phyllis est responsable de la comptabilité. Elle décide des clients qui doivent payer un acompte avant que les articles soient produits ou livrés. Phyllis configure [!INCLUDE[prod_short](includes/prod_short.md)] de façon à calculer automatiquement les acomptes.  

 Susan est préparatrice de documents de vente. Lorsque le client appelle pour passer une commande, elle entre la commande dans le système pendant que le client est au téléphone. Elle peut ainsi vérifier immédiatement les prix et les modalités de paiement avec le client et ajuster la commande pendant qu’elle négocie avec le client.  

 Arnie travaille dans le département Comptabilité client où sa fonction consiste à reporter les factures et les paiements.  

 Dans ce scénario, Phyllis configure les conditions de paiement anticipé pour le client Selangorian, en se basant sur leurs antécédents en matière de crédit. Elle donne à Susan des instructions sur le traitement de leurs commandes.  

 Lorsque le client appelle, Susan négocie avec lui jusqu'à parvenir à une entente. Elle peut alors choisir de calculer le paiement anticipé de différentes manières.  

 Après que Susan a envoyé la facture paiement anticipé, le client commande un article supplémentaire. Susan met à jour la commande et crée une seconde facture paiement anticipé.  

 Arnie enregistre le paiement du client et l'affecte à la facture, puis envoie la facture finale.  

## <a name="set-up-prepayments"></a>Configuration des acomptes

Phyllis configure le système afin qu'il gère les acomptes des clients.  

- Elle décide d'utiliser la même série de numéros pour les paiements anticipés et la facturation vente.  
- Elle configure l'application pour qu'elle vérifie si des paiements anticipés sont requis avant la facturation finale d'une commande.  
- Elle configure les valeurs par défaut pour un pourcentage de paiement anticipé requis pour certains articles et clients.  

Les procédures suivantes décrivent le mode d'exécution des tâches de Phyllis :  

### <a name="to-set-up-number-series-for-prepayments"></a>Pour configurer des séries de numéros pour les paiements anticipés

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration ventes & à recevoir**, puis choisissez le lien associé.  
2. Sur la page **Configuration ventes & à recevoir**, affichez le raccourci **Série de numéros**.  
3. Vérifiez que la série de numéros des factures paiement anticipé reportées dans le champ **N° factures pour paiement anticipé reporté** est identique à celle des factures vente reportées (**N° facture reportée**) et que la série de numéros des notes de crédit pour paiement anticipé reporté (**N° notes de crédit pour paiement anticipé reporté**) est identique à celle des notes de crédit reportées (**N° note de crédit reportée**).  

### <a name="to-block-shipments-for-unpaid-prepayment"></a>Pour bloquer les livraisons pour un paiement anticipé impayé

1. Sur la page **Configuration ventes & à recevoir**, sur le raccourci **Général**, cochez la case **Vérifier les acomptes lors du report**.

Vous ne pouvez pas livrer ou facturer une commande dont le montant de paiement anticipé n’est pas réglé.  

Par défaut, Phyllis requiert que le client 20000 soit facturé avec un acompte de 30 % sur toutes les commandes. Pour cela, elle entre un pourcentage de paiement anticipé par défaut dans la fiche client.  

Phyllis requiert que tous les clients soient facturés avec un acompte de 20 % pour l’article 1896-S. Le client 20000 a un mauvais historique des paiements, c’est pourquoi elle requiert un paiement anticipé de 40 % pour ce client pour l’article 1896-S. La procédure suivante présente le mode de configuration des pourcentages de paiement anticipé par défaut.  

### <a name="to-assign-default-prepayment-percentages-to-customers-and-items"></a>Pour affecter des pourcentages de paiement anticipé par défaut aux clients et aux articles

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.  
2. Ouvrez la fiche pour le client 20000 (Trey Research).
3. Sur le raccourci **Paiements**, dans le champ **% paiement anticipé**, entrez **30**.  
4. Choisissez l’action **Associé**, sélectionnez l’élément de menu **Ventes**, puis choisissez l’élément de menu **Pourcentages paiement anticipé**.  
5. Renseignez deux lignes de la page **Pourcentages paiement anticipé vente**, comme suit.  

    |**Type vente**|**Code vente**|**N° article**|**% acompte**|  
    |--------------------|--------------------|------------------|----------------------|  
    |**Client**|**20000**|**1896-S**|**40**|
    |**Client**|**20000**|**1900-S**|**30**|  
    
    > [!TIP]
    > En fonction de votre pays/région, vous devez également spécifier un code groupe fiscal sur le raccourci **Coûts et report** pour l’article 1896-S. Lorsque vous utilisez la compagnie de démonstration, ce champ est déjà défini.

6. Fermez toutes les pages.  

### <a name="to-specify-an-account-for-sales-prepayments-in-general-posting-setup"></a>Pour spécifier un compte pour les paiements anticipés vente dans la configuration de report générale

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du report général**, puis choisissez le lien associé.  
2. Sélectionnez la ligne où le champ **Groupe de report de marché** est défini sur **NATIONAL**, et où le champ **Groupe de report de produit** est défini sur **DÉTAIL**.  
3. Dans le champ **Compte paiements anticipés vente**, indiquez le compte approprié. Votre sélection est automatiquement enregistrée.  

> [!TIP]
> Si vous ne pouvez pas voir le champ de la page **Configuration du report général**, utilisez la barre de défilement horizontale au bas de la page pour faire défiler l’affichage vers la droite.  

## <a name="create-an-order-that-requires-a-prepayment"></a>Création d’une commande nécessitant un paiement anticipé

 Dans le scénario suivant, Susan, la préparatrice des commandes, crée une commande en discutant avec le client. Les articles commandés par le client nécessitent un paiement anticipé. De plus, le client a effectué des paiements en retard dans le passé. Susan a reçu l’ordre de demander un montant fixe de **800** comme paiement anticipé sur la commande.  

Le client demande à payer 35 %. Susan accepte et modifie la commande en conséquence.  

Susan crée la facture paiement anticipé et l'envoie au client.  

### <a name="to-create-a-sales-order-with-a-prepayment"></a>Pour créer un document de vente avec paiement anticipé

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Nom du client**, choisissez **Trey Research**.  
4. Fermez l’avertissement de solde échu qui s’affiche.  
5. Renseignez deux lignes vente avec les informations suivantes.  

    |**Type**|**N°**|**Quantité**|  
    |--------------|-------------|------------------|  
    |**Article**|**1896-S**|**1**|  
    |**Article**|**1900-S**|**1**|

    Par défaut, les champs du paiement anticipé sont masqués. Pour afficher les champs vous devez personnaliser la page. Pour plus d’informations, consultez [Commencer à personnaliser une page au moyen de la bannière Personnalisation](ui-personalization-user.md#to-start-personalizing-a-page-through-the-personalizing-banner).

6. Vérifiez que le champ **% paiement anticipé** de la ligne correspondant à l’article **1900-S** a pour valeur **30**. La valeur par défaut a été prise dans l'en-tête vente, qui a été renseigné à partir de la fiche client.  

    Le champ **% paiement anticipé** de la ligne correspondant à l’article **1896-S** a pour valeur **40**. 40 désigne le pourcentage que vous avez entré sur la page **Pourcentages paiement anticipé vente** pour l’article **1896-S** et le client **20000**.  

    Pour plus d'informations, reportez\-vous à [Configuration des acomptes](finance-set-up-prepayments.md).  
7. Dans l’action **Ordre**, choisissez **Statistiques**.  
8. Sur le raccourci **Paiement anticipé**, le champ **Montant paiement anticipé HT** indique **458,16**. Si vous créez une facture paiement anticipé pour la commande dès maintenant, 458,16 est le montant qui s’affiche sur la facture.  

    Dans ce scénario, Susan a reçu des instructions lui demandant de proposer un paiement anticipé total de **800** pour la commande.  

    > [!IMPORTANT]  
    >  En fonction de votre pays/région, l'étape suivante peut ne pas s'appliquer.  
9. Remplacez le montant du champ **Montant paiement anticipé HT** par **800**, puis fermez la page.  
10. Consultez le champ **% paiement anticipé** des lignes vente : le montant a été recalculé, il est désormais de **67,02438** et **67,02282**.  

     Le nouveau calcul inclut toutes les lignes dont le pourcentage de paiement anticipé est supérieur à 0.  

     À présent, le client demande si le pourcentage du paiement anticipé peut être fixé à 35 %. Le chef de Susan accepte la modification.
11. Sur la page **Document de vente**, sur le raccourci **Paiement anticipé**, dans le champ **% paiement anticipé**, entrez **35**.  
12. Dans l'avertissement qui s'affiche, cliquez sur le bouton **Oui** . Un taux de 35 % sera affecté comme pourcentage du paiement de l'ensemble de la commande.  
13. Vérifiez que les lignes ont été mises à jour en conséquence.  

## <a name="create-a-prepayment-invoice"></a>Créer une facture paiement anticipé

Après avoir entré la valeur de paiement anticipé correcte sur la commande, Susan crée la facture paiement anticipé et l'envoie au client.  

### <a name="to-create-a-prepayment-invoice"></a>Pour créer une facture paiement anticipé

1. Sur la page **Document de vente**, choisissez **Actions**, puis **Report**, puis **Paiement anticipé**, et sélectionnez ensuite **Reporter et imprimer facture paiement anticipé**.
2. Choisissez le bouton **Oui** pour reporter la facture.  

> [!NOTE]  
> Susan doit maintenant envoyer la facture au client.  

## <a name="create-an-additional-prepayment-invoice"></a>Créer une facture paiement anticipé supplémentaire

Le jour suivant, le client appelle Susan et modifie sa commande. Il souhaite deux exemplaires de l’article 1896-S. Susan rouvre la commande et la met à jour. Susan crée ensuite une seconde facture paiement anticipé pour la commande et l’envoie au client.  

### <a name="to-create-an-additional-prepayment-invoice"></a>Pour créer une facture paiement anticipé supplémentaire

1. Sur la page **Document de vente**, choisissez l’action **Libérer**, puis **Rouvrir**  
2. Sur la ligne de l’article **1896-S**, dans le champ **Quantité**, entrez **2**.  

    Dans l’action **Ordre**, choisissez **Statistiques**. Le champ **Montant paiement anticipé HT** indique à présent **768,04** et le champ **Montant fact. paiement anticipé HT** indique **417,76**. Ces valeurs indiquent qu’il existe un montant de paiement anticipé supplémentaire qui n’a pas encore été facturé.  
3. Pour reporter une facture pour le montant de paiement anticipé supplémentaire, choisissez **Actions**, puis **Report**, puis **Paiement anticipé**, puis **Reporter et imprimer facture paiement anticipé**
4. Choisissez le bouton **Oui** pour reporter la facture.  

## <a name="apply-the-prepayments"></a>Affecter les paiements anticipés

Le client paie le montant du paiement anticipé. Arnie, du service comptabilité, enregistre le paiement et l'affecte aux factures de paiement anticipé.  

### <a name="to-apply-a-payment-to-the-prepayment-invoices"></a>Pour affecter un paiement aux factures paiement anticipé

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux des encaissements**, puis choisissez le lien associé.  
2. Renseignez une ligne journal avec les informations suivantes.  

    |Nom du champ|Entrée|  
    |----------------|-----------|  
    |**Type document**|**Règlement**|  
    |**Type compte**|**Client**|  
    |**N° compte**|**20000**|  
3. Choisissez l’action **Traitement**, puis **Affecter écritures**.  
4. Sur la page **Affecter écritures client**, sélectionnez la première facture paiement anticipé, puis, sélectionnez l’action **Traitement** et enfin l’action **Définir Code référence**.  
5. Répétez l'étape précédente pour le deuxième paiement anticipé.  
6. Choisissez le bouton **OK**.  

    Les champs **Montant** sont maintenant renseignés avec la somme des deux factures paiement anticipé.  

7. Pour reporter le journal, choisissez l’action **Reporter/Imprimer**, puis sélectionnez **Reporter**.
8. Cliquez sur le bouton **Oui**.

## <a name="invoice-the-remaining-amount"></a>Facturer le montant ouvert

Arnie a été informé que les articles de la commande ont été livrés et que la commande est prête pour facturation. Il crée donc la facture correspondante.  

### <a name="to-invoice-the-remaining-amount"></a>Pour facturer le montant ouvert

1. Ouvrez le document de vente.
2. Choisissez l’action **Report**, puis **Reporter**.
3. Sélectionnez **Livraison et facturation**, puis cliquez sur le bouton **OK**.
4. Si vous souhaitez afficher un aperçu de la facture, cliquez sur le bouton **Oui**.

    > [!NOTE]  
    > Normalement, le département Livraison devrait déjà avoir reporté la livraison.  

    Arnie peut afficher l'historique pour vérifier que la facture vente a été créée comme prévue.

5. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente reportées**, puis sélectionnez le lien associé.  

## <a name="update-the-status-of-prepaid-orders-and-invoices-automatically"></a>Mettre à jour automatiquement l'état des commandes prépayées et des factures

Vous pouvez accélérer le traitement des commandes et des factures en configurant des entrées de file d’attente des travaux qui mettent automatiquement à jour l'état de ces documents. Lorsqu’une facture de paiement anticipé est payée, les entrées de la file d’attente des travaux peuvent changer automatiquement l'état du document de **Paiement anticipé en attente** sur **Validé**. Lorsque vous configurez les entrées de la file d’attente des travaux, les codeunits que vous devrez utiliser sont **383 Mise à jour En attente Paiement anticipé Ventes** et **383 Mise à jour En attente Paiement anticipé Achats**. Nous vous recommandons de programmer les entrées pour qu’elles s’exécutent fréquemment, par exemple, toutes les minutes. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## <a name="next-steps"></a>Étapes suivantes

Cette procédure pas-à-pas vous a présenté les étapes de configuration de [!INCLUDE[prod_short](includes/prod_short.md)] pour la gestion des paiements anticipés. 

- Configurez les pourcentages de paiement anticipé par défaut sur les clients et les articles.
- Utilisez différentes méthodes pour calculer les paiements anticipés sur une commande.  
- Calculez le montant du paiement anticipé en pourcentage du total de la commande.
- Attribuez un montant total de paiement anticipé à la commande.  

Vous avez également reporté une facture paiement anticipé, créé une deuxième lorsque la commande est modifiée, et reporté la facture finale pour le montant ouvert.  

Les fonctionnalités de paiement anticipé facilitent la configuration et l’application des règles de paiement anticipé pour les clients et les articles. Ils vous permettent également de reporter chaque paiement sur une facture.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/prepayment-invoices-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi .

[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
