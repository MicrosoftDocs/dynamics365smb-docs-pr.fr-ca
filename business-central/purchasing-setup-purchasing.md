---
title: Aperçu des tâches permettant de paramétrer vos achats
description: Décrit les tâches permettant de définir les stratégies d'approvisionnement de votre compagnie et de déterminer vos processus d'achat.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: 'procurement, supply, vendor order'
ms.search.form: '175, 176, 177, 178, 456, 460, 5727, 5729'
ms.date: 06/10/2024
ms.service: dynamics-365-business-central
---
# <a name="setting-up-purchasing"></a>Définition des achats

Avant de pouvoir gérer les processus achat, vous devez configurer les règles et valeurs qui définissent les stratégies d'achat de la compagnie.

Vous devez définir la configuration générale sur la page **Configuration achats**, ce qui se fait généralement une seule fois lors de la mise en œuvre initiale. Pour en savoir plus, voir la section suivante, [Configuration des achats](#purchases-and-payables-setup).

Une série de tâches distincte en relation avec l’enregistrement de nouveaux fournisseurs consiste à enregistrer les prix spéciaux ou les ententes d’escompte établies avec chaque fournisseur.

Les configurations relatives à la finance, telles que les modes de règlement et les devises, sont traitées dans la section Configuration financière. En savoir plus sur [Configurer Finance](finance-setup-finance.md). De même, la configuration des achats liés à l’inventaire, comme les unités de mesure et les codes de suivi des articles, peut être trouvée dans la section [Configuration inventaire](inventory-setup-inventory.md).

## <a name="purchases-and-payables-setup"></a>Configuration achats

Avant d’utiliser les achats, précisez sur la page **Configuration achats** comment les valeurs d’achat sont reportées et les séries de numéros utilisées pour les fournisseurs et les documents achat.

### <a name="general-settings"></a>Paramètres généraux

Sur le raccourci **Général**, vous pouvez spécifier des options comme le mode de calcul et de report des escomptes et l’activation de la fonction d’arrondi sur les factures. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

Certains champs nécessitent une attention particulière, comme le champ **Calc. escompte fact. par code TVA** qui précise si l’escompte facture est calculé en fonction de l’identifiant fiscal ou du total de la facture. Pour en savoir plus, voir [Regrouper des groupes de report TVA dans les paramètres report TVA](finance-setup-vat.md#combine-vat-posting-groups-in-vat-posting-setups).

De même, le champ **Affectation entre devises** peut entraîner de légères différences d’arrondissement lors de l’affectation d’écritures dans différentes devises les unes aux autres. Pour en savoir plus, voir [Activer l’affectation d’écritures en devises différentes](finance-how-enable-application-ledger-entries-different-currencies.md).

En outre, certains champs modifient leur comportement ou dépendent de la façon dont d’autres champs sont définis. Par exemple, la fonctionnalité **Vérifier paiement anticipé au report** est influencée par la façon dont le champ **Mise à jour automatique de l’acompte** est défini pour vérifier les paiements anticipés en attente.

Consultez les détails sur les champs [**N° doc. ext. obligatoire**](#external-document-number) et [**Inversion coût exacte obligatoire**](#exact-cost-reversing) dans les sections plus loin dans cet article.

### <a name="number-series-settings"></a>Paramètres de séries de numéros

Sur le raccourci **Série de numéros**, vous devez spécifier les codes d’identification uniques à utiliser pour les fournisseurs, les factures et autres documents achat. La numérotation est importante non seulement pour les processus internes, mais peut également nécessiter le respect des réglementations locales. Il peut donc être utile d’envisager de configurer toutes les séries sur la page **N° de série** au préalable au lieu d’en créer de nouvelles à partir de **Configuration achats**. Pour en savoir plus, voir [Créer des séries de numéros](ui-create-number-series.md).

## <a name="external-document-number"></a>Numéro de document externe

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="exact-cost-reversing"></a>Inversion de même coût

La fonction **Coût retour identique obligatoire** aide à garantir que les marchandises retournées sont évaluées au même coût que lorsqu’elles ont été extraites de l’inventaire, à l’aide d’une application fixe plutôt que de suivre une méthode d’évaluation des coûts de type moyenne ou premier entré-premier sorti (FIFO). Pour en savoir plus, voir la section [Détails de conception : Affectation fixe](design-details-item-application.md#fixed-application). Si un coût supplémentaire est ensuite ajouté à l’achat d’origine, le programme met à jour la valeur du retour achat en conséquence.

Avec la fonctionnalité activée, une transaction de retour peut être reportée uniquement en précisant le numéro d’écriture du grand livre d’articles dans le champ **Écr. article à lettrer** sur la ligne retour achat. Par défaut, le champ ne s’affiche pas sur le raccourci **Lignes**. Comment ajouter des champs aux pages, voir [Personnaliser votre espace de travail](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

[!INCLUDE[local-functionality](includes/local-functionality.md)]

## <a name="more-purchasing-setups"></a>Plus de configurations d’achat

| À | Voir |
| --- | --- |
| Créez une fiche fournisseur pour chaque fournisseur auquel vous achetez des biens. |[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md) |
| Octroyer une priorité aux fournisseurs. |[Octroyer une priorité aux fournisseurs](purchasing-how-prioritize-vendors.md) |
| Entrez les informations de compte bancaire, y compris les codes IBAN et SWIFT, sur la carte de votre fournisseur. | [Configurer des comptes bancaires fournisseur](purchasing-how-set-up-vendors-bank-accounts.md) |
| Configurez des acheteurs, affectez-leur des fournisseurs et des codes pour suivre les statistiques. |[Configurer les acheteurs](purchasing-how-setup-purchasers.md) |
| Entrez les différents escomptes et prix spéciaux que vous accordent les fournisseurs en fonction de l’article, des quantités et/ou de la date. |[Enregistrer des accords sur les prix d'achat, les remises et les paiements](purchasing-how-record-purchase-price-discount-payment-agreements.md) |
| Définissez ce que vous payez pour les articles et services achetés par votre compagnie.  | [Configurer les prix et les escomptes](across-prices-and-discounts.md) |
| Créez des lignes standard à insérer sur les documents d'achat récurrents. | [Configurer des lignes achat récurrentes](purchasing-how-work-recurring-purchase-lines.md) |
| Créez des séquences de tâches pour connecter les processus exécutés par différents utilisateurs, tels que la demande et l'approbation des bons de commande. | [Configurer les flux de travail d’approbation achat](across-set-up-workflows.md) |
| Gérez les interactions commerciales avec vos fournisseurs, importez les documents de facturation reçus et enregistrez de nouveaux fournisseurs à l’aide du client de courriel Outlook. | [Configurer le complément Business Central pour Outlook](admin-outlook.md) |
| Examinez les reçus de dépenses, convertissez les documents papier et électroniques en lignes de journal et numérisez les factures papier des fournisseurs. | [Configurer des documents entrants](across-how-setup-income-documents.md) |
| Spécifiez les rapports par défaut à utiliser pour différents types de documents. |[Sélection des rapports dans Business Central](across-report-selections.md)|
|Spécifiez si les utilisateurs sont autorisés à reporter des factures achat et s’ils doivent les reporter avec une livraison. |[Définir une stratégie de report des factures pour les utilisateurs](admin-setup-invoice-posting-policy.md)|

## <a name="see-also"></a>Voir aussi .

[Procédure d'achat](purchasing-manage-purchasing.md)  
[Présentation de la configuration](setup.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
