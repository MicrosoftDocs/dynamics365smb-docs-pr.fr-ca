---
title: Familiarisation avec le Grand livre et les COA
description: 'Décrit le grand livre, le plan comptable et les catégories de compte. Utilisez la page Configuration du grand livre pour préciser la gestion des problèmes comptables dans votre compagnie.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'analysis, history, track'
ms.search.form: '18, 20, 37, 65, 99, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158'
ms.date: 12/19/2023
ms.author: bholtorf
---
# <a name="understanding-the-general-ledger-and-chart-of-accounts"></a>Comprendre le grand livre et le plan comptable

Le grand livre (GL) stocke vos données financières, et le plan comptable (COA) affiche les comptes sur lesquels toutes les écritures sont reportées. [!INCLUDE[prod_short](includes/prod_short.md)] inclut un plan comptable standard prêt à prendre en charge votre société.

## <a name="general-ledger-setup-and-general-posting-setup"></a>Configuration du grand livre et configuration du report général

La configuration du grand livre est la composante principale des processus financiers car elle définit comment vous reportez les données. Deux pages jouent un rôle particulièrement important dans la configuration de vos processus financiers :  

* La page **Configuration du grand livre**

  Sur la page **Configuration du grand livre**, vous spécifiez comment gérer certains problèmes comptables dans votre compagnie, par exemple :  

  * Les détails arrondissement facture  
  * Les formats d'adresse  
  * Rapports financiers

  > [!TIP]
  > La page **Configuration du grand livre** comprend des champs génériques et des champs spécifiques à votre pays ou région. Si vous n’êtes pas sûr de la signification d’un champ, nous vous suggérons de travailler avec votre comptable pour déterminer s’il est pertinent pour votre organisation. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

  Ouvrez la page [ici](https://businesscentral.dynamics.com/?page=118).
  
* La page **Configuration du report général**

  De même, sur la page **Configuration du report général**, vous spécifiez comment vous souhaitez configurer les combinaisons de groupes de report général marché et de report général produit. Les groupes de report mappent des entités telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat dans des comptes GL. Saisissez une ligne pour chaque combinaison de groupes de report marché et de groupes de report produit. Mais vous pouvez également ouvrir chaque ligne dans sa propre fiche configuration report. Pour en savoir plus, voir [Configurations des groupes de report](finance-posting-groups.md).  

  > [!TIP]
  > Si vous ne pouvez pas voir les champs que vous recherchez sur la page **Configuration du report général**, utilisez la barre de défilement horizontale au bas de la page pour faire défiler l’affichage vers la droite.  

  Ouvrez la page [ici](https://businesscentral.dynamics.com/?page=314).

## <a name="the-chart-of-accounts"></a>Le plan comptable

Le plan comptable affiche tous les comptes généraux. Vous pouvez effectuer les opérations suivantes à partir du plan comptable :  

* Afficher les rapports qui affichent les écritures et les soldes.  
* Fermez votre état des résultats.  
* Ouvrez la fiche compte général pour ajouter ou modifier des paramètres.  
* Consulter la liste des groupes de report pour ce compte.
* Afficher les soldes débit et crédit d’un seul compte.

Vous pouvez ajouter, modifier ou supprimer des comptes généraux. Toutefois, pour éviter les différences, vous ne pouvez pas supprimer un compte GL si ses données sont utilisées dans le plan comptable. De plus, à partir de la 2e vague de lancement 2022, vous pouvez également bloquer la suppression accidentelle de comptes pendant les périodes sensibles. Pour plus d’informations, consultez la section [Supprimer des comptes](finance-setup-chart-accounts.md#delete-accounts).  

## <a name="account-categories"></a>Catégories de compte

Vous pouvez personnaliser la structure de vos états financiers en mappant les comptes généraux aux catégories de comptes.  

La page **Catégories de compte GL** affiche vos catégories et sous-catégories et les comptes GL qui leur sont affectés. Vous pouvez créer des sous-catégories et affecter ces catégories à des comptes existants.  

Vous pouvez créer un groupe des catégories en effectuant une indentation d’autres sous-catégories sous une ligne de la page **Catégories de compte GL**. Les groupes de catégorie facilitent l’obtention d’une vue d’ensemble, car chaque groupement affiche un solde total. Par exemple, vous pouvez créer des sous-catégories pour différents types d’actifs, puis créer des groupes des catégories pour différencier les immobilisations des actifs à court terme, par exemple.  

Vous pouvez définir si des types de rapports spécifiques doivent inclure les comptes de chaque sous-catégorie. Les catégories de compte vous aident à définir la présentation de vos états financiers.  

### <a name="example"></a>Exemple :

Par exemple, le solde relevé par défaut solde est doté d’une sous-catégorie pour la *trésorerie* dans *Actifs à court terme*. Si vous souhaitez que le solde relevé tienne compte du fonds de caisse et du compte chèque, vous devez procéder comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Catégories de compte GL**, puis choisissez le lien associé.
   1. Sinon, ouvrez la page [ici](https://businesscentral.dynamics.com/?page=790).
2. Choisissez l'action **Modifier la liste**.
3. Ajoutez deux nouvelles sous-catégories : une pour le fonds de caisse, et l’autre pour le compte chèque.
   1. Sélectionnez la catégorie **Actifs à court terme**.
   2. Sélectionnez l'action **Nouveau**.
   3. Entrez le nom de la sous-catégorie dans le champ **Description**.
   4. Dans le champ **Comptes GL dans une catégorie**, sélectionnez le compte GL approprié.
   5. Dans le champ **Définition de rapport supplémentaire**, sélectionnez l’option **Comptes de trésorerie**.
4. Effectuer une indentation sous la sous-catégorie **Trésorerie**.
   1. Sélectionnez la sous-catégorie créée à l’étape 3.
   2. Sélectionnez l’action **Décaler**.
   3. Choisissez l’action **Déplacer vers le bas**.
   4. Sélectionnez l’action **Décaler** pour définir une indentation sous la sous-catégorie **Trésorerie**.

Lorsque vous sélectionnez l’action **Générer des rapports financiers** (ou la prochaine fois que le rapport sera généré), votre relevé de solde affichera les lignes suivantes :

* Solde total en espèces.
* Lignes avec soldes pour le fonds de caisse et le compte courant.  

> [!NOTE]
> Si vous créez un compte GL sans affecter de catégorie de compte, lorsque vous affectez le compte à un groupe de report, [!INCLUDE[prod_short](includes/prod_short.md)] attribue automatiquement la catégorie de compte du compte GL immédiatement au-dessus du compte dans votre plan comptable. Cependant, pour inclure le nouveau compte dans vos rapports financiers, vous devez choisir l’action **Générer des rapports financiers** sur la page **Catégories de compte GL**. Vous pouvez également ouvrir la page Fiche de compte GL, spécifier la catégorie de compte, puis régénérer votre rapport financier.

## <a name="get-a-quick-overview"></a>Obtenir un aperçu rapide

La page **Plan comptable** affiche les comptes dans une liste hiérarchique qui offre un accès rapide aux informations clés pour chaque compte. Cependant, la liste est statique et si vous avez un grand nombre de comptes, vous devrez peut-être défiler pour afficher les différents comptes. Si vous souhaitez simplement un aperçu rapide des éléments de base, tels que les variations nettes et les soldes, la page **Vue d’ensemble du plan comptable** est une alternative utile. La disposition des colonnes sur la page est maintenant la même que celle que vous trouverez sur la page **Plan comptable** (mais avec moins de colonnes), vous n’aurez donc pas à vous réorienter. Vous pouvez développer ou réduire les niveaux hiérarchiques pour condenser la vue. Pour faciliter le passage d’une page à l’autre, la page **Vue d’ensemble du plan comptable** est disponible à partir de la page **Plan comptable**.

## <a name="access-to-create-and-edit-accounts-and-account-categories"></a>Accès pour créer et modifier des comptes et des catégories de comptes

Dans une petite organisation, comme la compagnie de démonstration CRONUS, la plupart des utilisateurs peuvent modifier le plan comptable, à l’exception des utilisateurs disposant d’une licence MEMBRE D’ÉQUIPE. Cependant, les grandes organisations utilisent généralement des rôles et des autorisations d’utilisation pour limiter l’accès pour modifier le plan comptable. Si vous êtes administrateur ou si vous avez le rôle de *Gestionnaire d’activité* ou de *Comptable*, vous pouvez contrôler les autorisations utilisateur pour vous assurer que les bonnes personnes ont accès aux tables pertinentes. Pour plus d’informations, consultez la section [Pour afficher ou modifier les autorisations d’un utilisateur](ui-define-granular-permissions.md#to-get-an-overview-of-a-users-permissions).  

## <a name="see-also"></a>Voir aussi .

[Configurer ou modifier le plan comptable](finance-setup-chart-accounts.md)  
[Affectation des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md)  
[Veille économique](bi.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
