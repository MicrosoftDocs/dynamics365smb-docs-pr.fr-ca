---
title: 'Procédure pas à pas : configuration et facturation de paiements anticipés | Microsoft Docs'
description: Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. Vous utilisez la fonctionnalité de paiements anticipés dans Business Central pour facturer et collecter les dépôts requis des clients ou régler des dépôts aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: f8010f87b1e3d67bb34fbe77495654c001edf8f0
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5771989"
---
# <a name="walkthrough-setting-up-and-invoicing-sales-prepayments"></a>Procédure pas à pas : configuration et facturation de paiements anticipés vente

[!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]  

Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. Vous utilisez la fonctionnalité d'acomptes dans [!INCLUDE[prod_short](includes/prod_short.md)] pour facturer et collecter les acomptes requis des clients ou régler des acomptes aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture.  

 Les conditions de paiement anticipé peuvent être définies pour un client ou un fournisseur pour tous les articles ou pour une sélection d'articles. Lorsque vous avez effectué la configuration requise, vous pouvez générer des factures paiement anticipé à partir des documents de vente et des bons de commande pour le montant paiement anticipé calculé. Au besoin, vous pouvez modifier les montants par défaut dans la facture. Par exemple, vous pouvez également envoyer des factures paiement anticipé supplémentaires si des articles supplémentaires sont ajoutés à la commande.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
 Cette procédure pas à pas présente les scénarios suivants :  

-   Configuration des paiements anticipés  
-   Création d'une commande nécessitant un paiement anticipé  
-   Création d'une facture de paiement anticipé  
-   Correction des conditions de paiement anticipé sur une commande  
-   Affectation de paiements anticipés à une commande  
-   Facturation du montant final sur une commande faisant l'objet d'un paiement anticipé.  

### <a name="roles"></a>Rôles  
 Cette procédure pas à pas inclut les tâches correspondant aux rôles suivants :  

-   responsable de la comptabilité (Phyllis) ;  
-   préparatrice de commandes (Susan) ;  
-   administrateur Ventes (Arnie).  

## <a name="story"></a>Scénario  
 Phyllis est responsable de la comptabilité. Elle décide des clients qui doivent payer un acompte avant que les articles soient produits ou livrés. Phyllis configure [!INCLUDE[prod_short](includes/prod_short.md)] de façon à calculer automatiquement les acomptes.  

 Susan est préparatrice de documents de vente. Lorsque le client appelle pour passer une commande, elle entre la commande dans le système pendant que le client est au téléphone. Elle peut ainsi vérifier immédiatement les prix et les modalités de paiement avec le client et ajuster la commande pendant qu'elle négocie avec le client.  

 Arnie travaille dans le département Comptabilité client où sa fonction consiste à reporter les factures et les paiements.  

 Dans ce scénario, Phyllis configure les conditions de paiement anticipé pour le client Selangorian, en se basant sur leurs antécédents en matière de crédit. Elle donne à Susan des instructions sur le traitement de leurs commandes.  

 Lorsque le client appelle, Susan négocie avec lui jusqu'à parvenir à une entente. Elle peut alors choisir de calculer le paiement anticipé de différentes manières.  

 Après que Susan a envoyé la facture paiement anticipé, le client commande un article supplémentaire. Susan met à jour la commande et crée une seconde facture paiement anticipé.  

 Arnie enregistre le paiement du client et l'affecte à la facture, puis envoie la facture finale.  

## <a name="setting-up-prepayments"></a>Configuration d'acomptes  
 Phyllis configure le système afin qu'il gère les acomptes des clients.  

-   Elle décide d'utiliser la même série de numéros pour les paiements anticipés et la facturation vente.  
-   Elle configure l'application pour qu'elle vérifie si des paiements anticipés sont requis avant la facturation finale d'une commande.  
-   Elle configure les valeurs par défaut pour un pourcentage de paiement anticipé requis pour certains articles et clients.  

Les procédures suivantes décrivent le mode d'exécution des tâches de Phyllis :  

#### <a name="to-set-up-number-series-for-prepayments"></a>Pour configurer des séries de numéros pour les paiements anticipés  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.  
2.  Sur la page **Configuration ventes & à recevoir**, affichez le raccourci **Numérotation**.  
3.  Vérifiez que la série de numéros des factures paiement anticipé reportées dans le champ **N° factures pour paiement anticipé reporté** est identique à celle des factures vente reportées (**N° facture reportée**) et que la série de numéros des notes de crédit pour paiement anticipé reporté (**N° notes de crédit pour paiement anticipé reporté**) est identique à celle des notes de crédit reportées (**N° note de crédit reportée**).  

#### <a name="to-block-shipments-for-unpaid-prepayment"></a>Pour bloquer les livraisons pour un paiement anticipé impayé  
1.  Sur la page **Configuration ventes & à recevoir**, sur le raccourci **Général**, cochez la case **Vérifier les acomptes lors du report**.

    Vous ne pouvez pas livrer ou facturer une commande dont le montant de paiement anticipé n'a pas été réglé.  

Par défaut, Phyllis requiert que le client 20000 soit facturé avec un acompte de 30 % sur toutes les commandes. Pour cela, elle entre un pourcentage de paiement anticipé par défaut dans la fiche client.  

Phyllis requiert que tous les clients soient facturés avec un acompte de 20 % pour l'article 1100. Le client 20000 a un mauvais historique de paiements. Par conséquent, elle demande un paiement anticipé de 40 % au client 20000 pour l'article 1100. La procédure suivante présente le mode de configuration des pourcentages de paiement anticipé par défaut.  

#### <a name="to-assign-default-prepayment-percentages-to-customers-and-items"></a>Pour affecter des pourcentages de paiement anticipé par défaut aux clients et aux articles  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.  
2.  Ouvrez la fiche pour le client 20000 (Selangorian).
3.  Dans le champ **% acompte**, entrez **30**.  
4.  Cliquez sur le bouton **OK** pour fermer la fiche client.  
5.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
6.  Ouvrez la fiche pour le client 1100.
7.  Choisissez l'action **Pourcentages paiement anticipé**.  
8.  Renseignez deux lignes de la page **Pourcentages paiement anticipé vente**, comme suit.  

    |**Type vente**|**Code vente**|**N° article**|**% acompte**|  
    |--------------------|--------------------|------------------|----------------------|  
    |**Client**|**20000**|**1100**|**40**|  
    |**Tous les clients**||**1100**|**20**|  

    > [!IMPORTANT]  
    >  En fonction de votre pays/région, vous devez également spécifier un code groupe fiscal sur le raccourci **Facturation** pour les articles 1000 et 1100.  

9. Fermez toutes les pages.  

#### <a name="to-specify-an-account-for-sales-prepayments-in-general-posting-setup"></a>Pour spécifier un compte pour les paiements anticipés vente dans la configuration de report générale  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du report général**, puis sélectionnez le lien associé.  
2.  Sélectionnez la ligne où le champ **Groupe report marché** est défini sur **EXPORTATION**, et où le champ **Groupe report produit** est défini sur **DÉTAIL**, puis sélectionnez l'action **Modifier**.  
3.  Sur la page **Fiche configuration report général**, dans le champ **Compte paiements anticipés vente**, spécifiez le compte approprié.  
4.  Cliquez sur le bouton **OK**.  

## <a name="creating-an-order-that-requires-a-prepayment"></a>Création d'une commande nécessitant un paiement anticipé  
 Dans le scénario suivant, Susan, la préparatrice des commandes, crée une commande en discutant avec le client. Les articles que le client commande nécessitent un paiement anticipé et le client a connu des retards de paiement par le passé. Susan a donc reçu l'ordre de demander un montant fixe de 2 000 comme paiement anticipé sur la commande.  

Le client demande à pouvoir payer 35 %, ce que Susan peut accepter. Elle modifie donc la commande.  

Susan crée la facture paiement anticipé et l'envoie au client.  

#### <a name="to-create-a-sales-order-with-a-prepayment"></a>Pour créer un document de vente avec paiement anticipé  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **N° donneur d'ordre** , sélectionnez **20000**.  
5.  Acceptez l'avertissement de solde échu qui s'affiche.  
6.  Renseignez deux lignes vente avec les informations suivantes.  

    |**Type**|**N°**|**Quantité**|  
    |--------------|-------------|------------------|  
    |**Article**|**1000**|**1**|  
    |**Article**|**1100**|**1**|

    Par défaut, les champs du paiement anticipé étant masqués, vous devez les afficher.  

7. Vérifiez que le champ **% acompte** de la ligne correspondant à l'article **1000** a pour valeur **30**. La valeur par défaut a été prise dans l'en-tête vente, qui a été renseigné à partir de la fiche client.  

    Le champ **% acompte** de la ligne correspondant à l'article **1100** a pour valeur **40**. Il s'agit du pourcentage que vous avez entré sur la page **Pourcentages paiement anticipé vente** pour l'article **1100** et le client **20000**.  

    Pour plus d'informations, reportez\-vous à [Configuration des acomptes](finance-set-up-prepayments.md).  
8. Sélectionnez l'action **Statistiques**.  
9. Sur le raccourci **Acompte**, le champ **Montant acompte HT** indique **1 560**. Si vous créez une facture paiement anticipé pour la commande dès maintenant, c'est le montant qui s'affiche sur la facture.  

    Dans ce scénario, Susan a reçu des instructions lui demandant de proposer un paiement anticipé total de 2 000 pour la commande.  

    > [!IMPORTANT]  
    >  En fonction de votre pays/région, l'étape suivante peut ne pas s'appliquer.  
10. Remplacez le montant du champ **Montant acompte HT** par **2 000**, puis fermez la page.  
11. Consultez le champ **% acompte** des lignes vente : le montant a été recalculé, il est désormais de **40,81625**.  

    Le nouveau calcul inclut toutes les lignes dont le pourcentage de paiement anticipé est supérieur à 0.  

    À présent, le client demande si le pourcentage du paiement anticipé peut être fixé à 35 %. Le chef de Susan accepte la modification.  

12. Sur la page **Document de vente**, dans le champ **% paiement anticipé**, entrez **35**.  
13. Dans l'avertissement qui s'affiche, cliquez sur le bouton **Oui** . Un taux de 35 % sera affecté comme pourcentage du paiement de l'ensemble de la commande.  
14. Vérifiez que les lignes ont été mises à jour en conséquence.  

## <a name="creating-a-prepayment-invoice"></a>Création d'une facture paiement anticipé  
Après avoir entré la valeur de paiement anticipé correcte sur la commande, Susan crée la facture paiement anticipé et l'envoie au client.  

#### <a name="to-create-a-prepayment-invoice"></a>Pour créer une facture paiement anticipé  

1.  Sur la page **Document de vente** sélectionnez l'action **Reporter facture paiement anticipé**.  

> [!NOTE]  
>  Susan pourrait sélectionner **Valider et imprimer facture acompte** et envoyer par courrier la facture au client.  

## <a name="creating-an-additional-prepayment-invoice"></a>Création d'une facture paiement anticipé supplémentaire  
Le jour suivant, le client appelle Susan et modifie sa commande. Il souhaite deux exemplaires de l'article 1100. Susan rouvre et met à jour la commande, puis crée une seconde facture paiement anticipé sur la commande et l'envoie au client.  

#### <a name="to-create-an-additional-prepayment-invoice"></a>Pour créer une facture paiement anticipé supplémentaire  

1.  Sur la page **Document de vente**, sélectionnez l'action **Rouvrir**.  
2.  Sur la ligne de l'article **1100**, dans le champ **Quantité**, entrez **2**.  

    Faites défiler pour afficher les champs de paiement anticipé. Le champ **Montant acompte HT** affiche à présent **630** et le champ **Montant fact. acompte HT** indique **315**. Ceci indique qu'il existe un montant de paiement anticipé supplémentaire qui n'a pas encore été facturé.  
3.  Pour reporter une facture pour le montant paiement anticipé supplémentaire, choisissez l'action **Reporter facture paiement anticipé**.  

## <a name="applying-the-prepayments"></a>Affectation des paiements anticipés  
Le client paie le montant des paiements anticipés. Arnie, qui travaille au département Comptabilité, enregistre le paiement et l'affecte aux factures paiement anticipé.  

#### <a name="to-apply-a-payment-to-the-prepayment-invoices"></a>Pour affecter un paiement aux factures paiement anticipé  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux des encaissements**, puis sélectionnez le lien associé.  
2.  Renseignez une ligne journal avec les informations suivantes.  

    |Nom du champ|Entrée|  
    |----------------|-----------|  
    |**Type document**|**Règlement**|  
    |**Type compte**|**Client**|  
    |**N° compte**|**20000**|  
3. Sélectionnez l'action **Lettrer écritures**.  
4.  Sur la page **Affecter écritures client**, sélectionnez la première facture paiement anticipé, puis, sélectionnez **Définir code référence**.  
5.  Répétez l'étape précédente pour le deuxième paiement anticipé.  
6.  Cliquez sur le bouton **OK**.  

    Le champ montant est maintenant renseigné avec la somme des deux factures paiement anticipé.  

7.  Reportez le journal.  

## <a name="invoicing-the-remaining-amount"></a>Facturation du montant ouvert  
Arnie a été informé que les articles de la commande ont été livrés et que la commande est prête pour facturation. Il crée donc la facture correspondante.  

#### <a name="to-invoice-the-remaining-amount"></a>Pour facturer le montant ouvert  
1. Ouvrez le document de vente.  
2. Sélectionnez **Livrer**, puis le bouton **OK**.  

> [!NOTE]  
>  Normalement, le département Livraison devrait déjà avoir reporté la livraison.  

Arnie peut afficher l'historique pour vérifier que la facture vente a été créée comme prévue.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Factures vente reportées**, puis sélectionnez le lien associé.  

## <a name="next-steps"></a>Étapes suivantes  
Cette procédure pas-à-pas vous a présenté les étapes de configuration de [!INCLUDE[prod_short](includes/prod_short.md)] pour la gestion des acomptes. Vous avez configuré des pourcentages de paiement anticipé par défaut pour des clients et des articles et vous avez également utilisé différentes méthodes pour calculer les paiements anticipés d'une commande. Vous avez essayé d'affecter un montant de paiement anticipé total à la commande et vous avez enregistré le montant paiement anticipé calculé en tant que pourcentage de l'ensemble de la commande.  

Vous avez également reporté une facture paiement anticipé, créé une deuxième lorsque la commande est modifiée, et reporté la facture finale pour le montant ouvert.  

La fonctionnalité d'acompte de [!INCLUDE[prod_short](includes/prod_short.md)] facilite la configuration et la mise en place de règles d'acompte pour les clients et les articles. Elle vous permet également de valider tous les paiements d'une facture.  

## <a name="see-also"></a>Voir aussi  
[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]