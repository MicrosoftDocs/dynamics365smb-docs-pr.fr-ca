---
title: Collecte des soldes restants
description: Découvrez comment envoyer un rappel à un client sur un paiement dû et ajouter des frais ou des commissions au paiement en raison du retard.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 81f43ef3f021ef0d348eb14abdffdfda2b3d85fc
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4758403"
---
# <a name="collect-outstanding-balances"></a>Collecte des soldes restants

La gestion des clients comprend le contrôle du règlement des montants à temps. Si des clients ont des paiements dus, vous pouvez commencer par envoyer le rapport du **Relevé client** comme rappel. Sinon, vous pouvez émettre de relances.

Vous pouvez utiliser des relances pour rappeler aux clients les soldes échus. Vous pouvez également utiliser les rappels pour calculer les frais financiers tels que les intérêts ou les frais et les inclure dans le rappel. Utilisez les factures d'intérêts pour débiter des clients d'intérêts ou de frais sans leur rappeler les montants échus.

## <a name="statements"></a>Relevés

À partir de la fiche client, vous pouvez créer un relevé avec les transactions de ce client avec vous. Ensuite, vous envoyez au client le fichier PDF généré. Sinon, utilisez le rapport **Relevé client** pour envoyer à vos clients un aperçu de leur activité avec vous. Le relevé client peut être envoyé à Excel pour un traitement ultérieur.  

### <a name="to-send-the-customer-statement-report"></a>Pour envoyer le rapport Relevé client

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Relevé client**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans **Options sortie**, sélectionnez la manière dont l'état est envoyé au client.

> [!NOTE]
> Si vous utilisez plusieurs devises, le rapport Relevé client est toujours imprimé dans la devise du client. La dernière date dans une période de déclaration est également utilisée comme date de relevé et cumul date, si le cumul est inclus.

## <a name="reminders"></a>Rappels

Avant de pouvoir créer des rappels, vous devez configurer des modalités de rappel et les affecter à vos clients. Pour plus d’informations, voir [Configurer les niveaux et modalités de rappel](finance-setup-reminders.md). [!INCLUDE [reminder-terms](includes/reminder-terms.md)] Le contenu de la page **Modalités de frais financiers** détermine si les intérêts sont calculés dans le rappel.  

Vous pouvez exécuter périodiquement le traitement par lots **Création de relances** afin de créer des relances pour tous les clients ayant des soldes échus. Vous pouvez également créer manuellement une relance pour un client spécifique et demander à ce que les lignes soient calculées et renseignées automatiquement.  

Une fois que vous avez créé les relances, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque relance est déterminé par les conditions niveau de relance de la colonne **Désignation**. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mettre à jour texte relance**.  

Une écriture comptable client pour laquelle le champ **En attente** est renseigné ne génèrera pas la création d'une relance. Néanmoins, si un rappel est créé à partir d'une autre écriture, une écriture échue en attente d'approbation est incluse dans le rappel. Les intérêts ne sont pas calculés sur les lignes avec ces écritures.

Après avoir créé les rappels et effectué toutes les modifications souhaitées, vous pouvez imprimer les rapports de test ou émettre les rappels, en général par courriel.

### <a name="to-create-a-reminder-automatically"></a>Pour créer automatiquement un rappel

Un rappel est identique à une facture. Lorsque vous créez un rappel, un en-tête rappel, ainsi qu'une ou plusieurs lignes rappel, doivent être renseignés. Vous pouvez utiliser une fonction pour créer des relances pour tous les clients automatiquement.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Rappels**, puis sélectionnez le lien associé.
2. Sur la page **Rappel**, cliquez sur l'action **Créer rappels**.
3. Sur la page **Créer rappels**, renseignez les champs pour définir comment et pour qui les rappels sont créées.
4. Cliquez sur le bouton **OK**.

### <a name="to-create-a-reminder-manually"></a>Pour créer un rappel manuellement

Sur la page **Rappel**, vous pouvez renseigner le raccourci **Général** manuellement et ensuite renseigner les lignes automatiquement.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Rappels**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire.
4. Choisissez l'action **Proposer lignes relance**.
5. Dans le traitement par lots **Proposer lignes relance**, renseignez les champs pour définir comment et pour qui les relances sont créées.
6. Activez la case à cocher **Inclure les écritures en attente** si vous souhaitez que les relances contiennent des écritures ouvertes impayées qui sont en attente.
7. Sélectionnez la case à cocher **Seulement écritures dont l'échéance est dépassée** si vous souhaitez que les rappels contiennent uniquement des écritures ouvertes impayées. Seuls les factures et les paiements seront affichés car ce sont les écritures pour lesquelles les paiements de vos clients peuvent être en retard.

    > [!Important]
    > Les écritures ouvertes en attente sont insérées, indépendamment du paramètre de la case à cocher **Seulement écritures dont l'échéance est dépassée**.

8. Cliquez sur le bouton **OK**.

### <a name="to-replace-reminder-texts"></a>Pour remplacer les textes rappel

Vous pouvez déterminer de plusieurs manières le texte devant figurer sur le rappel imprimé. Dans certains cas, vous pouvez remplacer les textes début et fin définis pour le niveau actuel par ceux d'un autre niveau.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Rappels**, puis sélectionnez le lien associé.
2. Ouvrez la relance appropriée, puis cliquez sur l'action **Mettre à jour texte relance**.
3. Sur la page **Mettre à jour texte rappel**, entrez le niveau requis dans le champ **Niveau rappel**.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.

### <a name="to-issue-a-reminder"></a>Pour émettre un rappel

Après avoir créé les relances et effectué toutes les modifications souhaitées, vous pouvez lancer les impressions test ou émettre les relances.

Lorsque vous émettez une rappel, les données sont transférées vers une page séparée pour les rappels émis. Les écritures rappel sont simultanément reportées. Si des intérêts ou des frais supplémentaires ont été calculés, les écritures sont reportées dans les écritures client et dans le grand livre.

Lorsqu'une rappel est émise, les écritures sont reportées selon les spécifications de la page **Modalités de rappel**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration sur la page **Groupes report client** détermine les comptes qui seront utilisés.

Pour chaque écriture client de la note de frais financiers, une écriture est créée sur la page **Écritures rappel/frais financiers**.

Si les cases à cocher **Reporter intérêts** ou le champ **Reporter frais supplémentaires** de la page **Modalités de rappel** sont activées, les écritures suivantes sont aussi créées :

- Une écriture sur la page **Écritures client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre un rappel peut créer des écritures de TVA.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Rappels**, puis sélectionnez le lien associé.
2. Sélectionnez la relance concernée, puis cliquez sur l'action **Émission**.
3. Sur la page **Émettre rappels**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

Le rappel est imprimé pour être envoyé à une adresse de courriel spécifiée en tant que pièce jointe PDF.

### <a name="to-cancel-an-issued-reminder"></a>Pour annuler un rappel émis

Si des rappels ont été émis par erreur, vous pouvez les annuler avant leur envoi. Vous pouvez les annuler un par un ou en lot.

1. Sur la page **Rappels émis**, sélectionnez une ou plusieurs lignes pour les rappels émis que vous souhaitez annuler, puis choisissez l'action **Annuler**.
2. Sur la page **Annuler les rappels émis**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

## <a name="finance-charges"></a>Frais financiers

Lorsqu'un client n'effectue pas son paiement à la date d'échéance, des frais financiers peuvent être calculés automatiquement et ajoutés aux montants échus sur le compte du client. Vous pouvez informer le client des frais ajoutés en lui envoyant une facture d'intérêts.  

> [!NOTE]  
> Les notes de frais financiers permettent de calculer les intérêts et les frais financiers et d'en informer vos clients sans leur rappeler les paiements échus. Vous pouvez également calculer les intérêts sur les paiements échus lorsque vous créez des relances.  

Pour pouvoir créer des notes de frais financiers, vous devez configurer des modalités. Pour plus d’informations, voir [Configurer les modalités de frais financiers](finance-setup-finance-charges.md).  

Vous pouvez créer manuellement une note de frais financiers pour un client particulier et renseigner les lignes automatiquement. Vous pouvez également utiliser la tâche de fonction **Créer factures d'intérêts** pour créer des factures d'intérêts pour tous les clients ayant des soldes échus ou pour une sélection de clients ayant des soldes échus.  

Une fois que vous avez créé les factures d'intérêts, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque facture d'intérêts est déterminé par les conditions intérêts de retard de la colonne **Désignation** de chaque ligne. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mise à jour du texte des intérêts de retard**.  

Une fois que vous avez créé des notes de frais financiers et effectué toutes les modifications requises, vous pouvez imprimer les rapports de test ou émettre des notes de frais financiers; en général par courriel.

### <a name="to-create-a-finance-charge-memo-manually"></a>Pour créer manuellement des notes de frais financiers

Une note de frais financiers ressemble à une facture. Vous pouvez renseigner un en-tête manuellement et faire renseigner les lignes, ou créer des factures d'intérêts automatiquement pour tous les clients.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Notes de frais financiers**, puis sélectionnez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins.  
3. Sélectionnez **Proposer lignes fact. intérêts**.
4. Sur la page **Proposer lignes note de frais financiers**, définissez un filtre sur le raccourci **Écriture client** si vous souhaitez créer des notes de frais financiers uniquement pour des écritures spécifiques.

    > [!NOTE]
    > Même s'ils sont répertoriés, la sélection des champs **Paiement** et **Note de crédit** comme filtres de **Type de document** n'a aucun effet, car la fonction **Proposer lignes note de frais financiers** ne gère que les montants positifs.
5.  Pour démarrer le traitement en lot, cliquez sur le bouton **OK**.  

### <a name="to-update-finance-charge-memo-texts"></a>Pour mettre à jour des textes de notes de frais financiers  
Dans certains cas, vous pouvez modifier les textes début et fin définis pour les modalités de frais financiers. Si vous le faites au moment où vous avez créé, mais pas encore émis, les factures d'intérêts, vous pouvez mettre à jour ces factures avec le texte modifié.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Note de frais financiers**, puis sélectionnez le lien associé.  
2. ouvrez la facture d'intérêts dont vous souhaitez modifier le texte, puis sélectionnez **MAJ texte fact. d'intérêts**.
3. Sur la page **Mettre à jour texte frais financiers**, vous pouvez définir un filtre pour mettre à jour plusieurs notes.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.  

### <a name="to-issue-finance-charge-memos"></a>Pour émettre des factures d'intérêts
Une fois que vous avez créé des factures d'intérêts et effectué toutes les modifications requises, vous pouvez effectuer des impressions test ou émettre des factures d'intérêts.

Lorsqu'un rappel est émis, les écritures sont reportées selon les spécifications sur la page **Modalités de frais financiers**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration sur la page **Groupes report client** détermine les comptes qui seront utilisés.

Pour chaque écriture client de la note de frais financiers, une écriture est créée sur la page **Écritures rappel/frais financiers**.

Si les cases à cocher **Reporter intérêts** ou **Reporter frais supplémentaires** sont activées sur la page **Modalités de frais financiers**, les écritures suivantes sont aussi créées :

- Une écriture sur la page **Écritures client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre une note de frais financiers peut créer des écritures de TVA.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Notes de frais financiers**, puis sélectionnez le lien associé.
2. Sélectionnez la facture concernée, puis cliquez sur l'action **Emettre**.
3. Sur la page **Émettre notes de frais financiers**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

La note de frais financiers est imprimée pour être envoyée à une adresse de courriel spécifiée en tant que pièce jointe PDF.

### <a name="to-cancel-an-issued-finance-charge-memo"></a>Pour annuler une note de frais financiers émise
Si des notes de frais financiers ont été émises par erreur, vous pouvez les annuler avant leur envoi. Vous pouvez les annuler une par une ou par lots.
1. Sur la page **Notes de frais financiers émises**, sélectionnez une ou plusieurs lignes pour les notes de frais financiers émises que vous souhaitez annuler, puis choisissez l'action **Annuler**.
2. Sur la page **Annuler les notes de frais financiers émises**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

### <a name="to-view-reminder-and-finance-charge-entries"></a>Pour afficher les écritures rappel et note de frais financiers  
Lorsque vous émettez un rappel, une écriture rappel est créée sur la page **Écritures rappel/frais financiers** pour chaque ligne rappel contenant une écriture client. Vous pouvez ensuite obtenir un aperçu des écritures rappel créées pour un client spécifique.    
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.  
2. Ouvrez la fiche client appropriée, puis sélectionnez l'action **Écritures comptables**.
3. Sur la page **Écritures client**, cliquez sur la ligne de l'écriture pour laquelle vous souhaitez visualiser les écritures rappel, puis sélectionnez l'action **Écritures rappel/frais financiers**.

## <a name="multiple-interest-rates"></a>Taux d'intérêt multiples

Lorsque vous configurez des modalités de frais financiers et des modalités de rappel, pour la pénalité de retard de paiement, vous pouvez spécifier plusieurs taux d'intérêt afin que les frais de pénalité soient calculés sur la base de plusieurs taux d'intérêt à différentes périodes. Si la configuration n'intègre pas plusieurs taux d'intérêt, le taux d'intérêt et la période définis sur les pages **Modalités frais financiers** et **Modalités de rappel** seront utilisés pour l'ensemble de la période de calcul. Pour plus d'informations, reportez vous à [Paramétrer plusieurs taux d'intérêt](finance-how-to-set-up-multiple-interest-rates.md).  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/process-financial-periodic-activities-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi

[Configurer les niveaux et modalités de rappel](finance-setup-reminders.md)  
[Configurer les modalités de frais financiers](finance-setup-finance-charges.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]