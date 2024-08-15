---
title: Collecte des soldes restants
description: 'Découvrez comment rappeler à vos clients les impayés. Envoyez un relevé client, émettez un rappel ou envoyez une note de frais financiers.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: 'payment due, debt, overdue, fee, charge, reminder'
ms.search.form: '6, 25, 440, 443, 448, 452'
ms.date: 07/01/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="collect-outstanding-balances"></a>Collecte des soldes restants

La gestion des clients comprend le contrôle du règlement des montants à temps. Si des clients ont des paiements dus, vous pouvez commencer par envoyer le rapport du **Relevé client** comme rappel. Sinon, vous pouvez émettre de relances.

Utilisez des rappels pour alerter les clients de soldes échus. Vous pouvez également utiliser les rappels pour calculer les frais financiers tels que les intérêts ou les frais et les inclure dans le rappel. Utilisez les factures d'intérêts pour débiter des clients d'intérêts ou de frais sans leur rappeler les montants échus.

## <a name="statements"></a>Relevés

À partir de la fiche client, vous pouvez créer un relevé pour les transactions de ce client avec vous. Ensuite, vous pouvez générer un fichier PDF et l’envoyer au client. Sinon, utilisez le rapport **Relevé client** pour envoyer à vos clients un aperçu de leur activité avec vous. 

> [!TIP]
> Si nécessaire, vous pouvez envoyer le relevé vers Excel pour apporter des modifications.  

### <a name="to-send-the-customer-statement-report"></a>Pour envoyer le rapport Relevé client

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 10.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Relevé client**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans **Options sortie**, sélectionnez la manière dont l'état est envoyé au client.

> [!NOTE]
> Si vous utilisez plusieurs devises, le rapport Relevé client est toujours imprimé dans la devise du client. La dernière date dans une période de déclaration est également utilisée comme date de relevé et cumul date, si le cumul est inclus.

## <a name="reminders"></a>Relances

[!INCLUDE [receivables-reminders](includes/receivables-reminders.md)]

## <a name="finance-charges"></a>Frais financiers

Lorsqu’un client ne paie pas à la date d’échéance, vous pouvez faire calculer automatiquement les frais financiers et les ajouter aux montants en souffrance sur le compte du client. Vous pouvez informer le client des frais ajoutés en lui envoyant une facture d'intérêts.  

> [!NOTE]  
> Les notes de frais financiers permettent de calculer les intérêts et les frais financiers et d'en informer vos clients sans leur rappeler les paiements échus. Vous pouvez également calculer les intérêts sur les paiements échus lorsque vous créez des relances.  

Pour pouvoir créer des notes de frais financiers, vous devez configurer des modalités. Pour plus d’informations, voir [Configurer les modalités de frais financiers](finance-setup-finance-charges.md).  

Vous pouvez créer manuellement une note de frais financiers pour un client particulier et renseigner les lignes automatiquement. Vous pouvez également utiliser la fonction **Créer des notes de frais financiers** pour créer des notes de frais financiers pour certains clients ou tous les clients ayant des soldes échus.  

Une fois que vous avez créé les factures d'intérêts, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque facture d'intérêts est déterminé par les conditions intérêts de retard de la colonne **Désignation** de chaque ligne. Si un montant calculé a été inséré automatiquement au début ou à la fin du texte, le texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mise à jour du texte des intérêts de retard**.  

Une fois que vous avez créé des notes de frais financiers et effectué toutes les modifications requises, vous pouvez imprimer les rapports de test ou émettre des notes de frais financiers; en général par courriel.

### <a name="to-create-a-finance-charge-memo-manually"></a>Pour créer manuellement des notes de frais financiers

Une note de frais financiers ressemble à une facture. Vous pouvez renseigner un en-tête manuellement et faire renseigner les lignes, ou créer des factures d'intérêts automatiquement pour tous les clients.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de frais financiers**, puis sélectionnez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins.  
3. Sélectionnez **Proposer lignes fact. intérêts**.
4. Sur la page **Proposer lignes note de frais financiers**, définissez un filtre sur le raccourci **Écriture client** si vous souhaitez créer des notes de frais financiers uniquement pour des écritures spécifiques.

    > [!NOTE]
    > Même s'ils sont répertoriés, la sélection des champs **Paiement** et **Note de crédit** comme filtres de **Type de document** n'a aucun effet, car la fonction **Proposer lignes note de frais financiers** ne gère que les montants positifs.
5. Pour démarrer le traitement par lots, cliquez sur le bouton **OK**.  

### <a name="to-update-finance-charge-memo-texts"></a>Pour mettre à jour des textes de notes de frais financiers

Dans certains cas, vous souhaiterez peut-être modifier le texte de début et de fin que vous avez défini pour les conditions de frais financiers. Si vous le faites au moment où vous avez créé, mais pas encore émis, les factures d'intérêts, vous pouvez mettre à jour ces factures avec le texte modifié.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Note de frais financiers**, puis sélectionnez le lien associé.  
2. ouvrez la facture d'intérêts dont vous souhaitez modifier le texte, puis sélectionnez **MAJ texte fact. d'intérêts**.
3. Sur la page **Mettre à jour texte frais financiers**, vous pouvez définir un filtre pour mettre à jour plusieurs notes.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.  

### <a name="to-issue-finance-charge-memos"></a>Pour émettre des factures d'intérêts

Une fois que vous créez des notes de frais financiers et apportez toutes les modifications requises, vous pouvez imprimer des rapports de test ou émettre les notes de frais financiers.

Lorsque vous émettez un rappel, les écritures sont reportées selon les spécifications sur la page **Modalités de frais financiers**. Cette spécification détermine si des intérêts et/ou des frais supplémentaires sont reportés sur le compte client et dans le grand livre. Les paramètres de la page **Groupes report client** déterminent les comptes sur lesquels les intérêts ou les frais sont reportés.

Pour chaque écriture client de la note de frais financiers, une écriture est créée sur la page **Écritures rappel/frais financiers**.

Si les cases à cocher **Reporter intérêts** ou **Reporter frais supplémentaires** sont activées sur la page **Modalités de frais financiers**, les écritures suivantes sont aussi créées :

- Une écriture sur la page **Écritures client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, l’émission de la note de frais financiers peut créer des écritures TVA.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de frais financiers**, puis sélectionnez le lien associé.
2. Sélectionnez la facture concernée, puis cliquez sur l'action **Emettre**.
3. Sur la page **Émettre notes de frais financiers**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

La note de frais financiers est soit imprimée, soit envoyée à une adresse e-mail spécifiée sous forme de pièce jointe PDF.

### <a name="to-cancel-an-issued-finance-charge-memo"></a>Pour annuler une note de frais financiers émise

Si des notes de frais financiers ont été émises par erreur, vous pouvez les corriger avant qu’elles ne soient renvoyées. Vous pouvez le faire une par une ou par lot.

1. Sur la page **Notes de frais financiers émises**, sélectionnez une ou plusieurs lignes pour les notes de frais financiers émises que vous souhaitez annuler, puis choisissez l'action **Annuler**.
2. Sur la page **Annuler les notes de frais financiers émises**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

### <a name="to-view-reminder-and-finance-charge-entries"></a>Pour afficher les écritures rappel et note de frais financiers

Lorsque vous émettez un rappel, une écriture rappel est créée sur la page **Écritures rappel/frais financiers** pour chaque ligne rappel contenant une écriture client. Vous pouvez ensuite obtenir un aperçu des écritures rappel créées pour un client spécifique.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 5.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.  
2. Ouvrez la fiche client appropriée, puis sélectionnez l'action **Écritures comptables**.
3. Sur la page **Écritures client**, cliquez sur la ligne de l'écriture pour laquelle vous souhaitez visualiser les écritures rappel, puis sélectionnez l'action **Écritures rappel/frais financiers**.

## <a name="multiple-interest-rates"></a>Taux d’intérêt multiples

[!INCLUDE [multiple-interest-rates-def](includes/multiple-interest-rates-def.md)] Pour plus d’informations, reportez vous à [Paramétrer plusieurs taux d’intérêt](finance-how-to-set-up-multiple-interest-rates.md).  

## <a name="see-also"></a>Voir aussi .

[Configurer des niveaux et modalités de rappel](finance-setup-reminders.md)  
[Configurer des modalités de frais financiers](finance-setup-finance-charges.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
