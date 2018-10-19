---
title: Report de service | Microsoft Docs
description: "La fonctionnalité de report de service vous permet de traiter vos documents efficacement et de maintenir une stratégie de service client fructueuse. Vous pouvez créer et mettre à jour des documents reportés, et créer des écritures dans le module Service et dans d'autres modules pour garantir une mise à jour correcte."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 75f0fd760978b0efc4ab86b8d17a815280a09799
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="service-posting"></a>Report de service
La fonctionnalité de report de service vous permet de traiter vos documents efficacement et de maintenir une stratégie de service client fructueuse. Vous pouvez créer et mettre à jour des documents reportés, et créer des écritures dans le module Service et dans d'autres modules pour garantir une mise à jour correcte.  

> [!NOTE]  
>  La section suivante décrit le report de service indépendamment de la façon dont les articles sont gérés physiquement dans l'entrepôt.  
>   
>  Dans un magasin qui n'est pas configuré pour appeler une gestion d'entrepôt, vous effectuez des actions de validation directement dans la fenêtre **Lignes service**. Dans les emplacements qui impliquent une gestion d'entrepôt, les tâches de report décrites, à l'exception des tâches Livrer et Consommer, sont effectuées indirectement au moyen de différentes fonctions de livraison de l'entrepôt, selon la configuration. Pour plus d'informations, voir [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).  

## <a name="ship"></a>Livrer  
La fonction Livraison vous permet d'enregistrer les articles et le temps appropriés entrés dans les lignes d'une commande service après que vous ayez exécuté le service. Une expédition enregistrée est crée et des mises à jour interviennent dans le module Stock, ainsi que d'autres modules dans [!INCLUDE[d365fin](includes/d365fin_md.md)] afin d'indiquer que les articles ont été prélevés sur le stock et envoyés au client. Plus particulièrement, les écritures du grand livre d'articles, du livre garantie, les écritures valeur et les écritures service sont générées.  

Si l'emplacement est configuré pour exiger la gestion d'entrepôt, la livraison et le déplacement d'articles de ligne service s'exécutent de la même manière que pour d'autres documents source. La seule différence est que les articles de la ligne service peuvent être consommés en externe ou en interne, ce qui nécessite deux fonctions de libération différentes.

## <a name="invoice"></a>Facturer  
Vous devez utiliser l'option de facturation pour émettre une facture à l'adresse du client auquel vous voulez facturer le service. Généralement, il s'agit de la différence entre la quantité expédiée enregistrée par la fonction de **validation de l'expédition** et la quantité consommée enregistrée par la fonction de **validation de la consommation** sujette à facturation. Vous ne pouvez pas facturer ce qui n'a pas été livré. Lors de l'exécution de la fonction de **validation de la facture**, une facture service validée est crée et les documents validés sont mis à jour avant de les rendre cohérents avec les quantités qui sont contenues dans la facture émise. Comme pour les autres procédures de report, les écritures appropriées, qui incluent les écritures, sont générées.  

## <a name="ship-and-invoice"></a>Livrer et facturer  
L'option de livraison et de facturation vous permet d'émettre une livraison service et une facture en même temps.  

## <a name="ship-and-consume"></a>Livrer et consommer  
L'option Livrer et consommer vous permet d'enregistrer et de reporter des articles, des coûts ou des heures d'entretien, mais qui ne peuvent pas figurer dans la facture adressée au client. Une facture n'est pas émise mais vous pouvez émettre simultanément une livraison service et une consommation service afin de refléter le fait que certains articles ou des heures ont été donnés au client gratuitement. Les écritures correspondantes sont également créées pour enregistrer la consommation.  

> [!NOTE]  
>  La procédure de report de service vous permet d'effectuer un report partiel. Vous pouvez créer une expédition ou une facture partielle en renseignant les champs **Qté à expédier** et **Qté à facturer** sur des lignes service de commandes de service avant la validation. Notez que vous ne pouvez pas créer de facture pour un article qui n'est pas livré. Cela signifie que, avant de pouvoir facturer, vous devez avoir enregistré une livraison ou choisir de livrer et de facturer en même temps.  

Une fois la validation terminée, vous pouvez visualiser les documents service validés depuis les fenêtres correspondantes (**Expédition service enreg.** et **Facture service enreg.**). Vous pouvez visualiser les écritures reportées créées dans diverses fenêtres contenant des écritures reportées (**Écritures**, **Écritures article**, **Écritures entrepôt**, **Écritures service**, **Écritures projet**, **Écritures garantie**, etc.).  

## <a name="to-view-information-about-a-posted-service-document"></a>Pour visualiser les informations relatives aux documents service reportés  
Lorsque vous validez une facture service, une expédition service ou un avoir service, les informations du document sont transférées respectivement dans les fenêtres **Facture service enreg.**, **Expédition service enreg.**, ou **Avoir service enreg.**. Vous ne pouvez rien entrer, modifier ni supprimer dans ces fenêtres. Vous pouvez imprimer un bon de livraison, une facture ou une note de crédit à partir de ces fenêtres.  

La procédure suivante utilise un exemple de facture service reportée ; cette même procédure est applicable aux livraisons de service et aux notes de crédit reportées.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Facture service reportée**, puis sélectionnez le lien associé.  
2. Ouvrez la facture service reportée que vous souhaitez afficher.  
3. Pour obtenir un aperçu de la facture reportée, choisissez l'action **Statistiques**.  

    La fenêtre **Statistiques commande service** s'ouvre. La fenêtre affiche des informations telles que la quantité, le montant, la TVA, le coût, les profits, et la limite de crédit du client pour le document reporté.

## <a name="see-also"></a>Voir aussi  
[Reporter des commandes de service](service-how-to-post-service-orders.md)   
[Créer commande service](service-how-to-create-service-orders.md)

