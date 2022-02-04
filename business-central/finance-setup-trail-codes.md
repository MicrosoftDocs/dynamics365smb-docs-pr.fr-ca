---
title: Configurer des codes pour les pistes d’audit
description: Découvrez les tâches de configuration des codes source et des codes motif que vous pouvez utiliser pour suivre les pistes d'audit.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'accounting, auditing, bookkeeping'
ms.search.form: '257, 259, 279'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="setting-up-source-codes-and-reason-codes-for-audit-trails"></a>Configuration des codes source et des codes de motif pour les pistes d'audit

Un code source est affecté automatiquement à toutes les écritures reportées, de sorte que les transactions puissent être suivies jusqu'à leur origine. Pour attribuer un autre code journal aux écritures, vous pouvez utiliser les codes motif. Ces derniers permettent d'indiquer le motif de création d'une écriture. Lorsque vous configurez des codes motif, vous pouvez les affecter à des lots journal et des modèles journal entiers, ainsi qu'à des lignes journal et des documents spécifiques.  

Pour les codes source et les codes motif, utilisez des codes faciles à mémoriser et descriptifs. Le code doit être unique et vous pouvez configurer autant de codes que vous le souhaitez.

## <a name="define-source-codes"></a>Définir des codes journaux

Parfois, vous souhaitez savoir comment une écriture particulière a été créée, par exemple si elle vient du report d'un journal général ou d'une facture achat. Un code journal indique l'emplacement de création d'une écriture. Les écritures sont créées lors du report des journaux et des factures et lors de l'exécution de certains traitements en lot. Chaque type de report a un code source spécifique qui est affecté lors de la création d'écritures individuelles.  

Le report de journaux, de commandes, de factures ou de notes de crédit, et l'exécution de divers traitement en lot, créent des écritures dans les états financiers. La page **Configuration code source** comporte plusieurs raccourcis, un pour chaque module. Chaque raccourci indique les codes sources applicables pour ce module.

Lorsque vous reportez ou exécutez un traitement en lot, le code source correct est relié automatiquement à l'écriture. Par exemple, lorsque vous reportez à partir du journal général, l'écriture est codée comme *JNLGÉN*. Vous pouvez ensuite filtrer la page **Écritures journal général** pour afficher les écritures qui ont été reportées à partir du journal général ou des documents vente, par exemple

### <a name="to-define-source-codes"></a>Pour définir des codes journaux

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") saisissez **Configuration du code source**, puis choisissez le lien associé.  

2. Dans la fenêtre **Configuration code source**, pour chaque type de report et traitement en lot, spécifiez le code source approprié.  

Vous pouvez modifier le contenu d'un champ ultérieurement, et cette modification aura alors un impact sur les reports futurs.

## <a name="change-source-codes"></a>Modifier les codes journaux

Vous pouvez modifier un code journal. Par exemple, vous pouvez remplacer le code journal *GENJNL* par *GNJ*.

### <a name="to-change-source-codes"></a>Pour modifier des codes journaux

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Codes journal.**, puis choisissez le lien associé.

2. Sur la ligne du code à modifier, sélectionnez le code dans le champ **Code**.

3. Saisissez le nouveau code, puis cliquez sur le bouton **OK**. Vous pouvez également modifier la valeur du champ **Description**.

Toutes les nouvelles écritures qui sont reportées à partir du journal général, se verront attribuer un nouveau code source.

## <a name="define-reason-codes"></a>Définir des codes motif

Les codes de motif complètent les codes source et sont utilisés pour indiquer la raison pour laquelle une écriture a été créée. Vous pouvez affecter des codes motif à des écritures individuelles, et affecter des codes permanents à des modèles journal et des lots journal spécifiques. Lorsqu'un code motif est lié à une ligne journal ou à un en-tête vente ou achat, toutes les écritures sont marquées avec le code motif lorsqu'elles sont reportées.  

### <a name="to-set-up-reason-codes"></a>Pour configurer des codes motif

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche")  entrez **Codes de motif**, puis choisissez le lien associé.

2. Dans la fenêtre **Codes motif**, saisissez le premier code dans le champ **Code**. Dans le champ **Description**, saisissez un texte explicatif.

Répétez cette procédure pour chaque code à utiliser. Vous pouvez configurer autant de codes que vous le souhaitez.

La procédure suivante décrit comment ajouter un code motif à un modèle journal, mais des procédures similaires s'appliquent à l'ajout d'un code motif à une ligne journal ou à un lot journal.  

### <a name="to-assign-reason-codes-to-journal-templates"></a>Pour affecter des codes motif à des modèles journal

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche")  entrez **Modèles journal général**, puis sélectionnez le lien associé.

2. Sur la ligne du modèle journal sélectionné, renseignez le champ **Code motif** avec le code souhaité.

3. Fermez le modèle journal.

Le code motif sélectionné est copié dans les nouveaux lots journal créées sous ce modèle journal. Pour affecter des codes motif à des modèles journal dans les autres modules, procédez de la même manière.

### <a name="to-use-reason-codes-on-sales-and-purchase-documents"></a>Pour utiliser des codes motif dans les documents achat et vente

1. Ouvrez le document achat ou vente approprié.

2. Dans l'en-tête achat ou vente, entrez le code dans le champ **Code motif**.

Lors du report de la facture, le code motif est copié sur chaque écriture du grand livre, client et fournisseur. Vous ne pouvez pas affecter différents codes motif aux lignes achat et vente individuelles, car toutes les lignes sont reportées sous la forme d'une écriture unique.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/set-up-financial-management-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi

[Finance](finance.md)  
[Rapprochement de comptes bancaires](bank-manage-bank-accounts.md)  
[Utilisation des dimensions](finance-dimensions.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Analyse de la trésorerie dans votre compagnie](finance-analyze-cash-flow.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]