---
title: Exécuter une planification complète et un calcul PDP ou MRP
description: 'Le système de planification peut calculer le calendrier de production principal (MPS, Master Production Schedule) ou la planification des besoins matière (MRP, Material Requirements Planning) à la demande, ou les deux simultanément.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '99000852, 99000860'
ms.date: 06/22/2021
ms.author: edupont
---
# <a name="run-full-planning-mps-or-mrp" />Exécuter une planification complète et un calcul PDP ou MRP

Les termes « exécution de la feuille planification » ou « exécution d'un calcul MRP » font référence au calcul du calendrier de production principal et aux réquisitions de matériel sur la base de la demande réelle et prévue. Le système de planification peut calculer le calendrier de production principal (MPS, Master Production Schedule) ou la planification des besoins matière (MRP, Material Requirements Planning) à la demande, ou calculer les deux simultanément.  

-   Le calcul PDP est le calcul du calendrier de production principal basé sur la demande réelle et la prévision de la demande. Le calcul PDP est utilisé pour les articles finis disposant de prévisions ou d'une ligne document de vente. Ces articles sont appelés « articles PDP » et identifiés de façon dynamique au début du calcul.  
-   Le calcul MRP est le calcul des besoins matière basé sur la demande réelle de composantes et la prévision de la demande au niveau des composantes. Le calcul MRP n'est effectué que pour les articles qui ne sont pas des articles PDP. Le but du calcul MRP est de générer des plans formels en phases, par article, afin de fournir le bon article, au bon moment, au bon emplacement, et dans la bonne quantité.  

Les algorithmes de planification utilisés pour les calculs PDP et MRP sont identiques. Ces algorithmes ont trait à l'ajustement, à la réutilisation d'ordres de réapprovisionnement existants et à des messages d'action. Le processus du système de planification examine ce qui est ou sera nécessaire (demande) et ce qui est disponible ou attendu (approvisionnement). Lorsque ces quantités sont ajustées, [!INCLUDE[prod_short](includes/prod_short.md)] génère des messages d'action. Ces messages sont des suggestions de création d'un ordre, de modification d'un ordre (quantité ou date) ou d'annulation d'un ordre. Le terme « ordre » désigne les bons de commande, les ordres d'assemblage, les bons de production et les ordres de transfert.

Les liens créés par le moteur de planification entre la demande et son approvisionnement associé peuvent être suivis sur la page **Chaînage**. Pour plus d'informations, voir [Suivre les relations entre l'offre et la demande](production-how-track-demand-supply.md).   

Les résultats d'une planification appropriée dépendent de la configuration effectuée au niveau des fiches article, des nomenclatures d'assemblage et des gammes.  

## <a name="methods-for-generating-a-plan" />Méthodes de génération d'une planification

-   **Calculer planning régénératif** : cette fonction traite ou régénère la planification matières. Ce processus commence par supprimer toutes les commandes approvisionnement actuellement chargées. Tous les articles figurant dans la base de données son replanifiés.  
-   **Calculer planning par écart** : cette fonction traite une planification par écart. Dans une planification par écart, les articles sont considérés comme le résultat de deux types de modifications :  
    - **Modifications de demande/d'approvisionnement :** ces modifications sont celles apportées aux quantités sur des documents de vente, des prévisions de demande, des ordres d'assemblage, des bons de production ou des bons de commande. Une modification non planifiée du niveau d'inventaire est également considérée comme une modification de quantité.  
    - **Modifications de paramètres de planification :** ces modifications sont celles apportées au stock de sécurité, au point de commande, à la gamme, à la nomenclature et au calcul de la fréquence de vérification ou du délai de fabrication.  
-   **Extraire messages d'action :** cette fonction fait office d'outil de planification à court terme en émettant des messages d'action pour avertir l'utilisateur de toute modification introduite depuis le dernier calcul de la planification régénérative ou de la planification par écart.  

Avec chaque méthode planifiée, [!INCLUDE[prod_short](includes/prod_short.md)] génère des écritures de feuille basées sur l'hypothèse d'une capacité infinie. La capacité de l'atelier et de l'unité de production n'est pas prise en considération lors du développement de calendriers.  

> [!IMPORTANT]  
>  La fonction Calculer planning régénératif est le processus le plus couramment utilisé. Toutefois, les fonctions Calculer planning et Exécuter messages d'action permettent d'exécuter le processus Calculer planning par écart.  
>   
>  Vous pouvez exécuter la fonction Planification d'extraction de messages d'action entre une planification par écart et une planification régénérative pour visualiser instantanément l'impact de changements de calendrier, mais celle-ci n'est pas destinée à remplacer les processus de planification par écart ou de planification régénérative.  

## <a name="to-calculate-the-planning-worksheet" />Pour calculer la feuille planification
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuilles planification**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Calculer planning régénératif** pour ouvrir la page **Calculer planning**.  
3.  Sous le raccourci **Options**, renseignez les champs comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**PDP**|Sélectionnez cette option pour lancer le calcul d'un calendrier de production principal. Les articles avec des documents de vente ou des prévisions de demande ouverts sont pris en considération.|  
    |**MRP**|Sélectionnez pour lancer le calcul de la planification des besoins matière. Les articles avec des besoins dépendants sont pris en compte. En général, les PDP et les MRP sont exécutés simultanément. Pour les exécuter simultanément, le champ **Calcul PDP/MRP combiné** doit être sélectionné sur le raccourci **Planification** de la page **Configuration de la fabrication**.|  
    |**Date début**|Cette date permet d'évaluer la disponibilité de l'inventaire. Si la quantité disponible d'un article est inférieure au point de commande, le système programme en aval un ordre de réapprovisionnement à partir de cette date. Si la quantité disponible d'un article est inférieure à son stock de sécurité (à partir de la date début), le système programme en amont un ordre de réapprovisionnement dû à la date début de planification.|  
    |**Date fin**|Il s'agit de la date fin de l'horizon de planification. Ni la demande ni l'approvisionnement ne sont pris en compte au-delà de cette date. Si le regroupement pour un article s'étend au-delà de la date fin, l'horizon de planification effectif pour cet article équivaut à la date commande + le regroupement.<br /><br /> L'horizon de planification est la durée d'extension de la planification. Si l'horizon est trop court, les articles dont le temps de fabrication est plus long ne sont pas commandés à temps. Si l'horizon est trop long, trop de temps est consacré à l'examen et au traitement d'informations qui changent probablement avant que ce soit nécessaire. Vous pouvez définir un horizon de planification pour la production et un autre, plus long, pour les achats, même si ce n'est pas obligatoire. Un horizon de planification pour les achats et la production doit être défini pour couvrir le temps de fabrication cumulé des composants.|  
    |**Arrêter et afficher la première erreur**|Sélectionnez si vous souhaitez arrêter l'exécution de la planification dès qu'elle rencontre une erreur. Au même moment, un message affiche des informations sur la première erreur. S'il y a une erreur, seules les lignes planification traitées avant la détection de l'erreur apparaissent dans la feuille planification. Si vous ne sélectionnez pas ce champ, le traitement par lots **Calculer planning** se poursuivra jusqu'à son achèvement, ce qui signifie que des erreurs éventuelles ne l'interrompent pas. Si des erreurs existent, un message s'affichera un message après le traitement avec des informations sur le nombre d'articles affectés. La page **Journal des erreurs de planification** affiche ensuite des informations supplémentaires sur l'erreur et des liens vers les fiches article concernées.|  
    |**Utiliser prévisions**|Sélectionnez la prévision à inclure en tant que demande lors de l'exécution du traitement en lot de planification. La prévision par défaut est configurée sur le raccourci **Planification** sur la page **Configuration fabrication**.|  
    |**Exclure la prévision antérieure à**|Définissez la tâche de la prévision sélectionnée à inclure dans la planification exécutée en entrant une date avant laquelle une demande prévue n'est pas incluse, ce qui permet d'exclure les informations anciennes.|  
    |**Respecter les paramètres de planning pour les alertes d'exception**|Ce champ est sélectionné par défaut.<br /><br /> L'approvisionnement pour les lignes planification avec les alertes n'est normalement pas modifié en fonction des paramètres de planification. Au lieu de cela, le système de planification propose uniquement un approvisionnement pour couvrir la quantité de demande exacte. Cependant, vous pouvez définir certains paramètres de planification pour les lignes planification à respecter avec certaines alertes.<br /><br />|  

4.  Sur le raccourci **Article**, définissez des filtres pour exécuter la planification sur la base de l'article, de la désignation de l'article, ou du magasin.  
5.  Cliquez sur le bouton **OK**. Le traitement en lot est exécuté, puis la feuille planification est renseignée à l'aide des lignes planification.  

## <a name="to-perform-action-messages" />Pour traiter les messages d'action
1.  Sur la page **Feuille planification**, sélectionnez l'action **Traiter message d'action**.  
2.  Sur le raccourci **Options**, spécifiez comment créer des approvisionnements. Renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Ordre de fabrication**|Spécifiez comment vous souhaitez créer des ordres de fabrication. Vous pouvez le faire directement à partir des propositions de ligne planification. Vous pouvez créer des ordres de fabrication planifiés ou des ordres de fabrication planifiés fermes.|  
    |**Ordre d'assemblage**|Spécifiez comment vous souhaitez créer des ordres d'assemblage. Vous pouvez le faire directement à partir des propositions de ligne planification.|  
    |**Commande achat**|Spécifiez comment vous souhaitez créer des commandes achat. Vous pouvez le faire directement à partir des propositions de ligne planification.<br /><br /> Si vous avez choisi de copier les propositions ligne planification des bons de commande sur la feuille de réquisition, sélectionnez le modèle et le nom de la feuille.|  
    |**Ordre transfert**|Spécifiez comment vous souhaitez créer des ordres de transfert. Vous pouvez le faire directement à partir des propositions de ligne planification.<br /><br /> Si vous avez choisi de copier les propositions ligne planification des ordres de transfert sur la feuille de réquisition, sélectionnez le modèle et le nom de la feuille.|  
    |**Combiner les ordres de transfert**|Sélectionnez si vous souhaitez combiner des ordres de transfert.|  
    |**Arrêter et montrer la première erreur**|Sélectionnez si vous souhaitez que le traitement en lot **Traiter msg. action - Planification** s'arrête dès qu'il rencontre une erreur. Au même moment, un message affiche des informations sur la première erreur. S'il y a une erreur, seules les lignes planification traitées avant la détection de l'erreur créent des commandes approvisionnement.|  

3.  Sur le raccourci **Ligne planning**, vous pouvez définir des filtres pour limiter le traitement des messages d'action.  
4.  Cliquez sur le bouton **OK**.  

Le traitement en lot supprime les lignes dans la feuille planification après génération du message de tâche. Les autres lignes restent dans la feuille planification jusqu'à ce qu'elles soient acceptées à une date ultérieure ou supprimées. Vous pouvez également supprimer les lignes manuellement.  

## <a name="action-messages" />Messages d'action
Des messages d'action sont émis par le système de suivi des ordres quand l'équilibre est inaccessible dans le réseau d'ordres existant. Vous pouvez les consulter comme des suggestions pour traiter les modifications qui rétablissent l'équilibre entre l'approvisionnement et la demande.  

La génération de messages d'action se produit à un niveau à la fois, pour le code plus bas niveau de chaque article. Cela garantit que tous les articles faisant ou devant faire l'objet de modifications au niveau de l'approvisionnement ou de la demande sont pris en compte.  

Pour éviter les messages d'action brefs, superflus, ou sans importance, l'utilisateur peut mettre en place des seuils permettant de limiter la génération de messages d'action uniquement pour les modifications qui dépassent la quantité ou le nombre de jours spécifiés.  

Après avoir consulté les messages d'action et déterminé s'il convient d'accepter certains ou tous les changements suggérés, sélectionnez le champ **Accepter message d'action**, et vous êtes alors prêt à mettre à jour les plannings en conséquence.  

> [!NOTE]  
>  Un message d'action est une suggestion de création d'ordre, d'annulation d'ordre ou de modification de la quantité ou de la date d'un ordre. Un ordre peut être un bon de commande, un ordre de transfert ou un bon de production.  

En réponse à tout déséquilibre entre l'approvisionnement et la demande, les messages d'action suivants sont générés.  

|Message d'action|Description|  
|--------------------|---------------------------------------|  
|**Créer**|Si une demande ne peut pas être satisfaite par des messages d'action suggérant de **Modifier qté**, de **Replanifier** ou de **Replanifier et modifier qté** des ordres existants, le message d'action **Nouveau** est généré, suggérant un nouvel ordre. En outre, un message d'action **Nouveau** est généré s'il n'y a pas de commandes approvisionnement existantes dans le regroupement de l'article en question. Ce paramètre détermine le nombre de périodes en aval et en amont dans le profil de disponibilité lors de la recherche d'un ordre à replanifier.|  
|**Modifier la quantité**|Quand une demande suivie pour des commandes d'approvisionnement fait l'objet d'une modification de quantité, le message d'action **Changer qté** est généré, indiquant que l'approvisionnement en question doit être modifié par rapport à la modification de la demande. En cas de nouvelle demande, [!INCLUDE[prod_short](includes/prod_short.md)] recherche la commande approvisionnement non réservée la plus proche dans le regroupement et émet un message de changement d'action pour cette commande.|  
|**Replanifier**|Quand une commande approvisionnement ou une demande fait l'objet d'une modification de date entraînant un déséquilibre dans le réseau d'ordres, le message d'action **Replanifier** est généré. S'il y a une relation de un à un entre la demande et l'approvisionnement, un message d'action est généré, suggérant de déplacer la commande d'approvisionnement en conséquence. Si la commande d'approvisionnement couvre la demande liée à plusieurs documents de vente, la commande d'approvisionnement est reprogrammée comme égale à celle à la date de la première demande.|  
|**Replanifier & changer qté**|Si tant les dates que les quantités d'un ordre ont été modifiées, vous devez modifier les plannings en relation avec les deux circonstances. Le système de génération de messages d'action regroupe les deux actions dans un seul message, **Replan. et changer qté**, pour garantir le retour à l'équilibre du réseau d'ordres.|  
|**Annuler**|Si une demande qui a été couverte sur la base d'une relation ordre pour ordre est supprimée, un message d'action est généré pour annuler la commande d'approvisionnement qui y est liée. Si la relation n'est pas une relation ordre pour ordre, un message d'action est généré pour modifier l'ordre afin de réduire l'approvisionnement. Si, en vertu d'autres facteurs, tels que des ajustements de stock, une commande d'approvisionnement n'est pas requise au moment de la génération des messages d'action par l'utilisateur, [!INCLUDE[prod_short](includes/prod_short.md)] suggère un message d'action **Annuler** dans la feuille de calcul.|  

## <a name="see-also" />Voir aussi
[Planification](production-planning.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
