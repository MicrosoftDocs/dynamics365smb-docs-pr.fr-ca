---
title: Utilisation de journaux généraux pour reporter directement dans le grand livre
description: 'Découvrez comment utiliser les journaux pour reporter des transactions financières dans les comptes GL et dans d''autres comptes, tels que les comptes bancaires et fournisseur.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/27/2022
ms.custom: bap-template
ms.search.keywords: 'journals, recurring, accrual, renumber, bulk-post'
ms.search.form: '39, 101, 102, 182, 184, 185, 201, 207, 250, 251, 253, 255, 256, 261, 262, 283, 519, 750, 751, 752, 753, 754, 755, 12409, 12410, 12411, 1290, 10101, 11400, 11402, 11403, 11405, 11300, 2000000, 2000001, 2000003, 2000020, 2000021, 2000022'
---
# <a name="work-with-general-journals"></a><a name="work-with-general-journals"></a>Utiliser des journaux généraux

La plupart des transactions financières sont reportées dans le grand livre via les documents, tels que des factures achat et des documents de vente. Cependant, vous pouvez également traiter des activités commerciales telles que :

* Achats
* Paiements
* Utilisation de journaux récurrents pour reporter les régularisations
* Remboursement des dépenses des employés en reportant des lignes journal dans les journaux  

La plupart des journaux sont basés sur le journal général, et vous pouvez traiter toutes les transactions sur la page **Journal général**. En savoir plus sur [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).  

Par exemple, vous pouvez utiliser les dépenses des employés pour le remboursement. En savoir plus sur [Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md).

Cependant, [!INCLUDE [prod_short](includes/prod_short.md)] propose également des journaux qui sont optimisés pour les types de transactions spécifiques, telles que **Journal paiement** pour enregistrer les paiements. Pour en savoir plus, voir [Enregistrer les paiements et remboursements dans le journal paiement](payables-how-post-payments-refunds.md).  

Vous utilisez les journaux généraux pour reporter des transactions financières dans les compte GL et autres comptes divers. Parmi les autres comptes figurent les comptes bancaires, clients, fournisseurs et employés. Le report avec un journal général génère des écritures sur les compte GL même lorsque, par exemple, vous reportez une ligne journal sur un compte client. L’écriture est reportée sur un compte client du grand livre via un groupe de report.

Les informations que vous saisissez dans un journal sont temporaires et peuvent être modifiées tant qu’elles sont dans le journal. Lorsque vous reportez le journal, les informations sont transférées vers des écritures de comptes individuels, où elles ne peuvent pas être modifiées. Toutefois, vous pouvez annuler l'affectation des écritures reportées et reporter des écritures d'inversion ou de correction. Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).

> [!NOTE]
> [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]  

## <a name="use-journal-templates-and-batches"></a><a name="use-journal-templates-and-batches"></a>Utiliser des lots et des modèles journal

Il existe plusieurs modèles journal général. Chaque modèle journal est représenté par une page dédiée avec des fonctions particulières et les champs nécessaires pour la prise en charge de ces fonctions, notamment la page **Journal rapprochement paiement** qui permet de traiter les paiements bancaires et la page **Journal paiement** qui permet de payer vos fournisseurs ou de rembourser vos employés. Pour en savoir plus, voir [Exécuter des paiements](payables-make-payments.md) et [Rapprocher des paiements clients avec le journal règlement ou les écritures client](receivables-how-apply-sales-transactions-manually.md).

Pour chaque modèle journal, vous pouvez configurer votre propre journal personnel sous forme de lot journal. Par exemple, vous pouvez définir votre propre lot de journal pour le journal paiement doté de votre présentation et de vos paramètres personnels. Le conseil suivant est un exemple de la manière de personnaliser un journal.

> [!TIP]  
> Si vous cochez la case **Suggérer le montant contrepartie** de la ligne pour votre lot sur la page **Lots journal général**, le champ **Montant** dans, par exemple, les lignes journal général pour le même numéro de document est automatiquement prérempli avec la valeur nécessaire à la contrepartie du document. Learn more at [Laisser [!INCLUDE[prod_short](includes/prod_short.md)] suggérer des valeurs](ui-let-system-suggest-values.md).

> [!TIP]
> Vous pouvez ajouter ou supprimer des champs dans les journaux en personnalisant ceux-ci. Pour plus d’informations, consultez [Personnaliser votre espace de travail](ui-personalization-user.md).

### <a name="validating-general-journal-batches"></a><a name="validating-general-journal-batches"></a>Validation des lots journal général

Vous pouvez activer une vérification des antécédents qui aidera à éviter les retards lors du report. Le contrôle vous informe lorsqu’une erreur dans le journal financier sur lequel vous travaillez vous empêche de reporter le journal. Sur la page **Lot journal général**, vous pouvez choisir **Vérification des erreurs d’arrière-plan** pour que [!INCLUDE[prod_short](includes/prod_short.md)] valide les journaux financiers, tels que les journaux généraux ou paiement, pendant que vous les utilisez.

Lorsque vous activez la validation, le Récapitulatif **Vérification de journal** affiche les problèmes de la ligne actuelle et du lot entier. La validation se produit lorsque vous chargez un lot journal financier et lorsque vous choisissez une autre ligne journal. La vignette **Nombre total d’erreurs** du Récapitulatif montre le nombre total de problèmes que [!INCLUDE[prod_short](includes/prod_short.md)] a trouvées, et vous pouvez le choisir pour ouvrir un aperçu des problèmes.

Vous pouvez utiliser les actions **Afficher les lignes avec des problèmes** et **Afficher toutes les lignes** pour basculer entre les lignes journal qui ont ou n’ont pas de problèmes. Le nouveau Récapitulatif **Détails de la ligne journal** fournit un aperçu rapide et un accès aux données des lignes journal, telles que le compte du grand livre, le client ou le fournisseur, ainsi que la configuration du report pour des comptes spécifiques.

[!INCLUDE [background_doc_journal_check](includes/background_doc_journal_check.md)]  

## <a name="understanding-main-accounts-and-balancing-accounts"></a><a name="understanding-main-accounts-and-balancing-accounts"></a>Compte principaux et comptes de contrepartie

Si vous avez configuré des comptes de contrepartie par défaut pour les lots journal sur la page **Journaux généraux**, le compte de contrepartie sera renseigné automatiquement lorsque vous renseignez le champ **Numéro du compte**. Sinon, renseignez manuellement les champs **Numéro du compte** et **N° compte contrepartie**. Un montant positif dans le champ **Montant** est débité du compte principal et crédité dans le compte contrepartie. Un montant négatif est crédité sur le compte principal et débité du compte contrepartie.

> [!NOTE]  
> La TVA est calculée séparément pour le compte principal et le compte de contrepartie, afin qu'ils puissent utiliser des taux de pourcentage de TVA différents.

## <a name="work-with-recurring-journals"></a><a name="work-with-recurring-journals"></a>Utiliser des journaux récurrents

Un journal récurrent est un journal général contenant des champs spécifiques pour la gestion des transactions que vous reportez fréquemment avec peu ou pas de modifications. Par exemple, les transactions pour les dépenses telles que le loyer, les abonnements, l’électricité et le chauffage. L’utilisation de journaux récurrents vous permet de reporter des montants fixes et variables et de spécifier des écritures d’inversion automatiques pour le jour suivant la date de report. Les clés d'affectation vous permettent de répartir les écritures récurrentes entre plusieurs comptes. Pour en savoir plus, voir [Ventilation des montants journal récurrent sur plusieurs comptes](#allocating-recurring-journal-amounts-to-several-accounts).

Avec un journal récurrent, vous ne créez les écritures qui sont régulièrement reportées qu’une fois. Par exemple, les comptes, dimensions, valeurs de dimension, etc. restent dans le journal après report. Si des modifications sont nécessaires, vous pouvez les apporter à chaque report.

### <a name="recurring-method-field"></a><a name="recurring-method-field"></a>Champ Mode récurrent

Le champ **Mode récurrent** est important. Il détermine la manière dont le montant de la ligne journal est traité après report. Par exemple, si vous utilisez le même montant chaque fois que vous reportez la ligne, vous pouvez conserver ce montant. Si vous utilisez les mêmes comptes et le même texte pour la ligne, mais que le montant varie chaque fois que vous reportez, vous pouvez choisir de supprimer le montant après report.

| Pour | Voir |
| --- | --- |
|F Fixe|Le montant de la ligne journal est conservé après report.|
|V Variable|Le montant de la ligne journal est supprimé après report.|
|S Solde|Le montant reporté sur le compte de la ligne est affecté sur les comptes spécifiés pour la ligne de la table Affectation journal. Le solde du compte est positionné à zéro. Pensez à renseigner le champ **% affectation** sur la page **Affectations**. Pour plus d'informations, voir [Affectation de montants journal récurrent à plusieurs comptes](#allocating-recurring-journal-amounts-to-several-accounts).|
|FI Fixe inversion|Le montant de la ligne journal est conservé après report, et une écriture contrepartie est reportée le lendemain.|
|VI Variable inversion|Le montant de la ligne journal est supprimé après report, et une écriture contrepartie est reportée le lendemain.|
|SI Solde inversion|Le montant reporté sur le compte de la ligne sera affecté sur les comptes spécifiés pour la ligne de la page **Affectations**. Le solde du compte est défini sur zéro, et une écriture contrepartie est reportée le lendemain.|
|Solde BD par dimension|La ligne journal répartit les coûts en fonction du solde d’un compte du grand livre par dimension. Vous serez invité à définir les filtres dimension à utiliser pour calculer le solde du compte du grand livre source par dimension à partir de laquelle vous souhaitez allouer les coûts. Sinon, choisissez l’action **Définir des filtres dimension** ultérieurement.|
|Solde inverse RBD par dimension|La ligne journal répartit les coûts en fonction du solde inversion d’un compte du grand livre par dimension. Vous serez invité à définir les filtres dimension à utiliser pour calculer le solde du compte du grand livre source par dimension à partir de laquelle vous souhaitez allouer les coûts. Vous pouvez également choisir l’action **Définir des filtres dimension** ultérieurement.|

> [!NOTE]  
> Les champs TVA peuvent être renseignés sur la ligne journal récurrent ou sur la ligne journal affectation, mais pas sur les deux. Ils peuvent être renseignés sur la page **Affectations** uniquement si les lignes correspondantes du journal récurrent ne sont pas renseignées.

### <a name="recurring-frequency-field"></a><a name="recurring-frequency-field"></a>Champ Périodicité récurrente

Ce champ de formule de date détermine la fréquence de report de l’écriture sur la ligne journal et doit être renseigné. En savoir plus sur [Utiliser des formules de date](ui-enter-date-ranges.md#use-date-formulas).

#### <a name="examples"></a><a name="examples"></a>Exemples

Si la ligne journal doit être reportée tous les mois, saisissez « 1M ». Après chaque report, la date du champ **Date de report** est mise à jour, elle est remplacée par la même date du mois suivant.

Si vous souhaitez reporter une écriture le dernier jour de chaque mois, vous pouvez suivre l'un des deux exemples ci-dessous :

* Reportez la première écriture le dernier jour d'un mois en saisissant la formule 1J+1M-1J (1 jour + 1 mois - 1 jour). Avec cette formule, la date de report est calculée correctement, quel que soit le nombre de jours que comprend le mois.

* Reportez la première écriture n’importe quel jour du mois en saisissant la formule : 1M+CM. Avec cette formule, la date de report sera située après un mois entier + le nombre de jours restants du mois en cours.

### <a name="expiration-date-field"></a><a name="expiration-date-field"></a>Champ Date expiration

Ce champ détermine la date à laquelle la ligne est reportée pour la dernière fois. La ligne n’est plus reportée après cette date.

L’avantage d’utiliser le champ Date d’expiration est que la ligne n’est pas supprimée immédiatement du journal. Vous pouvez entrer une date ultérieure afin de pouvoir utiliser la ligne à l’avenir.

Si le champ est vide, la ligne est reportée à chaque fois, jusqu’à ce qu’elle soit supprimée du journal.

### <a name="allocating-recurring-journal-amounts-to-several-accounts"></a><a name="allocating-recurring-journal-amounts-to-several-accounts"></a>Ventilation des montants journal récurrent sur plusieurs comptes

Sur la page **Journal récurrent**, vous pouvez choisir l’action **Affectations** pour spécifier la manière dont les montants de la ligne journal récurrent sont affectés à plusieurs comptes et dimensions. Une affectation fonctionne comme une ligne compte de contrepartie pour la ligne journal récurrent.

À l’instar d’un journal récurrent, vous entrez une affectation une fois et elle reste dans le journal affectation après report. Vous n’avez pas besoin d’entrer des montants et des affectations chaque fois que vous reportez la ligne journal récurrent.

Si le mode récurrent dans le journal récurrent est paramétré sur **Solde** ou sur **Solde inverse**, tous les codes valeur de dimension du journal récurrent sont ignorés lorsque le compte est défini sur zéro. Si vous affectez une ligne récurrente à diverses valeurs de dimension sur la page **Affectations**, une seule écriture d'inversion est créée.

> [!NOTE]
> Si vous affectez une ligne journal récurrent qui comporte un code valeur de dimension, vous ne devez pas saisir le même code sur la page **Affectations**. Si vous le faites, les valeurs de dimension sont incorrectes.  

Pour allouer des montants de journal récurrent en fonction des dimensions, définissez le champ **Mode récurrent** sur **Solde par dimension** ou **Solde inverse par dimension**. Si le mode récurrent dans le journal récurrent est paramétré sur **Solde par dimension** ou sur **Solde inverse par dimension**, tous les codes valeur de dimension du journal récurrent sont pris en compte lorsque le compte est défini sur zéro. Si vous allouez une ligne récurrente à des valeurs de dimension sur la page **Affectations**, des écritures inversion sont créées qui correspondent au nombre de combinaisons de valeur de dimension dont est composé le solde. Si vous allouez le solde du compte via un journal récurrent qui contient un code valeur de dimension, n’oubliez pas d’utiliser **Solde par dimension** ou **Solde inverse par dimension** pour vous assurer que les valeurs de dimension sont correctement équilibrées ou inversées à partir du compte source.  

Par exemple, votre compagnie a quelques unités fonctionnelles et une poignée de départements que vos contrôleurs ont configurés en tant que dimensions. Pour accélérer le processus de saisie des factures achat, vous décidez de demander aux personnes chargées des comptes fournisseurs de saisir uniquement les dimensions des unités fonctionnelles. Étant donné que chaque unité fonctionnelle dispose de clés d'affectation spécifiques pour la dimension Département, par exemple en fonction du nombre d’employés, vous pouvez utiliser les modes récurrents **Solde BD par dimension** ou **Solde inverse RBD par dimension** pour réaffecter les dépenses de chaque unité fonctionnelle aux départements qui conviennent en fonction des clés d'affectation.  

> [!NOTE]
> Les dimensions que vous définissez sur les lignes affectation ne sont pas calculées automatiquement et vous devez spécifier les valeurs de dimension à définir sur les comptes d’affectation. Si vous souhaitez conserver le lien entre la dimension du compte source et la dimension du compte d’affectation, nous vous recommandons d’utiliser la fonctionnalité [Comptabilité analytique](finance-about-cost-accounting.md) à la place.

#### <a name="example-allocating-rent-payments-to-different-departments"></a><a name="example-allocating-rent-payments-to-different-departments"></a>Exemple : Ventilation des paiements du loyer entre plusieurs départements

Vous payez un loyer tous les mois, vous avez donc saisi le montant du loyer sur le compte règlement d’une ligne journal récurrent. Sur la page **Affectations**, vous pouvez utiliser la dimension Département pour répartir les dépenses entre plusieurs départements. Par exemple, selon le nombre de pieds carrés qu’occupe chaque département. Le calcul est basé sur le pourcentage d'affectation de chaque ligne. Vous pouvez ventiler de diverses manières :

* Saisissez différents comptes sur différentes lignes d'affectation pour répartir les dépenses de location entre plusieurs comptes.
* Entrez le même compte, mais utilisez des codes de valeur de dimension différents pour la dimension Département sur chaque ligne.

[!INCLUDE [rev-general-journal](includes/rev-general-journal.md)]

### <a name="calculate-the-reversal-date"></a><a name="calculate-the-reversal-date"></a>Calcul de date de contrepassation

Lorsque vous utilisez des journaux généraux récurrents pour reporter les régularisations à la fin d’une période, il est important d’avoir un contrôle total sur les écritures de contrepassation. Sur la page **Journaux généraux récurrents**, le champ **Calcul de date de contrepassation** vous permet de contrôler la date à laquelle les écritures de contrepassation seront reportées lorsque les méthodes de contrepassation récurrentes seront utilisées.

#### <a name="example"></a><a name="example"></a>Exemple :

Les régularisations sont généralement reportées avec des méthodes récurrentes **Fixe**, **Variable** ou **Solde** sur la ligne journal. La date de report du montant reporté sur le compte sur la ligne journal est calculée en utilisant la fréquence récurrente. La date de report de l’écriture contrepartie est calculée à l’aide du champ **Calcul de la date de contrepassation**, comme suit :

* Si le champ est vide, l’écriture contrepartie sera reportée le jour suivant.
* Si le champ contient une formule de date (par exemple, **5D** pendant cinq jours), l’écriture contrepartie sera reportée avec une date de report calculée à l’aide du calcul de la date de contrepassation.

> [!NOTE]
> Par défaut, le champ **Calcul de la date de contrepassation** n’est pas disponible sur la page **Journaux généraux récurrents**. Pour utiliser le champ, vous devez l’ajouter en personnalisant la page. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

## <a name="work-with-standard-journals"></a><a name="work-with-standard-journals"></a>Utiliser des journaux standard

Lorsque vous créez des lignes journal dont vous savez que vous risquez de les recréer ultérieurement, vous pouvez les enregistrer en tant que journal standard avant de reporter le journal. La même chose s’applique aux journaux article et aux journaux généraux.

> [!NOTE]
> Les journaux standard peuvent ne pas contenir tous les champs que vous souhaitez inclure dans les écritures résultantes. Par exemple, si vous utilisez un journal général standard pour enregistrer un paiement, les écritures ne contiendront pas le champ Code mode de paiement.

> [!NOTE]  
> Les procédures suivantes traitent du journal article, mais concernent également le journal général.

### <a name="to-save-a-standard-journal"></a><a name="to-save-a-standard-journal"></a>Pour enregistrer un journal standard

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article**, puis choisissez le lien associé.
2. Entrez une ou plusieurs lignes journal.
3. Sélectionnez les lignes journal à réutiliser.
4. Choisissez l'action **Enregistrer en tant que feuille standard**.
5. Sur la page de demande **Enregistrer en tant que journal article standard**, définissez un journal article standard, nouveau ou existant, dans lequel enregistrer les lignes.

    Si vous avez déjà créé un ou plusieurs journaux article standard et souhaitez en remplacer un avec la nouvelle série de lignes journal article, dans le champ **Code**, sélectionnez le journal article.
6. Cliquez sur le bouton **OK** pour vérifier que vous souhaitez remplacer le contenu du journal article standard existant.
7. Pour enregistrer les valeurs dans le champ **Montant unitaire** du journal article standard, sélectionnez **Enregistrer le montant unitaire**.
8. Pour enregistrer les valeurs dans le champ **Quantité**, choisissez le champ **Enregistrer la quantité**.
9. Sélectionnez **OK** pour enregistrer le journal article standard.

Lorsque vous enregistrez le journal article standard, la page journal article s’affiche afin que vous puissiez la reporter.

### <a name="to-reuse-a-standard-journal"></a><a name="to-reuse-a-standard-journal"></a>Pour réutiliser un journal standard

> [!NOTE]
> Les journaux standard n’ont pas toujours les mêmes champs que les journaux généraux. Lorsque vous utilisez l’action Extraire journaux standard pour copier les champs dans le journal général, le journal général peut contenir moins d’informations que si vous l’aviez créé manuellement. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article**, puis choisissez le lien associé.
2. Choisissez l'action **Obtenir les feuilles standard**.
3. Pour passer en revue une feuille article standard avant de la sélectionner pour la réutiliser, choisissez l'action **Afficher la feuille**.

    Toute modification apportée à un journal article standard est immédiatement appliquée et reste en vigueur lorsque vous rouvrez ou réutilisez ce journal. Il est donc recommandé de s’assurer que la modification en question est suffisamment importante pour devoir s’appliquer de manière générale. Sinon, effectuez la correction spécifique dans le journal article après avoir inséré les lignes journal article standard. Reportez-vous à l'étape 4.
4. Sur la page **Journaux article standard**, sélectionnez le journal article standard à réutiliser et cliquez sur **OK**.

    Le journal article contient les lignes que vous avez enregistrées. Si le journal article comporte déjà des lignes, les nouvelles lignes apparaissent après celles-ci.

    Si vous n’avez pas activé le bouton à bascule **Enregistrer le montant unitaire** lorsque vous avez enregistré le journal, le champ **Montant unitaire** sur les lignes ajoutées à partir du journal standard contient la valeur du champ **Coût unitaire** sur la fiche article.

    > [!NOTE]  
    > Si vous avez activé les boutons à bascule **Enregistrer le montant unitaire** ou **Enregistrer la quantité** lorsque vous avez enregistré le journal, assurez-vous que les valeurs insérées sont adaptées à cet ajustement de stock précis avant de reporter le journal article.
    >
    > Si les lignes journal article insérées contiennent des montants unitaires enregistrés que vous ne souhaitez pas reporter, vous pouvez les ajuster à la valeur actuelle de l’article.

5. Sélectionnez les feuilles articles standard que vous souhaitez ajuster, puis sélectionnez l'action **Recalculer le montant unitaire**. Cette action met à jour avec le champ Montant unitaire avec le coût unitaire actuel de l’article.
6. Sélectionnez l'action **Valider**.

## <a name="to-renumber-document-numbers-in-journals"></a><a name="to-renumber-document-numbers-in-journals"></a>Pour renuméroter des numéros de document dans les feuilles

Pour éviter les erreurs de report causées par le numéro de document, vous pouvez utiliser l’action **Renuméroter les numéros de document** avant de reporter un journal.

Dans tous les journaux basés sur le journal général, le champ **N° document** est modifiable de sorte que vous puissiez spécifier des numéros de document différents pour des lignes journal différentes, ou le même numéro de document pour les lignes journal associées.

Si le champ **Souches de n°** du nom feuille est rempli, la fonction de validation dans les feuilles comptabilité nécessite que le numéro de document sur les lignes feuille individuelles ou groupées soit dans un ordre séquentiel. Choisissez simplement l’action **Renuméroter les numéros de document** et les champs **N° de document** pertinents sont alors mis à jour. Si les lignes journal associées ont été regroupées par numéro de document avant d’utiliser la fonction, elles resteront groupées, mais peuvent être affectées à un autre numéro de document.  

Cette fonction fonctionne également sur les vues filtrées.

Toute renumérotation des numéros de document respectera les affectations associées, par exemple une affectation de paiement qui a été effectuée à partir du document de la ligne journal pour un compte fournisseur. Par conséquent, les champs **Code référence** et **N° doc. référence** seront mis à jour sur les écritures.

### <a name="to-renumber-documents-in-journals"></a><a name="to-renumber-documents-in-journals"></a>Pour renuméroter des documents dans les journaux

La procédure suivante est basée sur la page **Journal général**, mais s'applique à tous les autres journaux qui sont basés sur le journal général, comme la page **Journal des paiements**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux**, puis choisissez le lien associé.
2. Lorsque vous êtes prêt à reporter le journal, choisissez l’action **Renuméroter les numéros de document**.

Les valeurs dans le champ **N° document** sont modifiées, le cas échéant, pour que le numéro de document sur les lignes journal individuelles ou groupées soit dans un ordre séquentiel. Une fois que les documents sont renumérotés, vous pouvez procéder au report du journal.

## <a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/use-journals-dynamics-365-business-central/) associée

## <a name="see-also"></a><a name="see-also"></a>Voir aussi

[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md)  
[Répartition des coûts et du revenu](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)  
[Réévaluer l'inventaire dans le journal réévaluation](inventory-how-revalue-inventory.md)  
[Comptabiliser, ajuster et reclasser l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md)  
[Rapprocher les paiements clients avec le journal des encaissements ou les écritures client](receivables-how-apply-sales-transactions-manually.md)  
[Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md)  
[Utiliser les documents et les journaux intersociétés](intercompany-how-work-documents-journals.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
