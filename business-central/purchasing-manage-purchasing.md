---
title: Aperçu des tâches permettant de gérer vos achats
description: 'Décrit les tâches permettant de gérer vos processus d''achat ou d''approvisionnement, y compris le fonctionnement des factures achat et des commandes achat.'
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'procurement, supply, vendor order'
ms.search.form: 460
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="purchasing"></a>Procédure d'achat
Vous créez une facture achat ou un bon de commande pour enregistrer le coût d'achats et suivre les créances. Si vous devez contrôler un inventaire, les factures achat sont également utilisées pour mettre à jour les niveaux d'inventaire de manière dynamique afin que vous puissiez réduire vos coûts d'inventaire et fournir un meilleur service au client. Le prix d'achat, notamment les frais de service, et les valeurs d'inventaire qui résultent du report des factures achat contribuent aux chiffres du profit et à d'autres KPI financiers sur votre Tableau de bord.

Vous devez utiliser les commandes achat si votre processus de vente exige que vous enregistriez des réceptions partielles d'une quantité de commande, par exemple, si la quantité totale n'était pas disponible auprès du fournisseur. Si vous commercialisez des articles en les livrant directement depuis votre fournisseur auprès de votre client, vous devez également utiliser les bons de commande. Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md). Pour tous les autres aspects, les commandes achat fonctionnent de la même manière que les factures achat.

Les factures achat peuvent être créées automatiquement en utilisant le service de reconnaissance optique de caractères (OCR) pour convertir les factures PDF de vos fournisseurs en documents électroniques qui sont ensuite convertis en factures achat par un flux de travail. Pour utiliser cette fonctionnalité, vous devez d'abord vous inscrire au service OCR, puis effectuer diverses configurations. Pour plus d'informations, voir la section [Traiter les documents entrants](across-process-income-documents.md).      

Les produits peuvent être des articles en inventaire et des services. Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).

Pour tous les processus d'achat, vous pouvez incorporer un flux de travail d'approbation, par exemple, pour exiger que les achats en grande quantité soient approuvés par le responsable de la comptabilité. Pour plus d'informations, reportez-vous à [Procédure : utilisation des flux d'approbation](across-how-use-approval-workflows.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Créer une facture achat pour enregistrer votre entente avec un fournisseur pour acheter des biens selon certaines méthodes de livraison et de paiement. |[Enregistrer des achats](purchasing-how-record-purchases.md) |
|Créez une devis pour refléter une demande de devis auprès de votre fournisseur, que vous pourrez ensuite convertir en bon de commande.|[Demander des devis](purchasing-how-request-quotes.md)|
| Créer une facture achat pour toutes les lignes ou pour les lignes sélectionnées sur une facture vente. |[Acheter des articles pour une vente](purchasing-how-purchase-products-sale.md) |
|Comprendre ce qui se passe lorsque vous reportez des documents achat.|[Report des achats](ui-post-purchases.md)|
| Effectuez une action sur une facture achat reportée impayée pour créer automatiquement une note de crédit et annulez la facture achat ou recréez-la pour que vous puissiez y apporter des corrections. |[Corriger ou annuler des factures vente impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md) |
| Créez une note de crédit achat pour rétablir une facture achat reportée spécifique pour indiquer quels produits vous retournez au fournisseur et quel montant règlement vous récupérez. |[Traiter les retours ou annulations d'achats](purchasing-how-register-new-vendors.md) |
|Préparez la facturation de plusieurs réceptions provenant du même fournisseur en une seule fois en regroupant les réceptions sur une facture.|[Regroupement de bons de réception sur une seule facture](purchasing-how-to-combine-receipts.md)|
|Conversion, par exemple, de factures électroniques de vos fournisseurs en factures achat dans Business Central.|[Recevoir et convertir des documents électroniques](purchasing-how-to-receive-and-convert-electronic-documents.md)|
| Découvrez comment [!INCLUDE[prod_short](includes/prod_short.md)] calcule le moment où vous devez commander un article pour le recevoir à une certaine date.|[Calcul de la date des achats](purchasing-date-calculation-for-purchases.md)|
|Résolvez la confusion lorsque deux enregistrements ou plus existent pour le même fournisseur.|[Fusionner l'enregistrement des doublons](sales-how-merge-duplicate-records.md)|
|Gérez votre engagement envers un fournisseur à acheter de grandes quantités livrées en plusieurs livraisons sur une certaine période.|[Utiliser des commandes permanentes achats](sales-how-to-create-blanket-sales-orders.md)|

## <a name="external-document-numbers"></a>Numéros de document externe

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/purchase-items-services-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi
[Définition des achats](purchasing-setup-purchasing.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Gestion des projets](projects-manage-projects.md)    
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]