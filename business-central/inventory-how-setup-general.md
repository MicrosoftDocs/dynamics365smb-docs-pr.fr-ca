---
title: Configurer des informations générales relatives à l'inventaire
description: Décrit comment définir la configuration inventaire général afin que vous puissiez gérer votre entrepôt et votre stock.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'warehouse, stock'
ms.search.form: '30, 456, 461'
ms.date: 07/28/2021
ms.author: edupont
---
# <a name="set-up-general-inventory-information"></a>Configurer des informations générales relatives à l'inventaire

Vous pouvez spécifier votre configuration d'inventaire générale sur la page **Configuration de l'inventaire**.

## <a name="to-set-up-general-inventory-information"></a>Pour configurer des informations générales relatives à l'inventaire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration de l’inventaire**, puis choisissez le lien associé.
2. Sur la page **Configuration de l'inventaire**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pour des informations détaillées sur les champs d'évaluation des coûts **Report coûts automatique**, **Report coûts prévus** et **Mode évaluation coûts par défaut**, consultez [Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Détails de conception : évaluation du coût de l'inventaire](design-details-inventory-costing.md) et [Détails de conception : report du coût prévu](design-details-expected-cost-posting.md). Pour plus d’informations sur l'évaluation des coûts en général, voir [Gestion des coûts d'inventaire](finance-manage-inventory-costs.md).  

Vous pouvez inclure un délai entrepôt par défaut pour votre inventaire sur la page **Configuration de l'inventaire** ou pour votre emplacement dans le calcul de la promesse de livraison sur la ligne achat. Pour plus d'informations, voir [Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).  

> [!NOTE]
> Le champ **Ajustement automatique des coûts** est défini sur *Toujours* par défaut pour garantir que les valeurs de l’inventaire soient toujours correctes dans le grand livre, qui à son tour maintient vos statistiques vente et profit à jour. Les modifications de coût des écritures entrantes, telles que celles des sorties achat ou production, sont affectées aux écritures sortantes correspondantes, telles que les ventes ou les transferts. Ceci est utile pour les nouveaux clients et petites entreprises [!INCLUDE[prod_short](includes/prod_short.md)] avec des niveaux de transaction d'inventaire relativement bas.
>
> Cependant, à mesure que l’entreprise se développe et que les niveaux d'inventaire augmentent, cela peut ralentir les performances du système. Pour minimiser les performances réduites lors du report, sélectionnez une option de temps pour définir jusqu’où dans le passé depuis la date de travail une transaction entrante peut se produire pour déclencher potentiellement l’ajustement des entrées de valeur sortantes associées.
>
> Sinon, vous pouvez ajuster manuellement les coûts à intervalles réguliers avec le traitement en lot Ajuster coûts - Écr. article. Vous pouvez également désactiver le report automatique des coûts ou définir le champ **Ajustement automatique des coûts** sur *Jamais*. Dans les deux cas, une notification s’affiche pour vous permettre de démarrer un guide de configuration assistée qui vous aide à programmer des tâches pour la file d’attente des travaux. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## <a name="see-also"></a>Voir aussi

[Configuration du stock](inventory-setup-inventory.md)  
[Détails de conception : modes évaluation stock](design-details-costing-methods.md)  
[Gestion du stock](inventory-manage-inventory.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
