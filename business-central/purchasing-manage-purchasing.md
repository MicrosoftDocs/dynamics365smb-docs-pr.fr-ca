---
title: Aperçu des tâches permettant de gérer vos achats
description: 'Décrit les tâches permettant de gérer vos processus d''achat ou d''approvisionnement, y compris le fonctionnement des factures achat et des commandes achat.'
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: 'procurement, supply, vendor order'
ms.search.form: '460, 9307'
ms.date: 03/21/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="purchasing"></a>Procédure d'achat

Vous créez une facture achat ou un bon de commande pour enregistrer le coût d'achats et suivre les créances. Si vous devez contrôler un inventaire, les factures achat sont également utilisées pour mettre à jour les niveaux d'inventaire de manière dynamique afin que vous puissiez réduire vos coûts d'inventaire et fournir un meilleur service au client. Le prix d'achat, notamment les frais de service, et les valeurs d'inventaire qui résultent du report des factures achat contribuent aux chiffres du profit et à d'autres KPI financiers sur votre Tableau de bord.

Vous devez utiliser des bons de commande si votre processus d’achat exige que vous enregistriez des réceptions partielles d’une quantité de commande, par exemple, si la quantité totale n’était pas disponible auprès du fournisseur. Si vous commercialisez des articles en les livrant directement depuis votre fournisseur auprès de votre client, vous devez également utiliser les bons de commande. Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md). Pour tous les autres aspects, les commandes achat fonctionnent de la même manière que les factures achat.

Les factures achat peuvent être créées automatiquement en utilisant le service de reconnaissance optique de caractères (OCR) pour convertir les factures PDF de vos fournisseurs en documents électroniques qui sont ensuite convertis en factures achat par un flux de travail. Pour utiliser cette fonctionnalité, vous devez d’abord vous inscrire au service OCR, puis effectuer diverses configurations. Pour plus d’informations, voir [Documents entrants](across-income-documents.md).

Les produits peuvent être des articles en inventaire et des services. Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).

Pour tous les processus d'achat, vous pouvez incorporer un flux de travail d'approbation, par exemple, pour exiger que les achats en grande quantité soient approuvés par le responsable de la comptabilité. Pour plus d'informations, reportez-vous à [Utilisation des flux d'approbation](across-how-use-approval-workflows.md).

Le section suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

## <a name="get-started-with-purchase-capabilities"></a>Démarrer avec les capacités achat

Avant d’acheter des marchandises, précisez comment vous souhaitez gérer les processus d’achat de votre compagnie.

|Pour...| Voir |
|---|---|
| Configurez les règles et les valeurs qui définissent les stratégies d’achat de votre compagnie. | [Configuration des achats](purchasing-setup-purchasing.md) |
| Enregistrez chaque fournisseur à qui vous achetez des biens en tant que fiche fournisseur. | [Enregistrement des nouveaux fournisseurs](purchasing-how-register-new-vendors.md) |

## <a name="purchase-analytics"></a>Analyse des achats

Cette section décrit les outils analytiques que vous pouvez utiliser pour obtenir des informations sur vos processus achats.

| Pour... | Voir |
| --- | --- |
| Découvrez les fonctionnalités d’analyse des données de achats. | [Vue d’ensemble de l’analyse achats](purchasing-analytics-overview.md) |
| Effectuez une analyse ad hoc des données de achats directement sur les pages de liste et les requêtes. | [Analyse ad hoc des données achats](ad-hoc-analysis-purchasing.md) |
| Explorez des rapports d’achat intégrés. | [Rapports achat intégrés](purchase-reports.md) |

## <a name="quote-to-order-to-purchase-invoice"></a>Devis de commande à facture de achat

Le tableau suivant décrit comment utiliser des processus de achat simples.

| À | Voir |
| --- | --- |
|Créez une devis pour refléter une demande de devis auprès de votre fournisseur, que vous pourrez ensuite convertir en bon de commande.|[Demander des devis](purchasing-how-request-quotes.md)|
| Créer une facture achat pour toutes les lignes ou pour les lignes sélectionnées sur une facture vente. |[Achat des articles pour une vente](purchasing-how-purchase-products-sale.md) |
| Créer une facture achat pour enregistrer votre entente avec un fournisseur pour acheter des biens selon certaines méthodes de livraison et de paiement. |[Enregistrement des achats](purchasing-how-record-purchases.md) |
| Découvrez comment [!INCLUDE[prod_short](includes/prod_short.md)] calcule le moment où vous devez commander un article pour le recevoir à une certaine date.|[Calcul de la date des achats](purchasing-date-calculation-for-purchases.md)|
|Comprendre ce qui se passe lorsque vous reportez des documents achat.|[Validation des achats](ui-post-purchases.md)|

Si vous avez besoin de processus de achat plus complexes, le tableau suivant répertorie les articles qui expliquent ce que vous pouvez faire avec [!INCLUDE[prod_short](includes/prod_short.md)].

| À | Voir |
| --- | --- |
| Effectuez une action sur une facture achat reportée impayée pour créer automatiquement une note de crédit et annulez la facture achat ou recréez-la pour que vous puissiez y apporter des corrections. |[Corriger ou annuler des factures vente impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md) |
| Créez une note de crédit achat pour rétablir une facture achat reportée spécifique pour indiquer quels produits vous retournez au fournisseur et quel montant règlement vous récupérez. |[Traitement des retours ou annulations d’achats](purchasing-how-process-purchase-returns-cancellations.md) |
|Gérez votre engagement envers un fournisseur à acheter de grandes quantités livrées en plusieurs livraisons sur une certaine période.|[Utiliser des bons de commande permanents](sales-how-to-create-blanket-sales-orders.md)|


## <a name="canceled-orders-refunds-and-returns"></a>Commandes annulées, remboursements et retours

Le tableau suivant décrit comment gérer les commandes annulées, les remboursements et les retours de marchandises achetés.

| À | Voir |
| --- | --- |
|Préparez la facturation de plusieurs réceptions provenant du même fournisseur en une seule fois en regroupant les réceptions sur une facture.|[Regroupement de bons de réception sur une seule facture](purchasing-how-to-combine-receipts.md)|
|Conversion, par exemple, de factures électroniques de vos fournisseurs en factures achat dans Business Central.|[Réception et conversion des documents électroniques](purchasing-how-to-receive-and-convert-electronic-documents.md)|


## <a name="other-processes-in-sales"></a>Autres processus de vente

Le tableau suivant décrit comment traiter autres des processus de achat.

| À | Voir |
| --- | --- |
|Résolvez la confusion lorsque deux enregistrements ou plus existent pour le même fournisseur.|[Fusion des enregistrements en double](sales-how-merge-duplicate-records.md)|


## <a name="external-document-numbers"></a>Numéros de document externe

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="see-also"></a>Voir aussi .

[Définition des achats](purchasing-setup-purchasing.md)  
[Enregistrement des nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Vue d’ensemble de l’analyse achats](purchasing-analytics-overview.md)   
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
