---
title: Rapports et analyses de vente
description: Découvrez les rapports et analyses de vente disponibles dans la version standard de Business Central afin que vous puissiez suivre votre activité.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa
ms.openlocfilehash: b738eeef9771185c6907d963f368c462ae02f2d2
ms.sourcegitcommit: e891484daad25f41c37b269f7ff0b97df9e6dbb0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/27/2021
ms.locfileid: "7440401"
---
# <a name="sales-reports-and-analytics-in-business-central"></a>Rapports et analyses de vente dans Business Central

Les rapports de vente dans [!INCLUDE [prod_short](includes/prod_short.md)] permettent aux professionnels des ventes et des affaires d’obtenir des informations et des statistiques sur les activités de vente actuelles et passées.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports de vente.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Clients : Liste des commandes**|107| Affiche le détail de la commande avec la quantité qui n’est pas encore livrée, de chaque client sur 3 périodes de 30 jours chacune commençant à la date spécifiée. Il contient également des colonnes avec les commandes à livrer avant et après les 3 périodes et une colonne avec le détail de la commande totale de chaque client. Utilisez le rapport pour analyser le volume de vente attendu d’une compagnie. |
|**Client – Liste des 10 meilleurs**|111| Affiche des informations sur les achats et les soldes des clients pour la période sélectionnée. Vous pouvez choisir le nombre de clients qui sont inclus dans le rapport. Seuls les clients qui ont des achats pour cette période ou un solde à la fin de la période sont inclus.<br>Les clients sont triés par montant, et vous pouvez choisir s’ils doivent être triés par montant de ventes ou par solde. Le rapport vous donne un bref aperçu des clients qui achètent le plus et de ceux qui doivent le plus d’argent.|
|**Ventes Client/Article**|113|Affiche la liste des ventes article pour chaque client pendant la période choisie. Le rapport donne des informations sur la quantité, le montant des ventes, le profit et les escomptes possibles. Il peut servir, par exemple, à l’analyse des groupes clients d’une compagnie.|
|**Inventaire – Vente client**|713|Aperçu du point de vue de l’entrepôt. Il s’agit d’un point de vue différent de celui du rapport **Vente Client/Article**, et il montre d’abord l’article, puis le client qui a acheté ce produit.|
|**Clients – Liste des ventes**|119|Affiche les ventes client pour une période. Vous l’utilisez pour les déclarations auprès des administrations douanières et fiscales. Vous pouvez choisir de n’inclure que les clients dont le total des ventes excède un montant minimum. Vous pouvez également spécifier si vous souhaitez que le rapport reprenne les informations adresse de chaque client.<br>Le rapport est basé sur les ventes enregistrées ($) provenant des écritures client. En bas du rapport, le total des ventes déclarées est indiqué en $. Le total est basé sur les clients que vous avez inclus dans le rapport, autrement dit ceux qui figurent dans les filtres du raccourci Client et dont le total des ventes est supérieur au montant spécifié dans le champ **Montants $ supérieurs à** du raccourci **Options**.|
|**Clients – Solde à ce jour**|121|Affiche un solde détaillé des clients sélectionnés. Utilisez le rapport lors de la fermeture d’une période comptable ou d’un exercice financier, par exemple.|
|**Clients –– Balance de vérification**|129|Affiche le solde détaillé de clients sélectionnés. Vous pouvez utiliser le rapport pour vérifier que le solde pour un groupe de report client est égal à celui du compte du grand livre correspondant à une certaine date. Utilisez le rapport lors de la fermeture d’une période comptable ou d’un exercice financier, par exemple. Si vous avez besoin d’une version plus détaillée de ce type de rapport, utilisez le rapport **Balance de vérification détaillée clients** (104).|
|**Statistique vente**|112|[!INCLUDE [reports-sales-statistics](includes/reports-sales-statistics.md)] |
|**Dispo. réservation vente**|209|Affiche la disponibilité des articles pour les livraisons faites à partir de documents vente. Vous déterminez si le rapport indique l'état de chaque document ou de chaque ligne vente. Lorsque vous imprimez le rapport, vous pouvez également mettre à jour les quantités disponibles pour livraison dans le champ **Qté à livrer** des lignes vente. Vous pouvez alors utiliser ce rapport pour déterminer les documents à reporter.<br>Il existe également une capacité avec laquelle vous pouvez définir la quantité de produits à livrer. **Remarque** : ce rapport n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|
|**État livraison entrepôt**|7313|Ce rapport peut être utilisé pour tous les emplacements pour lesquels le champ **Livraison requise** est sélectionné. Le rapport **État livraison entrepôt** vous montre tous les documents de livraison d’entrepôt non reportés, y compris les emplacements, les codes de zone, l'état document, les quantités, etc. Ce rapport est parfait pour avoir une vue d’ensemble.|
|**Liste des prélèvements inventaire**|813|Affiche la liste des documents de vente dans lesquels un article est inclus. Les informations suivantes sont données pour chaque article : ligne document de vente avec le nom du client, code de variante, code d'emplacement, code de zone, date de livraison, quantité à livrer et unité de mesure. La quantité à livrer est totalisée pour chaque article. Le rapport peut être utilisé lorsque des articles vont être retirés de l'inventaire.<br>**Remarque** : ce rapport n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|
|**Commandes en retard vente inventaire**|718|Affiche une liste qui comprend les lignes commande dont la date de livraison est dépassée. Les informations suivantes sont données pour chaque article d’une commande : numéro, nom du client, numéro de téléphone du client, date de livraison, quantité commandée et quantité sur commande en attente. Le rapport indique aussi s’il y a d’autres articles en commande en souffrance pour le client.|
|**Détails de commande d'inventaire**|708|Affiche la liste des commandes qui n’ont pas encore été livrées, ainsi que les articles commandés. Il indique le numéro de commande, le nom du client, la date de livraison, la quantité commandée, la quantité retardée, la quantité en attente, la quantité ouverte et le prix unitaire, ainsi que les pourcentages d'escompte possibles et leur montant. La quantité sur commande en attente, la quantité ouverte et le montant sont totalisés pour chaque article. Utilisez le rapport pour visualiser s’il y a des problèmes de livraison ou s’il risque d’y en avoir.|



## <a name="tasks"></a>Tâches

Les articles suivants décrivent certaines des tâches clés pour analyser l’état de votre entreprise :

* [Créer des rapports d'analyse](bi-how-create-analysis-views-reports.md)  
* [Voir la disponibilité des articles](inventory-how-availability-overview.md)


## <a name="see-also"></a>Voir aussi

[Définition des ventes](sales-setup-sales.md)  
[Vente](sales-manage-sales.md)  
[Réserver des articles](inventory-how-to-reserve-items.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
