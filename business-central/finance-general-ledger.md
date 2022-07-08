---
title: Familiarisation avec le Grand livre et les COA
description: Décrit le grand livre, la chartes de comptes et les catégories de compte. Utilisez la page Configuration du grand livre pour préciser la gestion des problèmes comptables dans votre compagnie.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.search.form: 18, 20, 37, 65, 99, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158
ms.date: 01/21/2022
ms.author: edupont
ms.openlocfilehash: bb94f725c57f538f9d8704ba66e3d66e120d41d2
ms.sourcegitcommit: 00a8acc82cdc90e0d0db9d1a4f98a908944fd50a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9079152"
---
# <a name="understanding-the-general-ledger-and-the-chart-of-accounts"></a>Comprendre le grand livre et le plan comptable

Le grand livre stocke vos données financières, et le plan comptable affiche les comptes sur lesquels toutes les écritures sont reportées. [!INCLUDE[prod_short](includes/prod_short.md)] inclut un plan comptable standard prêt à prendre en charge votre société.

## <a name="general-ledger-setup-and-general-posting-setup"></a>Configuration du grand livre et configuration du report général

La configuration du grand livre est la composante principale des processus financiers car elle définit comment vous reportez les données. Deux pages jouent un rôle important dans la configuration de vos processus financiers :  

* La page **Configuration du grand livre**

    Sur la page **Configuration du grand livre**, vous spécifiez comment gérer certains problèmes comptables dans votre compagnie, par exemple :  

    * Les détails arrondissement facture  
    * Les formats d'adresse  
    * Rapports financiers  

    > [!TIP]
    > La page **Configuration du grand livre** comprend des champs génériques et des champs spécifiques à votre pays ou région. Si vous n'êtes pas sûr de la signification d'un champ, nous vous suggérons de travailler avec votre comptable pour déterminer s'il est pertinent pour votre organisation. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    Ouvrez la page [ici](https://businesscentral.dynamics.com/?page=118)
* La page **Configuration du report général**

    De même, sur la page **Configuration du report général**, vous spécifiez comment vous souhaitez configurer les combinaisons de groupes de report général marché et de report général produit. Les groupes comptabilisation mappent des entités telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat dans des comptes généraux. Saisissez une ligne pour chaque combinaison de groupes de report marché et de groupes de report produit. Mais vous pouvez également ouvrir chaque ligne dans sa propre fiche configuration report. Pour plus d'informations, voir [Configurations du groupe de report](finance-posting-groups.md).  

    > [!TIP]
    > Si vous ne pouvez pas voir les champs que vous recherchez sur la page **Configuration du report général**, utilisez la barre de défilement horizontale au bas de la page pour faire défiler l’affichage vers la droite.  

    Ouvrez la page [ici](https://businesscentral.dynamics.com/?page=314)

## <a name="the-chart-of-accounts"></a>Le plan comptable

Le plan comptable affiche tous les comptes généraux. Vous pouvez effectuer les opérations suivantes à partir du plan comptable :  

* Afficher les rapports qui affichent les écritures et les soldes.  
* Fermez votre état des résultats.  
* Ouvrez la fiche compte général pour ajouter ou modifier des paramètres.  
* Consulter la liste des groupes de report qui effectuent les reports vers ce compte.
* Afficher les soldes débit et crédit d'un seul compte  

Vous pouvez ajouter, modifier ou supprimer des comptes généraux. Toutefois, pour éviter les différences, vous ne pouvez pas supprimer un compte GL si ses données sont utilisées dans le plan comptable. De plus, à partir de la 2e vague de lancement 2022, vous pouvez également bloquer la suppression accidentelle de comptes pendant les périodes sensibles. Pour plus d’informations, voir [Suppression des comptes](finance-setup-chart-accounts.md#delete-accounts).  

## <a name="account-categories"></a>Catégories de compte

Vous pouvez personnaliser la structure de vos états financiers en mappant les comptes généraux aux catégories de comptes.  

La page **Catégories de compte du grand livre** affiche vos catégories et sous-catégories et les comptes GL qui leur sont affectés. Vous pouvez créer des sous-catégories et affecter ces catégories à des comptes existants.  

Vous créez un groupe des catégories en effectuant un décalage d'autres sous-catégories sous une ligne de la page **Catégories de compte du grand livre**. Cela vous facilite l'obtention d'une vue d'ensemble, car chaque groupement affiche un solde total. Par exemple, vous pouvez créer des sous-catégories pour différents types d'actifs puis créer des groupes des catégories pour différencier les immobilisations des actifs à court terme, par exemple.  

Vous pouvez spécifier si les comptes de chaque sous-catégorie doivent être inclus dans des types spécifiques d'états. Les catégories de compte vous aident à définir la présentation de vos états financiers.  

### <a name="example"></a>Exemple :

Par exemple, le solde relevé par défaut solde est doté d’une sous-catégorie pour la *trésorerie* dans *Actifs à court terme*. Vous souhaitez que le solde relevé tienne compte du fonds de caisse et du compte chèque, vous pouvez donc procéder comme suit :  

1. Ajouter deux nouvelles sous-catégories. :

    * Une pour le fonds de caisse  
    * Une pour votre compte courant  
2. Spécifier une autre définition de rapport **Comptes de trésorerie** pour ces sous-catégories.  
3. Effectuer une indentation sous la sous-catégorie **Trésorerie**.  

À la prochaine génération des tableaux d’analyse, votre relevé solde suivant affichera un solde total pour l’argent comptant et deux lignes avec les soldes pour le fonds de caisse et le compte chèque.  

## <a name="get-a-quick-overview"></a>Obtenir un aperçu rapide

La page **Plan comptable** affiche les comptes dans une liste hiérarchique qui offre un accès rapide aux informations clés pour chaque compte. Cependant, la liste est statique et si vous avez un grand nombre de comptes, vous devrez peut-être défiler quelque peu pour afficher les informations de différents comptes. Si vous souhaitez simplement un aperçu rapide des éléments de base, tels que les variations nettes et les soldes, la page **Vue d’ensemble du plan comptable** est une alternative utile. La disposition des colonnes sur la page est désormais la même que celle que vous trouverez sur la page **Plan comptable** (il y en a juste moins) ; vous n’aurez donc pas à vous réorienter et vous pourrez développer ou réduire les niveaux hiérarchiques pour condenser la vue. Pour faciliter le passage d’une page à l’autre, la page **Vue d’ensemble du plan comptable** est disponible à partir de la page **Plan comptable**.

## <a name="access-to-create-and-edit-accounts-and-account-categories"></a>Accès pour créer et modifier des comptes et des catégories de comptes

Dans une petite organisation, comme la compagnie de démonstration CRONUS, la plupart des utilisateurs peuvent modifier la chartes de comptes, à l’exception des utilisateurs disposant d’une licence MEMBRE D’ÉQUIPE. Cependant, dans les grandes organisations, l’accès pour modifier le plan comptable est limité selon les rôles et les autorisations. Si vous êtes administrateur ou si vous avez le rôle de *Chef d’entreprise* ou de *Comptable*, vous pouvez vérifier les autorisations de tous les utilisateurs pour vous assurer que les bonnes personnes ont accès aux tables pertinentes. Pour plus d'informations, voir [Pour afficher ou modifier les autorisations d'un utilisateur](ui-define-granular-permissions.md#to-get-an-overview-of-a-users-permissions).  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/business-central-configure-general-ledger-setup/)

## <a name="see-also"></a>Voir aussi .

[Finance](finance.md)  
[Configurer ou modifier le plan comptable](finance-setup-chart-accounts.md)  
[Veille économique](bi.md)  
[Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
