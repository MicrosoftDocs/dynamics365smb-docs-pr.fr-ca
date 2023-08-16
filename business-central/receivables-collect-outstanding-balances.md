---
title: Collecte des soldes restants
description: 'Découvrez comment rappeler à vos clients les impayés. Envoyez un relevé client, émettez un rappel ou envoyez une note de frais financiers.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment due, debt, overdue, fee, charge, reminder'
ms.search.form: '6, 25, 440, 443, 448, 452'
ms.date: 02/09/2022
ms.author: edupont
---
# Collecte des soldes restants

La gestion des clients comprend le contrôle du règlement des montants à temps. Si des clients ont des paiements dus, vous pouvez commencer par envoyer le rapport du **Relevé client** comme rappel. Sinon, vous pouvez émettre de relances.

Vous pouvez utiliser des relances pour rappeler aux clients les soldes échus. Vous pouvez également utiliser les rappels pour calculer les frais financiers tels que les intérêts ou les frais et les inclure dans le rappel. Utilisez les factures d'intérêts pour débiter des clients d'intérêts ou de frais sans leur rappeler les montants échus.

## Relevés

À partir de la fiche client, vous pouvez créer un relevé avec les transactions de ce client avec vous. Ensuite, vous envoyez au client le fichier PDF généré. Sinon, utilisez le rapport **Relevé client** pour envoyer à vos clients un aperçu de leur activité avec vous. Le relevé client peut être envoyé à Excel pour un traitement ultérieur.  

### Pour envoyer le rapport Relevé client

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 10.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Relevé client**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans **Options sortie**, sélectionnez la manière dont l'état est envoyé au client.

> [!NOTE]
> Si vous utilisez plusieurs devises, le rapport Relevé client est toujours imprimé dans la devise du client. La dernière date dans une période de déclaration est également utilisée comme date de relevé et cumul date, si le cumul est inclus.

## Rappels

[!INCLUDE [receivables-reminders](includes/receivables-reminders.md)]

## Frais financiers

Lorsqu'un client n'effectue pas son paiement à la date d'échéance, des frais financiers peuvent être calculés automatiquement et ajoutés aux montants échus sur le compte du client. Vous pouvez informer le client des frais ajoutés en lui envoyant une facture d'intérêts.  

> [!NOTE]  
> Les notes de frais financiers permettent de calculer les intérêts et les frais financiers et d'en informer vos clients sans leur rappeler les paiements échus. Vous pouvez également calculer les intérêts sur les paiements échus lorsque vous créez des relances.  

Pour pouvoir créer des notes de frais financiers, vous devez configurer des modalités. Pour plus d’informations, voir [Configurer les modalités de frais financiers](finance-setup-finance-charges.md).  

Vous pouvez créer manuellement une note de frais financiers pour un client particulier et renseigner les lignes automatiquement. Vous pouvez également utiliser la tâche de fonction **Créer factures d'intérêts** pour créer des factures d'intérêts pour tous les clients ayant des soldes échus ou pour une sélection de clients ayant des soldes échus.  

Une fois que vous avez créé les factures d'intérêts, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque facture d'intérêts est déterminé par les conditions intérêts de retard de la colonne **Désignation** de chaque ligne. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mise à jour du texte des intérêts de retard**.  

Une fois que vous avez créé des notes de frais financiers et effectué toutes les modifications requises, vous pouvez imprimer les rapports de test ou émettre des notes de frais financiers; en général par courriel.

### Pour créer manuellement des notes de frais financiers

Une note de frais financiers ressemble à une facture. Vous pouvez renseigner un en-tête manuellement et faire renseigner les lignes, ou créer des factures d'intérêts automatiquement pour tous les clients.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de frais financiers**, puis sélectionnez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins.  
3. Sélectionnez **Proposer lignes fact. intérêts**.
4. Sur la page **Proposer lignes note de frais financiers**, définissez un filtre sur le raccourci **Écriture client** si vous souhaitez créer des notes de frais financiers uniquement pour des écritures spécifiques.

    > [!NOTE]
    > Même s'ils sont répertoriés, la sélection des champs **Paiement** et **Note de crédit** comme filtres de **Type de document** n'a aucun effet, car la fonction **Proposer lignes note de frais financiers** ne gère que les montants positifs.
5.  Pour démarrer le traitement en lot, cliquez sur le bouton **OK**.  

### Pour mettre à jour des textes de notes de frais financiers  
Dans certains cas, vous pouvez modifier les textes début et fin définis pour les modalités de frais financiers. Si vous le faites au moment où vous avez créé, mais pas encore émis, les factures d'intérêts, vous pouvez mettre à jour ces factures avec le texte modifié.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Note de frais financiers**, puis sélectionnez le lien associé.  
2. ouvrez la facture d'intérêts dont vous souhaitez modifier le texte, puis sélectionnez **MAJ texte fact. d'intérêts**.
3. Sur la page **Mettre à jour texte frais financiers**, vous pouvez définir un filtre pour mettre à jour plusieurs notes.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.  

### Pour émettre des factures d'intérêts
Une fois que vous avez créé des factures d'intérêts et effectué toutes les modifications requises, vous pouvez effectuer des impressions test ou émettre des factures d'intérêts.

Lorsqu'un rappel est émis, les écritures sont reportées selon les spécifications sur la page **Modalités de frais financiers**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration sur la page **Groupes report client** détermine les comptes qui seront utilisés.

Pour chaque écriture client de la note de frais financiers, une écriture est créée sur la page **Écritures rappel/frais financiers**.

Si les cases à cocher **Reporter intérêts** ou **Reporter frais supplémentaires** sont activées sur la page **Modalités de frais financiers**, les écritures suivantes sont aussi créées :

- Une écriture sur la page **Écritures client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre une note de frais financiers peut créer des écritures de TVA.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de frais financiers**, puis sélectionnez le lien associé.
2. Sélectionnez la facture concernée, puis cliquez sur l'action **Emettre**.
3. Sur la page **Émettre notes de frais financiers**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

La note de frais financiers est imprimée pour être envoyée à une adresse de courriel spécifiée en tant que pièce jointe PDF.

### Pour annuler une note de frais financiers émise
Si des notes de frais financiers ont été émises par erreur, vous pouvez les annuler avant leur envoi. Vous pouvez les annuler une par une ou par lots.
1. Sur la page **Notes de frais financiers émises**, sélectionnez une ou plusieurs lignes pour les notes de frais financiers émises que vous souhaitez annuler, puis choisissez l'action **Annuler**.
2. Sur la page **Annuler les notes de frais financiers émises**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

### Pour afficher les écritures rappel et note de frais financiers  
Lorsque vous émettez un rappel, une écriture rappel est créée sur la page **Écritures rappel/frais financiers** pour chaque ligne rappel contenant une écriture client. Vous pouvez ensuite obtenir un aperçu des écritures rappel créées pour un client spécifique.    
1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 5.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.  
2. Ouvrez la fiche client appropriée, puis sélectionnez l'action **Écritures comptables**.
3. Sur la page **Écritures client**, cliquez sur la ligne de l'écriture pour laquelle vous souhaitez visualiser les écritures rappel, puis sélectionnez l'action **Écritures rappel/frais financiers**.

## Taux d'intérêt multiples

[!INCLUDE [multiple-interest-rates-def](includes/multiple-interest-rates-def.md)] Pour plus d’informations, reportez vous à [Paramétrer plusieurs taux d’intérêt](finance-how-to-set-up-multiple-interest-rates.md).  

## Voir la [formation Microsoft](/training/paths/process-financial-periodic-activities-dynamics-365-business-central/) associée

## Voir aussi

[Configurer les niveaux et modalités de rappel](finance-setup-reminders.md)  
[Configurer les modalités de frais financiers](finance-setup-finance-charges.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
