---
title: Comment reporter des commandes service
description: 'Après avoir créé une commande service, fourni toutes les informations et apporté les éventuelles modifications, vous pouvez reporter cette commande.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="post-service-orders-and-credit-memos" />Reporter des commandes et des notes de crédit de service
Après avoir créé une commande service, fourni toutes les informations et apporté les éventuelles modifications, vous pouvez reporter cette commande. Pour que vous puissiez reporter une commande, celle-ci doit contenir au moins une ligne article de service et une ligne service. Si la commande contient plusieurs lignes service, toutes les lignes sont reportées en même temps.  

Si vous avez un grand nombre de commandes service, vous pouvez gagner du temps en utilisant un traitement en lot pour les reporter simultanément. Vous pouvez exécuter le traitement en lot à partir d'une commande service quelconque.

> [!Tip]
> Avant de reporter un document service, il est recommandé d'utiliser l'action **Rapport de test** pour vérifier toutes les erreurs ou informations manquantes. S'il existe des erreurs, vous devez corriger le problème. Vous pouvez imprimer un nouveau rapport de test pour vérifier le correctif, puis reporter le document.

## <a name="to-post-a-service-order" />Pour reporter une commande service
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes service**, puis choisissez le lien associé.  
2. Ouvrez la commande service.  
3. Sur la page **Commande service**, choisissez l'une des actions suivantes.  

    |**Action**|**Résultat**|  
    |------------------|----------------|  
    |**Impression test** | Vérifie tous les éléments du document et présente les résultats dans un rapport. Si le rapport signale des erreurs ou des informations manquantes, vous devez corriger le problème. Vous pouvez ensuite imprimer un nouveau rapport de test.|  
    |**Valider** | Reporte la commande sans imprimer de bon de livraison ou de facture.|  
    |**Valider et Imprimer** | Reporte la commande et imprime un bon de livraison (si vous livrez la commande sans la facturer) ou une facture (si vous facturez la commande).|  
    |**Valider par lot** | Reporte plusieurs commandes service en une seule fois.|  

4. Lorsque vous reportez la commande, vous devez choisir l'une des options suivantes indiquant la manière dont vous souhaitez reporter la commande.  

    |**Option de validation**|**Résultat**|  
    |------------------------|----------------|  
    |**Livraison** | Reporte la livraison des articles.|  
    |**Facture** | Facture les articles déjà livrés.|  
    |**Expédition et facturation** | Livre et facture les articles.|  
    |**Livrer et consommer** | Reporte la livraison et la consommation sur la commande. Il met à jour les quantités appropriées sur les lignes service de la commande et sur le document livraison service reporté précédemment.|  

Vous ne pouvez reporter la consommation que si la ligne contient une quantité qui a été livrée mais pas facturée ni consommée.  

Lors du report de la commande, les écritures et les documents reportés correspondants sont créés. Les champs appropriés dans le document commande service sont mis à jour.  

## <a name="to-batch-post-service-orders" />Pour reporter en lot des commandes service
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes service**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Reporter par lot**.  
3.  Vous pouvez positionner un filtre pour sélectionner des numéros commande service ou un intervalle de numéros commande pour le traitement en lot à effectuer.  
4.  Cliquez sur **OK** pour démarrer le traitement en lot.  

## <a name="to-post-a-service-credit-memo" />Pour reporter une note de crédit service
Une fois la note de crédit service créée et renseignée, vous pouvez reporter la note de crédit. S'il y a des erreurs ou s'il manque certaines informations sur la note de crédit lors du report, le processus est interrompu par un message d'erreur.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit service**, puis sélectionnez le lien associé.  
2. Créez une note de crédit service. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs suivants.  
4. Sélectionnez l'action **Reporter**. Si vous souhaitez imprimer et reporter la note de crédit simultanément, choisissez plutôt l'action **Reporter et imprimer**.  
5. Pour tester des notes de crédit avant de les reporter, choisissez **Rapport de test**. Lorsque vous exécutez le rapport, les dates de report spécifiées dans le document sont vérifiées.  
6. Pour reporter simultanément plusieurs notes de crédits service. exécutez le traitement en lot **Reporter en lot les notes de crédit service**. Ceci peut être avantageux si vous avez beaucoup de notes de crédit à reporter.  

> [!NOTE]  
>  Il est important d'entrer toutes les informations nécessaires sur les notes de crédit avant de les exécuter en lot. Sinon, elles risquent de ne pas être reportées. Lorsque le traitement en lot a terminé le report, un message indique le nombre des notes de crédit service reportés.  

## <a name="to-post-consumption-from-a-service-order" />Pour reporter une consommation à partir d'une commande service
La procédure suivante décrit comment reporter les articles, les heures et/ou coûts ressource utilisés pour une opération de service spécifique que vous n'allez pas facturer au client. Notez que vous ne pouvez reporter des articles, des heures et/ou des coûts consommés que pour une livraison reportée pour laquelle il n'y a pas de facture ni de consommation reportée.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes service**, puis choisissez le lien associé.  
2. Ouvrez la commande service dont vous voulez reporter la consommation.  
3. Choisissez l'article de service. Choisissez l'action **Lignes service**.  
4. Recherchez les écritures requises et spécifiez les quantités pour lesquelles vous allez reporter la consommation dans le champ **Qté à consommer**. La quantité ne peut pas être supérieure à la quantité déjà livrée et la quantité restante, mais non facturée après la facturation partielle de cette livraison.  

    > [!NOTE]  
    >  Pour enregistrer la consommation relative à un projet, renseignez les champs **N° projet**, **N° tâche projet**, et **Type ligne projet** dans la ligne service.  

5. Choisissez les lignes à reporter, puis sélectionnez l'action **Reporter**. Sur la page qui s'ouvre, sélectionnez **Livrer et consommer**.  

Le service est validé comme étant consommé, entièrement ou partiellement, en fonction de la valeur renseignée dans le champ **Qté à consommer** et les écritures comptables correspondantes sont créées. En outre, les documents livraison service précédemment reportés sont mis à jour, de façon chronologique, avec les quantités consommées. Les quantités appropriées sont mises à jour dans les lignes service de la commande.  

## <a name="to-post-shipments-from-service-orders" />Pour reporter des livraisons à partir de commandes service
Après avoir spécifié les détails d'un service, vous pouvez ajuster et reporter les quantités d'articles utilisées, le temps passé et les coûts exposés. Par conséquent, [!INCLUDE[prod_short](includes/prod_short.md)] apporte les modifications nécessaires afin de refléter le nouvel état du stock et le statut actuel du traitement de commande spécifique.  

La procédure suivante explique comment reporter la livraison des articles ligne service dans les emplacements qui ne sont pas configurés pour appeler une gestion d'entrepôt.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commande service**, puis choisissez le lien associé. 2. Sur la page de la commande service sélectionnée, choisissez **Actions**, **Commande**, **Lignes service**.  
3. Sur la page **Lignes service**, recherchez les écritures requises, puis spécifiez la quantité à reporter dans le champ **Qté à livrer**.  

   > [!NOTE]  
   >  La valeur de la quantité à livrer varie selon que vous voulez reporter la livraison entièrement ou partiellement. Si vous décidez d'expédier entièrement, la valeur renseignée dans le champ **Qté à expédier** doit être égale à celle renseignée dans le champ **Quantité**. Si vous reportez une livraison partielle, vous devez spécifier la quantité que vous voulez livrer initialement. Si vous avez déjà expédié une partie du service en commande, prenez note de la valeur dans le champ **Qté expédiée**. La quantité maximale que vous pouvez entrer dans le champ **Qté à expédier** est le nombre d'unités qui n'ont pas encore été expédiées.  

4. Sélectionnez l'action **Reporter**. Sur la page qui apparaît, sélectionnez le bouton **Livrer**.

[!INCLUDE[prod_short](includes/prod_short.md)] crée les écritures appropriées (dans le livre garantie, le grand livre article, le livre service ou le grand livre), génère également le document livraison service reporté et met à jour les champs appropriés dans les lignes service de la commande service.  

Si l'emplacement est configuré pour exiger la gestion d'entrepôt, la livraison et le déplacement d'articles de ligne service s'exécutent de la même manière que pour d'autres documents source. La seule différence est que les articles de la ligne service peuvent être consommés en externe ou en interne et nécessitent donc deux fonctions de libération différentes.  

Pour en savoir plus sur la manière de livrer des articles ligne service dans les configurations d’entrepôt avancées, voir [Prélever des articles pour la livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md).  

## <a name="to-undo-posted-consumption" />Pour annuler une consommation reportée
Vous pouvez annuler la consommation sur les commandes service. Par exemple, parce qu'elle a été reportée par erreur.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons service reportées**, puis sélectionnez le lien associé.  
2. Ouvrez la livraison service reportée pour laquelle la consommation erronée a été reportée.  
3. Choisissez l'action **Lignes livraison service**.  
4. Sélectionnez les lignes contenant la consommation incorrecte, puis sélectionnez l'action **Annuler consommation**.  

 Une ligne livraison service de contrepartie contenant des valeurs négatives est insérée dans les champs de quantité pour les lignes sélectionnées.  
  
> [!NOTE]  
>  Vous ne pouvez pas annuler la consommation service si :  

>    * La commande service a été fermée.  
>    * Elle a été reportée dans la zone Projets, ce qui signifie que des écritures projet sont liées à cette consommation.  

## <a name="to-post-service-lines" />Pour reporter des lignes service
Si vous devez travailler sur une commande service pendant longtemps sans la reporter, vous pouvez reporter certaines lignes service qui y sont liées afin, par exemple de tenir votre inventaire à jour. Vous pouvez reporter en spécifiant les quantités appropriées dans les lignes à reporter. Vous pouvez décider de reporter les lignes une à une ou en sélectionnant plusieurs lignes à la fois.  

La procédure suivante décrit le report de la livraison directement à partir d'une commande service dans des emplacements sans configuration de la gestion d'entrepôt. Si l'emplacement est configuré pour appeler une gestion d'entrepôt, le report de livraison a lieu dans un autre document entrepôt, en fonction de la configuration de l'emplacement.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes service**, puis choisissez le lien associé.  
2. Ouvrez la commande service, puis cliquez sur l'action **Lignes service**.  
4. Dans les lignes que vous allez reporter, renseignez les champs **Qté à livrer**, **Qté à facturer** et **Qté à consommer**, en fonction de la manière dont vous allez reporter les lignes.  
5. Sélectionnez l'action **Valider**.

## <a name="see-also" />Voir aussi
[Report dans la Gestion des services](service-service-posting.md)  
[Créer une commande service](service-how-to-create-service-orders.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
