---
author: brentholtorf
ms.topic: include
ms.date: 04/27/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
Lorsque vous commencez à utiliser [!INCLUDE[prod_short](../../../includes/prod_short.md)], vous pouvez exécuter un guide de configuration assistée afin de rapidement et facilement configurer les informations relatives à la taxe de vente pour votre compagnie, vos clients et vos fournisseurs. En quelques minutes, vous êtes prêt à créer des documents vente et des documents achat pour lesquels la taxe de vente est calculée correctement. Il suffit de rechercher le guide de configuration assistée **Configuration de la taxe de vente**, puis d'effectuer la procédure du guide. I s'agit de spécifier les comptes à utiliser pour la taxe de vente pour les ventes et les achats.  

Nous vous recommandons de choisir d'appliquer la nouvelle région fiscale aux informations de votre propre compagnie. Si vous choisissez également de l'appliquer aux clients ou fournisseurs, il vous sera demandé de définir un filtre pour les clients ou fournisseurs auxquels vous voulez appliquer les informations. Par exemple, vous pouvez choisir d'appliquer la région fiscale aux clients qui se trouvent dans votre propre ville ou comté, ou à tous les clients.

Les personnes auxquelles vous attribuez les codes de région fiscale déterminent les taxes qui sont calculées sur vos transactions de vente et d'achat.

Si vous passez à la section *Ma compagnie* vierge, nous vous recommandons de commencer par utiliser chacun des guides de configuration assistée, y compris celui qui concerne la taxe de vente. Si vous préférez configurer la taxe de vente par vous-même, cet article explique ce que vous devez prendre en compte. Mais nous vous recommandons de collaborer étroitement avec votre conseiller fiscal.  

## <a name="tax-groups-tax-areas-and-tax-jurisdictions"></a>Groupes taxes, zones de recouvrement et autorités de recouvrement

Dans [!INCLUDE[prod_short](../../../includes/prod_short.md)], un groupe fiscal représente un groupe d'articles en inventaire ou de ressources soumis au même conditions pour ce qui est des taxes. Par exemple, vous pouvez configurer un groupe fiscal pour les articles soumis à la taxe et un autre pour les articles non soumis à la taxe. Vous devez affecter des codes groupe fiscal aux articles en inventaire et aux comptes du grand livre. De même, vous devez affecter des codes de région fiscale aux clients, aux emplacements et aux paramètres de votre compagnie. Le guide de configuration assistée vous aide à effectuer ces opérations.  

Chaque région fiscale correspond à un regroupement d'autorités fiscales basé sur une situation géographique particulière. Par exemple, la région fiscale de Miami, Floride, comprend trois autorités fiscales de la taxe de vente : la ville (Miami), le comté (Dade) et l'état (Floride). [!INCLUDE[prod_short](../../../includes/prod_short.md)] inclut un ensemble limité de zones de recouvrement avec une configuration par défaut, mais vous pouvez les modifier et ajouter de nouvelles régions fiscales.  

