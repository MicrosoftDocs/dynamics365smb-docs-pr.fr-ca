---
title: "Procédure : calculer des dates promesse livraison | Microsoft Docs"
description: "La fonction de configuration des promesses livraison est un outil permettant de calculer la date la plus proche à laquelle un article est disponible pour la livraison. Cette fonction crée également des lignes demande achat pour les dates que vous acceptez."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 11/23/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 2b1eae5f8562999f3fca227b6de6778ef1c5374e
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="calculate-order-promising-dates"></a>Calculer des dates promesse livraison
Une compagnie doit pouvoir informer ses clients des dates de livraison de commande. La page **Lignes promesse de livraison** vous permet d'effectuer cette opération à partir d'une ligne document de vente.  

À partir des dates de disponibilité connues et attendues d'un article, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule immédiatement les dates de livraison, qui peuvent être annoncées au client.  

Si vous spécifiez une date de livraison demandée sur une ligne document de vente, alors cette date est utilisée comme point de départ du calcul suivant :  

- date livraison demandée - délai livraison = date de livraison planifiée  
- date de livraison planifiée - délai désenlogement = date de livraison  

Si les articles peuvent être prélevés à la date de livraison, alors le processus vente peut continuer. Si les articles ne peuvent pas être prélevés à la date de livraison, alors une alerte rupture de stock est affichée.  

Si vous ne spécifiez aucune date livraison demandée sur une ligne de document de vente ou si la date livraison demandée ne peut pas être respectée, alors la première date à laquelle les articles sont disponibles est calculée. Cette date est ensuite renseignée dans le champ **Date de livraison** sur la ligne, et la date à laquelle vous prévoyez de livrer les articles, ainsi que la date à laquelle ces derniers seront livrés au client sont calculées à l'aide des calculs suivants :  

- date de livraison + délai désenlogement = date de livraison planifiée  
- date de livraison planifiée + délai de livraison = date de livraison planifiée  

## <a name="about-order-promising"></a>À propos de la promesse de livraison
La fonctionnalité de promesse de livraison vous permet de promettre la livraison d'une commande à une date donnée. La date à laquelle un article est disponible afin de le promettre ou de pouvoir le promettre est calculée, et des lignes commande sont créées pour les dates que vous acceptez. Cette fonctionnalité calcule la date la plus proche à laquelle un article est disponible pour livraison. Elle crée également des lignes de réquisition, dans le cas où les articles doivent d'abord être achetés, pour les dates que vous acceptez.

[!INCLUDE[d365fin](includes/d365fin_md.md)] utilise deux concepts essentiels :  

- Disponible à la vente (DAV)  
- Simulation de délai (SDD)  

### <a name="available-to-promise"></a>Disponible à la vente  
La fonction Disponible à la vente (ATP) calcule les dates sur la base du système de réservation. Elle effectue une vérification de la disponibilité des quantités non réservées en inventaire vis-à-vis de la production, des achats, des transferts et des retours vente planifiés. En fonction de ces informations, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule automatiquement la date de livraison de la commande du client dans la mesure où les articles sont disponibles (en inventaire ou sur réceptions planifiées).  

### <a name="capable-to-promise"></a>Simulation de délai  
La fonction Simulation de délai (CTP) considère un scénario basé sur l'hypothèse, qui s'applique uniquement aux quantités d'articles qui ne figurent pas dans l'inventaire ou des commandes programmées. En fonction de ce scénario, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule la date la plus proche à laquelle cet article sera disponible s'il doit être produit, acheté ou transféré.

#### <a name="example"></a>Exemple :
S'il y a une commande de 10 pièces, et que 6 pièces sont disponibles dans l'inventaire ou dans des commandes programmées, alors le calcul de simulation de délai est basé sur 4 pièces.

### <a name="calculations"></a>Calculs  
Lorsque [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule la date de livraison du client, il effectue deux tâches :  

- Calcule la première date de livraison possible lorsque le client n'a pas demandé une date de livraison spécifique.  
- Vérifie si la date de livraison demandée par le client ou confirmée au client est réaliste.  

Si le client ne demande pas de date de livraison spécifique, la date de livraison est configurée comme la date de travail, et la disponibilité est ensuite basée sur cette date. Si l'article est en inventaire, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule à l'avance pour déterminer quand la commande peut être livrée. Ceci est accompli par les formules suivantes :  

- Date de livraison + Délai traitement entrepôt sortant = Date de livraison planifiée  
- Date de livraison planifiée + délai de livraison = date de livraison planifiée  

Ensuite, [!INCLUDE[d365fin](includes/d365fin_md.md)] vérifie si la date de livraison calculée est réaliste en calculant en amont dans le temps, pour déterminer quand l'article doit être disponible pour respecter la date confirmée. Ceci est accompli par les formules suivantes :  

- Date de livraison planifiée - délai de livraison = date de livraison planifiée  
- Date de livraison planifiée - Désenlogement = Date de livraison  

La date de livraison est utilisée pour effectuer la vérification de disponibilité. Si l'article est disponible à cette date, [!INCLUDE[d365fin](includes/d365fin_md.md)] confirme que la livraison demandée/promise peut être respectée en configurant la date de livraison planifiée à la date de livraison demandée/confirmée. Si l'article n'est pas disponible, il renvoie une date vide et le préparateur de commandes peut alors utiliser la fonctionnalité CTP.  

Sur la base des nouvelles dates et heures, toutes les dates liées sont calculées en fonction des formules répertoriées précédemment dans cette section. Le calcul CTP prend plus de temps, mais donne une date précise à laquelle le client peut attendre la livraison de l'article. Les dates qui sont calculées à partir de la SDD sont présentées dans les champs **Date livraison planifiée** et **Date de livraison au plus tôt** sur la page **Lignes promesse de livraison**.  

Le préparateur de commandes finit le processus CTP en acceptant les dates. Cela signifie qu'une ligne de planification et une écriture de réservation sont créées pour l'article avant les dates calculées pour assurer que la commande est satisfaite.  

En plus de la promesse de livraison externe que vous pouvez effectuer sur la page **Lignes promesse de livraison**, vous pouvez également promettre des dates de livraison internes ou externes pour les articles de nomenclature. Pour plus d'informations, voir [Voir la disponibilité des articles](inventory-how-availability-overview.md).

## <a name="to-set-up-order-promising"></a>Pour configurer une promesse livraison  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration de promesse de commande**, puis sélectionnez le lien associé.  
2. Entrez un numéro et un code unité de temps dans le champ **Décalage (durée)**. Sélectionnez l'une des options suivantes.  

    |Code|Description|  
    |----------|-----------------|  
    |**j**|Jour du calendrier|  
    |**t**|Semaine|  
    |**m**|Mois|  
    |**t**|Trimestre|  
    |**a**|Année|  

    Par exemple, « 3S » indique que le décalage est de trois semaines. Pour indiquer la période en cours, utilisez le préfixe « c » devant l'un de ces codes. Par exemple, si vous souhaitez que le décalage porte sur le mois en cours, entrez **mc**.  
3. Entrez une série de numéros dans le champ **N° promesse de livraison** en sélectionnant une ligne dans la liste de la page **Séries de n°**.  
4. Entrez un modèle promesse de livraison dans le champ **Modèle promesse de livraison** en sélectionnant une ligne de la liste de la page **Liste des modèles demande achat**.  
5. Entrez une feuille de réquisition dans le champ **Feuille promesse de livraison** en sélectionnant une ligne de la liste de la page **Noms demandes achat**.

### <a name="to-enter-inbound-warehouse-handling-time-in-the-inventory-setup-page"></a>Pour entrer un délai d'enlogement sur la page Configuration de l'inventaire  
Vous pouvez configurer un délai entrepôt par défaut pour l'inventaire et votre emplacement, à inclure dans le calcul de promesse livraison sur la ligne achat.    
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration de l'inventaire**, puis sélectionnez le lien associé.  
2. Sur le raccourci **Général**, dans le champ **Délai enlogement**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.  

> [!NOTE]  
>  Si vous avez renseigné le champ **Délai enlogement** dans la **fiche magasin** pour votre magasin, ce champ est utilisé en tant que délai d'enlogement par défaut.  

### <a name="to-enter-inbound-warehouse-handling-time-on-location-cards"></a>Pour entrer des délais d'enlogement dans les fiches emplacement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Emplacement**, puis sélectionnez le lien associé.  
2.  Ouvrez la fiche emplacement appropriée.  
3.  Sur le raccourci **Entrepôt**, dans le champ **Délai enlogement**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.  

> [!NOTE]  
>  Si vous laissez le champ **Délai enlogement** vide, le calcul utilise la valeur de la page **Configuration de l'inventaire**.

### <a name="to-enter-outbound-warehouse-handling-time-in-the-inventory-setup-page"></a>Pour entrer un délai de désenlogement sur la page Configuration de l'inventaire  
Vous pouvez configurer un délai désenlogement par défaut pour l'inventaire, à inclure dans le calcul de promesse livraison sur la ligne de vente.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration de l'inventaire**, puis sélectionnez le lien associé.  
2. Sur le raccourci **Général**, dans le champ **Délai enlogement sortant**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.  

> [!NOTE]  
>  Si vous avez renseigné le champ **Délai enlogement sortant** dans la fiche magasin pour votre magasin, ce champ est utilisé en tant que délai d'enlogement sortant par défaut.  

### <a name="to-enter-outbound-warehouse-handling-time-on-location-cards"></a>Pour entrer un délai de désenlogement sortant dans les fiches emplacement  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Emplacements**, puis sélectionnez le lien associé.  
2.  Ouvrez la fiche emplacement appropriée.  
3.  Sur le raccourci **Entrepôt**, dans le champ **Délai enlogement sortant**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.  

> [!NOTE]  
>  Si vous laissez le champ **Délai désenlogement** vide, le calcul utilise la valeur de la page **Configuration de l'inventaire**.

## <a name="to-make-an-item-critical"></a>Pour affecter le statut critique à un article  
Avant qu'un article puisse être inclus dans le calcul de la promesse de livraison, il doit être signalé comme critique. Cette configuration garantit que les articles non critiques ne génèrent pas de calculs inutiles de promesse de livraison.   
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.  
2.  Ouvrez la fiche article appropriée.  
3.  Sur le raccourci **Planifié**, sélectionnez le champ **Critique**.  

## <a name="to-calculate-an-order-promising-date"></a>Pour calculer une date promesse livraison  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Document de vente**, puis sélectionnez le lien associé.  
2.  Ouvrez le document de vente approprié et sélectionnez les lignes de document de vente que vous souhaitez que le programme calcule.  
3.  Choisissez l'action **Promesse de livraison**, puis sélectionnez l'action **Lignes promesse de livraison**.  
4.  Sélectionnez une ligne, puis l'une des options suivantes :  

    - Choisissez **Disponible à la vente** si vous souhaitez calculer la date la plus proche à laquelle l'article sera disponible pour ce qui est de l'inventaire, des réceptions programmées, et des besoins bruts.  
    - Choisissez **Simulation de délai** si vous savez que l'article est actuellement en rupture de stock et que vous souhaitez calculer la date la plus proche à laquelle cet article sera disponible grâce à l'émission de demandes de réapprovisionnement.  
5.  Choisissez le bouton **Accepter** pour accepter la date d'expédition disponible la plus proche.  

## <a name="see-also"></a>Voir aussi  
[Vente](sales-manage-sales.md)  
[Calcul de la date des achats](purchasing-date-calculation-for-purchases.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

