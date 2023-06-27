---
title: Configurer ou modifier le plan comptable (contient une vidéo)
description: 'Le plan comptable affiche les comptes généraux qui stockent vos données financières. Vous pouvez modifier les comptes par défaut dans le plan comptable, et vous pouvez ajouter de nouveaux comptes.'
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'COA, cha of acc'
ms.search.form: '16, 17, 18, 118, 386, 391'
ms.date: 01/21/2022
ms.author: edupont
---
# <a name="set-up-or-change-the-chart-of-accounts" />Configurer ou modifier le plan comptable

Le plan comptable affiche les comptes généraux qui stockent vos données financières. [!INCLUDE[prod_short](includes/prod_short.md)] inclut un plan comptable standard prêt à prendre en charge votre société. Vous pouvez, cependant, modifier les comptes par défaut, et vous pouvez ajouter de nouveaux comptes.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE43KO9?rel=0]

## <a name="add-or-change-accounts" />Ajouter ou modifier les comptes

À partir du plan comptable, vous pouvez ouvrir chaque compte GL et ajouter ou modifier des paramètres. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] 

Vous pouvez, au besoin, utiliser plusieurs lignes pour le nom d’un compte GL. Sur la page **Fiche compte GL**, dans le groupe **Compte**, choisissez **Textes étendus**, puis remplissez une ou plusieurs lignes avec le texte à copier et le nom du compte.  

Pour les comptes de type **Total**, vous devez renseigner le champ **Totalisation**. Pour les comptes de type **Fin total**, ce champ est renseigné automatiquement par la fonction Décaler. Après avoir configuré tous les comptes, choisissez l’action **Traiter**, puis choisissez **Décaler plan comptable**.  

> [!IMPORTANT]
> Si vous avez entré des définitions dans les champs **Totalisation** pour les comptes de type **Fin total** avant d’exécuter la fonction de décalage, vous devez les entrer à nouveau car cette fonction remplace les valeurs de tous les champs **Fin total**.

## <a name="delete-accounts" />Supprimer les comptes

Vous pouvez supprimer un compte GL. Toutefois, avant que de le supprimer, les conditions suivantes doivent être réunies :  

* Le solde du compte doit être nul.  
* Le champ **Perm. sup. ctes gr. liv. avant** doit être défini sur la page **Configuration du grand livre**, et le compte ne doit pas comporter d'écritures à cette date ou après celle-ci.  
* Si le champ **Vérifier utilisation cpte GL** de la page **Configuration du grand livre** est sélectionné, le compte ne doit pas être utilisé dans les groupes de report ni dans la configuration de report.  

[!INCLUDE[prod_short](includes/prod_short.md)] vous empêche de supprimer un compte GL qui stocke les données nécessaires au plan comptable.  

## <a name="block-deletion-of-gl-accounts" />Bloquer la suppression des comptes du grand livre

[!INCLUDE [2022_releasewave1](includes/2022_releasewave1.md)]

La 2e vague de lancement 2022 introduit une protection supplémentaire contre la suppression accidentelle de comptes du grand livre, même dans les scénarios où les critères sont satisfaits.  

Un nouveau champ, **Bloquer la suppression des comptes GL**, est ajouté à la page **Configuration du grand livre**. Quand le champ Bloquer la suppression des comptes GL est défini sur *Oui*, vous ne pouvez pas supprimer les comptes GL qui ont des écritures postérieures à la date indiquée dans le champ **Vérifier suppr. cpte GL après**. Pour supprimer un compte de ce type, un utilisateur ayant accès à la page **Configuration du grand livre** doit d’abord définir ce champ sur *Non*.  

Le fait de régler le champ **Bloquer la suppression des comptes GL** sur *Oui* peut être considéré comme une pratique exemplaire, tout comme définir la date dans le champ **Vérifier suppr. cpte GL après**, par exemple à la date à laquelle vous devez stocker vos données financières.  

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/modules/chart-accounts-dynamics-365-business-central/index) associée

## <a name="see-also" />Voir aussi

[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Rapprochement de comptes bancaires](bank-manage-bank-accounts.md)  
[Utiliser des dimensions](finance-dimensions.md)  
[Importation des données à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Utiliser les rapports financiers](bi-how-work-account-schedule.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fermer les comptes état des résultats dans la version française](LocalFunctionality/France/how-to-close-income-statement-accounts.md)  
[Imprimer les états des résultats dans la version australienne](LocalFunctionality/Australia/how-to-print-income-statements.md)  
[Imprimer les états des résultats dans la version néo-zélandaise](LocalFunctionality/NewZealand/how-to-print-income-statements.md)  
[Configurer et fermer les soldes d’état des résultats dans la version espagnole](LocalFunctionality/Spain/how-to-set-up-and-close-income-statement-balances.md)  
[Décaler et valider la chartes de comptes dans la version espagnole](LocalFunctionality/Spain/how-to-indent-and-validate-chart-of-accounts.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
