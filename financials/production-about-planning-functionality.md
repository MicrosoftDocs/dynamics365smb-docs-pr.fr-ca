---
title: "À propos de la fonctionnalité Planification | Microsoft Docs"
description: "Le système de planification prend en compte toutes les données d'offre et de demande, ajuste les résultats et génère des suggestions pour l'équilibrage de l'offre en fonction de la demande."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: a00f88aaf70464c8911d59b829b08dda900dc474
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="about-planning-functionality"></a>À propos de la fonctionnalité Planification
Le système de planification prend en compte toutes les données d'offre et de demande, ajuste les résultats et génère des suggestions pour l'équilibrage de l'offre en fonction de la demande.  

Pour plus d'informations, voir [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md).  

> [!NOTE]  
> Pour tous les champs mentionnés dans cette rubrique, lisez l'info-bulles pour comprendre leur fonction. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="demand-and-supply"></a>Offre et demande  
La planification comporte deux volets : l'offre et la demande. Ces derniers doivent être équilibrés pour garantir que la demande soit satisfaite rapidement et efficacement.  

- Le mot demande désigne tout sorte de besoin brut, tel qu'un document de vente, une commande service, un besoin composante d'un ordre d'assemblage ou de fabrication, un transfert sortant, une commande permanente ou une prévision. En outre, le programme autorise d'autres types techniques de demande - tels qu'un bon de production ou un bon de commande négatif, un inventaire négatif et un retour achat.  
- Le mot offre désigne toute sorte de réapprovisionnement telle qu'un inventaire, un bon de commande, un ordre d'assemblage, un bon de production ou un transfert entrant. Par conséquent, il peut y avoir un document de vente ou une commande service négative, un besoin de composante ou un retour vente négatif – tous représentant aussi l'offre d'une certaine façon.  

Un autre objectif du système de planification est de garantir que l'inventaire n'augmente pas inutilement. En cas de baisse de la demande, le système de planification suggère de reporter, de réduire ou d'annuler des ordres de réapprovisionnement existants.  

## <a name="planning-calculation"></a>Calcul de planification  
Le système de planification est guidé par la demande prévue et réelle des clients, ainsi que par les paramètres de réapprovisionnement d'inventaire. L'exécution du calcul de planification a pour effet que le programme suggère des mesures spécifiques (messages d'action) à prendre concernant le réapprovisionnement possible auprès de fournisseurs, les transferts entre entrepôts ou la production. S'il y a déjà des ordres de réapprovisionnement, les mesures suggérées peuvent être d'augmenter ou d'accélérer les commandes pour répondre à l'évolution de la demande.  

La base de la routine de planification réside dans le calcul gros/net. Les besoins nets déterminent les libérations de commandes planifiées, qui sont programmées sur la base des informations d'itinéraire (articles fabriqués) ou du délai de réapprovisionnement de la fiche article (articles achetés). Les quantités de libération de commandes planifiées sont basées sur le calcul de planification et affectées par les paramètres définis sur les fiches article individuelles.  

## <a name="planning-with-manual-transfer-orders"></a>Planification à l'aide d'ordres de transfert manuels
Comme l'indique le champ **Système réappro** d'une fiche point de stock, le système de planification peut être configuré pour créer des ordres de transfert destinés à équilibrer l'offre et la demande dans tous les magasins.  

Outre ce type d'ordre de transfert automatique, vous devrez parfois effectuer un déplacement général des quantités en inventaire vers un autre emplacement, quelle que soit la demande existante. Vous créez pour cela un ordre de transfert manuel correspondant à la quantité à déplacer. Pour être sûr que le système de planification ne tente pas de manipuler cet ordre de transfert manuel, vous devez paramétrer le champ **Flexibilité planification** des lignes transfert sur Aucune.  

À l'inverse, si vous souhaitez que le système de planification ajuste les quantités de l'ordre de transfert et les dates en fonction de la demande existante, vous devez paramétrer le champ **Flexibilité planification** sur la valeur Illimitée.

## <a name="planning-parameters"></a>Paramètres de planification  
Les paramètres de planification déterminent le moment, la quantité et la méthode de réapprovisionnement en fonction des divers paramètres de la fiche article (ou unité de stock) et de la configuration de la fabrication.  

Les paramètres de planification suivants existent pour l'article ou la fiche unité de stock :  

-   Période tampon  
-   Quantité tampon  
-   Politique réapprovisionnement  
-   Point de réapprovisionnement
-   Stock maximum  
-   Niveau de dépassement de capacité  
-   Plage de temps  
-   Période de cumul de lot  
-   Période de replanification  
-   Quantité de réappro.  
-   Délai de sécurité  
-   Quantité de stocks de sécurité  
-   Stratégie d'assemblage  
-   Mode de lancement  

Les modificateurs d'ordre suivants existent pour l'article ou la fiche unité de stock :  

-   Quantité minimum commande  
-   Quantité maximum commande  
-   Commande multiple  

Les champs de paramètres de planning figurant dans la fenêtre **Paramètres production** sont les suivants :  

-   Code dern. niv. nomenc. dynam.  
-   Prévision actuelle production  
-   Prévision sur magasin  
-   Délai de sécurité par défaut  
-   Niveau de dépassement de capacité vide  
-   Calcul PDP/PBM combinés   
-   Mag. composant par déf.  
-   Période tampon par défaut  
-   Quantité tampon par défaut  

Pour plus d'informations, voir [Détails de conception : paramètres de planification](design-details-planning-parameters.md)  

## <a name="other-important-planning-fields"></a>Autres champs de planification importants
### <a name="planning-flexibility"></a>Flexibilité de planification
Dans la plupart des commandes d'approvisionnement, comme les bons de production, vous pouvez sélectionner **Illimité** ou **Aucun** dans le champ **Flexibilité planification** des lignes.

Cela spécifie si l'approvisionnement représenté par la ligne O.F. est pris en compte par le système de planification lors du calcul des messages d'action.
Si le champ affiche l'option **Illimitée**, le système de planification inclut la ligne lors du calcul des messages d'action. S'il est paramétré sur **Aucune**, la ligne est ferme et définitive, et le système de planification n'inclut pas la ligne dans le calcul des messages d'action.

### <a name="warning"></a>Alerte
Le champ d'informations **Avertissement** dans la fenêtre **Feuille planification** vous informe lorsqu'une ligne planification est créée pour une situation inhabituelle avec un texte. L'utilisateur peut cliquer sur ce texte pour lire des informations supplémentaires. Les types d'alerte suivants existent :

- Urgence
- Exception
- Attention
- Urgence

L'avertissement Urgence est affiché dans deux situations :

- L'inventaire est négatif à la date début de la planification.
- Des événements d'offre ou de demande rétroactifs existent.

Si l'inventaire d'un article est négatif à la date début de la planification, le système de planification suggère une commande d'approvisionnement d'urgence afin que la quantité négative arrive à la date début de la planification. Le texte d'avertissement indique la date début et la quantité de la commande d'urgence.

Les lignes document avec une date d'échéance antérieure à la date début de la planification sont consolidées dans une commande d'approvisionnement d'urgence pour que l'article arrive à la date début de la planification.

### <a name="exception"></a>Exception
L'avertissement Exception s'affiche si le stock disponible prévu descend en dessous du stock de sécurité.

Le système de planification suggère une commande d'approvisionnement pour répondre aux besoins à la date d'échéance. Le texte d'avertissement indique la quantité du stock de sécurité et la date à laquelle elle est entamée.

Entamer le stock de sécurité est considéré comme une exception car cela ne doit pas se produire si le point de commande a été correctement défini.

> [!NOTE]
> L'approvisionnement pour les lignes planification avec les alertes Exception n'est normalement pas modifié en fonction des paramètres de planification. Au lieu de cela, le système de planification propose uniquement un approvisionnement pour couvrir la quantité de demande exacte. Cependant, vous pouvez définir l'exécution de la planification de manière à respecter certains paramètres de planification pour les lignes planification avec certaines alertes. Pour plus d'informations, voir « Respecter les paramètres de planification pour les avertissements d'exception » dans Calc. planification - F. planning.

### <a name="attention"></a>Attention
L'avertissement Attention est affiché dans deux situations :

- La date début de la planification est antérieure à la date de travail.
- La ligne planification suggère de changer un bon de commande ou de production libéré.

> [!NOTE]
> Dans les lignes planification comportant des avertissements, le champ **Accepter message d'action** n'est pas sélectionné, car le gestionnaire doit poursuivre l'étude de ces lignes avant de mettre en application ce plan.

## <a name="see-also"></a>Voir aussi  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  
[Planification](production-planning.md)   
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

