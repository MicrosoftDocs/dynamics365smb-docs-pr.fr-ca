---
title: "Détails de conception - Flux d'entrepôt internes | Microsoft Docs"
description: "Circulation des articles entre les zones dans les centres d'une compagnie lors du prélèvement des composantes, du rangement des articles finis pour les ordres d'assemblage ou les bons de production et les mouvements ad-hoc, tels que les réapprovisionnements de zone, sans relation avec les documents sources."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: 957c8889d943ed412af7555271897b52c0759969
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="design-details-internal-warehouse-flows"></a>Détails de conception : flux d'entrepôt internes
Circulation des articles entre les zones dans les centres d'une compagnie lors du prélèvement des composantes, du rangement des articles finis pour les ordres d'assemblage ou les bons de production et les mouvements ad-hoc, tels que les réapprovisionnements de zone, sans relation avec les documents sources. La portée et la nature des activités impliquées varient entre l'entreposage de base et l'entreposage avancé.  

 Certains flux internes chevauchent des flux entrants ou sortants. Une partie de cette superposition est illustrée aux étapes 4 et 5 dans les schémas graphiques des flux enlogement et désenlogement avancés respectivement. Pour plus d'informations, reportez\-vous à [Détails de conception : flux d'enlogement](design-details-outbound-warehouse-flow.md).  

## <a name="internal-flows-in-basic-warehousing"></a>Flux internes dans l'entreposage de base  
 Dans une configuration entrepôt de base, la circulation des articles entre les zones dans les centres de la compagnie lors du prélèvement des composantes, du rangement des articles finis pour les bons de production ou les ordres d'assemblage et les mouvements ad-hoc, tels que les réapprovisionnements de zone, sans relation avec les documents sources.  

### <a name="flows-to-and-from-production"></a>Flux entrants et sortants de la production  
 La principale intégration entre les bons de production et les activités d'entrepôt de base est représentée par la capacité à prélever des composantes de production à l'aide de la fenêtre **Prélèvement inventaire** ou **Mouvement d'inventaire**.  

> [!NOTE]  
>  Dans la fenêtre **Prélèvement inventaire**, la consommation de composantes est reportée lors du report du prélèvement. À l'aide de la fenêtre **Mouvement d'inventaire**, seuls les ajustements de zone sont enregistrés, aucun report dans la grand livre article n'a lieu.  

 En plus de la gestion de composantes, l'intégration est représentée par la capacité de ranger les articles fabriqués à l'aide de la fenêtre **Rangement inventaire**.  

 Les champs **Code de zone avant production**, **Code de zone post-production**, et **Code de zone d'atelier ouvert** de la fiche emplacement ou des fiches unité de production/atelier définissent les flux par défaut depuis ou vers les zones de production.  

 Pour plus d'informations sur la manière dont la consommation de composantes est purgée des zones avant production ou des zones d'atelier ouvert, reportez-vous à la section « Purge des composantes de production dans l'entrepôt » de cette rubrique.  

### <a name="flows-to-and-from-assembly"></a>Flux entrants et sortants de l'assemblage  
 La principale intégration entre les ordres d'assemblage et les activités d'entrepôt de base est représentée par la capacité à déplacer les composantes d'assemblage vers la zone d'assemblage.  

 Lorsqu'aucune fonctionnalité entrepôt spécifique n'existe pour le rangement des éléments d'assemblage, le code de zone sur l'ordre d'assemblage peut être défini sur une zone de rangement par défaut. Le report de l'ordre d'assemblage fonctionne alors comme le report d'un rangement. L'activité entrepôt pour déplacer des éléments d'assemblage dans l'entrepôt peut être gérée dans la fenêtre **Mouvement interne**, sans rapport avec l'ordre d'assemblage.  

 Les flux d'assemblage suivants existent.  

|Flux de travail|Description|  
|----------|---------------------------------------|  
|Assembler pour stock|Les composantes sont nécessaires sur un ordre d'assemblage dans lequel la production est stockée dans l'entrepôt.<br /><br /> Ce flux d'entrepôt est géré dans la fenêtre **Mouvement d'inventaire**. Une ligne prélèvement spécifie où prélever les composantes. Une ligne emplacement spécifie où placer les composantes.|  
|Assembler pour commande|Les composantes sont nécessaires sur un ordre d'assemblage qui est lié à un document de vente livré lors de l'assemblage de l'article vendu.|  

> [!NOTE]  
>  Si les articles sont assemblés pour commande, le prélèvement inventaire du document de vente lié déclenche un mouvement d'inventaire pour toutes les composantes d'assemblage impliquées, et pas uniquement pour l'article vendu, comme lors de la livraison d'articles de l'inventaire.  

 Les champs **Code de zone vers assemblage**, **Code de zone depuis assemblage** et **Code de zone livr. ass. pr comm.** de la fiche emplacement définissent les flux par défaut depuis et vers les champs d'assemblage.  

> [!NOTE]  
>  Le champ **Code de zone livr. ass. pr comm.** fonctionne comme une zone après assemblage dans les scénarios assembler pour commande.  

### <a name="ad-hoc-movements"></a>Mouvements ad hoc  
 Dans l'entreposage de base, un mouvement d'articles d'une zone à l'autre sans relation avec les documents sources est effectuée dans la fenêtre **Mouvement interne** qui fonctionne conjointement avec la fenêtre **Mouvement d'inventaire**.  

 Il existe un autre moyen de déplacer des articles ad hoc entre les zones : il suffit de reporter les écritures positives dans le champ **Nouveau code de zone** de la fenêtre **Journal reclassement article**.  

## <a name="internal-flows-in-advanced-warehousing"></a>Flux internes dans l'entreposage avancé  
 Dans les configurations d'entrepôt avancées, la circulation des articles entre les zones dans les centres de la compagnie lors du prélèvement des composantes, du rangement des articles finis pour les bons de production et du prélèvement des composantes pour les ordres d'assemblage. En outre, les flux internes se produisent en tant que mouvements ad-hoc, tels que les réapprovisionnements de zone, sans relation avec les documents sources.  

### <a name="flows-to-and-from-production"></a>Flux entrants et sortants de la production  
 La principale intégration entre les bons de production et les activités d'entrepôt avancées est représentée par la capacité à prélever des composantes de production, dans la fenêtre **Prélèvement entrepôt** et dans la fenêtre **Feuille prélèvement**, et par la capacité à ranger des articles produits à l'aide de la fenêtre **Rangement interne entrepôt**.  

 Un autre point d'intégration dans la production est fourni via la fenêtre **Mouvement entrepôt**, ainsi que la fenêtre Feuille mouvement, ce qui vous permet de placer des composantes et de prendre des articles fabriqués pour des bons de production libérés.  

 Les champs **Code de zone avant production**, **Code de zone post-production**, et **Code de zone d'atelier ouvert** de la fiche emplacement ou des fiches unité de production/atelier définissent les flux par défaut depuis ou vers les zones de production.  

 Pour plus d'informations sur la manière dont la consommation de composantes est purgée des zones avant production ou des zones d'atelier ouvert, reportez-vous à la section « Purge des composantes de production dans l'entrepôt » de cette rubrique.  

### <a name="flows-to-and-from-assembly"></a>Flux entrants et sortants de l'assemblage  
 La principale intégration entre les ordres d'assemblage et les activités d'entrepôt avancées est représentée par la capacité à prélever des composantes d'assemblage, aussi bien à l'aide de la fenêtre **Prélèvement entrepôt** que de la fenêtre **Feuille prélèvement**. Cette fonctionnalité est identique au prélèvement des composantes pour les bons de production.  

 Lorsqu'aucune fonctionnalité entrepôt spécifique n'existe pour le rangement des éléments d'assemblage, le code de zone sur l'ordre d'assemblage peut être défini sur une zone de rangement par défaut. Le report de l'ordre d'assemblage fonctionne alors comme le report d'un rangement. L'activité entrepôt pour déplacer des éléments d'assemblage dans l'entrepôt peut être gérée dans la fenêtre **Feuille mouvement** ou la fenêtre **Rangement interne entrepôt**, sans rapport avec l'ordre d'assemblage.  

> [!NOTE]  
>  Si les articles sont assemblés pour commande, la livraison entrepôt du document de vente lié déclenche un prélèvement entrepôt de toutes les composantes d'assemblage impliquées, et non uniquement pour l'article vendu, comme lors de la livraison d'articles en inventaire.  

 Les champs **Code de zone vers assemblage** et **Code de zone depuis assemblage** de la fiche emplacement définissent les flux par défaut depuis et vers les zones d'assemblage.  

### <a name="ad-hoc-movements"></a>Mouvements ad hoc  
 Dans l'entreposage avancé, un mouvement d'articles d'une zone à l'autre sans relation avec les documents sources est géré dans la fenêtre **Feuille mouvement** et enregistré dans la fenêtre Mouvement entrepôt.  

## <a name="flushing-production-components-in-the-warehouse"></a>Purge des composantes de production dans l'entrepôt  
 Si cela est configuré dans la fiche article, les composantes prélevées avec des prélèvements entrepôt sont reportées comme étant consommées par le bon de production lorsque le prélèvement entrepôt est enregistré. En utilisant la méthode **Prélèvement + Aval** et la méthode de consommation **Prélèvement + Amont**, l'enregistrement de prélèvement déclenche le report des consommations associées lorsque la première opération commence ou lorsque la dernière opération finit, respectivement.  

 Considérez le scénario suivant basé sur la base de données de démonstration [!INCLUDE[d365fin](includes/d365fin_md.md)], emplacement BLANC.  

 Il existe un ordre de fabrication pour 15 pièces de l'article LS-100. Certains articles sur la liste des composantes doivent être purgés manuellement dans un journal consommation et d'autres articles de la liste peuvent être prélevés et purgés automatiquement à l'aide de la méthode consommation **Prélèvement + Amont**.  

> [!NOTE]  
>  **Prélèvement + Aval** ne fonctionne que si la deuxième opération ligne itinéraire de production utilise le code lien itinéraire. Le lancement d'un bon de production planifié entame la purge en aval des composantes définies sur **Prélèvement + Aval**. Toutefois, la purge ne peut pas avoir lieu tant que le prélèvement des composantes n'est pas enregistré, ce qui à nouveau ne peut avoir lieu que lorsque la commande est libérée.  

 Les étapes suivantes décrivent les actions impliquées par divers utilisateurs et la réponse associée :  

1.  Le chef atelier lance l'ordre de fabrication. Les articles utilisant la méthode consommation **Aval** et aucun code lien itinéraire sont déduits de la zone d'atelier ouvert.  
2.  Le chef atelier choisit le bouton **Créer prélèvement entrepôt** sur l'ordre de fabrication. Un document prélèvement entrepôt est créé pour les articles avec les méthodes de consommation **Manuelle**, **Prélèvement + Amont** et **Prélèvement + Aval**. Ces articles sont placés dans la zone avant production.  
3.  Le gestionnaire d'entrepôt affecte les prélèvements à un magasinier.  
4.  L'employé d'entrepôt prélève les articles dans les zones appropriées et les place dans la zone avant production ou dans la zone spécifiée sur le prélèvement entrepôt, qui peut être une zone d'atelier ou d'unité de production.  
5.  L'employé d'entrepôt enregistre le prélèvement. La quantité est soustraite des zones prélèvement et ajoutée à la zone consommation. Le champ **Qté prélevée** sur la liste des composantes de tous les articles prélevés est mis à jour.  

    > [!NOTE]  
    >  Seule la quantité qui est prélevée peut être consommée.  

6.  L'opérateur indique au gestionnaire de production que les articles finis sont terminés.  
7.  Le responsable d'atelier utilise le journal consommation ou le journal production pour reporter la consommation de composantes qui utilisent la méthode consommation **Manuel** ou les méthodes consommation **Aval** ou **Prélèvement + Aval** avec des codes lien itinéraire.  
8.  Le gestionnaire de production reporte la production du bon de production et modifie l'état en **Terminé**. La quantité de composantes qui utilisent la méthode consommation **Amont** est déduite de la zone d'atelier ouvert, et la quantité d'articles composantes qui utilisent la méthode de consommation **Prélèvement + Amont** est déduite de la zone avant production.  

 La figure ci-après indique la date à laquelle le champ **Code de zone** de la liste des composantes est renseigné en fonction de la configuration de votre emplacement ou unité de production/atelier.  

 ![Organigramme Flux d'emplacement](media/binflow.png "BinFlow")  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)

