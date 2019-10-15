---
title: Utilisation de journaux généraux pour reporter directement dans le grand livre| Microsoft Docs
description: Découvrez comment utiliser les journaux pour reporter des transactions financières dans les comptes GL et dans d'autres comptes, tels que les comptes bancaires et fournisseur.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 635e53040ab9920780cd1cf05a14f6dfa17496d9
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2314974"
---
# <a name="working-with-general-journals"></a>Utilisation de feuilles comptabilité

La plupart des transactions financières sont reportées dans le grand livre via les documents commerciaux dédiés, tels que des factures achat et des documents de vente. Mais vous pouvez également traiter des activités commerciales comme l'achat, le paiement ou le remboursement des frais d'un employé en reportant des lignes journal dans les divers journaux de [!INCLUDE[d365fin](includes/d365fin_md.md)].  

La plupart des journaux sont basés sur le *Journal général*, et vous pouvez traiter toutes les transactions sur la page **Journal général**. Pour plus d'informations, voir [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).  

Par exemple, vous pouvez utiliser les dépenses de vos employés avec leurs fonds propres pour des activités professionnelles, afin de les rembourser ultérieurement. Pour plus d'informations, voir [Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md).

Mais dans de nombreux cas, vous devrez utiliser les journaux qui sont optimisées pour les types de transactions spécifiques, telles que **Journal paiement** pour enregistrer les paiements. Pour plus d'informations, voir [Enregistrer les paiements et remboursements dans le journal paiement](payables-how-post-payments-refunds.md).  

Les journaux généraux vous permettent de reporter des transactions financières directement dans les comptes GL et dans d'autres comptes tels que les comptes bancaires, client, fournisseur et employé. Le report avec un journal général crée toujours des écritures dans les comptes du grand livre. C'est le cas même lorsque, par exemple, vous reportez une ligne journal sur un compte client, parce qu'une écriture est reportée dans un compte client du grand livre via un groupe de report.

Les informations que vous saisissez dans un journal sont temporaires et peuvent être modifiées tant qu'elles sont dans le journal. Lorsque vous reportez le journal, les informations sont transférées vers des écritures de comptes individuels, où elles ne peuvent pas être modifiées. Toutefois, vous pouvez annuler l'affectation des écritures reportées et reporter des écritures d'inversion ou de correction. Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).

> [!NOTE]
> [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]  

## <a name="using-journal-templates-and-batches"></a>Utilisation de modèles et lots de journal

Il existe plusieurs modèles journal général. Chaque modèle journal est représenté par une page dédiée avec des fonctions particulières et les champs nécessaires pour la prise en charge de ces fonctions, notamment la page **Journal rapprochement paiement** qui permet de traiter les paiements bancaires et la page **Journal paiement** qui permet de payer vos fournisseurs ou de rembourser vos employés. Pour plus d'informations, voir [Exécuter des paiements](payables-make-payments.md) et [Rapprocher les paiements clients avec le journal des encaissements ou les écritures client](receivables-how-apply-sales-transactions-manually.md).

Pour chaque modèle journal, vous pouvez configurer votre propre journal personnel sous forme de lot journal. Par exemple, vous pouvez définir votre propre lot de journal pour le journal paiement doté de votre présentation et de vos paramètres personnels. Le conseil suivant est un exemple de la manière de personnaliser un journal.

> [!TIP]  
> Si vous cochez la case **Suggérer le montant contrepartie** de la ligne pour votre lot sur la page **Lots journal général**, le champ **Montant** dans, par exemple, les lignes journal général pour le même numéro de document est automatiquement prérempli avec la valeur nécessaire à la contrepartie du document. Pour plus d'informations, voir [Laisser [!INCLUDE[d365fin](includes/d365fin_md.md)] suggérer des valeurs](ui-let-system-suggest-values.md).

## <a name="understanding-main-accounts-and-balancing-accounts"></a>Compte principaux et comptes contrepartie
Si vous avez configuré des comptes de contrepartie par défaut pour les lots journal sur la page **Journaux généraux**, le compte de contrepartie sera renseigné automatiquement lorsque vous renseignez le champ **Numéro du compte**. Sinon, renseignez manuellement les champs **Numéro du compte** et **N° compte contrepartie**. Un montant positif dans le champ **Montant** est débité du compte principal et crédité dans le compte contrepartie. Un montant négatif est crédité sur le compte principal et débité du compte contrepartie.

> [!NOTE]  
>   La TVA est calculée séparément pour le compte principal et le compte de contrepartie, afin qu'ils puissent utiliser des taux de pourcentage de TVA différents.

## <a name="working-with-recurring-journals"></a>Utilisation de journaux récurrents
Un journal récurrent est un journal général contenant des champs spécifiques pour la gestion des transactions que vous reportez fréquemment avec peu ou pas de modifications comme le loyer, les abonnements, l'électricité et le chauffage. Utilisez ces champs dans le cadre des transactions récurrentes pour reporter les montants fixes et variables. Vous pouvez également définir des écritures inversion automatiques le lendemain de la date de report. Vous pouvez également utiliser des clés d'affectation pour répartir les écritures récurrentes entre plusieurs comptes. Pour plus d'informations, voir [Affectation de montants journal récurrent à plusieurs comptes](ui-work-general-journals.md#allocating-recurring-journal-amounts-to-several-accounts).

Avec un journal récurrent, les écritures qui sont régulièrement reportées ne sont saisies qu'une fois. Les comptes, dimensions, valeurs de dimension, etc., que vous saisissez restent ainsi dans le journal après report. Si des ajustements sont nécessaires, vous pouvez les faire à chaque report.

### <a name="recurring-method-field"></a>Champ Mode récurrent
Ce champ détermine la manière dont le montant de la ligne journal est traité après report. Par exemple, si vous utilisez le même montant chaque fois que vous reportez la ligne, vous pouvez conserver ce montant. Si vous utilisez les mêmes comptes et le même texte pour la ligne mais que le montant varie chaque fois que vous reportez, vous pouvez choisir de supprimer le montant après report.

| À | Voir |
| --- | --- |
|Statique|Le montant de la ligne journal est conservé après report.|
|Variable|Le montant de la ligne journal est supprimé après report.|
|Solde|Le montant reporté sur le compte de la ligne est affecté sur les comptes spécifiés pour la ligne de la table Affectation journal. Le solde du compte est donc positionné à zéro. Pensez à renseigner le champ **% affectation** sur la page **Affectations**. Pour plus d'informations, voir [Affectation de montants journal récurrent à plusieurs comptes](ui-work-general-journals.md#allocating-recurring-journal-amounts-to-several-accounts).|
|Inversion fixe|Le montant de la ligne journal est conservé après report, et une écriture contrepartie est reportée le lendemain.|
|Inversion variable|Le montant de la ligne journal est supprimé après report, et une écriture contrepartie est reportée le lendemain.|
|Inversion solde|Le montant reporté sur le compte de la ligne sera affecté sur les comptes spécifiés pour la ligne de la page **Affectations**. Le solde du compte est défini sur zéro, et une écriture contrepartie est reportée le lendemain.|

> [!NOTE]  
>  Les champs TVA peuvent être renseignés sur la ligne journal récurrent ou sur la ligne journal affectation, mais pas sur les deux. Ils peuvent être renseignés sur la page **Affectations** uniquement si les lignes correspondantes du journal récurrent ne sont pas renseignées.

### <a name="recurring-frequency-field"></a>Champ Périodicité récurrente
Ce champ détermine la fréquence de report de l'écriture de la ligne journal. Il s'agit d'un champ de formule de date qui doit être renseigné pour les lignes journal récurrent. Pour plus d'informations, voir [Utilisation de formules date](ui-enter-date-ranges.md#using-date-formulas).

#### <a name="examples"></a>Exemples
Si la ligne journal doit être reportée tous les mois, saisissez « 1M ». Après chaque report, la date du champ **Date de report** est mise à jour, elle est remplacée par la même date du mois suivant.

Si vous souhaitez reporter une écriture le dernier jour de chaque mois, vous pouvez suivre l'un des deux exemples ci-dessous :

- Reportez la première écriture le dernier jour d'un mois en saisissant la formule 1J+1M-1J (1 jour + 1 mois - 1 jour). Avec cette formule, la date de report est calculée correctement, quel que soit le nombre de jours que comprend le mois.

- Reportez la première écriture n'importe quel jour en saisissant la formule : 1M+CM. Avec cette formule, la date de report sera située après un mois entier + le nombre de jours restants du mois en cours.

### <a name="expiration-date-field"></a>Champ Date expiration
Ce champ détermine la date à laquelle la ligne est reportée pour la dernière fois. La ligne n'est plus reportée après cette date.

L'avantage d'utiliser ce champ réside dans le fait que la ligne n'est pas immédiatement supprimée du journal et que vous pouvez toujours remplacer la date d'expiration par une date ultérieure afin de pouvoir continuer à utiliser la ligne.

Si le champ est blanc, la ligne est reportée à chaque report, jusqu'à ce qu'elle soit supprimée du journal.

### <a name="allocating-recurring-journal-amounts-to-several-accounts"></a>Affectation de montants journal récurrent à plusieurs comptes
Sur la page **Journal général récurrent**, vous pouvez choisir l'action **Affectations** pour visualiser ou gérer la manière dont les montants de la ligne journal récurrent sont affectés à plusieurs comptes et dimensions. Notez qu'une affectation fonctionne comme une ligne compte de contrepartie pour la ligne journal récurrent.

Tout comme dans un journal récurrent, vous n'avez à saisir qu'une fois une affectation. L'affectation reste dans le journal affectation après report, ainsi vous n'avez pas à saisir les montants et les affectations chaque fois que vous reportez la ligne journal récurrent.

Si le mode récurrent du journal récurrent est défini sur **Solde** ou sur **Solde inverse**, tous les codes valeur de dimension du journal récurrent sont ignorés lorsque le compte est défini sur zéro. Par conséquent, si vous affectez une ligne récurrente à diverses valeurs de dimension sur la page **Affectations**, une seule écriture de contrepassation est créée. De ce fait, si vous affectez une ligne journal récurrent qui comporte un code section, vous ne devez pas saisir le même code sur la page **Affectations**. Si vous le faites, les valeurs de dimension sont incorrectes.

#### <a name="example-allocating-rent-payments-to-different-departments"></a>Exemple : Ventilation des paiements du loyer entre plusieurs départements
Vous payez un loyer tous les mois, vous avez saisi le montant du loyer sur le compte caisse d'une ligne journal récurrent. Sur la page **Affectations**, vous pouvez diviser les dépenses entre plusieurs départements (dimension Département) selon le nombre de mètres carrés occupé par chacun d'eux. Le calcul est basé sur le pourcentage d'affectation de chaque ligne. Vous pouvez saisir divers comptes sur différentes lignes affectation (si le loyer est aussi divisé entre plusieurs comptes) ou saisir le même compte, mais avec divers codes valeur de dimension pour la dimension Département sur chaque ligne.

## <a name="working-with-standard-journals"></a>Utilisation de feuilles standard
Lorsque vous créez des lignes journal dont vous savez que vous risquez de les recréer ultérieurement, vous pouvez les enregistrer en tant que journal standard avant de reporter le journal. Cette fonctionnalité s'applique aux journaux article et aux journaux généraux.

> [!NOTE]  
>   La procédure suivante traite du journal article mais affecte également le journal général.

### <a name="to-save-a-standard-journal"></a>Pour enregistrer un journal standard
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux article**, puis sélectionnez le lien associé.
2. Entrez une ou plusieurs lignes journal.
3. Sélectionnez les lignes journal à réutiliser.
4. Choisissez l'action **Enregistrer en tant que feuille standard**.
5. Sur la page de demande **Enregistrer en tant que journal article standard**, définissez un journal article standard, nouveau ou existant, dans lequel enregistrer les lignes.

    Si vous avez déjà créé une ou plusieurs feuilles article standard et souhaitez en remplacer une avec la nouvelle série de lignes feuille article, dans le champ Code, sélectionnez le code souhaité.
6. Choisissez le bouton **OK** pour vérifier que vous souhaitez écraser la feuille article standard existante et remplacer tout son contenu.
7. Sélectionnez le champ **Enregistrer le montant unitaire** si vous souhaitez enregistrer les valeurs dans le champ **Montant unitaire** de la feuille article standard.
8. Sélectionnez le champ **Enregistrer la quantité** si vous souhaitez que l'application enregistre les valeurs dans le champ **Quantité**.
9. Cliquez sur le bouton **OK** pour enregistrer la feuille article standard.

Une fois l'enregistrement du journal article standard effectué, la page Journal article s'affiche. Vous pouvez alors procéder au report tout en sachant que vous pouvez très facilement recréer ce journal si vous devez reporter des lignes identiques ou analogues.

### <a name="to-reuse-a-standard-journal"></a>Pour réutiliser un journal standard
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux article**, puis sélectionnez le lien associé.
2. Choisissez l'action **Obtenir les feuilles standard**.

    La page Journaux article standard qui s'ouvre alors contient des codes et des descriptions de tous les journaux article standard existants.
3. Pour passer en revue une feuille article standard avant de la sélectionner pour la réutiliser, choisissez l'action **Afficher la feuille**.

    Toutes les modifications que vous apportez dans un journal article standard sont effectuées immédiatement. Elles seront là la prochaine fois que vous rouvrirez ou réutiliserez le journal article en question. Il est donc recommandé de veiller à ce que la modification en question soit suffisamment importante pour s'appliquer de manière générale. Sinon, effectuez la correction ponctuelle dans le journal article après avoir inséré les lignes journal article standard. Reportez-vous à l'étape 4 ci-dessous.
4. Sur la page **Journaux article standard**, sélectionnez le journal article standard à réutiliser et cliquez sur le bouton **OK**.

    le journal article est alors rempli avec les lignes enregistrées en tant que journal article standard. Si des lignes journal figurent déjà dans le journal article, les lignes insérées sont placées en dessous.

    Si vous n'avez pas coché le champ **Enregistrer le montant unitaire** au cours de la tâche de fonction **Enregistrer en tant que feuille article standard**, alors le champ **Montant unitaire** des lignes insérées adopte automatiquement la valeur actuelle de l'article, copiée du champ **Coût unitaire** de la fiche article.

    > [!NOTE]  
    >   Si vous avez sélectionné les champs **Enregistrer le montant unitaire** ou **Enregistrer la quantité**, assurez-vous que les valeurs insérées sont adaptées à cet ajustement de stock précis avant de valider la feuille article.

    Si les lignes journal article insérées contiennent des montants unitaires enregistrés que vous ne souhaitez pas reporter, vous pouvez rapidement les ajuster sur la valeur actuelle de l'article comme suit.

6. Sélectionnez les feuilles articles standard que vous souhaitez ajuster, puis sélectionnez l'action **Recalculer le montant unitaire**. Le champ Montant unitaire est mis à jour avec le coût unitaire actuel de l'article.
7. Sélectionnez l'action **valider**.

## <a name="to-renumber-document-numbers-in-journals"></a>Pour renuméroter des numéros de document dans les feuilles
Pour vous assurer de ne pas recevoir d'erreurs de validation en raison de l'ordre des numéros de document, vous pouvez utiliser la fonction **Renuméroter les numéros de document** avant de valider une feuille.

Dans tous les journaux basés sur le journal général, le champ **N° document** est modifiable de sorte que vous puissiez spécifier des numéros de document différents pour des lignes journal différentes, ou le même numéro de document pour les lignes journal associées.

Si le champ **Souches de n°** du nom feuille est rempli, la fonction de validation dans les feuilles comptabilité nécessite que le numéro de document sur les lignes feuille individuelles ou groupées soit dans un ordre séquentiel. Pour vous assurer de ne pas recevoir d'erreurs de validation en raison de l'ordre des numéros de document, vous pouvez utiliser la fonction **Renuméroter les numéros de document** avant de valider la feuille. Si les lignes journal associées ont été regroupées par numéro de document avant d'utiliser la fonction, elles resteront groupées, mais peuvent être affectées à un autre numéro de document.

Cette fonction fonctionne également sur les vues filtrées.

Toute renumérotation des numéros de document respectera les affectations associées, par exemple une affectation de paiement qui a été effectuée à partir du document de la ligne journal pour un compte fournisseur. Par conséquent, les champs **Code affecté à** et **N° doc. affecté à** sur les écritures affectées peuvent être mis à jour.

La procédure suivante est basée sur la page **Journal général**, mais s'applique à tous les autres journaux qui sont basés sur le journal général, comme la page **Journal des paiements**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.
2. Lorsque vous êtes prêt à valider la feuille, choisissez l'action **Renuméroter les numéros de document**.

Les valeurs dans le champ **N° document** sont modifiées, le cas échéant, pour que le numéro de document sur les lignes journal individuelles ou groupées soit dans un ordre séquentiel. Une fois que les documents sont renumérotés, vous pouvez procéder au report du journal.

## <a name="see-also"></a>Voir aussi
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md)  
[Répartition des coûts et du revenu](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
