---
author: edupont04
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 5c99520c40098f568df543ccda2996639e22dcb8
ms.sourcegitcommit: cdb57f14960f58b1d36a1b373fbf35dfed5fad9e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/23/2022
ms.locfileid: "8334750"
---
Le tableau suivant décrit certains des principaux rapports dans les rapports d'inventaire et d’entrepôt.

| Rapport | Description | Code | 
|---------|---------|---------|
|[Plan de disponibilité de l'inventaire](https://businesscentral.dynamics.com?report=707)|Si vous souhaitez avoir un aperçu d’articles/d'unités de stock spécifiques et de leur disponibilité. Ce rapport affiche des valeurs cumulées telles que les besoins bruts, les réceptions programmées et prévues, l'inventaire, etc. |707|
|[Évaluation de l'inventaire](https://businesscentral.dynamics.com?report=1001)|Affiche l’évaluation de l'inventaire des articles sélectionnés dans votre inventaire. Le rapport indique également des informations sur la valeur des augmentations et des diminutions d'inventaire au fil du temps.|1 001|
|[Date expiration article : Quantité](https://businesscentral.dynamics.com?report=5809)|Propose une vue d’ensemble des quantités des articles sélectionnés dans votre inventaire dont les dates d’expiration sont incluses dans une période donnée. La liste indique le nombre d’unités de l’article sélectionné qui expirent à une date donnée. Pour chaque article spécifié lors de la configuration du rapport, le document imprimé indique le nombre d’unités qui expirent au cours de trois périodes de même durée et la quantité d’inventaire totale de l’article sélectionné.<br>Vous pouvez définir ce que le rapport doit inclure en configurant des filtres. Si vous ne définissez aucun filtre, le rapport inclut tous les enregistrements. Les quantités indiquées dans le rapport reflètent seulement les quantités des articles pour lesquels des dates d’expiration ont été définies.|5809|
|[Ancienneté stock : Quantité](https://businesscentral.dynamics.com?report=5807)|Affiche un aperçu de l’ancienneté des articles sélectionnés dans votre inventaire. La liste indique la valeur ou le nombre d’unités de l’article sélectionné qui ont été ajoutées à l'inventaire ou supprimées de l'inventaire, ainsi que la date d’ajout ou de retrait. Les articles peuvent être ajoutés à l'inventaire ou supprimés de ce même inventaire après des achats, des ventes, et des ajustements positifs ou négatifs.|5807|
|[Ancienneté stock : Valeur](https://businesscentral.dynamics.com?report=5808)|Affiche un aperçu de l’ancienneté des articles sélectionnés dans votre inventaire. La liste indique la valeur ou le nombre d’unités de l’article sélectionné qui ont été ajoutées à l'inventaire ou supprimées de l'inventaire, ainsi que la date d’ajout ou de retrait. Les articles peuvent être ajoutés à l'inventaire ou supprimés de ce même inventaire après des achats, des ventes, et des ajustements positifs ou négatifs.|5808|
|[Liste coût de l'inventaire et liste de prix](https://businesscentral.dynamics.com?report=716)|Affiche la liste d’informations sur les prix des articles sélectionnés ou des unités de stock : coût unitaire direct, dernier coût direct, prix unitaire, pourcentage de profit et profit. |716|
|[Liste zones de stockage](https://businesscentral.dynamics.com?report=7319)|Affiche une vue d’ensemble des zones de stockage, leur configuration et la quantité d’articles dans les zones. Ce rapport peut être utilisé pour tous les emplacements, qui ont « zone » comme champ obligatoire. |7319|
|[État livraison entrepôt](https://businesscentral.dynamics.com?report=7313)|Affiche un aperçu des documents origine ouverts avec les articles livrés ou devant être livrés, par emplacement. Ce rapport peut être utilisé pour tous les emplacements, pour lesquels **Livraisons requises** est activé. **État livraison entrepôt** affiche les emplacements, les codes de zone, l'état du document, les quantités.|7313|
|[Liste des prélèvements inventaire](https://businesscentral.dynamics.com?report=813)|Affiche la liste des documents de vente dans lesquels un article est inclus. Les informations suivantes sont données pour chaque article : ligne document de vente avec le nom du client, code de variante, code d'emplacement, code de zone, date de livraison, quantité à livrer et unité de mesure. La quantité à livrer est totalisée pour chaque article. Le rapport peut être utilisé lorsque des articles vont être retirés de l'inventaire.<br>REMARQUE : cette fonctionnalité n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|813|
|[Zone d'ajustement entrepôt](https://businesscentral.dynamics.com?report=7320)|Ce rapport spécial est destiné uniquement à un entrepôt avancé et affiche les quantités restantes qui sont encore stockées dans la zone d'ajustement proprement dite. Normalement, cette zone spécifique doit être vide. La seule raison pour laquelle cette zone sera remplie est la conséquence du processus de comptage physique ou si des quantités d’articles ont été retirées ou ajoutées à l’entrepôt|7320|