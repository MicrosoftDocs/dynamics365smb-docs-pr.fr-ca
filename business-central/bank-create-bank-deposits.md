---
title: Créer des dépôts bancaires
description: Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: 'bank, deposit'
ms.search.form: '10140, 10141, 10143, 10144, 10146, 10147, 10148, 36646'
ms.date: 09/04/2023
ms.custom: bap-template
---
# <a name="create-bank-deposits"></a>Créer des dépôts bancaires

> [!NOTE]
> La possibilité de créer des dépôts bancaires est nouvelle dans la 1re vague de lancement 2022 de Business Central pour de nombreuses versions nationales/régionales. Si vous utilisiez Business Central aux États-Unis, au Canada ou au Mexique avant cette version, vous utilisiez peut-être les fonctionnalités antérieures. Vous pouvez continuer, mais les nouvelles fonctionnalités remplaceront les anciennes dans une prochaine version. Pour commencer à utiliser les nouvelles fonctionnalités décrites dans cet article, votre administrateur peut accéder à la page **Gestion des fonctionnalités** et activer **Mise à jour des fonctionnalités : rapprochements et dépôts bancaires standardisés**.  

Utilisez la page **Dépôts bancaires** pour enregistrer les dépôts sous la forme d’un document unique qui valide une ou plusieurs écritures sur un compte bancaire. Généralement, les dépôts bancaires sont utilisés pour enregistrer les dépôts en espèces. La page Dépôts bancaires est disponible dans le menu **Banques** du tableau de bord Business Manager et d’autres tableaux de bord traitant de la gestion de la trésorerie.

Les montants sur les dépôts bancaires peuvent provenir de plusieurs sources :

* Ventes, en utilisant un compte du grand livre pour les revenus.
* Paiements client.
* Remboursements en espèces des fournisseurs ou paiements en espèces aux fournisseurs. 

Les lignes de dépôt bancaire contiennent des informations sur les dépôts individuels, tels que les chèques des clients. Le total des montants inscrits sur les lignes doit correspondre au montant total du dépôt.

Après avoir rempli les informations et les lignes relatives au dépôt, vous devez les reporter. Le report mettra à jour les livres comptables appropriés. Ces livres comptables comprennent le grand livre ainsi que le grand livre bancaire, le grand livre client et le grand livre fournisseur. Les dépôts affichés sont stockés sur la page **Dépôts bancaires reportés**, afin que vous puissiez vous y référer par la suite.

Le rapport **Dépôt bancaire** affiche les dépôts des clients et des fournisseurs avec le montant du dépôt initial, le montant du dépôt qui reste ouvert et le montant affecté. Le rapport indique également le montant total du dépôt reporté à rapprocher.

## <a name="before-you-start"></a>Avant de commencer

Avant de pouvoir utiliser les dépôts bancaires, plusieurs éléments doivent être définis. Vous devez disposer d’une série de numéros et d’un modèle de journal général. Vous devez également spécifier si vous souhaitez reporter les montants des dépôts bancaires sous forme de somme forfaitaire. C’est-à-dire comme un total de tous les montants sur les lignes de dépôt. Sinon, chaque ligne est reportée comme une écriture individuelle. Le report d’un dépôt sous la forme d’une seule écriture bancaire peut faciliter le rapprochement bancaire.

### <a name="number-series-and-lump-sum-deposits"></a>Séries de numéros et dépôts forfaitaires

Vous devez configurer une série de numéros pour les dépôts bancaires, puis spécifier la série de numéros dans le champ **Numéros de dépôt bancaire** sur la page **Configuration ventes**. Pour plus d’informations sur les séries de numéros, reportez-vous à [Création des séries de numéros](ui-create-number-series.md).

Sur la page **Configuration ventes** également, pour reporter des dépôts sous forme de montants forfaitaires plutôt que sous forme de lignes individuelles, activez le bouton bascule **Reporter les montants des dépôts bancaires sous forme de somme forfaitaire**. Le report d’un dépôt sous forme de somme forfaitaire crée une écriture bancaire pour le montant total du dépôt, qui peut faciliter le rapprochement bancaire.

### <a name="general-journal-templates-for-bank-deposits"></a>Modèles journal général pour les dépôts bancaires

Vous devez également créer un modèle journal général pour les dépôts. Vous utilisez les journaux généraux pour reporter des écritures dans les comptes banque, client, fournisseur, immobilisation et grand livre. Les modèles journal conçoivent le journal général en fonction de l’objectif de votre travail. Autrement dit, les champs du modèle de journal sont exactement ceux dont vous avez besoin.

Les dépôts seront des encaissements. Vous pouvez donc réutiliser votre série de numéros pour les journaux règlement. Sinon, si vous devez faire la distinction entre les écritures journal des dépôts bancaires et des encaissements, utilisez une série de numéros différente.

Vous devrez également créer un traitement en lot pour le modèle. Pour créer un traitement en lot, sur la page **Modèles journal général**, choisissez l’action **Lots**. Pour en savoir plus sur les lots, reportez-vous à [Utilisation de modèles et de lots journal](ui-work-general-journals.md#use-journal-templates-and-batches).

## <a name="dimensions-on-bank-deposit-lines"></a>Dimensions sur les lignes de dépôt bancaire

Les lignes du dépôt bancaire utiliseront automatiquement les dimensions par défaut que vous avez spécifiées dans les champs **Code emplacement immo** et **Code groupe clients**. Lorsque vous choisissez **Client** ou **Fournisseur** dans le champ **Type de compte**, les dimensions spécifiées pour le client ou le fournisseur remplaceront les valeurs par défaut. Au besoin, vous pouvez modifier les dimensions sur les lignes.

> [!TIP]
> Les dimensions sur les lignes sont définies en fonction des priorités de dimension par défaut. Les dimensions ligne sont prioritaires par rapport aux dimensions en-tête. Pour éviter les conflits, vous pouvez créer des règles qui déterminent quand utiliser une dimension en fonction de la source. Si vous souhaitez modifier la priorité des dimensions, vous pouvez modifier leur classement dans l’onglet **Priorités de dimensions par défaut**. Pour plus d’informations, voir [Pour configurer des priorités de dimensions par défaut](finance-dimensions.md#to-set-up-default-dimension-priorities).

## <a name="create-a-bank-deposit"></a>Créer un dépôt bancaire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Dépôts bancaires**, puis sélectionnez le lien associé.
2. Choisissez **Nouveau** pour ouvrir la page **Dépôt bancaire**.
3. Choisissez le modèle journal général que vous avez créé pour les dépôts bancaires.  

    > [!NOTE]
    > Si le modèle journal général comporte plusieurs lots, vous serez invité à en choisir un.

4. Dans le champ **N° compte bancaire**, choisissez le compte bancaire sur lequel effectuer le dépôt.

    > [!TIP]
    > Vous pouvez vérifier que vous déposez sur le compte correct en utilisant les actions **Fiche compte** et **Écritures compte** pour rechercher les écritures pour le compte bancaire sélectionné. Par exemple, pour vérifier si des dépôts similaires ont été effectués sur le compte.

5. Dans le champ **Montant total du dépôt**, entrez le montant total du dépôt. Ce total doit être la somme des montants de toutes les lignes.
6. Renseignez les champs restants selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]

    La date du champ **Date de report** et les dimensions des champs **Code département** et **Code groupe clients** seront affectées aux lignes que vous créez pour le dépôt bancaire. Si nécessaire, vous pouvez les modifier.

7. Selon que vous souhaitez reporter le dépôt bancaire sous forme de somme forfaitaire ou chaque ligne individuellement dans le grand livre bancaire, activez ou désactivez le bouton **Reporter sous forme de somme forfaitaire**. Le paramètre par défaut provient du même bouton bascule sur la page **Configuration ventes**.

    > [!NOTE]
    > Le champ **Code devise** indique la devise spécifiée pour le compte bancaire que vous avez choisi. Vous ne pouvez pas choisir une devise différente.

8. Sur le raccourci **Lignes**, créez une nouvelle ligne pour chaque paiement en espèces que vous souhaitez déposer.
9. Dans le champ **Type de compte**, précisez d’où provient le paiement. Pour les dépôts bancaires, le type est généralement **Client** ou **Fournisseur**.

    > [!NOTE]
    > Vous pouvez également enregistrer un paiement en espèces pour un fournisseur. Pour ce faire, choisissez **Fournisseur**, puis entrez le montant du paiement sous la forme d’un nombre négatif dans le champ **Montant du crédit** sur la ligne.

10. Dans le champ **N° document**, saisissez le numéro de document de la facture d’où provient le montant crédit. Vous pouvez utiliser un numéro de document pour chaque ligne ou le même numéro pour toutes les lignes.

    > [!TIP]
    > En règle générale, vous n’avez pas besoin de remplir le champ **Type de document** pour les écritures financières. Par exemple, si vous déposez de l’argent provenant de la vente d’une journée, vous laissez le champ vide. Si vous déposez de l’argent provenant d’un paiement client, vous choisissez **Paiement**.

11. Si vous déposez un paiement en espèces pour une facture client spécifique, choisissez l’action **Affecter écritures**, puis saisissez le numéro de facture dans le champ **Code référence**.
12. Si vous êtes prêt à reporter le dépôt bancaire, choisissez l’action **Reporter**.

    > [!TIP]
    > Avant de reporter le dépôt, vous pouvez utiliser l’action **Rapport de test** pour vérifier vos données. Le rapport indiquera s’il existe des problèmes, tels que des données manquantes, qui empêcheront le report.  

## <a name="find-posted-bank-deposits"></a>Rechercher des dépôts bancaires reportés

La page **Dépôts bancaires reportés** répertorie les dépôts antérieurs de votre compagnie. Dans la liste, vous pouvez vérifier les commentaires et les dimensions qui ont été spécifiés pour les dépôts. Vous pouvez ouvrir le dépôt bancaire pour afficher plus de détails, et à partir de là, vous pouvez approfondir vos recherches. Par exemple, vous pouvez choisir l’action **Rechercher des écritures** pour afficher les écritures bancaires reportées. À partir de l’écriture banque, vous pouvez trouver l’écriture reportée correspondante dans le grand livre.

Si vous voulez consulter toutes les écritures du grand livre pour les lignes de dépôt reportées, accédez à la page **Registre GL** et utilisez l’action **Grand livre**. Vous y trouverez toutes les écritures, y compris les écritures pour les clients et les fournisseurs.

## <a name="reverse-a-posted-bank-deposit"></a>Inverser un dépôt bancaire reporté

Il existe plusieurs façons d’inverser un dépôt bancaire reporté :

* Sur la page **Dépôts bancaires reportés**, choisissez le dépôt, puis choisissez l'action **Annuler le report**.
* Sur la page **Registres GL**, identifiez le registre du dépôt, puis choisissez l’action **Inverser le registre**.

> [!NOTE]
> Vous pouvez uniquement inverser un registre contenant un seul type d’écriture. Autrement dit, le registre ne doit contenir que des écritures client ou des écritures fournisseur, mais ne peut pas contenir les deux. Si un historique contient les deux, vous devez inverser manuellement le dépôt.

## <a name="see-also"></a>Voir aussi

[Finance](finance.md)  
[Configuration de Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]



