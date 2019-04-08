---
title: 'Procédure pas à pas : planification manuelle des approvisionnements | Microsoft Docs'
description: Cette procédure pas à pas présente le processus de planification des commandes approvisionnement en vue de répondre à la nouvelle demande. Vous pouvez lancer la planification des approvisionnements à des intervalles fixes, par exemple, tous les matins ou tous les lundis, ou lorsque vous recevez une notification du département Ventes ou Production, en fonction du type de demande.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 01/31/2019
ms.author: sgroespe
ms.openlocfilehash: bed38cf158e5372ff9c4e2f23667fba8af93ec74
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813043"
---
# <a name="walkthrough-planning-supplies-manually"></a>Procédure pas à pas : planification manuelle des approvisionnements

**Remarque** : Ce guide pas-à-pas doit être effectué sur une compagnie de démonstration avec l'option **Évaluation complète - Renseigner des exemples de données**, disponible dans l'environnement Sandbox. Pour plus d’informations, voir [Création d'un environnement Sandbox](across-how-create-sandbox-environment.md).

Cette procédure pas à pas présente le processus de planification des commandes d'approvisionnement en vue de répondre à la nouvelle demande. Vous pouvez lancer la planification des approvisionnements à des intervalles fixes, par exemple, tous les matins ou tous les lundis, ou lorsque vous recevez une notification du département Ventes ou Production, en fonction du type de demande. Au cours de cette procédure, vous utiliserez la page **Planification commande**, un outil simplifié de planification des approvisionnements basé sur la prise de décision manuelle plutôt que la planification automatique basée sur des paramètres.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
 Cette procédure pas à pas présente les tâches suivantes :  

-   planification d'un bon de commande pour les composantes de production ;  
-   planification d'un ordre de transfert afin de répondre à la demande de vente ;  
-   Planification d'un bon de production pour un article multi-niveaux.  

## <a name="roles"></a>Rôles  
 Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

-   Gestionnaire de production  
-   Agent d'achats  
-   Préparateur de commandes vente  

## <a name="prerequisites"></a>Conditions préalables  
 Avant de commencer cette procédure pas à pas, vous devez installer la [!INCLUDE[d365fin](includes/d365fin_md.md)]. Les modifications suivantes doivent être apportées à la base de données :  

-   Supprimez toute commande vente existante de bicyclettes.  
-   Créez un document de vente pour 10 bicyclettes pour l'emplacement BLUE.  
-   Supprimez tous les ordres de fabrication planifiés et planifiés fermes. Ne supprimez pas les ordres démarrés dont les écritures ont déjà été reportées.  

 En règle générale, utilisez les données suggérées dans cette procédure pas à pas car elles incluent les enregistrements nécessaires.  

## <a name="story"></a>Scénario  
 Eduardo, Gestionnaire de production dans une petite compagnie manufacturière, est sur le point de planifier les bons de production et bons de commande en réponse à la demande de vente.  

 Dans la mesure où les produits disposent de peu de niveaux de nomenclature et où le flux de commandes est relativement faible, Eduardo utilise la page **Planification commande** pour créer manuellement les commandes d'approvisionnement (un niveau de produit à la fois).  

 Dans un environnement de fabrication plus complexe, la feuille planification permet de planifier l'approvisionnement sur la base des paramètres d'article, tels que la période de reprogrammation, le délai de sécurité, le point de réapprovisionnement et les calculs par lots de la demande consolidée à partir de tous les niveaux de produit.  

## <a name="setting-up-the-sample-data"></a>Configuration des exemples de données  
 La société de démonstration CRONUS standard dispose actuellement d'un grand nombre de demandes non planifiées. Au cours des différentes tâches de planification de cette procédure pas à pas, vous devrez passer outre le flux commercial réaliste : utilisez la demande dont les dates d'échéance sont ultérieures plutôt que celle dont les dates sont échues.  

## <a name="using-the-order-planning-page"></a>Utilisation de la page Planification commande  

<!--
The **Order Planning** page can be accessed from several different locations on the **Departments** menu in the navigation pane:  

-   Manufacturing, Planning  
-   Sales & Marketing, Order Processing  
-   Purchase, Planning  
-   In addition, you can open this page for a specific production order by choosing **Planning** on the **Navigate** tab in the **Order** group.

-->  

### <a name="to-use-the-order-planning-page"></a>Pour utiliser la page Planification commande :  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Planification commande**, puis sélectionnez le lien associé.  

     À la première ouverture de la page **Planification commande**, une planification doit être calculée pour afficher la nouvelle demande depuis le dernier calcul.  

2.  Choisissez l'action **Calculer planning**.  

     Le système de planification analyse chaque nouvelle demande, telle qu'une nouvelle vente, des modifications de ventes ou des ordres de fabrication.  

     Selon la disponibilité globale, la quantité nécessaire pour chaque ligne commande est calculée. Ce calcul est effectué commande par commande. Cela signifie que la commande dont la ligne de réquisition a la date d'échéance ou la date de livraison la plus proche sera calculée en premier. Les autres lignes de réquisition seront ensuite calculées dans le même ordre, quelle que soit la date d'échéance ou la date de livraison.  

3.  Assurez-vous d'agrandir au maximum la page **Planification commande** et de redimensionner les champs des colonnes pour afficher tous les noms de champ par défaut.  

     À la fin du calcul, la page affiche toutes les demandes insatisfaites sous la forme de lignes en-tête commande réduites triées par date de demande la plus proche.  

     Notez que CRONUS inclut plusieurs commandes dont la demande est insatisfaite. Chaque ligne planification en gras représente une commande, un document de vente ou un bon de production, comprenant au moins une ligne commande avec une disponibilité insuffisante.  

4.  Dans le champ **Afficher la demande en tant que**, sélectionnez le filtre **Toutes les demandes**.  

     Dans le champ **Type de demande**, vous pouvez sélectionner les types de commande à afficher.  

     Les commandes sans problème de disponibilité ne s'affichent pas. Si aucune commande n'existe lors du calcul d'une planification, un message s'affiche et aucune ligne planification n'apparaît.  

## <a name="planning-a-purchase-order-to-fulfill-component-demand"></a>Planification d'un bon de commande pour répondre à une demande de composante  
 Dans cette procédure, vous créez un bon de commande pour les composantes nécessaires à la fabrication.  

### <a name="to-plan-a-purchase-order-to-fulfill-component-need-in-production"></a>Pour planifier un bon de commande en vue de répondre aux besoins de composantes en production  

1.  Développez la première ligne en cliquant sur le symbole +.  
2.  Sélectionnez la première ligne demande, avec l'article **LSU-15**, puis sélectionnez l'action **Afficher document**.  
3.  Fermez le bon de production ouvert pour revenir à la page **Planification commande**.  
4.  Dans le champ **Système réappro.**, sélectionnez **Achats**.  

     La valeur par défaut est celle indiquée sur la fiche article (ou la fiche unité de stock), mais vous pouvez la modifier et lui attribuer l'une des options suivantes :  

    -   **Achat** : pour créer une commande achat.  
    -   **Transfert** : pour créer un ordre de transfert.  
    -   **O.F** : pour créer un ordre de fabrication.  

5.  Dans le champ **Origine approvisionnement**, sélectionnez l'une des options suivantes en fonction du système de réapprovisionnement sélectionné :  

    -   **Fournisseur** – Pour les achats  
    -   **Magasin** – Pour les transferts  

     Si le champ n'est pas renseigné, un message d'erreur s'affiche lorsque vous tentez de créer les commandes approvisionnement.  

    > [!NOTE]  
    >  Si un numéro fournisseur par défaut pour les composants est configuré sur les fiches article, les lignes sont prédéfinies.  

6.  Sélectionnez le champ **Origine approvisionnement**.  
7.  Sur la page **Catalogue fournisseur articles**, choisissez l'action **Nouveau**, puis sélectionnez le fournisseur **30000**.  
8.  Cliquez sur le bouton **OK** pour revenir à la page **Planification commande**.  
9. Copiez le fournisseur **30000** vers les autres lignes pour les composants « haut-parleurs » correspondant à cet ordre de fabrication.  

     Vous êtes maintenant prêt à créer un bon de commande.  

10. Sélectionnez l'action **Créer commandes**. La page **Créer des commandes d'approvisionnement** s'ouvre.  
11. Sur le raccourci **Planning commande**, dans le champ **Créer commandes pour**, sélectionnez l'option **Commande active**.  
12. Sur le raccourci **Options**, dans le champ **Créer commande achat**, sélectionnez l'option **Créer cdes achat**.  
13. Cliquez sur le bouton **OK** pour créer les commandes achat pour tous les composants de la commande.  

     Les commandes achat sont à présent créées et enregistrées en tant que dernières commandes dans la liste des commandes achat.  

## <a name="planning-a-transfer-order-to-fulfill-sales-demand"></a>Planification d'un ordre de transfert pour répondre à une demande de vente  
 Dans cette procédure, vous planifiez une demande à partir d'un document de vente. Les lignes de réquisition représentent les lignes vente (et non les lignes composante, comme c'est le cas pour les demandes de production).  

### <a name="to-plan-a-transfer-order-to-fulfill-sales-demand"></a>Pour planifier un ordre de transfert afin de répondre à la demande de vente :  

1.  Déplacez le pointeur vers la ligne planning correspondant à la commande **2008**.  
2.  Développez la ligne et déplacez le pointeur vers la ligne demande.  

     La document de vente **2008** correspond à dix haut-parleurs, article **LS-120**, commandés par la compagnie John Haddock Insurance Co.  

     Le système de réapprovisionnement et le fournisseur par défaut de l'article s'affichent.  

    > [!NOTE]  
    >  Au bas de la page, quatre champs d'informations s'affichent. Dans le champ **Date dispo. au plus tôt**, les dix pièces nécessaires sont disponibles sur une commande approvisionnement entrante, neuf jours après la date d'échéance actuelle. Si cette date est trop tardive pour le client, le champ **Disponible pour transfert** affiche 13 pièces de l'article provenant d'un autre magasin. Vous devez planifier ce stock.  

3.  Choisissez le champ **Disponible pour transfert** pour ouvrir la page **Obtenir un approvisionnement secondaire**.  
4.  Cliquez sur le bouton **OK** pour réserver les dix articles disponibles.  

    > [!NOTE]  
    >  Dans la ligne de réquisition, l'achat proposé a été remplacé par un transfert à partir de l'emplacement GREEN. La fonction **Créer commandes** crée un ordre de transfert du magasin GREEN vers le magasin demandé. Le champ **Articles de substitution** fonctionne de la même manière.  

5.  Sélectionnez l'action **Créer commandes**. La page **Créer des commandes d'approvisionnement** s'ouvre.  
6.  Sur le raccourci **Planning commande** dans le champ **Créer commandes pour**, sélectionnez l'option **La commande active**.  
7.  Sur le raccourci **Options**, dans le champ **Créer un ordre de transfert**, sélectionnez l'option **Créer ordres transfert**.  
8.  Cliquez sur le bouton **OK** pour créer l'ordre de transfert visant à approvisionner la commande vente.  

     L'ordre de transfert est à présent créé et enregistré en tant que dernier ordre dans la liste des ordres de transfert en cours.  

## <a name="planning-a-multilevel-production-order-to-fulfill-sales-demand"></a>Planification d'un ordre de production multi-niveaux pour répondre à une demande de vente  
 Dans cette procédure, vous effectuez une planification en vue de satisfaire la demande de vente pour un article produit avec plusieurs niveaux de produit, chacun d'entre eux créant une demande de production dépendante.  

### <a name="to-plan-multilevel-production-to-fulfill-sales-demand"></a>Pour planifier une production multi-niveaux afin de répondre à la demande de vente :  

1.  Sélectionnez la ligne planning avec une demande de vente pour la commande **1001**, créée plus tôt comme données préalables.  

     Cette demande est une ligne vente, mais l'article a un système de réapprovisionnement défini sur **O. F.**. Ajoutez ensuite une sonnette supplémentaire au besoin composante de chaque bicyclette.  

2.  Choisissez l'action **Composantes** pour ouvrir la page **Composantes planification**.  
3.  Sur la ligne correspondant à l'article Sonnerie, remplacez la valeur **1** du champ **Quantité par** par **2**.  
4.  Sur la page **Planification commande**, étudiez les différentes possibilités de planification. Dans ce cas, vous ne disposez pas d'autres moyens d'approvisionnement, ni d'aucun transfert, remplacement ou livraison en retard. Vous devez créer la commande approvisionnement suggérée, à savoir un bon de production.  
5.  Choisissez l'action **Créer commandes** pour créer l'ordre de fabrication.  

     Sur la page **Planification commande**, vous remarquez que la ligne planification correspondant au document de vente **1001** n'existe plus et que la demande de vente initiale a été couverte.  

6.  Fermez la page **Planification commande**.  

     Vous pourriez à présent conserver cet affichage et exécuter toutes les tâches de planification. Au lieu de cela, vous devez prendre le rôle Gestionnaire de production en accédant à l'ordre de fabrication que vous venez de créer, puis à la page **Planification commande**.  

 En tant que gestionnaire de production, vous devez maintenant planifier un bon de production spécifique.  

### <a name="to-plan-a-specific-production-order"></a>Pour planifier un bon de production spécifique :  

1.  Ouvrez l'ordre de fabrication **101001** pour dix bicyclettes, créé à l'aide de la fonction **Créer commandes**.  
2.  Ouvrez la page **Composantes bon de production** pour vérifier que la sonnette supplémentaire figure dans le bon de production.  
3.  Sélectionnez l'action **Planification**.  

     La page **Planification commande** s'ouvre dans une vue qui est toujours filtrée en fonction de la demande de production spécifique. La demande de vente ne s'affiche pas. Vous devez calculer une planification avant de pouvoir visualiser les demandes supplémentaires.  

4.  Choisissez l'action **Calculer planning**.  

     Remarque : quatre nouveaux ordres de fabrication s'affichent en tant que demande de production non planifiée issue de la commande **101001**. Les nouvelles lignes représentent la nouvelle demande de production de sous-ensembles que vous devez créer pour produire la commande.  

5.  Choisissez l'action **Développer tout** pour obtenir un aperçu de la demande de production correspondant aux ordres de fabrication.  

     Pour indiquer des informations supplémentaires sur les lignes demande, vous pouvez ajouter les champs **Quantité demandée** et **Qté demande disponible** à votre affichage.  

     Vous devez à présent approvisionner dix unités de chaque composante.  

     Notez que quatre des lignes demande ont pour système de réapprovisionnement O. F. Ces quatre sous-ensembles représentent le deuxième niveau de produit de la bicyclette.  

     Les paramètres de réapprovisionnement par défaut étant déjà renseignés, vous pouvez créer les commandes.  

6.  Sélectionnez l'action **Créer commandes**.  

     Avant de cliquer sur le bouton **OK**, observez attentivement le texte sous le raccourci **Planning commande**. Ce texte est important, car il vous permet de savoir que la bicyclette possède plusieurs composantes produits (ou sous-ensembles) dans sa structure produit qui peuvent être demandés lorsque vous créez ce bon de production.  

7.  Sur la page **Créer des commandes d'approvisionnement**, dans le champ **Créer commandes pour**, sélectionnez l'option **Toutes les lignes**, puis cliquez sur le bouton **OK** pour créer des bons de production pour le deuxième niveau de produit de la commande.  

     Remarquez que la demande de production de niveau supérieur pour l'ordre de fabrication 101001 n'existe plus. Cela signifie que la demande de production initiale des sous-ensembles a été planifiée.  

     Sur la page **Planification commande**, recalculez une planification pour planifier la structure de la bicyclette.  

8.  Choisissez l'action **Calculer planning** pour recalculer le planning selon les instructions du texte d'aide incorporé.  

     Les deux nouvelles lignes représentent la demande de production supplémentaire issue des sous-ensembles planifiés au cours des étapes précédentes. Il est recommandé de créer deux ordres de fabrication pour approvisionner les moyeux des roues, à savoir un ordre pour les 10 moyeux avant et un autre pour les 10 moyeux arrière.  

9. Choisissez l'action **Développer tout** pour obtenir un aperçu de la demande correspondant aux deux ordres de fabrication.  

     Le programme d'approvisionnement proposé indique que quatre commandes achat seront créées pour les composants. Vous décidez de créer les commandes suggérées.  

10. Sélectionnez l'action **Créer commandes**.  
11. Dans le champ **Créer commandes pour**, sélectionnez l'option **Toutes les lignes**, puis cliquez sur le bouton **OK**. Vérifiez s'il existe une demande supplémentaire pour la production de l'article parent, la bicyclette, qui est vendue dans le cadre du document de vente 1001.  
12. Choisissez l'action **Calculer planning**.  

     Le message indique que tous les articles requis sont à présent approvisionnés. Vérifiez les ordres de fabrication planifiés fermes qui ont été créés.  

13. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Bons de production planifiés fermes**, puis sélectionnez le lien associé.  

     Sur la page **Ordre de production planifiés fermes**, passez en revue la planification des heures de début et de fin de chaque commande par rapport à la structure produit. Les composantes de niveau inférieur sont produites en premier. Par conséquent, vous devez planifier des commandes multi-niveaux conformément aux instructions de ce flux de planification.  

## <a name="see-also"></a>Voir aussi  
 [Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)   
 [Procédure pas à pas : planification automatique des approvisionnements](walkthrough-planning-supplies-automatically.md)
