---
title: Détails de conception - Modification des modes évaluation stock pour les articles
description: Découvrez comment attribuer un mode évaluation stock différent à un article bien que vous l'ayez déjà utilisé dans des transactions.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'costing methods, costing, item cost'
ms.search.form: 8645
ms.date: 06/08/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# <a name="design-details-change-the-costing-method-for-items"></a>Détails de conception : Modifier le mode évaluation stock pour les articles

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous ne pouvez pas modifier un mode évaluation stock pour un article après avoir inclus l'article dans une transaction. Par exemple, après avoir acheté ou vendu l'article. Si un mode évaluation stock incorrect a été affecté à l'article ou aux articles, vous ne découvrirez peut-être pas le problème tant que vous n'aurez pas effectué votre Financial Reporting.

Cette rubrique décrit comment résoudre cette situation. L'approche recommandée consiste à remplacer l'article dont le mode évaluation inventaire est incorrect par un nouvel article et à utiliser un ordre d'assemblage pour transférer l'inventaire de l'ancien article vers le nouveau.

> [!NOTE]
> L'utilisation des ordres d'assemblage permet aux coûts de continuer à circuler, bien qu'il y ait des factures achat ou des frais de livraison à reporter. De plus, cela vous permet d'annuler la conversion et de récupérer les quantités des articles d'origine, si nécessaire.

> [!TIP]
> Pour vous familiariser avec le processus, nous vous recommandons de démarrer le processus de conversion avec un seul article ou un petit ensemble d'articles.

## <a name="about-costing-methods"></a>À propos des modes évaluation stock

Les modes évaluation inventaire contrôlent les calculs de coûts lorsque les produits sont achetés, reçus en inventaire et vendus. Les modes évaluation stock affectent le calendrier des montants enregistrés dans les Valeurs sortie stock qui affectent le profit brut. C'est ce flux qui calcule les Valeurs sortie stock. Les Valeurs sortie stock (COGS) et les revenus sont utilisés pour déterminer le profit brut, comme suit :

*profit brut* = *revenus - COGS*

Lorsque vous configurez des articles d'inventaire, vous devez affecter un mode évaluation inventaire. Le mode peut varier d'une entreprise à l'autre et d'un article à l'autre, il est donc important de choisir le bon. [!INCLUDE[prod_short](includes/prod_short.md)] prend en charge les modes évaluation stock suivants :

* Moyenne
* FIFO
* LIFO
* Standard
* Spécifique

Pour plus d'informations, [Détails de conception : modes évaluation stock](design-details-costing-methods.md).

## <a name="use-assembly-orders-to-change-costing-method-assignments"></a>Utiliser des ordres d’assemblage pour modifier les affectations de mode évaluation stock

Cette section décrit les étapes suivantes pour modifier le mode évaluation stock affecté à un article :

1. Définir un mode évaluation stock par défaut.
2. Identifier les articles pour lesquels modifier le mode évaluation stock et les renuméroter.
3. Créer de nouveaux articles avec l'ancien schéma de numérotation et copier les données de base dans un lot.
4. Copier manuellement les données de base associées de l'article existant vers le nouvel article.
5. Déterminer la quantité en inventaire à convertir de l'article d'origine vers le nouvel article.
6. Transférer l'inventaire vers le nouvel article.
7. Gérer les quantités d'inventaire affectées à la demande.
8. Bloquer l'article d'origine de toute utilisation ultérieure.  

### <a name="define-a-default-costing-method"></a>Définir un mode évaluation stock

Pour éviter de futures erreurs, vous pouvez spécifier un mode évaluation stock par défaut pour les nouveaux articles. Chaque fois que quelqu'un crée un nouvel article, [!INCLUDE[prod_short](includes/prod_short.md)] suggérera le mode évaluation stock par défaut. Vous spécifiez le mode par défaut dans le champ **Mode évaluation inventaire par défaut** sur la page **Configuration inventaire**. 

### <a name="identify-the-items-to-change-the-costing-method-for-and-renumber-them"></a>Identifier les articles pour lesquels modifier le mode évaluation stock et les renuméroter

Vous voudrez peut-être donner à vos nouveaux articles les mêmes numéros que ceux qu'ils remplacent. Pour ce faire, modifiez les numéros des articles existants. Par exemple, si le numéro d'article existant est « P1000 », vous pouvez le remplacer par « X-P1000 ». Il s'agit d'une modification manuelle que vous devez effectuer pour chaque article.

### <a name="create-new-items-with-the-old-numbering-scheme-and-copy-the-master-data-in-a-batch"></a>Créer de nouveaux articles avec l'ancien schéma de numérotation et copier les données de base dans un lot

Créez les nouveaux articles à l'aide du schéma de numéros actuel. À l'exception du champ **Mode évaluation stock**, les nouveaux articles doivent contenir les mêmes données de base que les articles existants. Pour transférer les données de base de l'article et les données associées d'autres fonctionnalités, utilisez l'action **Copier article** sur la page **Fiche article**. Pour plus d'informations, voir [Copier des articles existants pour créer de nouveaux articles](inventory-how-copy-items.md).

Après avoir créé les nouveaux articles et transféré les données de base, affectez le mode évaluation stock correct.

### <a name="manually-copy-related-master-data-from-the-original-item-to-the-new-item"></a>Copier manuellement les données de base associées de l'article existant vers le nouvel article

Pour que les nouveaux articles soient pleinement utiles, vous devez copier manuellement certaines données de base à partir d'autres zones, comme décrit dans la table suivante.

|Région  |Que copier  |Comment le copier  |
|---------|---------|---------|
|Inventaire |Unités de stockage (points de stock) |Vérifiez si une unité de stock est spécifiée pour l'article d'origine. Si des paramètres de planification ont été saisis pour chaque fiche de unité de stock, vous devez créer manuellement l'unité de stock pour le nouvel article. Si les paramètres ne sont pas spécifiés, vous pouvez utiliser le traitement en lot **Créer unité de stock** à partir de la page **Fiche article** pour créer les données.|
| |Substitutions d'articles |Vérifiez si des substitutions d'articles sont définies pour l'article d'origine. S'il y en a, transférez ces données vers le nouvel article. Pour afficher les articles de substitution, utilisez l'action **Substitutions** sur la page **Fiche article**. |
| |Rapports d'analyse |Consultez les rapports d'analyse des articles, d'analyse des ventes et d'analyse des achats. Pour ceux qui font référence aux articles d'origine, vous pouvez soit créer un nouveau rapport d'analyse avec une référence au nouvel article (en conservant le rapport d'analyse d'origine à utiliser comme historique), soit ajuster les rapports afin qu'ils référencent le nouvel article. |
| |Journaux standard |Vérifiez si les journaux standard font référence à l'article d'origine et transférez ces données vers le nouvel article si nécessaire. Ces informations se trouvent dans les journaux standard, qui sont disponibles dans le journal article.  |
|Ventes |Pourcentage paiement anticipé vente | Vérifiez si des pourcentages paiement anticipé vente sont définis pour l'article d'origine et transférez ces données vers le nouvel article. Pour afficher les pourcentages paiement anticipé, sur la page **Fiche article**, choisissez **Ventes**, puis **Pourcentages paiement anticipé**.|
|Achat |Pourcentage paiement anticipé achat |Vérifiez si des pourcentages paiement anticipé achat sont définis pour l'article d'origine et transférez ces données vers le nouvel article. Pour afficher les pourcentages paiement anticipé, sur la page **Fiche article**, choisissez **Achats**, puis **Pourcentages paiement anticipé**. |
|Entrepôt |Contenus de la zone |Vérifiez le contenu de la zone défini pour l'article d'origine. Si des colonnes telles que Qté min., Qté max., Par défaut et Dédié ont été saisies individuellement, vous devez créer manuellement le contenu de la zone pour le nouvel article. Si ce n'est pas le cas, aucune action n'est requise. [!INCLUDE[prod_short](includes/prod_short.md)] conservera les enregistrements lorsque vous enregistrerez les documents et les journaux de l'entrepôt.|
|Projet |Prix projet |Vérifiez si des prix projet sont définis pour l’article d’origine et transférez ces données vers le nouvel article. Ces informations sont disponibles sur la page **Fiche projet** dans la partie **Détails projet - Nbre prix** sur le **volet Récapitulatif**. |
|Service |Compétence ressource de service |Vérifiez si des compétences ressource de service sont définies pour l'article d'origine et transférez ces données vers le nouvel article. Pour afficher les compétences ressource, utilisez l'action **Compétences ressource** sur la page **Fiche article**.  |
| |Composantes article de service |Vérifiez si des composantes sont définies pour l'article de service d'origine et transférez ces données vers le nouvel article. Pour afficher les composantes article de service, sur la page **Fiche article**, utilisez l'action **Article de service** pour ouvrir la liste des articles de service associés, puis choisissez l'action **Composantes**.  |
|Fabrication |Nomenclatures de production |Vérifiez si les nomenclatures production contiennent l'article d'origine et remplacez-le par le nouvel article. Pour remplacer l'article d'origine, sur la page **Nomenclatures production**, choisissez l'action **Remplacer article nomenclature production**. |
|Assemblage |Nomenclatures d'assemblage |Vérifiez si les nomenclatures d'assemblage contiennent l'article d'origine et remplacez-le manuellement par le nouvel article. |

> [!IMPORTANT]
> Si le nouveau mode évaluation stock est Standard, vous devez saisir une valeur dans le champ **Coût standard** sur la page **Fiche article**. Vous pouvez utiliser la page **Feuille coût standard** pour définir les coûts totaux en conséquence. Pour plus d'informations, voir [Mise à jour des coûts standard](finance-how-to-update-standard-costs.md).

### <a name="determine-the-inventory-quantity-to-convert-from-the-original-item-to-the-new-item"></a>Déterminer la quantité en inventaire à convertir de l'article d'origine vers le nouvel article

> [!NOTE]
> Cette étape ne prend pas en compte les quantités incluses dans les commandes non expédiées. Pour plus d'informations, voir [Gérer les quantités d'inventaire affectées à la demande](design-details-changing-costing-methods.md#handle-inventory-quantities-that-are-allocated-to-demand). 

Utilisez un journal d'inventaire pour produire une liste des quantités en inventaire. Selon la configuration de l'emplacement de l'entrepôt, utilisez l'une des options suivantes :

* Journaux inventaire physique
* Feuilles d'inventaire Journaux inventaire physique

Les deux journaux peuvent calculer la quantité en inventaire de l'article, y compris l'emplacement, la variante, et l'emplacement de stockage. Pour plus d'informations, voir [Inventaire, ajustement et reclassement de l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md).

### <a name="transfer-the-inventory-to-the-new-item"></a>Transférer l'inventaire vers le nouvel article

Créez et reportez des ordres d'assemblage pour transférer le coût et la quantité d'inventaire de l'article d'origine vers le nouvel article. Les ordres d'assemblage peuvent convertir un article en un autre tout en préservant les coûts. Cela permet de garantir que les totaux nets du compte d'inventaire et de la COGS ne sont pas affectés (sauf lorsque le nouveau mode évaluation inventaire est Standard, auquel cas les coûts peuvent être répartis dans les comptes d'écart). Pour plus d'informations, voir [Gestion d'assemblage](assembly-assemble-items.md).

Lorsque vous créez des ordres d'assemblage, utilisez les informations des journaux d'inventaire physique ou d'entrepôt. Journal inventaire physique Les tables suivantes décrivent les informations des rapports à saisir dans l'en-tête et les lignes de l'ordre d'assemblage.

#### <a name="header"></a>En-tête

|Champ  |Valeur à saisir  |
|---------|---------|
|N° article |Le numéro du nouvel article. |
|Quantité |La quantité dans le journal inventaire.<br> **REMARQUE :** les quantités calculées par les journaux inventaire n'incluent pas les quantités qui se trouvent sur des commandes qui n'ont pas encore été livrées.  |
|Code variante |Idem au journal inventaire.  |
|Code d'emplacement |Idem au journal inventaire. |
|Code unité de mesure |Idem au journal inventaire. |
|Code de zone |Idem au journal inventaire. |

#### <a name="lines"></a>Lignes

|Champ  |Valeur à saisir  |
|---------|---------|
|Type |Article ; |
|Non. |Le numéro de l'article d'origine. |
|Quantité par |1 |
|Code variante |Idem au journal inventaire. |
|Code d'emplacement |Idem au journal inventaire. |
|Code unité de mesure |Idem au journal inventaire. |

> [!NOTE]
> Un ordre d'assemblage ne peut gérer qu'une seul unité de stock d'un article à la fois. Vous devez créer un ordre d'assemblage pour chaque combinaison d'unités de stock ayant une quantité en inventaire.

> [!NOTE]
> Pour un emplacement d'entrepôt, vous devrez peut-être créer des prélèvements avant de pouvoir reporter l'ordre d'assemblage. Pour étudier cela, passez en revue la configuration pour le prélèvement sur la page **Fiche emplacement**. Pour plus d'informations, voir [Procédure : configurer des articles et des emplacements pour prélèvement et rangement suggérés](warehouse-how-to-set-up-items-for-directed-put-away-and-pick.md).

### <a name="handle-inventory-quantities-that-are-allocated-to-demand"></a>Gérer les quantités d'inventaire affectées à la demande

Idéalement, l'inventaire de l'article d'origine devrait être remis à zéro après le transfert des quantités en inventaire. Cependant, il peut y avoir des commandes, des journaux de calcul et des journaux en attente (voir la table ci-dessous) qui nécessitent toujours une quantité de l'article d'origine. La quantité peut également être bloquée par une réservation ou une traçabilité.

**Exemple** Il y a 1 000 pièces en inventaire et 20 pièces sont réservées pour un document de vente non encore livré. Dans ce cas, vous pourriez décider de conserver les 20 pièces dans l'ancien article afin que vous puissiez exécuter la commande en cours.

> [!NOTE]
> Il existe des domaines fonctionnels qui peuvent affecter la quantité, comme indiqué dans la table ci-dessous, il peut donc être difficile de trouver le montant correct. Pour être sûr, en utilisant l'exemple ci-dessus, vous pouvez choisir de conserver 100 pièces et de transférer les 900 pièces restantes à la place. Une autre façon de procéder serait de traiter les documents et les journaux de manière à n'en conserver que quelques-unes. Une autre alternative consiste à transférer la totalité de la quantité vers le nouvel article, puis à en transférer une partie vers l'article d'origine à l'aide de l'ordre d'assemblage.

La table suivante répertorie les domaines fonctionnels où il peut y avoir des quantités en suspens.

|Région  |Où chercher des quantités en suspens  |
|---------|---------|
|Ventes |Documents de vente, y compris commandes, retours, factures, devis, commandes permanentes et notes de crédit |
|Inventaire |Journaux article, réservations, traçabilité et feuille coût standard |
|Achat |Documents achat, y compris commandes, retours, factures, devis, commandes permanentes et notes de crédit |
|Planification |Feuille de réquisition, feuille planification et planification commande |
|Entrepôt |Ordres transfert, livraisons en entrepôt, journaux entrepôt, prélèvements, rangements et mouvements entrepôt, prélèvements et rangements internes, et journaux création zone |
|Assemblage |Documents d'assemblage, y compris les commandes, les retours et les commandes permanentes |
|Projets |lignes planification projet et lignes journal projet |
|Service |Documents de service et contrats de service |
|Fabrication |Bons de production (planifiés, et planifiés fermes et libérés) |

### <a name="block-the-original-item-from-further-use"></a>Bloquer l'article d'origine de toute utilisation ultérieure

Lorsque l'inventaire de l'article d'origine est nul, vous pouvez bloquer l'article pour éviter qu'il ne soit utilisé dans de nouvelles transactions. Pour bloquer l'article, sur la page **Fiche objet**, activez le bouton bascule **Bloqué**. Pour plus d'informations, voir [Bloquer les articles des ventes ou des achats](inventory-how-block-items.md).

## <a name="summary"></a>Résumé

La modification du mode évaluation stock des articles qui ont été utilisés dans des transactions est un traitement et non une action standard dans [!INCLUDE[prod_short](includes/prod_short.md)]. Vous pouvez utiliser les étapes décrites dans cette rubrique comme modèle pour le traitement.

Le traitement peut prendre du temps car il existe plusieurs étapes manuelles. Cependant, en prenant le temps de le terminer, vous minimiserez l'impact des erreurs sur votre grand livre.

Nous recommandons ce qui suit :

1. Évaluez la faisabilité du traitement en prenant un ou peut-être quelques articles représentatifs tout au long du traitement.
2. Envisagez de contacter un partenaire expérimenté qui puisse vous aider dans le traitement.

## <a name="see-also"></a>Voir aussi

[Détails de conception : modes évaluation stock](design-details-costing-methods.md)  
[Aperçu](design-details-inventory-costing.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
