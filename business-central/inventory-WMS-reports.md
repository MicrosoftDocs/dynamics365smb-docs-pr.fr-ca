---
title: Rapports et analyses d'inventaire et d’entrepôt
description: Découvrez les rapports et analyses d'inventaire et d’entrepôt disponibles dans la version standard de Business Central afin que vous puissiez suivre votre activité.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa
ms.openlocfilehash: 8a4418699f28acd3ede80616ba69c56f50781e43
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216432"
---
# <a name="inventory-and-warehouse-reports-and-analytics-in-business-central"></a>Rapports et analyses d'inventaire et d’entrepôt dans Business Central

Les rapports d'inventaire et d’entrepôt dans [!INCLUDE [prod_short](includes/prod_short.md)] permettent aux professionnels de l'inventaire et des affaires d’obtenir des informations et des statistiques sur les activités d'inventaire et d’entrepôt actuelles et passées.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports d'inventaire et d’entrepôt.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Plan de disponibilité de l'inventaire**|707|Si vous souhaitez avoir un aperçu d’articles/d'unités de stock spécifiques et de leur disponibilité. Ce rapport affiche des valeurs cumulées telles que les besoins bruts, les réceptions programmées et prévues, l'inventaire, etc. |
|**Évaluation de l'inventaire**|1 001|Affiche l’évaluation de l'inventaire des articles sélectionnés dans votre inventaire. Le rapport indique également des informations sur la valeur des augmentations et des diminutions d'inventaire au fil du temps.|
|**Date expiration article : Quantité**|5809|Propose une vue d’ensemble des quantités des articles sélectionnés dans votre inventaire dont les dates d’expiration sont incluses dans une période donnée. La liste indique le nombre d’unités de l’article sélectionné qui expirent à une date donnée. Pour chaque article spécifié lors de la configuration du rapport, le document imprimé indique le nombre d’unités qui expirent au cours de trois périodes de même durée et la quantité d’inventaire totale de l’article sélectionné.<br>Vous pouvez définir ce que le rapport doit inclure en configurant des filtres. Si vous ne définissez aucun filtre, le rapport inclut tous les enregistrements. Les quantités indiquées dans le rapport reflètent seulement les quantités des articles pour lesquels des dates d’expiration ont été définies.|
|**Ancienneté stock : Quantité** ou **Ancienneté stock : Valeur**|5807 ou 5808|Affiche un aperçu de l’ancienneté des articles sélectionnés dans votre inventaire. La liste indique la valeur ou le nombre d’unités de l’article sélectionné qui ont été ajoutées à l'inventaire ou supprimées de l'inventaire, ainsi que la date d’ajout ou de retrait. Les articles peuvent être ajoutés à l'inventaire ou supprimés de ce même inventaire après des achats, des ventes, et des ajustements positifs ou négatifs.|
|**Liste coût de l'inventaire et liste de prix**|716|Affiche la liste d’informations sur les prix des articles sélectionnés ou des unités de stock : coût unitaire direct, dernier coût direct, prix unitaire, pourcentage de profit et profit. |
|**Liste zones de stockage**|7319|Affiche une vue d’ensemble des zones de stockage, leur configuration et la quantité d’articles dans les zones. Ce rapport peut être utilisé pour tous les emplacements, qui ont « zone » comme champ obligatoire. |
|**État livraison entrepôt**|7313|Affiche un aperçu des documents origine ouverts avec les articles livrés ou devant être livrés, par emplacement. Ce rapport peut être utilisé pour tous les emplacements, pour lesquels **Livraisons requises** est activé. **État livraison entrepôt** affiche les emplacements, les codes de zone, l'état du document, les quantités.|
|**Liste des prélèvements inventaire**|813|Affiche la liste des documents de vente dans lesquels un article est inclus. Les informations suivantes sont données pour chaque article : ligne document de vente avec le nom du client, code de variante, code d'emplacement, code de zone, date de livraison, quantité à livrer et unité de mesure. La quantité à livrer est totalisée pour chaque article. Le rapport peut être utilisé lorsque des articles vont être retirés de l'inventaire.<br>REMARQUE : cette fonctionnalité n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|
|**Zone d'ajustement entrepôt**|7320|Ce rapport spécial est destiné uniquement à un entrepôt avancé et affiche les quantités restantes qui sont encore stockées dans la zone d'ajustement proprement dite. Normalement, cette zone spécifique doit être vide. La seule raison pour laquelle cette zone sera remplie est la conséquence du processus de comptage physique ou si des quantités d’articles ont été retirées ou ajoutées à l’entrepôt|


## <a name="tasks"></a>Tâches

Les articles suivants décrivent certaines des tâches clés pour analyser l’état de votre entreprise :

* [Créer des rapports d'analyse](bi-how-create-analysis-views-reports.md)  
* [Voir la disponibilité des articles](inventory-how-availability-overview.md)


## <a name="see-also"></a>Voir aussi

[Configuration de l'inventaire](inventory-setup-inventory.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
