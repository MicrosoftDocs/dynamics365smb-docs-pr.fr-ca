---
title: Rapports et analyses d'achat
description: Découvrez les rapports et analyses d'achat disponibles dans la version standard de Business Central afin que vous puissiez suivre votre activité.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa
ms.openlocfilehash: 5fc64db4120b80203f99742ed3ed834b23370c47
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216434"
---
# <a name="purchase-reports-and-analytics-in-business-central"></a>Rapports et analyses d'achat dans Business Central

Les rapports d'achat dans [!INCLUDE [prod_short](includes/prod_short.md)] permettent aux professionnels de l’approvisionnement et des affaires d’obtenir des informations et des statistiques sur les activités d’achat actuelles et passées.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports d'achat.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Statistique achat**|312|Affiche les statistiques achat pour chaque fournisseur. Cela inclut des informations pour cinq périodes, à partir de la date que vous spécifiez.<br>
Le rapport comprend les informations concernant le total des achats, les paiements, les frais financiers et les escomptes, y compris les escomptes de paiement gagnés et perdus. Les statistiques sont calculées pour les achats antérieurs à la date saisie, trois fois à un mois d’intervalle à compter de la date saisie et pour une période incluant tous les achats effectués après le troisième intervalle d’un mois.|
|**Fournisseur – Liste des 10 meilleurs**|311|Affiche des informations sur les achats aux fournisseurs pour une période déterminée. Vous pouvez choisir le nombre de fournisseurs inclus dans le rapport.<br>Les fournisseurs sont triés par montant, et vous pouvez choisir s’ils doivent être triés par montant d’achat ou par solde. Le rapport vous donne un bref aperçu des fournisseurs à qui vous achetez le plus et ceux à qui vous devez le plus d’argent.|
|**Catalogue article fournisseur** ou **Catalogue fournisseur/article**|320 ou 720|Affiche une liste des fournisseurs pour les articles sélectionnés ou des articles pour les fournisseurs sélectionnés. Pour chaque combinaison d’article et de fournisseur, l’état indique le coût unitaire direct, le délai de réapprovisionnement et la référence fournisseur.<br>Ce rapport n’est pas disponible aux États-Unis, au Canada et au Mexique. Utilisez plutôt le rapport **Catalogue Article/Fournisseur** (10164).|
|**Achats Fournisseur/Article**|313|Affiche la liste des écritures article de chaque fournisseur pendant la période choisie. Le rapport affiche des informations sur la quantité facturée, le montant et les escomptes possibles. Il peut être utilisé, par exemple, pour analyser les achats d’articles d’une compagnie et pour voir s’il existe une relation entre les escomptes et les achats d’articles.|
|**Liste coût de l'inventaire et liste de prix**|716|Affiche la liste d’informations sur les prix des articles sélectionnés ou des unités de stock : coût unitaire direct, dernier coût direct, prix unitaire, pourcentage de profit et profit.|
|**Plan de disponibilité de l'inventaire**|707|Si vous souhaitez avoir un aperçu d’articles/d'unités de stock spécifiques et de leur disponibilité. Ce rapport affichera des valeurs cumulées telles que les besoins bruts, les réceptions programmées et prévues, l'inventaire, etc. |
|**Achats fournisseur inventaire**|714|Affiche la liste des fournisseurs auxquels votre compagnie a acheté des articles pendant la période sélectionnée. Il indique la quantité facturée, le montant et l'escompte. Le rapport peut être utilisé pour analyser les achats d'article d'une compagnie.|
|**Bons de commande d'inventaire**|709|Affiche la liste des articles commandés chez les fournisseurs. Il indique aussi la date de réception prévue, la quantité et le montant des commandes en souffrance. Par exemple, utilisez le rapport pour visualiser le moment où les articles doivent être réceptionnés et si un rappel de commande en souffrance doit être émis.|
|**Disponibilité réservation achat**|409|Affiche la disponibilité des articles pour les livraisons effectuées à partir de documents achat, par exemple les retours. Vous déterminez si le rapport indique l'état de chaque document ou de chaque ligne achat. <br>Lorsque vous imprimez le rapport, vous pouvez également mettre à jour les quantités disponibles pour livraison dans le champ **Quantité à recevoir** des lignes achat. Sur les notes de crédit achat et les lignes bon de commande négatives, le champ **Quantité à recevoir** indique la quantité à livrer. Vous pouvez alors utiliser ce rapport pour déterminer les documents à livrer. **Remarque** : ce rapport n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|
<!--|**Fournisseur - chronologie détaillée**|11006| Spécifique à DACH : rapport qui pourrait être utilisé par le chef d’équipe de votre département d’achat ainsi que par la comptabilité. Vous aurez ici un aperçu des factures fournisseurs impayées, y compris les dates d’échéance, les devises et les montants. La base est constituée des écritures fournisseur ouvertes.| -->




## <a name="tasks"></a>Tâches

Les articles suivants décrivent certaines des tâches clés pour analyser l’état de votre entreprise :

* [Créer des rapports d'analyse](bi-how-create-analysis-views-reports.md)  
* [Voir la disponibilité des articles](inventory-how-availability-overview.md)  


## <a name="see-also"></a>Voir aussi

[Définition des achats](purchasing-setup-purchasing.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
