---
title: Aperçu des tâches permettant de gérer vos ventes
description: "Découvrez comment utiliser les services de Business\_Central pour gérer les activités de vente avec vos clients avec des factures de vente, des commandes, des devis et plus encore."
author: SorenGP
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'trade, sell'
ms.search.form: 253
ms.date: 09/02/2022
ms.author: edupont
---
# <a name="sales"></a>Vente

Vous créez une facture vente ou un document de vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines méthodes de livraison et de paiement.

Vous devez utiliser des documents de vente si votre processus de vente exige que vous livriez des parties d’une quantité de commande, par exemple, si la quantité totale est pas disponible d’un coup. Si vous commercialisez des articles en les livrant directement du fournisseur au client, vous devez également utiliser les documents de vente. Pour tous les autres aspects, les documents de vente fonctionnent de la même manière que les factures vente. Avec les documents de vente, vous pouvez également utiliser la fonctionnalité de promesse de commande pour indiquer les dates de livraison certaines à vos clients.  

Vous pouvez négocier avec le client en créant d'abord un devis, que vous pouvez convertir en facture vente ou en document de vente lorsque vous êtes d'accord sur la vente. Une fois que le client a confirmé l'entente, vous pouvez envoyer une confirmation de commande pour enregistrer votre obligation de fournir les produits comme convenu.

Vous pouvez facilement corriger ou annuler une facture vente reportée avant qu'elle ne soit payée. Cela est utile si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande. Si la facture vente reportée est payée, vous devez créer une note de crédit vente ou un retour vente pour inverser la vente.

Les pratiques recommandées en matière de vente et de marketing reposent toutes sur la prise de décisions appropriées au bon moment. La fonctionnalité Marketing de [!INCLUDE[prod_short](includes/prod_short.md)] fournit une vue d’ensemble précise et opportune de vos informations de contact afin d’offrir des services à vos prospects de manière plus efficace et d’accroître la satisfaction de la clientèle. En savoir plus sur [Gestion des relations](marketing-relationship-management.md).

Si vous utilisez Microsoft Dynamics 365 Sales for Customer Engagement, vous pouvez bénéficier de l’intégration parfaite dans le processus allant du prospect à l’encaissement à l’aide de Business Central pour les activités principales, telles que le traitement des commandes, la gestion de l'inventaire et de vos finances. En savoir plus, [Utiliser Dynamics 365 Sales depuis Business Central](marketing-integrate-dynamicscrm.md).

Dans les environnements d'entreprise où le client doit payer avant la livraison des produits vendus (par exemple la vente au détail), vous devez attendre la réception du paiement avant de fournir les produits. Dans la plupart des cas, vous traitez les paiements entrants plusieurs semaines après la livraison en affectant les paiements à leurs factures vente reportées et impayées associées. Pour plus d'informations, voir [Rapprocher les paiements à l’aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md).

Les documents de vente peuvent être envoyés sous forme de fichiers PDF joints au courriel. Le corps du message contient un extrait du document de vente, comme les produits, le montant total et un lien vers le site Paypal. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).

Pour tous les processus de vente, vous pouvez incorporer un flux de travail d'approbation, par exemple, pour exiger que les ventes en grande quantité à certains clients soient approuvés par le responsable de la comptabilité. En savoir plus sur [Utiliser des flux de travail](across-use-workflows.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

| À | Voir |
| --- | --- |
|Créer une fiche client pour chaque client auquel vous vendez des éléments.|[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)|
| Créer un devis dans lequel vous proposer des biens selon des conditions négociables avant de convertir le devis en facture vente. |[Créer des devis](sales-how-make-offers.md) |
| Créez une facture vente pour enregistrer votre entente avec un client afin de vendre certains produits selon certaines modalités de paiement et de livraison. |[Facturer des ventes](sales-how-invoice-sales.md) |
| Traiter un document de vente qui implique une livraison partielle ou un envoi direct. |[Vendre des produits](sales-how-sell-products.md) |
|Comprendre ce qui se passe lorsque vous reportez des documents vente.|[Validation des ventes](ui-post-sales.md)|
|Se préparer à prélever des articles pour la livraison.|[Imprimer la liste des prélèvements](sales-how-print-picking-list.md)|
| Exécutez un document de vente avec plusieurs livraisons partielles. | [Traiter les livraisons partielles](sales-how-send-partial-shipments.md) |
|Paramétrez les lignes vente ou achat standard que vous pouvez rapidement insérer dans les documents, par exemple, pour les ordres de réapprovisionnement récurrents.|[Créer des lignes ventes et achat récurrentes](sales-how-work-standard-lines.md)|  
| Lier un document de vente à un bon de commande pour vendre un article qui sera livré directement de votre fournisseur à votre client. |[Effectuer des livraisons directes](sales-how-drop-shipment.md) |
|Faites livrer par un fournisseur un article de catalogue à votre entrepôt pour pouvoir le livrer à votre client.|[Créer des commandes spéciales](sales-how-to-create-special-orders.md)|
| Effectuez une action sur une facture vente reportée impayée pour créer automatiquement une note de crédit et annulez la facture vente ou recréez-la pour que vous puissiez y apporter des corrections. |[Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md) |
| Créez une note de crédit vente pour rétablir une facture vente reportée spécifique pour indiquer quels produits sont retournés par le client et quel montant règlement vous rembourserez. |[Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md) |
|Gérez l'engagement de vos clients à acheter de grandes quantités livrées en plusieurs livraisons réparties au fil du temps.|[Utiliser des commandes permanentes ventes](sales-how-to-create-blanket-sales-orders.md)|
|Vendez les éléments d'assemblage qui ne sont pas disponibles actuellement en créant un ordre d'assemblage associé pour fournir la quantité totale ou partielle du document de vente.|[Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md)|
|Facturez un client une seule fois pour plusieurs livraisons en combinant les livraisons sur une seule facture.|[Regroupement de livraisons sur une seule facture](sales-how-to-combine-shipments-on-a-single-invoice.md)|
|Informez vos clients des dates de livraison en calculant, soit la date de simulation de délai, soit la date disponible à la vente.|[Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md)|
|Résolvez la confusion lorsque deux enregistrements ou plus existent pour le même client.|[Fusionner l'enregistrement des doublons](sales-how-merge-duplicate-records.md)|

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/sell-items-services-dynamics-365-business-central/) associée.

[Définition des ventes](sales-setup-sales.md)  
[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Gestion de projets](projects-manage-projects.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
