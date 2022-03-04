---
author: edupont04
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 0bfe45574f3f209ac5ee310546cd2ef0998ab417
ms.sourcegitcommit: cdb57f14960f58b1d36a1b373fbf35dfed5fad9e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/23/2022
ms.locfileid: "8334549"
---
Le tableau suivant décrit certains des principaux rapports dans les rapports de production.

| Rapport | Description | Code | 
|---------|---------|---------|
| [Nomenclature multi-niveau](https://businesscentral.dynamics.com?report=99000753)|Affiche une liste des nomenclatures décalée pour l’article ou les articles que vous définissez dans les filtres. La nomenclature de production est entièrement éclatée pour tous les niveaux.|99000753|
| [Article – Capable de fabriquer (Temps)](https://businesscentral.dynamics.com?report=5871)|Indique comment cinq chiffres de disponibilité principaux différents évoluent dans le temps pour un article de nomenclature. Ces chiffres sont modifiés en fonction des événements d’offre et de demande prévus et de l’approvisionnement qui est basé sur les composantes disponibles qui peuvent être assemblées ou produites.<br>Vous pouvez utiliser le rapport pour vérifier si vous pouvez traiter un document de vente d’un article à une date spécifique, en consultant sa disponibilité actuelle ainsi que les quantités potentielles que ses composantes peuvent fournir si un ordre d’assemblage a été lancé. Le rapport indique la date et le nombre d’unités d’un élément d’assemblage et de production que vous pouvez fabriquer, en fonction de la disponibilité des composantes et de la disponibilité actuelle de l’article. Cela est affiché en tant que quantité totale.<br>Les informations sont affichées dans un graphique dans lequel chaque chiffre de disponibilité est une ligne qui progresse dans la chronologie et se déplace vers le haut ou vers le bas en fonction des modifications des quantités. Les chiffres de quantité proviennent du même moteur qui fournit des informations dans la fenêtre **Disponibilité article par niveau de nomenclature**. |5871|
| [Distribution coût total nomenclature](https://businesscentral.dynamics.com?report=5872)|Indique graphiquement la manière dont le coût d’un article assemblé ou produit est distribué dans sa nomenclature.<br>Ces informations peuvent être utiles pour décider, par exemple, de changer de fournisseurs de composantes, de remplacer une utilisation interne de capacité par un travail externalisé, ou inversement, ou lors de l’examen et de la modification de la nomenclature d’un article.<br>Le premier graphique du rapport affiche le coût unitaire total des composantes et des ressources de travail de l’article parent, réparti en cinq coûts totaux différents au maximum et représenté graphiquement par des couleurs différentes.<br>Le graphique en secteurs avec la légende *Par matière/travail* affiche la répartition proportionnelle entre les coûts de matériel et de travail de l’article parent, ainsi que ses propres frais généraux de fabrication. L'action du coût matière inclut les coûts matière de l’article. La part du coût de travail inclut la capacité, l'utilisation fixe de capacité et les coûts de sous-traitance. Les coûts totaux sont affichés différemment en fonction des choix indiqués dans le champ **Afficher uniquement**.<br>Le graphique en secteurs avec la légende *Par direct/indirect* affiche la répartition proportionnelle entre les coûts directs et indirects de la nomenclature. L'action des coûts directs inclut les coûts matière, de capacité et les coûts de sous-traitance de l’article. La part des coûts indirects inclut l'utilisation fixe de capacité et les frais généraux de fabrication.<br>Le tableau en bas du rapport est inclus lorsque vous activez la case à cocher **Inclure détails**. Il affiche les valeurs sélectionnées dans la fenêtre Coûts totaux nomenclature par niveau unique ou multi-niveau, en fonction du choix que vous avez effectué dans le champ **Afficher coût total comme**.|5872|
| [Coût détaillé](https://businesscentral.dynamics.com?report=99000756)|Affiche la liste des coûts par article en tenant compte du rebut.|99000756|
| [Cas d’emploi (multi-niveau)](https://businesscentral.dynamics.com?report=99000757)|Affiche où et en quelle quantité sont utilisés les articles dans la structure produit.<br>Le rapport indique uniquement l’article comme cas d’emploi lorsque l’article de base est utilisé comme article de niveau supérieur. Par exemple, si l’article A est utilisé pour fabriquer l’article B, et que l’article B est utilisé pour fabriquer l’article C, le rapport affiche l’article B si vous exécutez ce rapport pour l’article A. Si vous exécutez l’article B, l’article C est affiché comme cas d’emploi.<br>Vous pouvez également ouvrir la page **Ligne cas d’emploi** directement à partir de l’article.|99000757|
| [Liste de comparaison des nomenclatures article](https://businesscentral.dynamics.com?report=99000758)|Ce rapport vous donne la possibilité de comparer des produits finis similaires concernant les coûts. Vous verrez une liste de toutes les composantes et leurs coûts, ainsi que les quantités nécessaires. La date de calcul est normalement fixée à la date de travail. |99000758|
| [Statistiques de bon de production](https://businesscentral.dynamics.com?report=99000791)|Spécifie les différents coûts qui se sont cumulés pour le bon de production sélectionné.<br>Le contenu du rapport est presque identique à la page **Statistiques de bons de production**.<br>Pour les bons de production utilisant la méthode de fabrication *Fabrication à la commande*, la fenêtre n’affiche que le coût matière et capacité des articles au niveau de nomenclature le plus élevé.|99000791|
| [Liste tâches capacité](https://businesscentral.dynamics.com?report=99000780)|Affiche les bons de production en attente de traitement dans les ateliers ou les unités de production. Les documents imprimés indiquent la capacité de l'atelier ou de l'unité de production). Le rapport comprend les données telles que l’heure début et fin, la date de chaque bon de production et la quantité d’entrée.|99000780|
| [Chargement atelier](https://businesscentral.dynamics.com?report=99000783)|Les deux rapports affichent la liste du chargement d’un atelier ou d’une unité de production. Le chargement d’un atelier/d'une unité de production représente la somme du nombre d’heures nécessaires pour exécuter toutes les commandes réelles et planifiées dans un atelier, sur une période précise.|99000783|
| [Chargement unité de production](https://businesscentral.dynamics.com?report=99000784)|Les deux rapports affichent la liste du chargement d’un atelier ou d’une unité de production. Le chargement d’un atelier/d'une unité de production représente la somme du nombre d’heures nécessaires pour exécuter toutes les commandes réelles et planifiées dans un atelier, sur une période précise.|99000784|
| [Liste des articles manquants bon de production](https://businesscentral.dynamics.com?report=99000788)|Ce rapport peut être utilisé pour voir toutes les composantes qui ne sont pas disponibles en raison d’un stock manquant. Ainsi, cet aperçu peut être utilisé pour voir si le calendrier d’un bon de production planifié ou libéré et si le temps planifié peuvent être respectés.|99000788|