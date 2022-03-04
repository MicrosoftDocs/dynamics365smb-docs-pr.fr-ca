---
title: Configurer le plan comptable (contient une vidéo)
description: Le plan comptable affiche les comptes généraux qui stockent vos données financières. Vous pouvez modifier les comptes par défaut dans le plan comptable, et vous pouvez ajouter de nouveaux comptes.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: COA, cha of acc
ms.search.form: 16, 17, 18, 118, 386, 391
ms.date: 06/22/2021
ms.author: edupont
ms.openlocfilehash: 3ddb1a5612eb4a2c060357b32e8209accdda7349
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8147632"
---
# <a name="setting-up-or-changing-the-chart-of-accounts"></a>Configuration ou modification du plan comptable

Le plan comptable affiche les comptes généraux qui stockent vos données financières. [!INCLUDE[prod_short](includes/prod_short.md)] inclut un plan comptable standard prêt à prendre en charge votre société.
Cependant, vous pouvez modifier les comptes par défaut, et vous pouvez ajouter de nouveaux comptes.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE43KO9?rel=0]

## <a name="adding-or-changing-accounts"></a>Ajout ou modification de comptes

À partir du plan comptable, vous pouvez ouvrir chaque compte du grand livre et ajouter ou modifier des paramètres. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

Vous pouvez, au besoin, utiliser plusieurs lignes pour le nom d’un compte GL. Sur la page **Fiche compte du grand livre**, dans le groupe **Compte**, choisissez **Textes étendus**, puis remplissez une ou plusieurs lignes avec le texte à copier et le nom du compte.  

Pour les comptes de type **Total**, vous devez renseigner le champ **Totalisation**. Pour les comptes de type **Fin total**, ce champ est renseigné automatiquement par la fonction Décaler. Après avoir configuré tous les comptes, choisissez l’action **Traiter**, puis choisissez **Décaler charte de comptes**.  

> [!IMPORTANT]
> Si vous avez entré des définitions dans les champs **Totalisation** pour les comptes de type **Fin total** avant d’exécuter la fonction de décalage, vous devez les entrer à nouveau car cette fonction remplace les valeurs de tous les champs **Fin total**.

## <a name="deleting-accounts"></a>Suppression des comptes

Vous pouvez supprimer un compte GL. Toutefois, avant que de le supprimer, les conditions suivantes doivent être réunies :  

* Le solde du compte doit être nul.  
* Le champ **Perm. sup. ctes gr. liv. avant** doit être défini sur la page **Configuration du grand livre**, et le compte ne doit pas comporter d'écritures à cette date ou après celle-ci.  
* Si le champ **Vérifier utilisation cpte GL** de la page **Configuration du grand livre** est sélectionné, le compte ne doit pas être utilisé dans les groupes de report ni dans la configuration de report.  

[!INCLUDE[prod_short](includes/prod_short.md)] vous empêchera de supprimer un compte général qui stocke les données nécessaires au plan comptable.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/chart-accounts-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Le grand livre et le plan comptable](finance-general-ledger.md)  
[Rapprochement de comptes bancaires](bank-manage-bank-accounts.md)  
[Utilisation des dimensions](finance-dimensions.md)  
[Importation des données à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Utilisation des tableaux d'analyse](bi-how-work-account-schedule.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fermer les comptes état des résultats dans la version française](LocalFunctionality/France/how-to-close-income-statement-accounts.md)  
[Imprimer les états des résultats dans la version australienne](LocalFunctionality/Australia/how-to-print-income-statements.md)  
[Imprimer les états des résultats dans la version néo-zélandaise](LocalFunctionality/NewZealand/how-to-print-income-statements.md)  
[Configurer et fermer les soldes d’état des résultats dans la version espagnole](LocalFunctionality/Spain/how-to-set-up-and-close-income-statement-balances.md)  
[Décaler et valider la chartes de comptes dans la version espagnole](LocalFunctionality/Spain/how-to-indent-and-validate-chart-of-accounts.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]