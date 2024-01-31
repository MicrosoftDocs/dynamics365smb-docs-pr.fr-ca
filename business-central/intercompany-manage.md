---
title: Gestion des transactions intersociétés
description: 'Avec la fonctionnalité Intercompagnie, vous pouvez simplifier les transactions et processus commerciaux entre les compagnies de la même organisation.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bhielse
ms.topic: conceptual
ms.date: 02/06/2023
ms.custom: bap-template
ms.search.keywords: 'IC, group, consolidation, affiliate, subsidiary'
ms.search.form: '605,'
ms.service: dynamics-365-business-central
---
# Gestion des transactions intersociétés

Les entreprises ayant plus d’une entité juridique avec des fonctions comptables distinctes peuvent bénéficier de transactions intersociétés. Par exemple, il est utile pour les entreprises qui ont des filiales sur plusieurs marchés ou régions internationaux. Ou, une organisation peut comprendre plusieurs compagnies, mais pourrait ne pas disposer du nombre équivalent d’équipes comptables et administratives. Les transactions intercompagnies vous permettent de simplifier et de rationaliser les processus et les transactions commerciaux entre les compagnies dans le cadre du partenariat intercompagnie.

Lorsque vous avez spécifié les relations client et fournisseur pour les transactions intersociétés, les partenaires saisissent les informations une seule fois dans les documents de vente et d’achat. Un document correspondant est créé chez l’autre partenaire impliqué dans la transaction. Les fonctionnalités de mappage pour le plan comptable et les dimensions permettent de veiller à ce que les informations apparaissent aux bons endroits.  

La fonctionnalité Intersociétés offre quatre grands avantages :  

* Productivité accrue résultant du gain de temps et de la simplification des transactions  
* Possibilité d’erreur réduite grâce à une saisie unique d’informations et de mises à jour automatisées à l’échelle du système  
* Piste d'audit et visibilité complètes des activités commerciales et des historiques de transactions  
* Transactions efficaces, rentables avec des filiales et des succursales  

## Rationaliser le flux des activités commerciales  

Les transactions intercompagnies vous permettent de distribuer des documents vente et achat, ainsi que des écritures journal général à l’ensemble de vos bureaux satellites, représentations commerciales ou succursales depuis le programme. La distribution des transactions permet de gagner du temps et d’augmenter l’efficacité dans toute l’organisation en réduisant la saisie de données. Il réduit le besoin d’envoyer, de recevoir, d’imprimer et d’archiver des documents de vente et d’achat.  

Vous contrôlez totalement tous les documents de transaction. Par exemple, vous pouvez rejeter un document qui vous a été envoyé et, de cette manière, utiliser les actions **Inverser des reports journal** et **Annuler les réceptions/envois** incorrects. Ou bien, lorsque vous faites un achat à une compagnie partenaire ou une filiale, vous pouvez mettre à jour le bon de commande tant que la compagnie vendeuse n’a pas livré de biens.  

Lorsque vous entrez une transaction, vous n’avez pas besoin de spécifier les comptes à utiliser. Vous choisissez simplement le partenaire intercompagnie. La fonctionnalité intercompagnie crée des lignes journaux comptabilité qui entraînent un équilibrage des lois des deux compagnies impliquées dans une transaction. Dans Clients et fournisseurs, vous affectez un code partenaire intercompagnie à tout client ou fournisseur. À partir de ce moment, toutes les commandes et factures des transactions entre ces compagnies produisent des documents correspondants dans la compagnie partenaire. Le résultat est des comptes correctement équilibrés.  

La fonctionnalité Intersociétés se concentre sur les documents de vente et d’achat et les lignes du journal général, et permet des transactions entre plusieurs bases de données [!INCLUDE [prod_short](includes/prod_short.md)]. Par exemple :

* Dans différents pays/régions
* Plusieurs devises
* Différents plans comptables
* Différentes dimensions
* Différents numéros d’article  

Les transactions intersociétés utilisent plusieurs types d’écritures et de documents :  

* Écritures du journal général
* Commandes achat et documents de vente
* Factures achat et vente
* Notes de crédit
* Retours

Lorsque vous configurez les transactions intercompagnies, vous créez une liste de partenaires intercompagnies, un plan comptable intercompagnie et des dimensions intercompagnies. Ensuite, vous pouvez créer des transactions dans les journaux comptables intercompagnies.

> [!NOTE]
> Le journal comptable en lui-même n’inclut pas les devises. Elle convertit tous les montants dans la devise locale au taux de change actuel.

Après avoir paramétré vos partenaires commerciaux comme clients et fournisseurs, et leur avoir affecté des codes partenaire intercompagnie, ils peuvent échanger des documents achat et vente intercompagnies, notamment des articles et des frais annexes. 

> [!NOTE]
> Les compagnies ne peuvent pas utiliser la fonctionnalité Intercompagnie pour échanger tous les types de données. Les factures achat ne sont pas soumises aux partenaires commerciaux via des processus intersociétés. Mais les factures vente soumises via des processus intercompagnies seront créées en tant que factures achat dans la compagnie destinataire.

La consolidation des données financières peut être particulièrement appropriée pour les processus intersociétés. Pour plus d'informations, voir [Consolidation des données financières de plusieurs compagnies](finance-consolidated-company-reporting.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

|Pour |Voir|
|---|---|
|Créez vos fournisseurs et vos clients intersociétés en tant que partenaires et configurez un plan comptable intersociétés.|[Configuration des fonctionnalités intersociétés](intercompany-how-setup.md)|
|Les documents ou journaux intercompagnies permettent de reporter les transactions effectuées avec vos partenaires intercompagnies.|[Utiliser les documents et les journaux intersociétés](intercompany-how-work-documents-journals.md)|
|Organisez et traitez les transactions entrantes et sortantes que vous échangez avec vos partenaires intersociétés.|[Gérer la boîte de réception et la boîte d'envoi intersociétés](intercompany-how-manage-intercompany-inbox.md)|
|Utilisez les transactions intercompagnies pour répartir les coûts entre les compagnies partenaires.|[Allouer les coûts aux partenaires intercompagnie](intercompany-allocate-costs.md)|

## Voir aussi

[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
