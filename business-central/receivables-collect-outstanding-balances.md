---
title: "Rappeler ou pénaliser les clients pour les impayés| Microsoft Docs"
description: "Décrit comment envoyer un rappel à un client concernant un paiement dû et ajouter des frais, ou des commissions au paiement en raison du retard."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.date: 03/16/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 8f4cb1b2fdd55275fc1a3cba494d1ea4b583b5ed
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="collect-outstanding-balances"></a>Collecte des soldes restants
La gestion des clients comprend le contrôle du règlement des montants à temps. Si des clients ont des paiements échus, vous pouvez commencer par envoyer le rapport du Relevé client en guise de rappel. Sinon, vous pouvez émettre de relances.

Vous pouvez utiliser des relances pour rappeler aux clients les soldes échus. Vous pouvez également utiliser les rappels pour calculer les frais financiers tels que les intérêts ou les frais et les inclure dans le rappel. Utilisez les factures d'intérêts pour débiter des clients d'intérêts ou de frais sans leur rappeler les montants échus.

## <a name="reminders"></a>Rappels
Avant de pouvoir créer des rappels, vous devez configurer des modalités de rappel et les affecter à vos clients. Chaque modalité de rappel a des niveaux de rappel prédéfinis. Chaque niveau de rappel inclut des règles relatives à l'émission du rappel, par exemple, le nombre de jours après la date d'échéance de la facture ou la date du rappel précédent après laquelle il doit être émis. Le contenu de la fenêtre **Conditions intérêts de retard** détermine si les intérêts sont calculés dans la relance.  

Vous pouvez exécuter périodiquement le traitement par lots **Création de relances** afin de créer des relances pour tous les clients ayant des soldes échus. Vous pouvez également créer manuellement une relance pour un client spécifique et demander à ce que les lignes soient calculées et renseignées automatiquement.  

Une fois que vous avez créé les relances, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque relance est déterminé par les conditions niveau de relance de la colonne **Désignation**. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mettre à jour texte relance**.  

Une écriture comptable client pour laquelle le champ **En attente** est renseigné ne génèrera pas la création d'une relance. Néanmoins, si un rappel est créé à partir d'une autre écriture, une écriture échue en attente d'approbation est incluse dans le rappel. Les intérêts ne sont pas calculés sur les lignes avec ces écritures.

Après avoir créé les rappels et effectué toutes les modifications souhaitées, vous pouvez imprimer les rapports de test ou émettre les rappels, en général par courriel.

## <a name="finance-charges"></a>Frais financiers
Lorsqu'un client n'effectue pas son paiement à la date d'échéance, des frais financiers peuvent être calculés automatiquement et ajoutés aux montants échus sur le compte du client. Vous pouvez informer le client des frais ajoutés en lui envoyant une facture d'intérêts.  

> [!NOTE]  
> Les notes de frais financiers permettent de calculer les intérêts et les frais financiers et d'en informer vos clients sans leur rappeler les paiements échus. Vous pouvez également calculer les intérêts sur les paiements échus lorsque vous créez des relances.  

Vous pouvez créer manuellement une note de frais financiers pour un client particulier et renseigner les lignes automatiquement. Vous pouvez également utiliser la tâche de fonction **Créer factures d'intérêts** pour créer des factures d'intérêts pour tous les clients ayant des soldes échus ou pour une sélection de clients ayant des soldes échus.  

Une fois que vous avez créé les factures d'intérêts, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque facture d'intérêts est déterminé par les conditions intérêts de retard de la colonne **Désignation** de chaque ligne. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mise à jour du texte des intérêts de retard**.  

Une fois que vous avez créé des notes de frais financiers et effectué toutes les modifications requises, vous pouvez imprimer les rapports de test ou émettre des notes de frais financiers; en général par courriel.

## <a name="multiple-interest-rates"></a>Taux d'intérêt multiples
Lorsque vous configurez des modalités de frais financiers et des modalités de rappel, pour la pénalité de retard de paiement, vous pouvez spécifier plusieurs taux d'intérêt afin que les frais de pénalité soient calculés sur la base de plusieurs taux d'intérêt à différentes périodes. Si vous n'avez pas configuré de taux d'intérêt multiples, le taux d'intérêt et la période définis dans les fenêtres **Modalités de frais financiers** et **Modalités de rappel** pour l'ensemble de la période de calcul seront utilisés. Pour plus d'informations, reportez vous à [Paramétrer plusieurs taux d'intérêt](finance-how-to-set-up-multiple-interest-rates.md).  

## <a name="to-send-the-customer-statement-report"></a>Pour envoyer le rapport Relevé client
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Relevé client**, puis sélectionnez le lien connexe.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans **Options sortie**, sélectionnez la manière dont l'état est envoyé au client.

> [!NOTE]  
>   Si vous utilisez plusieurs devises, le rapport Relevé client est toujours imprimé dans la devise du client. La dernière date dans une période de déclaration est également utilisée comme date de relevé et cumul date, si le cumul est inclus.

## <a name="to-set-up-reminder-terms"></a>Pour configurer des modalités de rappel
Si des clients ont des impayés, vous devez décider quand et comment leur envoyer un rappel. En outre, vous pouvez être amené à débiter leurs comptes d'intérêts ou de frais. Vous pouvez configurer autant de modalités de rappel que vous le souhaitez. Vous pouvez définir un nombre illimité de niveaux rappel pour chaque code modalités de rappel.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Conditions de relance**, puis sélectionnez le lien connexe.  
2. Renseignez les champs selon vos besoins.  
3. Pour utiliser plusieurs combinaisons de modalités de rappel, créez un code pour chacun d'eux.

## <a name="to-set-up-reminder-levels"></a>Pour configurer des niveaux rappel
La première fois qu'un rappel est créé pour un client, la configuration utilisée est celle du niveau 1. Lorsque le rappel est émis, le numéro du niveau est enregistré dans les écritures rappel qui sont créées et associées à l'écriture client spécifique. S'il est nécessaire de rappeler le client, toutes les écritures rappel associées aux écritures client ouvertes sont vérifiées afin de localiser le numéro de niveau le plus élevé. Les conditions du niveau suivant seront alors utilisées pour le nouveau rappel.

Si vous créez plus de relances qu'il n'y a de niveaux relance, les conditions utilisées seront celles du niveau le plus élevé. Vous pouvez utiliser autant de relances que le champ **Nombre max. de relances** des conditions relance le permet.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Conditions de relance**, puis sélectionnez le lien connexe.  
2. Dans la fenêtre **Conditions de relance**, cliquez sur la ligne comportant les conditions pour lesquelles configurer des niveaux, puis cliquez sur l'action **Niveaux**.  
3. Renseignez les champs selon vos besoins.  

    Pour chaque niveau de rappel, vous pouvez spécifier des conditions particulières, qui peuvent inclure des frais supplémentaires en devise locale ($) et en devise étrangère. Vous pouvez définir plusieurs frais supplémentaires en devise étrangère pour chaque code de la fenêtre **Niveaux relance**.
4. Sélectionnez l'action **Devises**.
5. Dans la fenêtre **Devises niveau relance**, définissez un code de niveau pour chaque relance et le numéro du niveau de rappel correspondant, une devise et des frais supplémentaires.

    > [!NOTE]  
    > Lorsque vous créez une relance en devise, les conditions devise définies ici permettront de créer des relances. Si aucune condition devise n'a été définie, les conditions devise société définies dans la fenêtre **Niveaux relance** seront utilisées et converties dans la devise appropriée.

    Pour chaque niveau relance, vous pouvez indiquer le texte à imprimer avant (**Texte début**) ou après (**Texte fin**) les écritures de la relance.

6. Choisissez les actions **Texte de début** ou **Texte de fin** respectivement, puis renseignez la fenêtre **Texte relance**.
7. Pour insérer automatiquement des valeurs correspondantes dans le texte de relance résultant, entrez les espaces réservés suivants dans le champ **Texte**.  

|Paramètre substituable|Valeur|  
|-----------------|-----------|  
|%1|Contenu du champ **Date du document** de l'en\-tête de relance|  
|%2|Contenu du champ **Date d'échéance** de l'en\-tête de relance|  
|%3|Contenu du champ **Taux d'intérêt** dans les conditions d'intérêts de retard associées|  
|%4|Contenu du champ **Montant ouvert** de l'en\-tête de relance|  
|%5|Contenu du champ **Montant intérêts** de l'en\-tête de relance|  
|%6|Contenu du champ **Frais supplémentaires** de l'en\-tête de relance|  
|%7|Montant total du rappel|  
|%8|Contenu du champ **Niveau relance** de l'en\-tête de relance|  
|%9|Contenu du champ **Code devise** de l'en\-tête de relance|  
|%10|Contenu du champ **Date de validation** de l'en\-tête de relance|  
|%11|Nom de la compagnie|  
|%12|Contenu du champ **Frais supplémentaires par ligne** de l'en\-tête de relance|  

Par exemple, si vous entrez **Vous devez %9 %7 dus au %2.**, le rappel résultant contiendra le texte suivant : **Vous devez 1 200,50 USD dus au 02-02-2014**.

Si vous avez configuré les modalités de rappel (avec des niveaux et du texte supplémentaires), entrez l'un des codes sur chaque fiche client. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).

## <a name="to-create-a-reminder-automatically"></a>Pour créer automatiquement un rappel
Un rappel est identique à une facture. Lorsque vous créez un rappel, un en-tête rappel, ainsi qu'une ou plusieurs lignes rappel, doivent être renseignés. Vous pouvez utiliser une fonction pour créer des relances pour tous les clients automatiquement.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Relances**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Relance**, cliquez sur l'action **Créer relance**.
3. Dans la fenêtre **Créer relances**, renseignez les champs pour définir comment et pour qui les relances sont créées.
4. Cliquez sur le bouton **OK**.

## <a name="to-create-a-reminder-manually"></a>Pour créer un rappel manuellement
Dans la fenêtre **Relance**, vous pouvez renseigner le raccourci **Général** manuellement et ensuite renseigner les lignes automatiquement.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Relances**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**.
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire.
4. Choisissez l'action **Proposer lignes relance**.
5. Dans le traitement par lots **Proposer lignes relance**, renseignez les champs pour définir comment et pour qui les relances sont créées.
6. Activez la case à cocher **Inclure les écritures en attente** si vous souhaitez que les relances contiennent des écritures ouvertes impayées qui sont en attente.

    > [!Important]
    > Les écritures ouvertes en attente sont insérées, indépendamment du paramètre de la case à cocher Seulement écritures dont l'échéance est dépassée.

7. Cliquez sur le bouton **OK**.

## <a name="to-replace-reminder-texts"></a>Pour remplacer les textes rappel  
Vous pouvez déterminer de plusieurs manières le texte devant figurer sur le rappel imprimé. Dans certains cas, vous pouvez remplacer les textes début et fin définis pour le niveau actuel par ceux d'un autre niveau.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Relances**, puis sélectionnez le lien connexe.
2. Ouvrez la relance appropriée, puis cliquez sur l'action **Mettre à jour texte relance**.
3. Dans la fenêtre **Mettre à jour texte relance**, entrez le niveau requis dans le champ **Niveau relance**.
3. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.

## <a name="to-issue-a-reminder"></a>Pour émettre un rappel
Après avoir créé les relances et effectué toutes les modifications souhaitées, vous pouvez lancer les impressions test ou émettre les relances.

Lorsque vous émettez un rappel, les données sont transférées vers une fenêtre séparée pour les rappels émis. Les écritures rappel sont simultanément reportées. Si des intérêts ou des frais supplémentaires ont été calculés, les écritures sont reportées dans les écritures client et dans le grand livre.

Lorsqu'une relance est émise, les écritures sont validées selon les spécifications de la fenêtre **Conditions de relance**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration dans la fenêtre **Groupes compta. client** détermine les comptes qui seront utilisés.

Pour chaque écriture comptable client de la facture d'intérêts, une écriture est créée dans la fenêtre **Ecr. relance/fact. intérêts**.

Si les cases à cocher **Comptabiliser intérêts** ou le champ **Compta. frais supplémentaires** de la table **Conditions de relance** sont activées, les écritures suivantes sont aussi créées :

- Une écriture dans la fenêtre **Écritures comptables client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre un rappel peut créer des écritures de TVA.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Relances**, puis sélectionnez le lien connexe.
2. Sélectionnez la relance concernée, puis cliquez sur l'action **Émission**.
3. Dans la fenêtre **Emettre relances**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

Le rappel est imprimé pour être envoyé à une adresse de courriel spécifiée en tant que pièce jointe PDF.

## <a name="to-set-up-finance-charge-terms"></a>Pour configurer des modalités de frais financiers
Vous devez configurer un code qui représente un calcul de frais financiers. Vous pouvez ensuite entrer ce code dans le champ **Code condition intérêts** des fiches client ou fournisseur.

Les frais financiers peuvent être calculés en utilisant la méthode du solde journalier moyen ou celle du solde échu.

* Méthode du solde échu

    Les frais financiers représentent simplement un pourcentage du montant échu :  
    *Méthode du solde échu* - *Frais financiers* = *Montant échu* x *(Taux d'intérêt / 100)*

*   Méthode du solde journalier moyen

    Le ombre de jours pendant lequel le paiement est en retard est pris en compte :  
    *Méthode Solde journalier moyen* - *Frais financiers* = *Montant échu* x *(Jours échus/ Période d'intérêts)* x *(Taux d'intérêt/100)*

En outre, chaque code de la table Modalités de frais financiers est lié à une autre table, la table Texte frais financiers. Pour chaque ensemble de modalités de frais financiers, vous pouvez définir un texte début et un texte fin à inclure dans la note de frais financiers.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Conditions intérêts de retard**, puis sélectionnez le lien connexe.  
2. Renseignez les champs selon vos besoins.  
3. Pour utiliser plusieurs combinaisons de modalités de frais financiers, créez un code pour chacun d'eux.

    Pour chaque modalité de frais financiers, vous pouvez spécifier des modalités particulières, qui peuvent inclure des frais supplémentaires en devise locale ($) et en devise étrangère. Vous pouvez définir des frais supplémentaires en devise pour chaque code de la fenêtre **Conditions intérêts de retard**.
4. Sélectionnez l'action **Devises**.
5. Dans la fenêtre **Devises condition intérêts**, définissez pour chaque condition un code devise et des frais supplémentaires.

    > [!NOTE]  
    > Lorsque vous créez des frais financiers en devise, les conditions devise définies ici serviront à créer des notes de frais financiers. Si aucune condition intérêts de retard en devise n'est définie, les conditions intérêts de retard en devise société définies dans la table **Conditions intérêts de retard** seront utilisées, puis converties dans la devise souhaitée.

    Pour chaque condition intérêts, vous pouvez spécifier le texte à imprimer avant (**Texte début**) ou après (**Texte fin**) les écritures de la facture d'intérêts.  
6. Choisissez les actions **Texte de début** ou **Texte de fin** respectivement, puis renseignez la fenêtre **Texte intérêts de retard**.
7. Pour insérer automatiquement des valeurs correspondantes dans le texte facture d'intérêts résultant, entrez les espaces réservés suivants dans le champ **Texte**.

|Paramètre substituable|Valeur|  
|-----------------|-----------|  
|%1|Contenu du champ **Date du document** de l'en-tête de facture d'intérêts|  
|%2|Contenu du champ **Date d'échéance** de l'en-tête de facture d'intérêts|  
|%3|Contenu du champ **Taux d'intérêt** dans les conditions d'intérêts de retard associées|  
|%4|Contenu du champ **Montant ouvert** de l'en-tête de facture d'intérêts|  
|%5|Contenu du champ **Montant intérêts** de l'en-tête de facture d'intérêts|  
|%6|Contenu du champ **Frais supplémentaires** de l'en-tête de facture d'intérêts|  
|%7|Montant total du rappel|  
|%8|Contenu du champ **Code devise** de l'en-tête de facture d'intérêts|  
|%9|Contenu du champ **Date comptabilisation** de l'en-tête de facture d'intérêts|  

## <a name="to-create-a-finance-charge-memo-manually"></a>Pour créer manuellement des notes de frais financiers  
Une note de frais financiers ressemble à une facture. Vous pouvez renseigner un en-tête manuellement et faire renseigner les lignes, ou créer des factures d'intérêts automatiquement pour tous les clients.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures d'intérêts**, puis sélectionnez le lien connexe.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins.  
3. Sélectionnez **Proposer lignes fact. intérêts**.
4. Dans la fenêtre **Proposer lignes note de frais financiers**, définissez un filtre sur le raccourci **Écriture client** si vous souhaitez créer des notes de frais financiers uniquement pour des écritures spécifiques.  
5.  Pour démarrer le traitement par lots, cliquez sur le bouton **OK**.  

## <a name="to-update-finance-charge-memo-texts"></a>Pour mettre à jour des textes de notes de frais financiers  
Dans certains cas, vous pouvez modifier les textes début et fin définis pour les modalités de frais financiers. Si vous le faites au moment où vous avez créé, mais pas encore émis, les factures d'intérêts, vous pouvez mettre à jour ces factures avec le texte modifié.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Facture d'intérêts**, puis sélectionnez le lien connexe.  
2. ouvrez la facture d'intérêts dont vous souhaitez modifier le texte, puis sélectionnez **MAJ texte fact. d'intérêts**.
3. Dans la fenêtre **MAJ texte fact. d'intérêts**, vous pouvez définir un filtre pour mettre à jour plusieurs factures d'intérêts.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.  

## <a name="to-issue-finance-charge-memos"></a>Pour émettre des factures d'intérêts
Une fois que vous avez créé des factures d'intérêts et effectué toutes les modifications requises, vous pouvez effectuer des impressions test ou émettre des factures d'intérêts.

Lorsqu'une relance est émise, les écritures sont validées selon les spécifications de la fenêtre **Conditions intérêts de retard**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration dans la fenêtre **Groupes compta. client** détermine les comptes qui seront utilisés.

Pour chaque écriture comptable client de la facture d'intérêts, une écriture est créée dans la fenêtre **Ecr. relance/fact. intérêts**.

Si les cases à cocher **Comptabiliser intérêts** ou le champ **Compta. frais supplémentaires** de la table **Conditions intérêts de retard** sont activées, les écritures suivantes sont aussi créées :

- Une écriture dans la fenêtre **Écritures comptables client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre une note de frais financiers peut créer des écritures de TVA.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures d'intérêts**, puis sélectionnez le lien connexe.
2. Sélectionnez la facture concernée, puis cliquez sur l'action **Emettre**.
3. Dans la fenêtre **Emettre factures d'intérêts**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

La note de frais financiers est imprimée pour être envoyée à une adresse de courriel spécifiée en tant que pièce jointe PDF.

## <a name="to-view-reminder-and-finance-charge-entries"></a>Pour afficher les écritures rappel et note de frais financiers  
Lorsque vous émettez une relance, une écriture relance est créée dans la fenêtre **Écr. relance/fact. intérêts** pour chaque ligne relance contenant une écriture comptable client. Vous pouvez ensuite obtenir un aperçu des écritures rappel créées pour un client spécifique.    
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.  
2. Ouvrez la fiche client appropriée, puis sélectionnez l'action **Écritures comptables**.
3. Dans la fenêtre **Écritures comptables client**, cliquez sur la ligne de l'écriture comptable pour laquelle vous souhaitez visualiser les écritures relance, puis sélectionnez l'action **Écr. relance/fact. intérêts**.

## <a name="see-also"></a>Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

