---
title: Rapprocher les paiements à l'aide de l'affectation automatique
description: Décrit comment rapprocher les paiements avec la fonction d'affectation automatique pour affecter les paiements ou les règlements à leurs écritures ouvertes correspondantes.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment process, direct payment posting, reconcile payment, expenses, cash receipts'
ms.search.form: '389, 1290, 1294, 1287'
ms.date: 06/22/2022
ms.author: bholtorf
---
# <a name="reconcile-payments-using-automatic-application" />Rapprocher les paiements à l'aide de l'affectation automatique

La page **Journal de rapprochement bancaire** précise les paiements, entrants ou sortants, qui ont été enregistrés comme des transactions sur votre compte bancaire en ligne ou sur un service de paiement. Vous pouvez affecter les paiements aux écritures client, fournisseur et compte bancaire ouvertes associées. Complétez le journal en important un relevé bancaire en tant que flux ou fichier bancaire ou en saisissant manuellement les transactions que vous effectuez sur votre service de paiement.

> [!NOTE]
> La page offre une fonctionnalité de correspondance automatique qui affecte les paiements à leurs écritures ouvertes associées sur la base d’une correspondance entre les données d’une ligne de relevé bancaire (ligne journal) et les données d’une ou de plusieurs écritures ouvertes. Notez que vous pouvez remplacer les applications automatiques suggérées, et vous pouvez choisir de ne pas utiliser du tout l'application automatique. Pour plus d'informations, voir l'étape 7.

Un journal de rapprochement bancaire est lié à un compte bancaire dans [!INCLUDE[prod_short](includes/prod_short.md)]. Le compte bancaire représente le compte bancaire en ligne où sont enregistrées les opérations de paiement. Toutes les écritures comptables compte bancaire ouvertes associées au client lettré ou à des écritures comptables fournisseur sont clôturées lorsque vous sélectionnez l'action **Valider les paiements et rapprocher les comptes bancaires**. Le compte bancaire est automatiquement rapproché pour les paiements que vous reportez avec le journal.

Si vous utilisez la page **Journal rapprochement des paiements** pour enregistrer et affecter des paiements clients, vous pouvez configurer le journal pour qu'il utilise une série de numéros spécifique. Ensuite, vous pouvez spécifier la série de numéros dans le champ **Séries de numéros rapprochement des paiements** sur un compte bancaire. L’utilisation d’une série de numéros dédiée peut faciliter l’identification des écritures qui ont été reportées via le journal.

Comme pour les autres journaux, lorsque vous corrigez des écritures reportées, vous pouvez inverser des écritures qui ont été reportées via le journal rapprochement des paiements à partir de la page **Registre GL**. Par exemple, vous souhaiterez peut-être inverser des écritures pour des paiements que vous avez affectés au mauvais client. Vous devez d’abord annuler l'affectation des écritures client reportées. Ensuite, vous pouvez utiliser l’action **Inverser le registre** dans la page **Registre GL** pour inverser le journal ayant reporté les paiements. Sinon, sur la page **Journaux généraux reportés**, vous pouvez utiliser l’action **Copier les lignes sélectionnées dans le journal** pour inverser des lignes spécifiques du journal rapprochement des paiements reporté. 

Lorsque vous utilisez l’affectation automatique, [!INCLUDE[prod_short](includes/prod_short.md)] reconnaît les écritures bancaires déjà reportées, ce qui permet d’éviter les doubles reports.

Vous pouvez importer des transactions bancaires sous forme de fichiers bancaires .csv ou d’un autre format fourni par votre banque. Si vous souhaitez importer des relevés bancaires en tant que flux bancaires, vous devez d’abord activer le service d’intégration bancaire dédié, puis associer le compte bancaire au compte bancaire en ligne associé. La feuille rapprochement bancaire détectera alors automatiquement les flux bancaire si vous sélectionnez l'action **Importer les transactions bancaires**. En outre, vous pouvez définir un compte bancaire de sorte à importer automatiquement de nouveaux flux de relevés bancaires toutes les heures. Les transactions pour les paiements qui ont déjà été reportés comme affectés et/ou rapprochés ne sont pas importées. Vous pouvez utiliser le service Envestnet Yodlee Bank Feeds pour obtenir ces transactions ; il est préinstallé dans certaines versions localisées de [!INCLUDE[d365fin](includes/d365fin_md.md)]. Pour plus d'informations, voir [Configurer le service Envestnet Yodlee Bank Feeds](bank-how-setup-bank-statement-service.md). Vous pouvez également contacter votre partenaire Microsoft pour obtenir de l’aide pour répondre aux exigences de votre entreprise ou de votre pays.

L’action **Mapper le texte avec le compte** vous permet de configurer des mappages entre le texte des paiements et des comptes de débit, de crédit et de contrepartie spécifiques afin que ces paiements soient reportés dans les comptes spécifiés lorsque vous reportez le journal rapprochement bancaire. Cela s’avère utile, par exemple, pour les recettes ou dépenses récurrentes en liquide, notamment les achats fréquents de carburant pour les voitures ou les frais et intérêts bancaires, qui apparaissent régulièrement sur le relevé bancaire et n’ont pas besoin d’un document d’entreprise lié. (Voir l’étape 10 ci-dessous) Pour plus d’informations, reportez-vous à [Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Les lignes de journal peuvent ne pas avoir d’application suggérée, et ce pour diverses raisons. Par exemple, parce qu'un document est manquant ou qu’un client a versé un montant trop élevé et qu’il y a un montant excédentaire après l’affectation du paiement sur une autre ligne journal. Dans de tels cas, vous pouvez utiliser l’action **Transférer la différence vers un compte** pour créer et reporter l’écriture de grand livre manquante, par exemple pour un remboursement, qui est nécessaire pour affecter le paiement. (Voir l’étape 11) Pour plus d’informations, voir [Rapprocher les paiements qui ne peuvent pas être affectés.](receivables-how-reconcile-payments-cannot-apply-auto.md).

Vous utilisez la fonction **Affecter automatiquement**, soit automatiquement lorsque vous importez un fichier ou flux bancaire avec des transactions de paiement ou lorsque vous l’activez, pour affecter des paiements à leurs écritures ouvertes associées sur la base d’une correspondance entre le texte d’une ligne relevé bancaire (ligne journal) et le texte d’une ou plusieurs écritures ouvertes. Cette automatisation est basée sur des règles que vous définissez sur la page **Règles d’affectation de paiement**, où vous définissez également si une suggestion d’affectation doit être examinée. Pour plus d'informations, voir [Configurer des règles pour l'affectation automatique des paiements](receivables-how-set-up-payment-application-rules.md).

Sur les lignes journal dans lesquelles un paiement a été affecté automatiquement à une ou plusieurs écritures ouvertes, le champ **Fiabilité correspondance** présente une valeur **Faible**, **Moyenne** ou **Élevée** pour indiquer la qualité de la correspondance des données sur laquelle l’affectation de paiement suggérée est basée.

Certaines affectations de paiement nécessitent que vous les examiniez tel que défini par la règle de correspondance utilisée, comme les lignes avec une fiabilité de correspondance **Faible**. Les autres lignes nécessitent que vous les examiniez ainsi qu’une modification manuelle, car il y a une valeur dans le champ **Différence**. Pour examiner une ou plusieurs affectations de paiement, choisissez le champ **Lignes à vérifier** ou **Lignes avec différence** en bas. La page **Révision affectation paiement** s’ouvre et affiche toutes les informations pertinentes sur le client ou le fournisseur auquel le paiement est affecté, les détails de la correspondance et les actions pour traiter la ligne, telles que l’action **Accepter l’affectation**. (Voir les étapes 7 et 8)

Pour chaque ligne journal de la page **Journal rapprochement paiement**, vous pouvez ouvrir la page **Affectation paiement** pour visualiser toutes les écritures ouvertes candidates au paiement et pour afficher les informations détaillées pour chaque écriture sur la correspondance des données sur laquelle une affectation de paiement est basée. Ici, vous pouvez affecter les paiements manuellement ou réaffecter les paiements qui ont été automatiquement affectés à une écriture incorrecte. (Voir l’étape 10) Pour plus d’informations, voir [Réviser ou affecter les paiements après affectation automatique](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> Vous pouvez lancer l’importation des transactions bancaires en même temps que vous ouvrez la page **Journal rapprochement bancaire** pour un journal existant. La procédure suivante décrit comment importer des transactions bancaires sur la page **Journal rapprochement paiement** après avoir créé un journal.

## <a name="to-reconcile-payments-using-automatic-application" />Pour rapprocher les paiements à l'aide de l'affectation automatique
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux rapprochement bancaire**, puis sélectionnez le lien associé.
2. Pour travailler dans une nouvelle feuille rapprochement bancaire, sélectionnez l'action **Nouvelle feuille**.
3. Sur la page **Liste comptes bancaires paiement**, sélectionnez le compte bancaire pour lequel vous voulez rapprocher des paiements, puis cliquez sur le bouton **OK**.
   La page **Journal rapprochement paiement** s'ouvre préparée pour le compte bancaire sélectionné.
4. Choisissez l'action **Importer les transactions bancaires**.
   Si le compte bancaire du journal sélectionné n’est pas configuré pour importer des opérations bancaires, [!INCLUDE[d365fin](includes/d365fin_md.md)] vous aide à y parvenir.
5. Sur la page **Sélectionner un fichier à importer**, sélectionnez le fichier contenant les transactions bancaires pour les paiements que vous souhaitez rapprocher, puis cliquez sur le bouton **Ouvrir**.  
6. Si le service Envestnet Yodlee Bank Feeds est activé, sur la page **Filtre de relevé bancaire** qui s’ouvre automatiquement, spécifiez l’intervalle de temps pour l’importation des relevés bancaires.

    La page **Journal rapprochement paiement** est renseignée avec les lignes pour les paiements représentant les transactions bancaires dans le relevé bancaire importé.

     Sur les lignes pour les paiements qui ont été automatiquement affectés à leurs écritures ouvertes associées, le champ **Fiabilité correspondance** indique la qualité de la correspondance des données sur laquelle l'affectation du paiement suggéré est basée. En outre, les champs **Nom du compte**, **Type de compte** et **N° compte** présentent des informations sur le client ou le fournisseur auquel le paiement est affecté.

    Les affectations automatiques, les qualités de correspondance et la nécessité de réviser les lignes sont définies par des règles. Vous pouvez modifier les règles pour ajuster les résultats. Pour plus d'informations, voir [Configurer des règles pour l'affectation automatique des paiements](receivables-how-set-up-payment-application-rules.md).

7. Pour examiner, accepter/supprimer ou modifier manuellement plusieurs affectations de paiement qui ont une valeur dans le champ **Différence**, choisissez l’action **Lignes avec différence** en bas.

    La page **Révision affectation paiement** s’ouvre et affiche la première affectation à examiner. La prochaine affectation à examiner sera affichée sur la page au fur et à mesure que vous traitez la précédente. La révision inclut des informations sur le client ou le fournisseur auquel le paiement est affecté, les détails de la correspondance et les actions pour traiter la ligne, telles que les actions **Accepter l'affectation** et **Affecter manuellement**.

8. Pour examiner, accepter/supprimer ou modifier manuellement plusieurs affectations de paiement que la règle a définies comme devant être examinées, choisissez l’action **Lignes à réviser**. 

9. Pour modifier une affectation automatique, sélectionnez une ligne journal, puis sélectionnez l’action **Affecter manuellement** pour affecter à nouveau ou affecter le paiement manuellement sur la page **Affectation paiement**. Pour plus d'informations, voir [Réviser ou affecter les paiements après affectation automatique](receivables-how-review-apply-payments-auto-application.md).

10. Sélectionnez une ligne feuille non lettrée pour une réception ou une dépense récurrente en liquide, par exemple l'achat de carburant pour une voiture, puis sélectionnez **Mapper le texte avec le compte**. Pour plus d'informations, voir [Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

    Une fois terminé le mappage du texte de paiement avec les comptes, sélectionnez l’action **Affecter manuellement**.

    Lorsqu’un mappage texte avec compte est configuré, l'affectation de paiement automatique qui en résulte contiendra **Élevée - Mappage de texte à compte** dans le champ **Fiabilité correspondance**.

11. Pour une ligne journal qui n’a pas d'affectation suggérée car il n’existe aucune écriture à laquelle elle peut être affectée, choisissez l’action **Transférer la différence vers un compte** pour créer et reporter l’écriture grand livre manquante à laquelle affecter le paiement. Pour plus d’informations, voir [Rapprocher les paiements qui ne peuvent pas être affectés](receivables-how-reconcile-payments-cannot-apply-auto.md).

12. Lorsqu’il n’y a plus de lignes à examiner et que le champ **Différence** est vide sur toutes les lignes, choisissez l’action **Reporter**, puis choisissez l’une des options suivantes :

    - **Reporter les paiements et rapprocher les comptes bancaires** - Pour reporter les paiements comme affectés et fermer également les écritures de compte bancaire associées comme rapprochées.
    - **Reporter les paiements uniquement** - Pour reporter uniquement les paiements comme affectés, mais laisser les écritures de compte bancaire associées ouvertes. Exige que vous rapprochiez le compte bancaire séparément, par exemple. Pour plus d'informations, voir [Rapprocher des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md).
    - **Rapport de test** - Pour examiner le résultat du report avant de reporter. L'état **Relevé de compte bancaire** s'ouvre et affiche les mêmes champs qu'en bas de la page **Journal rapprochement paiement**.

Lorsque vous reportez le journal rapprochement des paiements, les écritures ouvertes affectées sont fermées. Les comptes client, fournisseur ou grand livre sont mis à jour. Pour les paiements sur les lignes journal basés sur le mappage de texte à compte, les comptes du grand livre, client et fournisseur spécifiés sont mis à jour. Pour toutes les lignes journal, des écritures de compte bancaire sont créées. Si vous sélectionnez l'action **Valider les paiements et rapprocher les comptes bancaires**, toutes les écritures comptables compte bancaire ouvertes associées au client lettré ou à des écritures comptables fournisseur sont clôturées Cela signifie que le compte bancaire est automatiquement rapproché pour les paiements que vous reportez avec le journal.

Vous pouvez comparer la valeur du champ **Solde sur compte bancaire après validation** avec la valeur du champ **Solde final du relevé** pour avoir un suivi lorsque le compte bancaire a fait l'objet d'un rapprochement en fonction des paiements que vous validez.

> [!NOTE]  
>   Si vous ne souhaitez pas rapprocher le compte bancaire à partir de la page **Journal rapprochement paiement**, vous devez utiliser la page **Rapprochement compte bancaire**. Pour plus d'informations, voir [Rapprocher des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md).

## <a name="see-related-microsoft-trainingtrainingmodulesuse-journals-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/use-journals-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
