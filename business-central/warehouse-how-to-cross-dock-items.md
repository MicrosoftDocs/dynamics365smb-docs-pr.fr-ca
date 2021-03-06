---
title: Comment transborder des articles | Microsoft Docs
description: La fonctionnalité de transbordement est disponible si l'emplacement est configuré pour appeler un traitement des réceptions et des rangements entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 12281a872317a7ba02eedfbc13365b1f5410acdf
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5782694"
---
# <a name="cross-dock-items"></a>Transborder des articles
La fonctionnalité de transbordement est disponible si l'emplacement est configuré pour appeler un traitement des réceptions et des rangements entrepôt.  

Lorsque vous transbordez des articles, vous les manipulez en effectuant des réceptions et des expéditions, sans jamais les ranger. Vous évitez ainsi les processus de rangement et de prélèvement, et limitez la manipulation physique des articles. Vous pouvez transborder des articles tant pour des livraisons que pour des bons de production. Lorsque vous préparez une livraison ou prélevez des articles pour la production, et que vous utilisez des zones, le programme tente d'abord automatiquement de prélever l'article dans une zone de transbordement avant d'envisager toute autre zone. Vous devez vérifier si les articles dont vous avez besoin sont disponibles dans la zone de transbordement avant de pouvoir accéder à ces articles dans leur zone de stockage habituel.  

Lorsque vous avez calculé les quantités à transborder, des lignes rangement désignant la zone de transbordement sont créées pour effectuer les calculs de transbordement lors du report de la réception. Les autres lignes rangement sont créées normalement.  

Pour reporter immédiatement les articles à transborder afin qu'ils soient disponibles pour le prélèvement, vous devez aussi enregistrer un rangement pour les autres articles issus de la ligne réception, c'est-à-dire les articles à ranger. Si une partie seulement des articles d'une ligne réception doit être transbordée, efforcezvous de ranger le reste des articles le plus vite possible. Sinon, vous pouvez aussi instaurer dans votre entrepôt une politique encourageant les employés à effectuer le transbordement de lignes réception entières chaque fois que cela est possible.  

Dans l'instruction de rangement, vous avez tout intérêt à effacer les lignes d'instructions, les lignes prélèvement et placement de chaque ligne réception, concernant des réceptions qui doivent être entièrement rangées. Ces lignes pourront être créées ultérieurement en tant que lignes rangement à partir de la feuille rangement ou de la réception reportée. Une fois ces lignes effacées, vous pouvez ranger les articles à transborder et enregistrer les lignes concernant ces articles.  

Si vous avez sélectionné le champ **Utiliser feuille rangement** de la fiche emplacement et reporté votre réception en calculant les transbordements, toutes les lignes réception deviennent disponibles dans la feuille. Les informations de transbordement sont perdues et ne peuvent plus être créées. Par conséquent, pour utiliser la fonctionnalité de transbordement, il vaut mieux que vous transfériez les lignes vers la feuille rangement en effaçant les instructions de rangement plutôt que d'utiliser la fonction de transfert automatique prévue dans le champ **Utiliser feuille rangement**.  

Lorsque vous reportez la réception entrepôt, et que le champ **Utiliser feuille rangement** n'est pas coché, les articles à transborder figurent dans des lignes distinctes dans l'instruction de rangement. Le champ **Informations transbordement** de chaque ligne rangement indique si la ligne contient des articles à transborder, des articles provenant d'une même réception et devant tous être rangés ou des articles à ranger provenant d'une ligne réception dans laquelle certains des articles sont à transborder. Grâce à ce champ, les employés peuvent voir aisément pourquoi toute la quantité réceptionnée n'est pas rangée.  

L'application ne crée pas d'enregistrement distinct concernant les articles transbordés, mais les enregistre plutôt en tant qu'instructions de rangement ordinaires.  

## <a name="to-set-up-the-warehouse-for-cross-docking"></a>Pour configurer l'entrepôt en vue du transbordement  
1.  En cas d'utilisation de zones, configurez au moins une zone de transbordement. En cas d'utilisation d'un prélèvement et d'un rangement suggérés, configurez une zone de transbordement.  

    Le champ **Zone transbordement** d'une zone de transbordement est activé. Ses types de zone devant être sélectionnés sont **Réception** et **Prélèvement**. Pour plus d'informations, voir [Créer des zones](warehouse-how-to-create-individual-bins.md) et [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).  

    Si vous utilisez des zones, créez une zone pour vos zones de transbordement, puis sélectionnez le champ **Zone transbordement**. Pour plus d'informations, voir [Configurer des emplacements de sorte qu'ils utilisent des zones](warehouse-how-to-set-up-locations-to-use-bins.md).  

2.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacement**, puis sélectionnez le lien associé.  
3.  Sur la page **Emplacement**, sélectionnez l'emplacement que vous souhaitez configurer pour le transbordement, puis choisissez l'action **Modifier**.  
4.  Sur le raccourci **Entrepôt**, cochez la case **Utiliser transbordement**, puis renseignez le champ **Calc. date d'échéance transbordement** en y indiquant la période pendant laquelle le programme doit rechercher des opportunités de transbordement.

    L'option **Utiliser transbordement** n'est disponible que si vous avez coché les champs **Réception requise**, **Livraison requise**, **Prélèvement requis** et **Rangement requis**.  

5.  Si vous utilisez des zones, dans le raccourci **Zones**, renseignez le champ **Code de zone transbord.** en y insérant le code de la zone à utiliser comme zone de transbordement par défaut.  
6.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Unité de stock**, puis sélectionnez le lien associé.  
7.  Pour chaque article ou unité de stock que vous souhaitez pouvoir transborder, sélectionnez l'article, puis cliquez sur l'action **Modifier**.
8. Sur la page **Fiche unité de stock**, cochez la case **Utiliser transbordement**.  

> [!NOTE]  
>  Le transbordement n'est possible que si votre emplacement est configuré pour exiger un traitement des réceptions et des rangements entrepôt.  

## <a name="to-cross-dock-items-without-viewing-the-opportunities"></a>Pour transborder des articles sans afficher les opportunités  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Réceptions entrepôt**, puis sélectionnez le lien associé.  
2.  Créer des réceptions entrepôt pour un article qui est arrivé et qui pourrait nécessiter un transbordement. Pour plus d'informations, voir [Réceptionner des articles](warehouse-how-receive-items.md).  
3.  Renseignez le champ **Qté à recevoir**, puis choisissez l'action **Calculer transbordement**.  

    Les documents sources sortants demandant les articles programmés pour quitter l'entrepôt durant la période indiquée par la formule date sont identifiés.  [!INCLUDE[prod_short](includes/prod_short.md)] calcule les quantités pour que vous puissiez effectuer un maximum de transbordements pour éviter de ranger des articles, sans entasser trop d'articles dans la zone de transbordement. La valeur du champ **Qté à transborder** est ainsi la plus petite de ces deux valeurs : la somme de toutes les lignes sortantes demandant l'article avant la fin de la période de prévision des transbordements, moins la quantité d'articles déjà placés dans la zone de transbordement ou la valeur du champ **Qté à recevoir** de la ligne réception. Vous ne pouvez pas transborder plus d'articles que vous en avez reçus.  

4.  Pour transborder la quantité en suivant la procédure indiquée, reportez la réception. Vous pouvez aussi décider de modifier la quantité à transborder pour augmenter ou réduire sa valeur, puis reporter la réception.  

    Les quantités à transborder apparaissent maintenant en tant que lignes dans l'instruction de rangement, en supposant que vous n'ayez pas activé le champ **Utiliser feuille rangement**. Les quantités non destinées au transbordement apparaissent aussi en tant que lignes dans l'instruction de rangement.  

    Si vous possédez des zones, les articles transbordés ont été affectés à la zone de transbordement par défaut défini dans la fiche emplacement.  

5.  Supprimez les lignes **prélèvement** et **placement** pour les articles qui ne font l'objet d'aucun transbordement.  
6.  Imprimez l'instruction de rangement pour les lignes restantes, puis placez les quantités de la réception à ranger dans les zones appropriées ou dans la zone appropriée de l'entrepôt. Placez les articles à transborder dans la zone qui leur est attribuée par la politique de l'entrepôt. Parfois, la politique de l'entrepôt peut nécessiter simplement de les laisser dans la zone de réception.  
7.  Pour enregistrer les articles transbordés comme étant rangés et disponibles pour le prélèvement, choisissez l'action **Enregistrer**.  

## <a name="to-cross-dock-items-after-viewing-the-opportunities"></a>Pour transborder des articles après avoir affiché les opportunités  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Réceptions entrepôt**, puis sélectionnez le lien associé.  
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

## <a name="to-view-cross-docked-items-in-a-shipment-or-pick-worksheet"></a>Pour afficher des articles transbordés dans une feuille prélèvement ou livraison  
Si vous utilisez des zones, chaque fois que vous ouvrez une livraison ou la feuille prélèvement, vous pouvez voir le calcul mis à jour de la quantité de chaque article dans les zones de transbordement. Cette information est précieuse si vous attendez l'arrivée d'un article. Dès que vous voyez qu'un article est disponible dans la zone de transbordement, vous pouvez rapidement créer un prélèvement pour tous les articles de la livraison. Dans la feuille prélèvement, vous pouvez modifier les lignes, puis créer un prélèvement.  

Lorsque vous prélevez des articles à livrer, vous devez commencer par rechercher les articles concernés dans la zone de transbordement. Si, au cours du processus de réception, vous avez noté les documents origine à la base du transbordement, vous saurez plus précisément si l'article que vous recherchez se trouve ou non dans la zone de transbordement.  

Après la libération d'un bon de production, les lignes sont disponibles dans la feuille prélèvement et vous pouvez consulter le champ **Qté zone transbordement** pour voir si les articles que vous attendez sont arrivés et ont été placés dans les zones de transbordement. Lorsque vous créez une instruction de prélèvement, l'application vous propose de prélever d'abord les articles transbordés, après quoi il recherche les articles dans les zones de stockage.  

Si vous n'utilisez pas de zones, n'oubliez pas de vérifier, de temps en temps, la zone de transbordement ou consultez les notifications de réception pour connaître l'arrivée des articles destinés à la production.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]