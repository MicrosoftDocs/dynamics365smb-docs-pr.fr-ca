---
title: Report de service
description: La fonctionnalité de report de service vous permet de traiter vos documents efficacement et de maintenir une stratégie de service client fructueuse.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Report de service
La fonctionnalité de report de service vous permet de traiter vos documents efficacement et de maintenir une stratégie de service client fructueuse. Vous pouvez créer et mettre à jour des documents reportés, et créer des écritures dans le module Service et dans d'autres modules pour garantir une mise à jour correcte.  

> [!NOTE]  
>  La section suivante décrit le report de service indépendamment de la façon dont les articles sont gérés physiquement dans l'entrepôt.  
>   
>  Dans un emplacement qui n'est pas configuré pour exiger une gestion d'entrepôt, vous effectuez des actions de report directement sur la page **Lignes service**. Dans les emplacements qui impliquent une gestion d'entrepôt, les tâches de report décrites, à l'exception des tâches Livrer et Consommer, sont effectuées indirectement au moyen de différentes fonctions de livraison de l'entrepôt, selon la configuration. Pour plus d'informations, voir [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).  

## Livrer  
La fonction Livraison vous permet d'enregistrer les articles et le temps appropriés entrés dans les lignes d'une commande service après que vous ayez exécuté le service. Une expédition enregistrée est crée et des mises à jour interviennent dans le module Stock, ainsi que d'autres modules dans [!INCLUDE[prod_short](includes/prod_short.md)] afin d'indiquer que les articles ont été prélevés sur le stock et envoyés au client. Plus particulièrement, les écritures du grand livre d'articles, du livre garantie, les écritures valeur et les écritures service sont générées.  

Si l'emplacement est configuré pour exiger la gestion d'entrepôt, la livraison et le déplacement d'articles de ligne service s'exécutent de la même manière que pour d'autres documents source. La seule différence est que les articles de la ligne service peuvent être consommés en externe ou en interne, ce qui nécessite deux fonctions de libération différentes.

## Facturer  
Vous devez utiliser l'option de facturation pour émettre une facture à l'adresse du client auquel vous voulez facturer le service. Généralement, il s'agit de la différence entre la quantité expédiée enregistrée par la fonction de **validation de l'expédition** et la quantité consommée enregistrée par la fonction de **validation de la consommation** sujette à facturation. Vous ne pouvez pas facturer ce qui n'a pas été livré. Lors de l'exécution de la fonction de **validation de la facture**, une facture service validée est crée et les documents validés sont mis à jour avant de les rendre cohérents avec les quantités qui sont contenues dans la facture émise. Comme pour les autres procédures de report, les écritures appropriées, qui incluent les écritures, sont générées.  

## Livrer et facturer  
L'option de livraison et de facturation vous permet d'émettre une livraison service et une facture en même temps.  

## Livrer et consommer  
L'option Livrer et consommer vous permet d'enregistrer et de reporter des articles, des coûts ou des heures d'entretien, mais qui ne peuvent pas figurer dans la facture adressée au client. Une facture n'est pas émise mais vous pouvez émettre simultanément une livraison service et une consommation service afin de refléter le fait que certains articles ou des heures ont été donnés au client gratuitement. Les écritures correspondantes sont également créées pour enregistrer la consommation.  

> [!NOTE]  
>  La procédure de report de service vous permet d'effectuer un report partiel. Vous pouvez créer une expédition ou une facture partielle en renseignant les champs **Qté à expédier** et **Qté à facturer** sur des lignes service de commandes de service avant la validation. Notez que vous ne pouvez pas créer de facture pour un article qui n'est pas livré. Cela signifie que, avant de pouvoir facturer, vous devez avoir enregistré une livraison ou choisir de livrer et de facturer en même temps.  

Une fois le report terminé, vous pouvez visualiser les documents service reportés depuis les pages correspondantes (**Livraison de service reportée** et **Facture de service reportée**). Vous pouvez visualiser les écritures reportées créées sur diverses pages contenant des écritures reportées (**Écritures**, **Écritures article**, **Écritures entrepôt**, **Écritures service**, **Écritures de grand livre projet**, **Écritures garantie**, etc.).  

## Pour visualiser les informations relatives aux documents service reportés  
Lorsque vous reportez une facture service, une livraison service ou une note de crédit service, les informations du document sont transférées respectivement sur les pages **Facture service reportée**, **Livraison service reportée** ou **Note de crédit service reportée**. Vous ne pouvez rien entrer, modifier ni supprimer sur ces pages. Vous pouvez imprimer un bon de livraison, une facture ou une note de crédit à partir de ces pages.  

La procédure suivante utilise un exemple de facture service reportée ; cette même procédure est applicable aux livraisons de service et aux notes de crédit reportées.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Facture de service reportées**, puis sélectionnez le lien associé.  
2. Ouvrez la facture service reportée que vous souhaitez afficher.  
3. Pour obtenir un aperçu de la facture reportée, choisissez l'action **Statistiques**.  

    La page **Statistiques commande service** s'ouvre. La page affiche des informations telles que la quantité, le montant, la TVA, le coût, le profit et la limite de crédit du client pour le document reporté.

## Voir aussi  
[Reporter des commandes de service](service-how-to-post-service-orders.md)   
[Créer commande service](service-how-to-create-service-orders.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]