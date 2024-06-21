---
title: Modifier l’aspect d’un rapport en sélectionnant une disposition différente
description: 'Vous pouvez utiliser différentes présentations d''un rapport, et passer d''une présentation à l''autre pour modifier l''aspect d''un rapport.'
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'customized report, document layout, logo, personalize'
ms.search.form: '9652, 9650'
ms.date: 03/07/2022
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# (Hérité) Définir la présentation utilisée par un rapport

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

Un rapport peut être créé avec plus d'une présentation de rapport, que vous pouvez ensuite changer au besoin.

Selon les présentations qui sont disponibles pour un rapport, vous pouvez choisir d'utiliser une présentation de rapport RDLC intégrée, une présentation de rapport Word, ou une présentation personnalisée. Pour plus d'informations sur les présentations de rapport RDLC et Word, les présentations intégrées et personnalisées, et plus encore, reportez-vous à [Gérer la présentation des états](ui-manage-report-layouts.md).

Lorsque des présentations de rapport personnalisées sont définies, vous pouvez les sélectionner à partir des fiches client et fournisseur pour spécifier que les présentations sélectionnées sont utilisées pour les documents que vous créez pour le client ou le fournisseur en question. Pour plus d'informations, voir [Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md).

> [!TIP]  
> Les rapports de document (pas les listes) qui utilisent une mise en page de rapport Word sont généralement plus rapides que ceux qui utilisent une mise en page de rapport RDLC. Ainsi, si vous avez la possibilité de choisir entre une mise en page de rapport Word ou RDLC pour un rapport de document, utilisez la mise en page de rapport Word pour de meilleures performances.

## Pour modifier la présentation de rapport à utiliser pour un rapport ou un document

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sélection présentation rapport**, puis sélectionnez le lien associé.
  
   La page **Sélection de présentation de rapport** répertorie tous les rapports disponibles pour la compagnie spécifiée dans le champ **Compagnie** en haut de la page. Le champ **Description présentation** <!-- **Selected Layout** -->spécifie la présentation qui est actuellement utilisée sur le rapport.
2. Définissez le champ **Compagnie** en haut de la compagnie qui inclut le rapport.

   Ce champ vous permet de définir différentes présentations pour le même rapport dans différentes compagnies.

3. Pour modifier la présentation utilisée par un rapport, sur la ligne correspondant au rapport, définissez le champ **Présentation sélectionnée** sur l'une des options suivantes :
   * **RDLC (intégré)**, utilise la présentation de rapport RDLC intégrée sur le rapport.
   * **Word (intégré)**, utilise la présentation de rapport Word intégrée sur le rapport.
   * **Personnalisée**, utilise une présentation personnalisée sur le rapport.  

> [!NOTE]
> Si vous choisissez une présentation de rapport de type **RDLC (intégré)** ou **Word (intégré)** et si vous recevez un message d'erreur indiquant que le rapport n'a pas de présentation du type spécifié, alors vous devez choisir une autre option de présentation ou créer une présentation de rapport personnalisée du type que vous souhaitez utiliser. Consultez la procédure suivante.

Si vous avez sélectionné une présentation de rapport RDLC ou Word intégrée, aucune action supplémentaire n'est requise, et la présentation sera utilisée la prochaine fois que le rapport sera exécuté.

## Pour modifier la présentation personnalisée à utiliser pour une présentation de rapport

Vous pouvez également modifier la présentation personnalisée actuellement utilisée. Pour plus d'informations, voir [Créer et modifier des présentations de rapport personnalisées](ui-how-create-custom-report-layout.md).

Toutes les présentations de rapport personnalisées qui existent pour les présentations de rapport dans une compagnie sont répertoriées sur la page **Présentations de rapport personnalisées**. Sur la page **Sélection de présentation de rapport**, il est possible de savoir quelles présentations personnalisées sont disponibles pour chaque rapport dans le récapitulatif **Présentations personnalisées**.

1. Sur la page **Sélection de présentation de rapport**, sur la ligne de la présentation de rapport que vous souhaitez modifier, cliquez sur le bouton de recherche dans le champ **Description présentation personnalisée**.
2. Sur la page **Présentations de rapport personnalisées**, sélectionnez la ligne de la présentation personnalisée que vous souhaitez utiliser, puis cliquez sur le bouton **OK**.

Le nom de la présentation personnalisée sélectionnée s'affiche maintenant dans le champ **Description présentation personnalisée**, et sera utilisé la prochaine fois que le rapport ou le document sera prévisualisé, imprimé ou envoyé.

Vous pouvez maintenant accéder à vos fiches client et fournisseur pour spécifier les présentations à utiliser pour différents documents que vous créez pour le client ou le fournisseur en question, comme les confirmations de commande ou les rappels de paiement. Pour plus d'informations, voir [Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md).

## Voir aussi
[Gestion des présentations de rapport](ui-manage-report-layouts.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
