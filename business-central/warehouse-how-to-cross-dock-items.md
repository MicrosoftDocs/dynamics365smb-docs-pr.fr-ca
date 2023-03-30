---
title: Transborder des articles
description: La fonctionnalité de transbordement est disponible si l'emplacement est configuré pour appeler un traitement des réceptions et des rangements entrepôt.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '15, 5703, 7302, 7332, 5768'
ms.date: 04/01/2021
ms.author: edupont
---
# Transborder des articles

Les articles de transbordement sont les articles que vous recevez et livrez sans les ranger. Les processus de rangement et de prélèvement nécessitent une manipulation limitée des articles. Vous pouvez transborder des articles pour des livraisons comme pour des bons de production.

## Zones et zones de transbordement

Si vous utilisez des zones, configurez au moins une zone de transbordement, puis spécifiez la zone dans le champ **Code de zone transbord.** sur vos emplacements. Si vous utilisez le prélèvement et le rangement dirigés, configurez une zone de transbordement.

Lorsque vous préparez une livraison ou prélevez des articles pour la production, et que vous utilisez des zones, le programme tente d’abord automatiquement de prélever l’article dans une zone de transbordement avant d’envisager d’autres zones. Vous devez vérifier si les articles dont vous avez besoin sont disponibles dans la zone de transbordement avant de pouvoir accéder à ces articles dans leur zone de stockage habituel.  

Lorsque vous avez calculé les quantités à transborder, des lignes rangement désignant la zone de transbordement sont créées pour effectuer les calculs de transbordement lors du report de la réception. Les autres lignes rangement sont créées normalement.  

## Sélectionner des lignes transbordement pour une réception

<!--If a receipt contains items that you want to store, that is, items that you are not cross-docking, you must register a put-away for those items.-->

Pour reporter immédiatement les articles à transborder afin qu'ils soient disponibles pour le prélèvement, vous devez aussi enregistrer un rangement pour les autres articles issus de la ligne réception, c'est-à-dire les articles à ranger. Si une partie seulement des articles d'une ligne réception doit être transbordée, efforcezvous de ranger le reste des articles le plus vite possible. Sinon, vous pouvez aussi instaurer dans votre entrepôt une politique encourageant les employés à effectuer le transbordement de lignes réception entières chaque fois que cela est possible.

Dans l’instruction de rangement, supprimez les lignes d’instruction Prendre et Placer pour chaque ligne de réception des articles à ranger. Vous pouvez recréer les lignes d’instructions ultérieurement en tant que lignes rangement à partir de la feuille rangement ou de la réception reportée. Après avoir supprimé les lignes d’instruction, vous pouvez ranger et enregistrer les lignes pour les articles transbordés.  

## À propos de la feuille Rangement

Si vous avez activé le bouton à bascule **Utiliser feuille rangement** sur la page Fiche emplacement, et avez reporté votre réception en calculant les transbordements, toutes les lignes réception sont disponibles dans la feuille. Les informations de transbordement sont perdues et ne peuvent plus être créées. Par conséquent, pour utiliser la fonctionnalité de transbordement, il vaut mieux que vous transfériez les lignes vers la feuille rangement en effaçant les instructions de rangement plutôt que d’utiliser la fonction de transfert automatique prévue dans le champ **Utiliser feuille rangement**.  

Lorsque vous reportez la réception entrepôt, et que le bouton à bascule **Utiliser feuille rangement** est désactivé, les articles à transborder figurent dans des lignes distinctes dans l’instruction de rangement. Le champ **Informations transbord.** sur chaque ligne de rangement indique si la ligne contient les éléments suivants :

* Articles à transborder.
* Tous les articles d’une réception doivent être stockés.
* Certains articles d’une réception doivent être stockés et d’autres doivent faire l’objet d’un transbordement.

Les employés peuvent facilement comprendre pourquoi la quantité totale n’est pas stockée.  

[!INCLUDE [prod_short](includes/prod_short.md)] ne conserve pas d’enregistrements séparés pour les articles transbordés, mais les enregistre comme des instructions de rangement ordinaires.  

## Pour configurer l'entrepôt en vue du transbordement  

1. Si vous utilisez des zones, configurez au moins une zone de transbordement. Si vous utilisez le prélèvement et le rangement dirigés, configurez une zone de transbordement.  

    Le champ **Zone transbordement** d'une zone de transbordement est activé. Ses types de zone devant être sélectionnés sont **Réception** et **Prélèvement**. Pour plus d'informations, voir [Créer des zones](warehouse-how-to-create-individual-bins.md) et [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).  

    Si vous utilisez des zones, créez une zone pour vos zones de transbordement, puis sélectionnez le champ **Zone transbordement**. Pour plus d'informations, voir [Configurer des emplacements de sorte qu'ils utilisent des zones](warehouse-how-to-set-up-locations-to-use-bins.md).  

2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacement**, puis choisissez le lien associé.  
3. Sur la page **Emplacement**, sélectionnez l'emplacement que vous souhaitez configurer pour le transbordement, puis choisissez l'action **Modifier**.  
4. Sur le raccourci **Entrepôt**, activez le bouton à bascule **Utiliser transbordement**, puis renseignez le champ **Date d’échéance transbordement** en y indiquant la période pendant laquelle le programme doit rechercher des opportunités de transbordement.

    L'option **Utiliser transbordement** n'est disponible que si vous avez coché les champs **Réception requise**, **Livraison requise**, **Prélèvement requis** et **Rangement requis**.  

5.  Si vous utilisez des zones, dans le raccourci **Zones**, renseignez le champ **Code de zone transbord.** en y insérant le code de la zone à utiliser comme zone de transbordement par défaut.  
6.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unité de stock**, puis sélectionnez le lien associé.  
7.  Pour chaque article ou unité de stock que vous souhaitez pouvoir transborder, sélectionnez l'article, puis cliquez sur l'action **Modifier**.
8. Sur la page **Fiche unité de stock**, cochez la case **Utiliser transbordement**.  

> [!NOTE]  
>  Le transbordement n'est possible que si votre emplacement est configuré pour exiger un traitement des réceptions et des rangements entrepôt.  

## Pour transborder des articles sans afficher les opportunités  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réceptions entrepôt**, puis choisissez le lien associé.  
2.  Créer des réceptions entrepôt pour un article qui est arrivé et qui pourrait nécessiter un transbordement. Pour plus d'informations, voir [Réceptionner des articles](warehouse-how-receive-items.md).  
3.  Renseignez le champ **Qté à recevoir**, puis choisissez l'action **Calculer transbordement**.  

    Les documents sources sortants demandant les articles programmés pour quitter l'entrepôt durant la période indiquée par la formule date sont identifiés.  [!INCLUDE[prod_short](includes/prod_short.md)] calcule les quantités pour que vous puissiez effectuer un maximum de transbordements pour éviter de ranger des articles, sans entasser trop d'articles dans la zone de transbordement. La valeur du champ **Qté à transborder** est ainsi la plus petite de ces deux valeurs : la somme de toutes les lignes sortantes demandant l'article avant la fin de la période de prévision des transbordements, moins la quantité d'articles déjà placés dans la zone de transbordement ou la valeur du champ **Qté à recevoir** de la ligne réception. Vous ne pouvez pas transborder plus d'articles que vous en avez reçus.  

4.  Pour transborder la quantité en suivant la procédure indiquée, reportez la réception. Vous pouvez aussi décider de modifier la quantité à transborder pour augmenter ou réduire sa valeur, puis reporter la réception.  

    Les quantités à transborder apparaissent maintenant en tant que lignes dans l'instruction de rangement, en supposant que vous n'ayez pas activé le champ **Utiliser feuille rangement**. Les quantités non destinées au transbordement apparaissent aussi en tant que lignes dans l'instruction de rangement.  

    Si vous possédez des zones, les articles transbordés ont été affectés à la zone de transbordement par défaut défini dans la fiche emplacement.  

5.  Supprimez les lignes **prélèvement** et **placement** pour les articles qui ne font l'objet d'aucun transbordement.  
6.  Imprimez l'instruction de rangement pour les lignes restantes, puis placez les quantités de la réception à ranger dans les zones appropriées ou dans la zone appropriée de l'entrepôt. Placez les articles à transborder dans la zone qui leur est attribuée par la politique de l'entrepôt. Parfois, la politique de l'entrepôt peut nécessiter simplement de les laisser dans la zone de réception.  
7.  Pour enregistrer les articles transbordés comme étant rangés et disponibles pour le prélèvement, choisissez l'action **Enregistrer**.  

## Pour transborder des articles après avoir affiché les opportunités  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réceptions entrepôt**, puis choisissez le lien associé.  
2.  Créer des réceptions entrepôt pour un article qui est arrivé et qui pourrait nécessiter un transbordement. Pour plus d'informations, voir [Réceptionner des articles](warehouse-how-receive-items.md).  

    Vous souhaitez afficher les lignes document source demandant l'article avant de reporter la réception.  
3.  Choisissez l'action **Calculer transbordement**.  

    Sur la page **Opportunités transbordement**, vous pouvez voir les informations les plus importantes concernant les lignes demandant l'article, comme le type du document, la quantité demandée et la date d'échéance. Ces informations peuvent vous aider à décider de la quantité d'articles à transborder, de l'endroit où placer ces articles dans la zone de transbordement ou de la manière de les regrouper.  

4.  Choisissez l'action **Remplir quantité à transborder** pour savoir comment les quantités figurant dans les lignes réception sont calculées. Lorsque vous modifiez le nombre d'articles dans le champ **Qté à transborder** de chaque ligne, le calcul est mis à jour lorsque vous effectuez des modifications. Cela ne signifie pas que le bon de production ou de livraison concerné reçoit réellement les articles dont le transbordement est proposé, car ces opérations ne sont qu'un simple test. Toutefois, ce processus peut être intéressant à titre d'information si plusieurs unités de mesure sont utilisées.  
5.  Pour réserver une quantité de l'article pour une ligne commande donnée, placez le curseur sur cette ligne, puis choisissez l'action **Réserver**. Sur la page **Réservation**, vous pouvez maintenant réserver n'importe quelle quantité disponible de l'article pour cette commande. Cette réservation ne diffère pas des autres réservations, et le fait qu'elle ait été créée au cours d'un transbordement ne lui confère aucune priorité. Pour plus d'informations, voir [Réserver des articles](inventory-how-to-reserve-items.md).   
6.  Lorsque vous avez fini de refaire les calculs et que la réservation est terminée, sélectionnez le bouton **OK** pour insérer le calcul que vous venez de réviser dans le champ **Qté à transborder** de la ligne réception ou choisissez le bouton **Annuler** pour revenir à la réception entrepôt et y recalculer le transbordement.  
7.  Reportez à présent la réception. Vous pouvez ensuite passer à l'instruction de rangement, comme l'indiquent les étapes 3 à 7 de la section « Pour transborder des articles sans afficher les opportunités ».  

> [!NOTE]  
>  Dans le rangement entrepôt, vous pouvez continuer de modifier les quantités en cours de transbordement ou de rangement dans le stock, selon vos besoins. Par exemple, vous pouvez décider de transborder une quantité supplémentaire afin d'expédier l'enregistrement du transbordement.  

## Pour afficher des articles transbordés dans une feuille prélèvement ou livraison  
Si vous utilisez des zones, chaque fois que vous ouvrez une livraison ou la feuille prélèvement, vous pouvez voir le calcul mis à jour de la quantité de chaque article dans les zones de transbordement. Cette information est précieuse si vous attendez l'arrivée d'un article. Dès que vous voyez qu'un article est disponible dans la zone de transbordement, vous pouvez rapidement créer un prélèvement pour tous les articles de la livraison. Dans la feuille prélèvement, vous pouvez modifier les lignes, puis créer un prélèvement.  

Lorsque vous prélevez des articles à livrer, vous devez commencer par rechercher les articles concernés dans la zone de transbordement. Si, au cours du processus de réception, vous avez noté les documents origine à la base du transbordement, vous saurez plus précisément si l'article que vous recherchez se trouve ou non dans la zone de transbordement.  

Après la libération d'un bon de production, les lignes sont disponibles dans la feuille prélèvement et vous pouvez consulter le champ **Qté zone transbordement** pour voir si les articles que vous attendez sont arrivés et ont été placés dans les zones de transbordement. Lorsque vous créez une instruction de prélèvement, l'application vous propose de prélever d'abord les articles transbordés, après quoi il recherche les articles dans les zones de stockage.  

Si vous n'utilisez pas de zones, n'oubliez pas de vérifier, de temps en temps, la zone de transbordement ou consultez les notifications de réception pour connaître l'arrivée des articles destinés à la production.  

## Voir aussi  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]