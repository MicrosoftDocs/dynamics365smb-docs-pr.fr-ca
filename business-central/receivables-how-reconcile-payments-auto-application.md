---
title: Utilisation de l'affectation automatique pour rapprocher les paiements | Microsoft Docs
description: Décrit comment utiliser la fonction d'affectation automatique pour affecter les paiements ou les encaissements à leurs écritures ouvertes connexes, et rapprocher les paiements.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 693373c91fcc2bc8d0ef4eb3acea99dd13d9eaa0
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "814107"
---
# <a name="reconcile-payments-using-automatic-application"></a>Rapprocher les paiements à l'aide de l'affectation automatique
La page **Journal rapprochement paiement** spécifie les paiements (entrants ou sortants) qui ont été enregistrés en tant que transactions sur votre compte bancaire en ligne et que vous pouvez affecter à leurs écritures ouvertes client, fournisseur et compte bancaire. Vous renseignez les lignes du journal en important un relevé bancaire sous forme de fichier ou flux bancaire.

> [!NOTE]
> La page offre une fonctionnalité de correspondance automatique qui affecte les paiements à leurs écritures ouvertes associées sur la base d'une correspondance entre le texte d'une ligne de relevé bancaire (ligne journal) et le texte d'une ou de plusieurs écritures ouvertes. Notez que vous pouvez remplacer les applications automatiques suggérées, et vous pouvez choisir de ne pas utiliser du tout l'application automatique. Pour plus d'informations, voir l'étape 7.

Une feuille rapprochement bancaire est associée à un compte bancaire dans [!INCLUDE[d365fin](includes/d365fin_md.md)], qui reflète le compte bancaire en ligne sur lequel les transactions de paiement sont validées. Toutes les écritures comptables compte bancaire ouvertes associées au client lettré ou à des écritures comptables fournisseur sont clôturées lorsque vous sélectionnez l'action **Valider les paiements et rapprocher les comptes bancaires**. Cela signifie que le compte bancaire est automatiquement rapproché pour les paiements que vous reportez avec le journal.

Si vous souhaitez importer des relevés bancaires en tant que flux bancaires, vous devez d'abord activer le service de flux de la Envestnet Yodlee Bank, puis associer le compte bancaire au compte bancaire en ligne associé. La feuille rapprochement bancaire détectera alors automatiquement les flux bancaire si vous sélectionnez l'action **Importer les transactions bancaires**. En outre, vous pouvez définir un compte bancaire de sorte à importer automatiquement de nouveaux flux de relevés bancaires toutes les heures. Les transactions pour les paiements qui ont déjà été reportés comme affectés et/ou rapprochés ne sont pas importées. Pour plus d'informations, voir [Configurer le service de flux de la Envestnet Yodlee Bank](bank-how-setup-bank-statement-service.md).

L'action **Mapper le texte avec le compte** vous permet de configurer des mappages entre le texte des paiements et des comptes de débit, de crédit et de contrepartie spécifiques afin que ces paiements soient validés dans les comptes spécifiés lorsque vous validez la feuille rapprochement bancaire. Reportez-vous à l'étape 8. Pour plus d'informations, voir [Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Une fonctionnalité similaire existe pour rapprocher les montants excédentaires sur les lignes journal rapprochement paiement de façon ponctuelle. Pour plus d'informations, voir [Rapprocher les paiements qui ne peuvent pas être affectés](receivables-how-reconcile-payments-cannot-apply-auto.md).

Vous utilisez la fonction **Affecter automatiquement**, soit automatiquement lorsque vous importez un fichier ou flux bancaire avec des transactions de paiement ou lorsque vous l'activez, pour affecter des paiements à leurs écritures ouvertes associées sur la base d'une correspondance entre le texte d'une ligne relevé bancaire (ligne journal) et le texte d'une ou plusieurs écritures ouvertes.

Sur les lignes feuille dans lesquelles un paiement a été lettré automatiquement à une ou plusieurs écritures ouvertes, le champ **Fiabilité correspondance** présente une valeur entre Faible et Élevée pour indiquer la qualité de la correspondance des données sur laquelle le lettrage de paiement suggéré est basée. En outre, les champs **Type de compte** et **N° compte** sont renseignés à l'aide des informations sur le client ou le fournisseur auquel le paiement est affecté. Si vous définissez un mappage de texte à compte, le lettrage automatique peut entraîner une valeur de fiabilité de correspondance **Élevée – Mappage de texte à compte**.

Pour chaque ligne journal de la page **Journal rapprochement paiement**, vous pouvez ouvrir la page **Affectation paiement** pour visualiser toutes les écritures ouvertes candidates au paiement et pour afficher les informations détaillées pour chaque écriture sur la correspondance des données sur laquelle une affectation de paiement est basée. Ici, vous pouvez affecter les paiements manuellement ou réaffecter les paiements qui ont été automatiquement affectés à une écriture incorrecte. Pour plus d'informations, voir [Réviser ou affecter les paiements après affectation automatique](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> Vous pouvez lancer l'importation des transactions bancaires en même temps que vous ouvrez la page **Journal rapprochement paiement** pour un journal rapprochement paiement existant sur la page **Journaux rapprochement paiement**. La procédure suivante décrit comment importer des transactions bancaires sur la page **Journal rapprochement paiement** après avoir créé un journal.

## <a name="to-reconcile-payments-using-automatic-application"></a>Pour rapprocher les paiements à l'aide de l'affectation automatique
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux rapprochement paiement**, puis sélectionnez le lien associé.
2. Pour travailler dans une nouvelle feuille rapprochement bancaire, sélectionnez l'action **Nouvelle feuille**.
3. Sur la page **Liste comptes bancaires paiement**, sélectionnez le compte bancaire pour lequel vous voulez rapprocher des paiements, puis cliquez sur le bouton **OK**.
   La page **Journal rapprochement paiement** s'ouvre préparée pour le compte bancaire sélectionné.
4. Choisissez l'action **Importer les transactions bancaires**.
   Si le compte bancaire pour le journal sélectionné n'est pas configuré pour importer des transactions bancaires, alors une boîte de dialogue s'ouvre pour vous aider à renseigner les champs appropriés.
5. Sur la page **Sélectionner un fichier à importer**, sélectionnez le fichier contenant les transactions bancaires pour les paiements que vous souhaitez rapprocher, puis cliquez sur le bouton **Ouvrir**.  
6. Si le service de relevé bancaire est activé, sur la page **Filtre de relevé bancaire** qui s'ouvre automatiquement, spécifiez l'intervalle de temps pour l'importation des relevés bancaires.

    La page **Journal rapprochement paiement** est renseignée avec les lignes pour les paiements représentant les transactions bancaires dans le relevé bancaire importé.

    Sur les lignes pour les paiements qui ont été automatiquement lettrés à leurs écritures ouvertes associées, le champ **Fiabilité correspondance** présente une valeur entre **Faible** et **Élevée** pour indiquer la qualité de la correspondance des données sur laquelle le lettrage du paiement suggéré est basé. En outre, les champs **Type de compte** et **N° compte** sont renseignés à l'aide des informations sur le client ou le fournisseur auquel le paiement est affecté.
7. Sélectionnez une ligne journal, puis sélectionnez l'action **Affecter manuellement** pour réviser, appliquer à nouveau ou affecter le paiement manuellement sur la page **Affectation paiement**. Pour plus d'informations, voir [Réviser ou affecter les paiements après affectation automatique](receivables-how-review-apply-payments-auto-application.md).

    Une fois le lettrage manuel terminé, le champ **Fiabilité correspondance** de la ligne feuille que vous avez traitée manuellement contient la valeur **Accepté**.
8. Sélectionnez une ligne feuille non lettrée pour une réception ou une dépense récurrente en liquide, par exemple l'achat de carburant pour une voiture, puis sélectionnez **Mapper le texte avec le compte**. Pour plus d'informations, voir [Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).
9. Une fois terminé le mappage du texte de paiement avec les comptes, sélectionnez l'action **Lettrer manuellement**.
10. Lorsque vous êtes certain que tous les paiements sur les lignes journal sont correctement affectés ou définis sur le report direct, sélectionnez l'action **Reporter**, puis choisissez l'une des options suivantes :

    - **Reporter les paiements et rapprocher les comptes bancaires** - Pour reporter les paiements comme affectés et fermer également les écritures de compte bancaire associées comme rapprochées.
    - **Reporter les paiements uniquement** - Pour reporter uniquement les paiements comme affectés, mais laisser les écritures de compte bancaire associées ouvertes. Requis lorsque vous devez rapprocher le compte bancaire séparément, par exemple. Pour plus d'informations, voir [Rapprocher des comptes bancaires séparément](bank-how-reconcile-bank-accounts-separately.md).
    - **Rapport de test** - Pour examiner le résultat du report avant de reporter. L'état **Relevé de compte bancaire** s'ouvre et affiche les mêmes champs qu'en bas de la page **Journal rapprochement paiement**.

Lorsque vous reportez le journal rapprochement paiement, les écritures ouvertes affectées sont fermées et les comptes client, fournisseur ou grand livre associés sont mis à jour. Pour les paiements sur les lignes journal basés sur le mappage de texte à compte, les comptes du grand livre, client et fournisseur spécifiés sont mis à jour. Pour toutes les lignes journal, des écritures de compte bancaire sont créées. Si vous sélectionnez l'action **Valider les paiements et rapprocher les comptes bancaires**, toutes les écritures comptables compte bancaire ouvertes associées au client lettré ou à des écritures comptables fournisseur sont clôturées Cela signifie que le compte bancaire est automatiquement rapproché pour les paiements que vous reportez avec le journal.

Vous pouvez comparer la valeur du champ **Solde sur compte bancaire après validation** avec la valeur du champ **Solde final du relevé** pour avoir un suivi lorsque le compte bancaire a fait l'objet d'un rapprochement en fonction des paiements que vous validez.

> [!NOTE]  
>   Si vous ne souhaitez pas rapprocher le compte bancaire à partir de la page **Journal rapprochement paiement**, vous devez utiliser la page **Rapprochement compte bancaire**. Pour plus d'informations, reportez vous à [Rapprocher des comptes bancaires séparément](bank-how-reconcile-bank-accounts-separately.md).

## <a name="see-also"></a>Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
