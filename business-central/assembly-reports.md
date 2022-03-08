---
title: Rapports et analyses d’assemblage dans Business Central
description: Découvrez les rapports et analyses d’assemblage disponibles dans la version standard de Business Central afin que vous puissiez suivre votre activité.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa
ms.openlocfilehash: 91234cd02736d425116be40137efd9d068b5bd97
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216433"
---
# <a name="assembly-reports-and-analytics-in-business-central"></a>Rapports et analyses d’assemblage dans Business Central

Les rapports d’assemblage dans [!INCLUDE [prod_short](includes/prod_short.md)] permettent aux professionnels de la production et des affaires d’obtenir des informations et des statistiques sur les activités d’assemblage actuelles et passées.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports d’assemblage.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Nomenclatures d’assemblage**|801|Affiche la liste des nomenclatures : nom, numéro de nomenclature, composantes de nomenclature, et toutes autres nomenclatures qui font partie de la nomenclature. Les composantes de nomenclature sont définies dans la table Composante nomenclature. Vous verrez également ici l’unité de mesure et la quantité nécessaire de chaque composante par unité de mesure de base. |
|**Article – Capable de fabriquer (Temps)**|5871|Indique comment cinq chiffres de disponibilité principaux différents évoluent dans le temps pour un article de nomenclature. Ces chiffres sont modifiés en fonction des événements d’offre et de demande prévus et de l’approvisionnement qui est basé sur les composantes disponibles qui peuvent être assemblées ou produites.<br>Vous pouvez utiliser le rapport pour vérifier si vous pouvez traiter un document de vente d’un article à une date spécifique, en consultant sa disponibilité actuelle ainsi que les quantités potentielles que ses composantes peuvent fournir si un ordre d’assemblage est lancé. Le rapport indique la date et le nombre d’unités d’un élément d’assemblage et de production que vous pouvez fabriquer, en fonction de la disponibilité des composantes et de la disponibilité actuelle de l’article. Cela est affiché en tant que quantité totale.<br>Les informations sont affichées dans un graphique dans lequel chaque chiffre de disponibilité est une ligne qui progresse dans la chronologie et se déplace vers le haut ou vers le bas en fonction des modifications des quantités. Les chiffres de quantité proviennent du même moteur qui fournit des informations dans la fenêtre **Disponibilité article par niveau de nomenclature**. |
|**Distribution coût total nomenclature**|5872|Indique graphiquement la manière dont le coût d’un article assemblé ou produit est distribué dans sa nomenclature.<br>Ces informations peuvent être utiles pour décider de changer de fournisseurs de composantes, de remplacer une utilisation interne de capacité par un travail externalisé, ou inversement, ou lors de l’examen et de la modification de la nomenclature d’un article, par exemple.<br>Le premier graphique du rapport affiche le coût unitaire total des composantes et des ressources de travail de l’article parent, réparti en cinq coûts totaux différents au maximum et représenté graphiquement par des couleurs différentes.<br>Le graphique en secteurs avec la légende *Par matière/travail* affiche la répartition proportionnelle entre les coûts de matériel et de travail de l’article parent, ainsi que ses propres frais généraux de fabrication. L'action du coût matière inclut les coûts matière de l’article. La part du coût de travail inclut la capacité, l'utilisation fixe de capacité et les coûts de sous-traitance. Les coûts totaux sont affichés différemment en fonction des choix indiqués dans le champ **Afficher uniquement**.<br>Le graphique en secteurs étiqueté avec la légende *Par direct/indirect* affiche la répartition proportionnelle entre les coûts directs et indirects de la nomenclature. L'action des coûts directs inclut les coûts matière, de capacité et les coûts de sous-traitance de l’article. La part des coûts indirects inclut l'utilisation fixe de capacité et les frais généraux de fabrication.<br>Le tableau en bas du rapport est inclus lorsque vous activez la case à cocher Inclure détails. Il affiche les valeurs sélectionnées dans la fenêtre Coûts totaux nomenclature par niveau unique ou multi-niveau, en fonction de l’option que vous sélectionnez dans le champ Afficher coût total comme.|
|**Liste des cas d’emploi**|809|Affiche la liste des articles sélectionnés qui composent les nomenclatures. Aperçu utile si vous devez modifier une composante dans une nomenclature insérée dans un élément d’assemblage. Par exemple, si votre fournisseur ne peut plus livrer un article spécifique que vous avez utilisé pour votre assemblage/production. Dans ce type de scénario, ce rapport vous fournit un aperçu simple des nomenclatures dans lesquelles la composante est incluse. Vous pouvez définir un filtre pour le numéro de la composante.|
|**Nomenclature – Matières premières**|810|Ce rapport peut vous donner un aperçu des composantes nécessaires, à la fois pour l’assemblage et pour la production. Vous verrez l’inventaire, l’unité de mesure de base, le fournisseur principal si le numéro du fournisseur est écrit dans la fiche article elle-même, et le calcul du délai de réapprovisionnement.|
|**Nomenclature – sous-ensembles**|811|Si vous produisez et/ou assemblez des sous-ensembles, utilisez ce rapport pour avoir une vue d’ensemble sur ce type de composante. Ce rapport vous montre l’unité de mesure de base, l'inventaire, les coûts unitaires et un autre numéro d’article. |
|**Nomenclature d’assemblage – Produits finis**|812|Affiche la liste des articles ou des nomenclatures qui ne sont pas des composantes de nomenclature. **Remarque** : Ce rapport n’est pas limité à la nomenclature uniquement, alors n’oubliez pas de définir le filtre dans le champ **Nomenclature d’assemblage** ou les champs **Système réapprovisionnement**|
|**Assembler pour commande – Ventes**|915|Affiche les principaux chiffres de vente pour les éléments de composantes d’assemblage pouvant être vendus en tant qu’éléments d’assemblage dans les ventes assembler pour commande, ou en tant qu’éléments séparés directement à partir de l'inventaire.<br>Utilisez ce rapport pour analyser la quantité, le coût, les ventes et les chiffres du profit se rapportant aux composantes d’assemblage pour prendre des décisions, par exemple pour décider si vous devez modifier le prix d’un kit ou bien cesser ou commencer à utiliser un article particulier dans les assemblages.<br>La ligne **Assemblage** affiche les chiffres vente pour la quantité totale vendue en tant qu’élément d’assemblage. Les ventes propres à l’élément d’assemblage totalisant cette somme sont affichées si vous sélectionnez le champ **Afficher détails d’assemblage**.<br>La priorité est donnée aux composantes d’assemblage, mais les chiffres sont calculés à partir de la marge de profit de leur parent, l’élément d’assemblage. Par conséquent, le montant des ventes de chaque composante est calculé à partir de son propre coût et de la marge de profit de son parent à l’aide de la formule suivante.<br>Le rapport affiche des informations relatives aux éléments répondant à l’un des critères suivants ou aux deux :<br>- Existe dans la nomenclature d’assemblage d’un élément qui utilise la politique d’assemblage Assembler pour commande.<br>- A été vendu dans le cadre d’une vente assembler pour commande.|

## <a name="tasks"></a>Tâches

Les articles suivants décrivent certaines des tâches clés pour analyser l’état de votre entreprise :

* [Voir la disponibilité des articles](inventory-how-availability-overview.md)

## <a name="see-also"></a>Voir aussi

[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser les nomenclatures](inventory-how-work-boms.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
