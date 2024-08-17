---
title: Ajuster les coûts article manuellement
description: 'Vous pouvez ajuster l’évaluation de l’inventaire d’un article à l’aide des méthodes FIFO ou d’évaluation inventaire moyen, lorsque les coûts de produits changent.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'cost adjustment, cost forwarding, costing method, inventory valuation, costing'
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Ajustement coûts article

Le coût d’un article (valeur de l’inventaire) que vous achetez et vendez ultérieurement peut changer au cours de sa durée de vie, par exemple parce que des frais de transport sont ajoutés à son coût d’achat après que vous avez vendu l’article. L'ajustement des coûts est particulièrement utile dans les situations où vous vendez des biens avant de facturer leur achat. Pour toujours connaître la valeur de l’inventaire correcte, les coûts article doivent être ajustés régulièrement. Des coûts corrects garantit que les statistiques vente et profit sont à jour et que les indicateurs clés financiers sont corrects. Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-cost-adjustment.md).

La valeur du champ **Coût unitaire** sur la fiche article repose sur le coût standard des articles utilisant le mode évaluation stock standard. Pour les articles utilisant d’autres modes évaluation inventaire, la valeur repose sur le calcul de l’inventaire disponible (coûts facturés et prévus) divisé par la quantité disponible. Pour plus d'informations, voir [Comprendre le calcul du coût unitaire](inventory-how-adjust-item-costs.md#understanding-unit-cost-calculation).

Dans [!INCLUDE[prod_short](includes/prod_short.md)], les coûts article sont automatiquement ajustés chaque fois qu'un mouvement de stock se produit, par exemple lors de la validation d'une facture achat pour un article.

Vous pouvez également ajuster manuellement les coûts d’un ou de plusieurs articles. Par exemple, les ajustements manuels sont utiles si vous savez que les coûts article ont changé pour d’autres raisons que des mouvements de stock.

Les coûts article sont ajustés selon la méthode FIFO ou d'évaluation coût moyen, selon la sélection effectuée dans le guide de configuration assistée **Configurer ma compagnie** ou dans le champ **Mode évaluation stock** sur la fiche article. Pour plus d'informations, reportez vous à [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).  

Pour la méthode de calcul des coûts PEPS, le coût unitaire d’un article est la valeur réelle de toute réception de l’article. L’inventaire est évalué avec la supposition que les premiers articles stockés sont ceux vendus en premier.

Si vous utilisez la méthode de l'évaluation stock moyen, le coût unitaire d'un article est calculé comme le coût unitaire moyen à chaque moment après un achat. L'inventaire est évalué en supposant que tous les inventaires sont vendus simultanément. Pour les articles utilisant ce mode d'évaluation stock, vous pouvez choisir le champ **Coût unitaire** de la fiche article pour afficher l'historique des transactions à partir duquel est calculé le coût moyen

Les processus d’ajustement des coûts traite uniquement les écritures valeur non ajustées. Dans une situation où les coûts entrants modifiés doivent être transmis aux écritures sortantes associées, de nouvelles écritures de valeur d’ajustement sont créées. Les entrées de valeur d’ajustement sont basées sur les informations contenues dans les entrées de valeur d’origine mais contiennent le montant d’ajustement. La fonction d'ajustement des coûts utilise la date de report de l'écriture valeur d'origine dans l'écriture d'ajustement, sauf si la date est comprise dans une période d'inventaire fermée. Dans ce cas, l'application utilise la date début de la période d'inventaire ouverte suivante. Si aucune période inventaire n’est utilisée, la date du champ **Début période report** de la page **Configuration du grand livre** définit la date de report de l’écriture ajustée.

## Pour ajuster les coûts article manuellement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts : Écr. article**, puis sélectionnez le lien associé.
2. Sur la page **Ajuster coûts - Écr. article**, spécifiez les articles pour lesquels ajuster les coûts.
3. Cliquez sur le bouton **OK**.

## Pour apporter des modifications générales au coût unitaire direct

Si vous devez modifier le coût unitaire direct de plusieurs articles, vous pouvez utiliser le traitement en lot **Ajuster coûts et prix article**.  

Le traitement par lots modifie la valeur du champ **Prix unitaire** sur la fiche article. Le traitement en lot modifie la valeur du champ de la même manière pour tous les articles (ou pour les articles sélectionnés). Le traitement en lot multiplie la valeur du champ par un facteur appliqué que vous devez indiquer.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts/prix article**, puis sélectionnez le lien associé.  
2. Dans le champ **Ajuster champ**, indiquez l'article ou le champ de la fiche Unité de stock à modifier.  
3. Dans le champ **Facteur appliqué**, indiquez le facteur pour ajuster de la valeur. Par exemple, entrez **1,5** pour augmenter la valeur de 50 %.  
4. Sous le raccourci **Article**, définissez des filtres pour indiquer, par exemple, les articles à traiter avec le traitement par lots.  
5. Cliquez sur le bouton **OK**.  

## Comprendre le calcul du coût unitaire

La valeur du champ **Coût unitaire** sur la fiche article repose sur le coût standard des articles utilisant le mode évaluation stock standard. Pour les articles utilisant d’autres modes évaluation inventaire, la valeur repose sur le calcul de l’inventaire disponible (coûts facturés et prévus) divisé par la quantité disponible.  

Pour en savoir plus sur les incidences de la valeur du champ **Mode évaluation stock** sur le calcul du coût unitaire pour les achats et les ventes, consultez les chapitres suivants.  

## Calcul du coût unitaire pour les achats  

Lorsque vous achetez des articles, le programme copie toujours la valeur du champ **Dernier coût direct** de la fiche article vers le champ **Coût unitaire direct** d’une ligne achat ou vers la ligne **Montant unitaire** sur une ligne journal article.  

L'élément sélectionné dans le champ **Mode d'évaluation du stock** détermine la façon dont [!INCLUDE[prod_short](includes/prod_short.md)] calcule le contenu du champ **Coût unitaire** sur les lignes.  

### Modes d’évaluation des coûts PEPS, DEPS, spécifique ou moyen  

[!INCLUDE[prod_short](includes/prod_short.md)] utilise la formule suivante pour calculer la valeur du champ **Coût unitaire $** sur la ligne achat ou la valeur du champ **Coût unitaire** sur la ligne journal article :  

Coût unitaire $ = (Coût unitaire direct - (Montant de l'escompte/Quantité)) x (1 + % du coût indirect/100) + Frais généraux  

### Mode évaluation coûts Standard  

Le champ **Coût unitaire $** sur la ligne achat, ou le champ **Coût unitaire** est renseigné sur la ligne journal article en copiant la valeur du champ **Coût unitaire** de la fiche article. En utilisant le mode évaluation coûts Standard, la valeur repose toujours sur le coût standard.  

Lorsque vous reportez un achat, le coût unitaire de la ligne achat ou de la ligne journal article est copié vers l’écriture facture article achat. Le voir sur la liste des entrées pour l’élément.  

### Tous les modes évaluation stock  

Le coût unitaire de la ligne document source est utilisé pour calculer la valeur du champ **coût indiqué (réel)** ou, le cas échéant, du champ **coût indiqué (prévu)** concernant cette écriture article. Le coût est inclus dans le calcul quelle que soit la méthode de valorisation de l’article.  

## Calcul du coût unitaire pour les ventes  

Lorsque vous vendez des articles, le coût unitaire se copie du champ **Coût unitaire** de la fiche article vers la ligne vente ou la ligne journal article.  

Lors du report, le coût unitaire est copié vers l’écriture article facture vente, et il est affiché dans la liste d’écritures de l’article. [!INCLUDE[prod_short](includes/prod_short.md)] utilise le coût unitaire de la ligne document source pour calculer la valeur du champ **Coût indiqué (réel)** ou, le cas échéant, du champ **Coût indiqué (prévu)** dans l’écriture valeur concernant cette écriture article.  

## Suivi des ajustements des coûts d’articles

Les coûts des articles peuvent changer pour de nombreuses raisons, il est donc important que vous puissiez suivre les ajustements de coûts. Utilisez la page **Ajustement du coût de l’inventaire** pour gérer et surveiller le processus d’ajustement des coûts. Cette page affiche les articles avec leurs paramètres de valorisation et leur état d’ajustement des coûts. Vous pouvez filtrer la liste pour vous concentrer sur les éléments qui nécessitent un ajustement ou qui sont exclus du processus d’ajustement des coûts. Pour en savoir plus sur le suivi des ajustements de coût, accédez à [Suivi des ajustements de coût des articles](finance-track-inventory-costs.md).

## Voir aussi .

[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Ventes](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]