---
title: Calculer des dates promesse livraison
description: La fonction de configuration des promesses livraison est un outil permettant de calculer la date la plus proche à laquelle un article est disponible pour la livraison.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/29/2021
ms.author: edupont
---
# Calculer des dates promesse livraison

Une compagnie doit pouvoir informer ses clients des dates de livraison de commande. La page **Lignes promesse de livraison** vous permet d’effectuer cette opération à partir d’un document de vente.  

[!INCLUDE[prod_short](includes/prod_short.md)] calcule les dates de livraison à partir des dates de disponibilité connues et attendues d’un article, qui peuvent être annoncées au client.  

Si vous spécifiez une date de livraison demandée sur une ligne document de vente, alors cette date est utilisée comme point de départ du calcul suivant :  

- date livraison demandée - délai livraison = date de livraison planifiée  
- date de livraison planifiée - délai désenlogement = date de livraison  

Si les articles peuvent être prélevés à la date de livraison, alors le processus vente peut continuer. Si les articles ne peuvent pas être prélevés à la date de livraison, alors une alerte rupture de stock est affichée.  

Si vous ne spécifiez aucune date livraison demandée sur une ligne de document de vente ou si la date livraison demandée ne peut pas être respectée, alors la première date à laquelle les articles sont disponibles est calculée. Cette date est ensuite renseignée dans le champ **Date de livraison** sur la ligne, et la date à laquelle vous prévoyez de livrer les articles, ainsi que la date à laquelle ces derniers seront livrés au client sont calculées à l'aide des calculs suivants :  

- date de livraison + délai désenlogement = date de livraison planifiée  
- date de livraison planifiée + délai de livraison = date de livraison planifiée  

## À propos de la promesse de livraison

La fonctionnalité de promesse de livraison vous permet de promettre la livraison d'une commande à une date donnée. La date à laquelle un article est disponible afin de le promettre ou de pouvoir le promettre est calculée, et des lignes commande sont créées pour les dates que vous acceptez. Cette fonctionnalité calcule la date la plus proche à laquelle un article est disponible pour livraison. Elle crée également des lignes de réquisition, dans le cas où les articles doivent d’abord être achetés ou produits, pour les dates que vous acceptez.

[!INCLUDE[prod_short](includes/prod_short.md)] utilise deux concepts essentiels :  

- Disponible à la vente (DAV)  
- Simulation de délai (SDD)  

### Disponible à la vente

La fonction Disponible à la vente (ATP) calcule les dates sur la base du système de réservation. Elle effectue une vérification de la disponibilité des quantités non réservées en inventaire vis-à-vis de la production, des achats, des transferts et des retours vente planifiés. En fonction de ces informations, [!INCLUDE[prod_short](includes/prod_short.md)] calcule automatiquement la date de livraison de la commande du client, dans la mesure où les articles sont disponibles (en inventaire ou avec entrée planifiée).  

### Simulation de délai

La fonction Simulation de délai (CTP) considère un scénario basé sur l'hypothèse, qui s'applique uniquement aux quantités d'articles qui ne figurent pas dans l'inventaire ou des commandes programmées. En fonction de ce scénario, [!INCLUDE[prod_short](includes/prod_short.md)] calcule la date la plus proche à laquelle cet article sera disponible s'il doit être produit, acheté ou transféré.

#### Exemple :

Dans le cas d’une commande de 10 pièces, lorsque 6 pièces sont disponibles en inventaire ou dans des commandes programmées, alors le calcul de simulation de délai est basé sur 4 pièces.

### Calculs

Lorsque [!INCLUDE[prod_short](includes/prod_short.md)] calcule la date de livraison du client, il effectue deux tâches :  

- Calcule la première date de livraison possible lorsque le client n'a pas demandé une date de livraison spécifique.  
- Vérifie si la date de livraison demandée par le client ou confirmée au client est réaliste.  

Si le client ne demande pas de date de livraison spécifique, la date de livraison est configurée comme la date de travail, et la disponibilité est ensuite basée sur cette date. Si l'article est en inventaire, [!INCLUDE[prod_short](includes/prod_short.md)] calcule à l'avance pour déterminer quand la commande peut être livrée. Ceci est accompli par les formules suivantes :  

- Date de livraison + Délai traitement entrepôt sortant = Date de livraison planifiée  
- Date de livraison planifiée + délai de livraison = date de livraison planifiée  

Ensuite, [!INCLUDE[prod_short](includes/prod_short.md)] vérifie si la date de livraison calculée est réaliste en calculant en amont dans le temps, pour déterminer quand l'article doit être disponible pour respecter la date confirmée. Ceci est accompli par les formules suivantes :  

- Date de livraison planifiée - délai de livraison = date de livraison planifiée  
- Date de livraison planifiée - Désenlogement = Date de livraison  

La date de livraison est utilisée pour effectuer la vérification de disponibilité. Si l’article est disponible à cette date, [!INCLUDE[prod_short](includes/prod_short.md)] confirme que la livraison demandée/promise peut être respectée en configurant la date de livraison planifiée à la date de livraison demandée/confirmée. Si l'article n'est pas disponible, il renvoie une date vide et le préparateur de commandes peut alors utiliser la fonctionnalité CTP.  

Sur la base des nouvelles dates et heures, toutes les dates liées sont calculées en fonction des formules répertoriées précédemment dans cette section. Le calcul CTP prend plus de temps, mais donne une date précise à laquelle le client peut attendre la livraison de l'article. Les dates qui sont calculées à partir de la SDD sont présentées dans les champs **Date livraison planifiée** et **Date de livraison au plus tôt** sur la page **Lignes promesse de livraison**.  

Le préparateur de commandes finit le processus CTP en acceptant les dates. Cela signifie qu'une ligne de planification et une écriture de réservation sont créées pour l'article avant les dates calculées pour assurer que la commande est satisfaite.  

En plus de la promesse de livraison externe que vous pouvez effectuer sur la page **Lignes promesse de livraison**, vous pouvez également promettre des dates de livraison internes ou externes pour les articles de nomenclature. Pour plus d'informations, voir [Voir la disponibilité des articles](inventory-how-availability-overview.md).

## Pour configurer une promesse livraison

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration promesses livraison**, puis choisissez le lien associé.  
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

### Délais de traitement entrepôts entrants et sortants dans les promesses de livraison

Pour inclure un délai entrepôt dans le calcul de la promesse de livraison sur la ligne achat, sur la page **Configuration inventaire** vous pouvez spécifier un délai d’enlogement par défaut à utiliser sur les documents achat et vente. Vous pouvez également saisir des heures spécifiques pour chacun de vos emplacements sur la page **Fiche emplacement**. 

#### Pour saisir les délais de traitement d’entrepôt d’entrée et de sortie par défaut pour les documents vente et dachat

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration de l’inventaire**, puis choisissez le lien associé.  
2. Sur le raccourci **Général**, dans les champs **Délai enlogement** et **Délai désenlogement**, indiquez le nombre de jours que vous souhaitez inclure dans les calculs de la promesse de livraison.  

#### Pour entrer des délais d’enlogement et de désenlogement dans les fiches emplacement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacement**, puis choisissez le lien associé.  
2.  Ouvrez la fiche emplacement appropriée.  
3.  Sur le raccourci **Entrepôt**, dans les champs **Délai enlogement** et **Délai désenlogement**, indiquez le nombre de jours à inclure dans les calculs de la promesse de livraison.  

> [!NOTE]  
>  Lorsque vous créez un bon de commande, si vous choisissez **Emplacement** dans le champ **Destinataire** sur le raccourci **Livraison et paiement**, puis choisissez un emplacement dans le champ **Code emplacement**, les champs **Délai désenlogement** et **Délai enlogement** utiliseront le temps de traitement spécifié pour l’emplacement. Pour les documents de vente, il en va de même si vous choisissez un emplacement dans le champ **Code emplacement**. Si aucun délai de traitement n’est spécifié pour l’emplacement, les champs **Délai désenlogement** et **Délai enlogement** seront vides. Si vous laissez le champ **Code emplacement** vide sur les documents vente et achat, le calcul utilise le temps de traitement indiqué sur la page **Configuration inventaire**.

## Pour affecter le statut critique à un article

Avant qu'un article puisse être inclus dans le calcul de la promesse de livraison, il doit être signalé comme critique. Cette configuration garantit que les articles non critiques ne génèrent pas de calculs inutiles de promesse de livraison.   
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2.  Ouvrez la fiche article appropriée.  
3.  Sur le raccourci **Planifié**, sélectionnez le champ **Critique**.  

## Pour calculer une date promesse livraison

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Document de vente**, puis sélectionnez le lien associé.  
2.  Ouvrez le document de vente approprié et sélectionnez les lignes de document de vente que vous souhaitez que l'application calcule.  
3.  Choisissez l'action **Promesse de livraison**, puis sélectionnez l'action **Lignes promesse de livraison**.  
4.  Sélectionnez une ligne, puis l'une des options suivantes :  

    - Choisissez **Disponible à la vente** si vous souhaitez calculer la date la plus proche à laquelle l'article sera disponible pour ce qui est de l'inventaire, des réceptions programmées, et des besoins bruts.  
    - Choisissez **Simulation de délai** si vous savez que l'article est actuellement en rupture de stock et que vous souhaitez calculer la date la plus proche à laquelle cet article sera disponible grâce à l'émission de demandes de réapprovisionnement.  
5.  Choisissez le bouton **Accepter** pour accepter la date d'expédition disponible la plus proche.  

## Voir la [formation Microsoft](/training/modules/promising-sales-order-delivery-dynamics-365-business-central/) associée

## Voir aussi .

[Ventes](sales-manage-sales.md)  
[Calcul de la date des achats](purchasing-date-calculation-for-purchases.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
