---
title: "Utilisation de journaux généraux pour reporter directement dans le grand livre| Microsoft Docs"
description: "Découvrez comment utiliser des journaux généraux pour reporter des transactions financières dans les comptes GL et dans d'autres comptes, tels que les comptes bancaires et fournisseur."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/02/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 2aac957fc253f6c7d2f621ea2e5e039733081a19
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="working-with-general-journals"></a>Utilisation de feuilles comptabilité
La plupart des transactions financières sont reportées dans le grand livre via les documents commerciaux dédiés, tels que des factures achat et des documents de vente. Pour les activités économiques qui ne sont pas représentés par un document dans [!INCLUDE[d365fin](includes/d365fin_md.md)], comme de plus petits frais ou règlements, vous pouvez créer les transactions associées en validant des lignes de feuille dans la fenêtre **Feuille comptabilité**. Pour plus d'informations, voir [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).

Par exemple, vous pouvez reporter les dépenses de vos employés avec leurs fonds propres pour des activités professionnelles, afin de les rembourser ultérieurement. Pour plus d'informations, voir [Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md).

Les journaux généraux vous permettent de reporter des transactions financières directement dans les comptes GL et dans d'autres comptes tels que les comptes bancaires, client, fournisseur et employé. Le report avec un journal général crée toujours des écritures dans les comptes du grand livre. C'est le cas même lorsque, par exemple, vous reportez une ligne journal sur un compte client, parce qu'une écriture est reportée dans un compte client du grand livre via un groupe de report.

Les informations que vous saisissez dans un journal sont temporaires et peuvent être modifiées tant qu'elles sont dans le journal. Lorsque vous reportez le journal, les informations sont transférées vers des écritures de comptes individuels, où elles ne peuvent pas être modifiées. Toutefois, vous pouvez annuler l'affectation des écritures reportées et reporter des écritures d'inversion ou de correction. Pour plus d'informations, voir [Inverser des reports](finance-how-reverse-journal-posting.md).

## <a name="using-journal-templates-and-batches"></a>Utilisation de modèles et lots de journal
Il existe plusieurs modèles journal général. Chaque modèle journal est représenté par une fenêtre dédiée avec des fonctions particulières et les champs nécessaires pour la prise en charge de ces fonctions, notamment la fenêtre **Journal rapprochement paiement** qui permet de traiter les paiements bancaires et la fenêtre **Journal paiement** qui permet de payer vos fournisseurs ou rembourser vos employés. Pour plus d'informations, voir [Exécuter des paiements](payables-make-payments.md) et [Rapprocher des paiements client manuellement](receivables-how-apply-sales-transactions-manually.md).

Pour chaque modèle journal, vous pouvez configurer votre propre journal personnel sous forme de lot de journal. Par exemple, vous pouvez définir votre propre lot de journal pour le journal paiement doté de votre présentation et de vos paramètres personnels. Le conseil suivant est un exemple de la manière de personnaliser un journal.

> [!TIP]  
> Si vous cochez la case **Suggérer le montant contrepartie** de la ligne pour votre nom feuille dans la fenêtre **Noms feuilles comptabilité**, le champ **Montant** dans, par exemple, les lignes feuille comptabilité pour le même numéro de document est automatiquement prérempli avec la valeur nécessaire à la contrepartie dans le document. Pour plus d'informations, voir [Laisser [!INCLUDE[d365fin](includes/d365fin_md.md)] suggérer des valeurs](ui-let-system-suggest-values.md).

## <a name="understanding-main-accounts-and-balancing-accounts"></a>Compte principaux et comptes contrepartie
Si vous avez configuré des comptes de contrepartie par défaut pour les lots journal sur la page **Journaux généraux**, le compte de contrepartie sera renseigné automatiquement lorsque vous renseignez le champ **Numéro du compte**. Sinon, renseignez manuellement les champs **Numéro du compte** et **N° compte contrepartie**. Un montant positif dans le champ **Montant** est débité du compte principal et crédité dans le compte contrepartie. Un montant négatif est crédité sur le compte principal et débité du compte contrepartie.

> [!NOTE]  
>   La TVA est calculée séparément pour le compte principal et le compte de contrepartie, afin qu'ils puissent utiliser des taux de pourcentage de TVA différents.

## <a name="working-with-recurring-journals"></a>Utilisation de feuilles abonnement
Un journal récurrent est un journal général contenant des champs spécifiques pour la gestion des transactions que vous reportez fréquemment avec peu ou pas de modifications. Utilisez ces champs dans le cadre des transactions récurrentes pour reporter les montants fixes et variables. Vous pouvez également définir des inversions automatiques d'écritures pour le lendemain de la date de report et utiliser les affectations statiques avec les écritures récurrentes.

## <a name="working-with-standard-journals"></a>Utilisation de feuilles standard
Lorsque vous créez des lignes journal dont vous savez que vous risquez de les recréer ultérieurement, vous pouvez les enregistrer en tant que journal standard avant de reporter le journal. Cette fonctionnalité s'applique aux journaux article et aux journaux généraux.

> [!NOTE]  
>   La procédure suivante traite du journal article mais affecte également le journal général.

### <a name="to-save-a-standard-journal"></a>Pour enregistrer un journal standard
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles article**, puis sélectionnez le lien connexe.
2. Entrez une ou plusieurs lignes journal.
3. Sélectionnez les lignes journal à réutiliser.
4. Choisissez l'action **Enregistrer en tant que feuille standard**.
5. Dans le formulaire de sélection **Enregistrer en tant que feuille standard**, définissez une feuille article standard, nouvelle ou existante, dans laquelle enregistrer les lignes.

    Si vous avez déjà créé une ou plusieurs feuilles article standard et souhaitez en remplacer une avec la nouvelle série de lignes feuille article, dans le champ Code, sélectionnez le code souhaité.
6. Choisissez le bouton **OK** pour vérifier que vous souhaitez écraser la feuille article standard existante et remplacer tout son contenu.
7. Sélectionnez le champ **Enregistrer le montant unitaire** si vous souhaitez enregistrer les valeurs dans le champ **Montant unitaire** de la feuille article standard.
8. Sélectionnez le champ **Enregistrer la quantité** si vous souhaitez que le programme enregistre les valeurs dans le champ **Quantité**.
9. Cliquez sur le bouton **OK** pour enregistrer la feuille article standard.

Une fois l'enregistrement de la feuille article standard effectué, la fenêtre Feuille article s'affiche. Vous pouvez alors procéder à la validation tout en sachant que vous pouvez très facilement recréer cette feuille si vous devez valider des lignes identiques ou analogues.

### <a name="to-reuse-a-standard-journal"></a>Pour réutiliser un journal standard
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles article**, puis sélectionnez le lien connexe.
2. Choisissez l'action **Obtenir les feuilles standard**.

    La fenêtre Feuilles article standard qui s'ouvre alors contient des codes et des descriptions de toutes les feuilles article standard existantes.
3. Pour passer en revue une feuille article standard avant de la sélectionner pour la réutiliser, choisissez l'action **Afficher la feuille**.

    Toutes les modifications que vous apportez dans un journal article standard sont effectuées immédiatement. Elles seront là la prochaine fois que vous rouvrirez ou réutiliserez le journal article en question. Il est donc recommandé de veiller à ce que la modification en question soit suffisamment importante pour s'appliquer de manière générale. Sinon, effectuez la correction ponctuelle dans le journal article après avoir inséré les lignes journal article standard. Reportez-vous à l'étape 4 ci-dessous.
4. Dans la fenêtre **Feuilles article standard**, sélectionnez la feuille article standard à réutiliser et cliquez sur le bouton **OK**.

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

La procédure suivante est basée sur la fenêtre **Feuille comptabilité**, mais s'applique à toutes les autres feuilles qui sont basées sur la feuille comptabilité, tel que la fenêtre **Feuille paiement**.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles comptabilité**, puis sélectionnez le lien connexe.
2. Lorsque vous êtes prêt à valider la feuille, choisissez l'action **Renuméroter les numéros de document**.

Les valeurs dans le champ **N° document** sont modifiées, le cas échéant, pour que le numéro de document sur les lignes journal individuelles ou groupées soit dans un ordre séquentiel. Une fois que les documents sont renumérotés, vous pouvez procéder au report du journal.

## <a name="see-also"></a>Voir aussi
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Inverser des reports](finance-how-reverse-journal-posting.md)  
[Répartition des coûts et du revenu](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

