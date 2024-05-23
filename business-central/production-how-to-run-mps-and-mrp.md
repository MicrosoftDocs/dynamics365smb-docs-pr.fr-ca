---
title: Exécuter une planification complète et un calcul PDP ou MRP
description: 'Le système de planification peut calculer le calendrier de production principal (MPS, Master Production Schedule) ou la planification des besoins matière (MRP, Material Requirements Planning) à la demande, ou les deux simultanément.'
author: brentholtorf
ms.topic: conceptual
ms.search.form: '99000852, 99000860'
ms.date: 01/24/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Exécuter une planification complète et un calcul PDP ou MRP

Les termes « exécution de la feuille planification » ou « exécution d'un calcul MRP » font référence au calcul du calendrier de production principal et aux besoins matière. Le calcul est basé sur la demande réelle et prévue. Le système de planification peut calculer le calendrier de production principal (MPS, Master Production Schedule) ou la planification des besoins matière (MRP, Material Requirements Planning) à la demande, ou les deux simultanément.  

- Le calcul PDP est le calcul du calendrier de production principal basé sur la demande réelle et la prévision de la demande. Le calcul PDP est utilisé pour les articles finis disposant de prévisions ou d'une ligne document de vente. Ces articles sont appelés « articles PDP » et identifiés de façon dynamique au début du calcul.  
- Le calcul MRP est le calcul des besoins matière basé sur la demande réelle de composantes et la prévision de la demande au niveau des composantes. Le calcul MRP n'est effectué que pour les articles qui ne sont pas des articles PDP. Le but du calcul MRP est de générer des plans formels en phases, par article, afin de fournir le bon article, au bon moment, au bon endroit et dans la bonne quantité.  

Les algorithmes de planification utilisés pour les calculs PDP et MRP sont identiques. Ces algorithmes ont trait à l’ajustement, à la réutilisation d’ordres de réapprovisionnement existant et à des messages d’action. Le processus du système de planification examine ce qui est ou sera nécessaire (demande) et ce qui est disponible ou attendu (approvisionnement). Lorsque vous ajustez ces quantités, [!INCLUDE[prod_short](includes/prod_short.md)] génère des messages d’action. Ces messages sont des suggestions de création d’un ordre, de modification d’un ordre (quantité ou date) ou d’annulation d’un ordre. Le terme « ordre » désigne les bons de commande, les ordres d'assemblage, les bons de production et les ordres de transfert.

Vous pouvez suivre les liens créés par la planification entre la demande et l'approvisionnement sur la page **Chaînage**. Pour plus d'informations, voir [Suivre les relations entre l'offre et la demande](production-how-track-demand-supply.md).

Les résultats d'une planification appropriée dépendent de la configuration effectuée au niveau des fiches article, des nomenclatures d'assemblage et des gammes.  

## Méthodes de génération d’une planification  

- **Calculer planning régénératif** : traitement ou re-génération de la planification matières. Ce processus commence par supprimer toutes les commandes approvisionnement actuellement chargées. Tous les articles figurant dans la base de données son replanifiés.  
- **Calculer planning par écart** : traite une planification par écart. Dans une planification par écart, les articles sont considérés comme le résultat de deux types de modifications :  
   - **Modifications de demande/d’approvisionnement :** ces modifications sont celles apportées aux quantités sur des documents de vente, des prévisions de demande, des ordres d’assemblage, des bons de production ou des bons de commande. Une modification non planifiée du niveau d'inventaire est également considérée comme une modification de quantité.  
   - **Modifications de paramètres de planification :** ces modifications sont celles apportées au stock de sécurité, au point de commande, à l'itinéraire, à la nomenclature et au calcul de la fréquence de vérification ou du délai de fabrication.  
- **Extraire messages d’action :** fait office d’outil de planification à court terme en émettant des messages d’action pour avertir l’utilisateur des modifications introduites depuis le dernier calcul de la planification régénérative ou de la planification par écart.  

Avec chaque méthode planifiée, [!INCLUDE[prod_short](includes/prod_short.md)] génère des écritures de feuille basées sur l'hypothèse d'une capacité infinie. La capacité de l'atelier et de l'unité de production n’est pas prise en considération lors du développement de calendriers.  

> [!IMPORTANT]  
> Calculer planning régénératif est le processus le plus couramment utilisé. Toutefois, Calculer planning et Exécuter messages d’action permettent d’exécuter le processus Calculer planning par écart.  
>
> Vous pouvez exécuter le plan Obtenir les messages d’action entre les exécutions de planification des modifications régénératives et nettes pour obtenir une vue immédiate de l’effet des modifications de planification. Cependant, il n’est pas destiné à remplacer les processus complets de planification de changement régénératif ou net.  

## Pour calculer la feuille planification
  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuilles planification**, puis sélectionnez le lien associé.  
2. Choisissez l'action **Calculer planning régénératif** pour ouvrir la page **Calculer planning**.  
3. Sous le raccourci **Options**, renseignez les champs comme indiqué dans le tableau ci-dessous.  

    |Champ|Désignation|  
    |---------------------------------|---------------------------------------|  
    |**PDP**|Calculez un calendrier de production principal. Les articles avec des documents de vente ou des prévisions de demande ouverts sont pris en considération. <br/>Si d’autres demandes, par exemple un stock de sécurité, un point de commande ou des lignes de composantes de production ouvertes, existent également pour de tels articles, ces demandes sont incluses dans le calcul MPS pour garantir que le système de planification traite le profil d'inventaire complet.  |  
    |**MRP**|Calculer la planification des besoins matière. Les articles avec des besoins dépendants sont pris en compte. En général, les PDP et les MRP sont exécutés simultanément. Pour exécuter PDP et MRP simultanément, sur la page **Configuration de la fabrication** sur le raccourci **Planification**, cliquez sur le champ **Calcul PDP/MRP combiné**.|  
    |**Date début**|Évaluer la disponibilité de l'inventaire. Si la quantité disponible d'un article est inférieure au point de commande, le système programme en aval un ordre de réapprovisionnement à partir de cette date. Si la quantité disponible d'un article est inférieure à son stock de sécurité (à partir de la date début), le système programme en amont un ordre de réapprovisionnement dû à la date début de planification.|  
    |**Date de fin**|La date fin de l’horizon de planification. Ni la demande ni l’approvisionnement ne sont pris en compte au-delà de cette date. Si le regroupement pour un article s’étend au-delà de la date fin, l’horizon de planification effectif pour cet article équivaut à la date commande et le regroupement.<br/><br/> L'horizon de planification est la durée d'extension de la planification. Si l’horizon est trop court, les articles dont le temps de fabrication est plus long ne sont pas commandés à temps. Si l’horizon est trop long, trop de temps est consacré à l’examen et au traitement d’informations qui changent probablement avant que ce soit nécessaire. Vous pouvez définir un horizon de planification pour la production et un autre, plus long, pour les achats, même si ce n’est pas obligatoire. Un horizon de planification pour les achats et la production doit être défini pour couvrir le temps de fabrication total des composantes.|  
    |**Arrêter et afficher la première erreur**|Sélectionnez cette option si vous souhaitez arrêter l’exécution de la planification dès qu’elle rencontre une erreur. Un message affiche des informations sur l’erreur. S’il y a une erreur, seules les lignes planification traitées avant la détection de l’erreur apparaissent dans la feuille planification. Si vous ne sélectionnez pas ce champ, le traitement en lot **Calculer planning** se poursuit jusqu’à ce qu’il soit terminé. Les erreurs éventuelles n’interrompent pas le traitement en lot. Si des erreurs existent, un message s’affiche un message après le traitement avec des informations sur le nombre d’articles affectés. La page **Journal des erreurs de planification** affiche ensuite des informations supplémentaires sur l'erreur et des liens vers les fiches article concernées.|  
    |**Utiliser la prévision**|Sélectionnez la prévision à inclure en tant que demande lors de l’exécution du traitement en lot de planification. La prévision par défaut est configurée sur le raccourci **Planification** sur la page **Configuration fabrication**.|  
    |**Exclure la prévision antérieure à**|Saisissez la date qui déterminera le début de la période des prévisions sélectionnées prise en compte dans la planification.|  
    |**Respecter les paramètres de planification pour les avertissements d'exception**|Ce champ est sélectionné par défaut.<br/><br/> L'approvisionnement pour les lignes planification avec les alertes n'est normalement pas modifié en fonction des paramètres de planification. Au lieu de cela, le système de planification propose uniquement un approvisionnement pour couvrir la quantité de demande exacte. Cependant, vous pouvez définir certains paramètres de planification pour les lignes planification à respecter avec certaines alertes.<br/><br/>|  

4. Sur le raccourci **Article**, définissez des filtres pour exécuter la planification sur la base de l’article, de la description de l’article ou de l'emplacement.  
5. Cliquez sur le bouton **OK**. Le traitement en lot est exécuté et des lignes planification sont ajoutées à la feuille planification.  

## Pour traiter les messages d'action
  
1. Sur la page **Feuille planification**, sélectionnez l'action **Traiter message d'action**.  
2. Sur le raccourci **Options**, spécifiez comment créer des approvisionnements. Renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Désignation|  
    |---------------------------------|---------------------------------------|  
    |**Ordre de fabrication**|Spécifiez comment créer des bons de production. Vous pouvez le faire directement à partir des propositions de ligne planification. Vous pouvez créer des ordres de fabrication planifiés ou des ordres de fabrication planifiés fermes.|  
    |**Ordre d’assemblage**|Spécifiez comment créer des ordres d’assemblage. Vous pouvez le faire directement à partir des propositions de ligne planification.|  
    |**Commande achat**|Spécifiez comment créer des bons de commande. Vous pouvez le faire directement à partir des propositions de ligne planification.<br/><br/> Si vous avez choisi de copier les propositions ligne planification des bons de commande sur la feuille de réquisition, sélectionnez le modèle et le nom de la feuille.|  
    |**Ordre transfert**|Spécifiez comment créer des ordres de transfert. Vous pouvez le faire directement à partir des propositions de ligne planification.<br/><br/> Si vous avez choisi de copier les propositions ligne planification des ordres de transfert sur la feuille de réquisition, sélectionnez le modèle et le nom de la feuille.|  
    |**Combiner les ordres de transfert**|Sélectionnez si vous souhaitez combiner des ordres de transfert.|  
    |**Arrêter et afficher la première erreur**|Sélectionnez cette option si vous souhaitez que le traitement en lot **Traiter msg. action – Planification** s’arrête dès qu’il rencontre une erreur. Un message affiche des informations sur l’erreur. S’il y a une erreur, seules les lignes planification traitées avant la détection de l’erreur créent des commandes d’approvisionnement.|  

3. Sur le raccourci **Ligne planning**, vous pouvez définir des filtres pour limiter le traitement des messages d'action.  
4. Cliquez sur le bouton **OK**.  

Le traitement en lot supprime les lignes dans la feuille planification après génération du message de tâche. Les autres lignes restent dans la feuille planification jusqu'à ce qu'elles soient acceptées à une date ultérieure ou supprimées. Vous pouvez également supprimer les lignes manuellement.  

## Messages d’action
  
Des messages d'action sont émis par le système de suivi des ordres quand l'équilibre est inaccessible dans le réseau d'ordres existant. Vous pouvez consulter les messages comme des suggestions pour traiter les modifications qui rétablissent l’équilibre entre l’approvisionnement et la demande.  

La génération de messages d'action se produit à un niveau à la fois, pour le code plus bas niveau de chaque article. Cela garantit que tous les articles faisant ou devant faire l'objet de modifications au niveau de l'approvisionnement ou de la demande sont pris en compte.  

Pour éviter les messages d’action brefs, inutiles, ou sans importance, vous pouvez mettre en place des seuils permettant de limiter la génération de messages d’action uniquement pour les modifications qui dépassent la quantité ou le nombre de jours spécifiés.  

Après avoir vérifié les messages d’action et déterminé s’il convient d’accepter certains ou tous les changements suggérés, sélectionnez le champ **Accepter message d’action**. Ensuite, mettez à jour les calendriers en conséquence.  

> [!NOTE]  
> Un message d'action est une suggestion de création d'ordre, d'annulation d'ordre ou de modification de la quantité ou de la date d'un ordre. Un ordre peut être un bon de commande, un ordre de transfert ou un bon de production.  

En réponse à tout déséquilibre entre l'approvisionnement et la demande, les messages d'action suivants sont générés.  

|Message d’action|Désignation|  
|--------------------|---------------------------------------|  
|**Créer**|Si une demande ne peut pas être satisfaite par des messages d’action suggérant de **Modifier qté**, de **Replanifier** ou de **Replanifier et modifier qté** des ordres existants, le message d’action **Nouveau** est généré pour suggérer un nouvel ordre. Le message **Nouveau** est aussi généré s’il n’y a pas de commandes d’approvisionnement dans le cycle de réapprovisionnement de l’article. Cette option détermine le nombre de périodes en aval et en amont dans le profil de disponibilité lors de la recherche d’un ordre à replanifier.|  
|**Modifier la quantité**|Quand la quantité change pour une demande suivie pour des commandes d'approvisionnement, le message d'action **Modifier qté** est généré. Ce message indiquant que l'approvisionnement en question doit être modifié par rapport à la modification de la demande. En cas de nouvelle demande, [!INCLUDE[prod_short](includes/prod_short.md)] recherche la commande approvisionnement non réservée la plus proche dans le regroupement et émet un message de changement d'action pour cette commande.|  
|**Replanifier**|Quand une date change pour une commande approvisionnement ou une demande entraîne un déséquilibre dans le réseau d’ordres, le message d’action **Replanifier** est généré. S’il y a une relation de un à un entre la demande et l’approvisionnement, un message d’action est généré, suggérant de déplacer la commande d’approvisionnement. Si la commande d'approvisionnement couvre la demande liée à plusieurs documents de vente, la commande d'approvisionnement est reprogrammée comme égale à celle à la date de la première demande.|  
|**Replanifier & changer qté**|Si tant les dates que les quantités d’un ordre changent, vous devez modifier les plannings en relation avec les deux. Le système de génération de messages d'action regroupe les deux actions dans un seul message, **Replan. et changer qté**, pour garantir le retour à l'équilibre du réseau d'ordres.|  
|**Annuler**|Si une demande couverte sur la base d’une relation ordre pour ordre est supprimée, un message d’action est généré pour annuler la commande d’approvisionnement qui y est liée. Si la relation n’est pas une relation ordre pour ordre, un message d’action est généré pour modifier l’ordre afin de réduire l’approvisionnement. Si, en vertu d’autres facteurs, tels que des ajustements d'inventaire, une commande d’approvisionnement n’est pas requise au moment où vous générez des messages d’action, [!INCLUDE[prod_short](includes/prod_short.md)] suggère un message d’action **Annuler** dans la feuille de calcul.|  

## Voir aussi .  

[Planification](production-planning.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Fabrication](production-manage-manufacturing.md)    
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
