---
title: Création de budgets GL | Microsoft Docs
description: Décrit la création de budgets GL pour prévoir différentes activités financières et affecter des dimensions à des fins de veille économique.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: postpone
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 1a3adebe30e63ea295aed6aa7beffbf581ba1be3
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5784900"
---
# <a name="create-gl-budgets"></a>Créer des budgets GL
Vous pouvez avoir plusieurs budgets pour des périodes identiques en les créant sous des noms différents. Vous indiquez d'abord le nom du budget et entrez les chiffres correspondants. Le nom du budget est ensuite inclus sur toutes les écritures budget que vous créez.  

Lorsque vous créez un budget, vous pouvez définir quatre axes analytiques par budget. Ces dimensions propres au budget sont appelées dimensions budget. Vous sélectionnez les axes budget pour chaque budget parmi les axes analytiques que vous avez déjà configurés. Les dimensions budget peuvent être utilisées pour positionner des filtres sur un budget et pour ajouter des informations de dimensions aux écritures budget. Pour plus d'informations, reportez-vous à [Utilisation des axes](finance-dimensions.md).

Les budgets jouent un rôle important dans la veille économique, par exemple dans les états financiers basés sur des tableaux d'analyse incluant des écritures budget ou lors de l'analyse des montants budgétés et des montants réels dans le plan comptable. Pour plus d'informations, reportez-vous à [Veille économique](bi.md).

En comptabilité analytique, vous travaillez avec des budgets de coûts de manière similaire. Pour plus d'informations, voir [Procédure : Créer des budgets de coûts](finance-create-cost-budgets.md).    

## <a name="to-create-a-new-gl-budget"></a>Pour créer un budget GL  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Budgets grand livre**, puis sélectionnez le lien associé.  
2. Cliquez sur **Modifier la liste**, puis renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Sélectionnez **Modifier budget**.
4. En haut de la page **Budget**, renseignez les champs nécessaires pour définir ce qui est affiché.  

    Seules les écritures contenant le nom du budget entré dans le champ **Nom budget** s'affichent. Étant donné que le nom du budget vient juste d'être créé, aucune écriture ne correspond au filtre. Par conséquent, la page est vide.  
5. Pour entrer un montant, choisissez la cellule appropriée de la matrice. La page **Écritures budget** s'ouvre.  
6. Créez une ligne et renseignez le champ **Montant**. Fermez la page **Écritures budget**.  
7. Répétez les étapes 5 et 6 jusqu'à ce que vous ayez entré tous les montant du budget.  

> [!NOTE]  
>  Sur le raccourci **Filtres**, vous pouvez filtrer les informations sur le budget selon le nombre d'axes budget configurés sous le nom du budget.

## <a name="exporting-and-importing-gl-budgets-with-excel"></a>Exportation et importation de budgets GL vers Excel
Comme pour la majorité des autres pages, vous pouvez exporter des données des pages de budget vers Excel pour les traiter ou les analyser ultérieurement. Pour plus d'informations, voir [Exportation de vos données métier vers Excel](about-export-data.md).

> [!NOTE]
> Le plan comptable, sur lequel les budgets GL sont basés, comportent des lignes de compte de type En-tête qui contiennent le total des lignes sous ceux-ci. Lorsque vous exportez un budget GL, les données de toutes les lignes sont exportées quel que soit le type de compte. Cependant, seules les données sur les lignes du type de compte Report peuvent être réimportées. En conséquence : <br /><br /> **Lorsque vous importez un budget GL, toutes les valeurs qui existaient sur les lignes d'en-tête seront supprimées.** <br /><br /> Cette fonctionnalité permet d'éviter des totaux erronés après l'importation de données créées ou modifiées dans Excel.<br /><br /> **Scénario** : Vous savez que le nouveau coût des salaires budgétisé sera de 1 200 000 $. Vous souhaitez que le département Paies budgétise trois lignes spécifiques (du type de compte Report) pour les employés à temps plein, les employés à temps partiel et les intérimaires. Les trois lignes sont regroupées sous une ligne d'en-tête Paies.<br /><br />Vous saisissez 1 200 000 sur la ligne d'en-tête, exportez le budget vers Excel, puis l'envoyez au département Paies, en leur indiquant de distribuer les 1 200 000 $.<br /><br /> Le département Paies distribue le montant des trois comptes de report. Lorsque vous réimportez le budget GL, les trois comptes sont renseignés avec les nouvelles données Excel, pour une somme de 1 200 000 $, et la ligne d'en-tête est vide.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/budgets-exchange-rates-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Exportation de vos données métier vers Excel](about-export-data.md)  
[Finance](finance.md)  
[Veille économique](bi.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Le grand livre et le plan comptable](finance-general-ledger.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]