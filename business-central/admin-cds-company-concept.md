---
title: Modèles de propriété des données pour la synchronisation
description: 'Les compagnies sont des entités à la fois juridiques et commerciales, qui permettent de sécuriser et visualiser les données métier.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'CDS, Dataverse, integration, sync'
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# <a name="data-ownership-models-for-synchronization"></a>Modèles de propriété des données pour la synchronisation

[!INCLUDE[prod_short](includes/cds_long_md.md)] nécessite que vous indiquiez un propriétaire pour les données que vous stockez. Pour en savoir plus, consultez [Types de tables](/powerapps/maker/data-platform/types-of-entities) dans la documentation Power Apps. Lorsque vous configurez l’intégration entre [!INCLUDE[prod_short](includes/cds_long_md.md)] et [!INCLUDE[prod_short](includes/prod_short.md)], vous devez choisir la propriété **Utilisateur ou équipe** pour les enregistrements synchronisés. Les actions pouvant être effectuées sur ces enregistrements peuvent être contrôlées au niveau de l'utilisateur. <!--We recommend the Team ownership model because it makes it easier to manage ownership for multiple people.NO LONGER TRUE IN DATAVERSE-->

## <a name="team-ownership"></a>Propriété Équipe
Dans [!INCLUDE[prod_short](includes/prod_short.md)], une compagnie est une table juridique et commerciale qui permet de sécuriser et visualiser les données métier. Les utilisateurs travaillent toujours dans le cadre d'une compagnie. L’élément de [!INCLUDE[prod_short](includes/cds_long_md.md)] le plus proche de ce concept est la table unité fonctionnelle, qui n’a aucune implication juridique ou commerciale.

Comme les unités fonctionnelles n'ont aucune implication juridique ou commerciale, vous ne pouvez pas forcer un mappage un à un (1:1) pour synchroniser les données entre une compagnie et une unité fonctionnelle, que la synchronisation soit unidirectionnelle ou bidirectionnelle. Pour rendre la synchronisation possible, lorsque vous activez la synchronisation pour une compagnie dans [!INCLUDE[prod_short](includes/prod_short.md)], ce qui suit se produit dans [!INCLUDE[prod_short](includes/cds_long_md.md)] :

* Nous créons une table compagnie équivalente à la table compagnie dans [!INCLUDE[prod_short](includes/prod_short.md)]. Le nom de la compagnie est suivi de « Code compagnie BC ». Par exemple, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Nous créons une unité fonctionnelle par défaut qui porte le même nom que la compagnie. Par exemple, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Nous créons une équipe propriétaire distincte portant le même nom que la compagnie et l'associons à l'unité fonctionnelle. Le nom de l'équipe est précédé de « BCI - ». Par exemple, BCI - Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Les enregistrements créés et synchronisés avec [!INCLUDE[prod_short](includes/cds_long_md.md)] sont affectés à l'équipe « Propriétaire BCI » associée à l'unité fonctionnelle.

> [!NOTE]
> Si vous renommez une compagnie en [!INCLUDE[prod_short](includes/prod_short.md)], les noms de la compagnie, de l'activité commerciale et de l'équipe que nous créons automatiquement dans [!INCLUDE[prod_short](includes/cds_long_md.md)] ne sont pas mis à jour. Étant donné que seul le code compagnie est utilisé pour l'intégration, cela n'affecte pas la synchronisation. Si vous souhaitez que les noms correspondent, vous devez mettre à jour la compagnie, l'unité fonctionnelle et l'équipe dans [!INCLUDE[prod_short](includes/cds_long_md.md)].

L'image suivante montre un exemple de cette configuration de données dans [!INCLUDE[prod_short](includes/cds_long_md.md)].

![L'unité fonctionnelle racine est en haut, les équipes au centre, puis les compagnies en bas.](media/cds_bu_team_company.png)

Dans cette configuration, les enregistrements associés à la compagnie Cronus US appartiennent à une équipe associée à l'unité fonctionnelle Cronus US dans [!INCLUDE[prod_short](includes/cds_long_md.md)]. Les utilisateurs pouvant accéder à cette unité fonctionnelle au moyen d'un rôle de sécurité défini sur la visibilité au niveau de l'unité fonctionnelle dans [!INCLUDE[prod_short](includes/cds_long_md.md)] peuvent maintenant voir ces enregistrements. L'exemple suivant montre comment utiliser des équipes pour fournir l'accès à ces enregistrements.

* Le rôle de responsable commercial est attribué aux membres de l'équipe commerciale de Cronus US.
* Les utilisateurs ayant le rôle de responsable commercial peuvent accéder aux enregistrements de compte pour les membres de la même unité fonctionnelle.
* L'équipe commerciale de Cronus US est associée à l'unité fonctionnelle de Cronus US mentionnée précédemment. Les membres de l’équipe commerciale de Cronus US peuvent voir tout compte appartenant à l’utilisateur Cronus US, qui proviendrait de la table compagnie Cronus US dans [!INCLUDE[prod_short](includes/prod_short.md)].

Cependant, le mappage 1:1 entre l'unité fonctionnelle, la compagnie et l'équipe n'est qu'un point de départ, comme le montre l'image suivante.

![Le rôle de sécurité contrôle la visibilité des données.](media/cds_bu_team_company_2.png)

Dans cet exemple, une nouvelle unité fonctionnelle racine EUR (Europe) est créée dans [!INCLUDE[prod_short](includes/cds_long_md.md)] en tant que parent pour Cronus DE (Allemagne) et Cronus ES (Espagne). L'unité fonctionnelle EUR n'est pas associée à la synchronisation. Cependant, il peut donner aux membres de l'équipe commerciale EUR l'accès aux données de compte dans Cronus DE et Cronus ES en définissant la visibilité des données sur **Centre de profit parent/enfant** sur le rôle de sécurité associé dans [!INCLUDE[prod_short](includes/cds_long_md.md)].

La synchronisation détermine l'équipe devant posséder les enregistrements. Ceci est contrôlé par le champ **Équipe propriétaire par défaut** sur la ligne BCI. Lorsqu’un enregistrement BCI est activé pour la synchronisation, nous créons automatiquement l'unité fonctionnelle associée et l’équipe propriétaire (si elle n’existe pas encore), et définissons le champ **Équipe propriétaire par défaut**. Lorsque la synchronisation est activée pour une table, les administrateurs peuvent changer d’équipe propriétaire, mais une équipe doit toujours être affectée.

> [!NOTE]
> Les enregistrements passent en lecture seule après l'ajout et la sauvegarde d'une compagnie. Veillez donc à choisir la compagnie adéquate.

## <a name="choosing-a-different-business-unit"></a>Choix d'une autre unité fonctionnelle
Vous pouvez modifier la sélection de l'unité fonctionnelle si vous utilisez le modèle de propriété Équipes. Si vous utilisez le modèle de propriété Personne, l'unité fonctionnelle par défaut est toujours sélectionnée. 

Si vous choisissez une autre unité fonctionnelle, par exemple une unité que vous avez créée précédemment dans [!INCLUDE[prod_short](includes/cds_long_md.md)], elle conserve son nom initial. Autrement dit, elle n'est pas suivi du code compagnie. Nous allons créer une équipe qui utilise la convention de nommage.

Lorsque vous modifiez une unité fonctionnelle, vous ne pouvez choisir que les unités fonctionnelles situées un niveau en dessous de l'unité fonctionnelle racine.

## <a name="person-ownership"></a>Propriété Personne
Si vous choisissez le modèle de propriété Personne, vous devez indiquer chaque représentant qui possédera de nouveaux enregistrements. L'unité fonctionnelle et l'équipe sont créées comme décrit dans la section [Propriété Équipe](admin-cds-company-concept.md#team-ownership).

L'unité fonctionnelle par défaut est utilisée lorsque le modèle de propriété Personne est choisi et que vous ne pouvez pas choisir une autre unité fonctionnelle. L’équipe associée à l'unité fonctionnelle par défaut détiendra des enregistrements pour des tables communes, telles que la table Produit, qui ne sont pas liées à des représentants spécifiques.

Lorsque vous associez des représentants [!INCLUDE[prod_short](includes/prod_short.md)] aux utilisateurs de [!INCLUDE[prod_short](includes/cds_long_md.md)], [!INCLUDE[prod_short](includes/prod_short.md)] ajoute l’utilisateur à l’équipe par défaut dans [!INCLUDE[prod_short](includes/cds_long_md.md)]. Vous pouvez vérifier que les utilisateurs sont ajoutés en consultant la colonne **Membre de l’équipe par défaut** sur la page **Utilisateurs – Common Data Service**. Si l’utilisateur n’est pas ajouté, vous pouvez l’ajouter manuellement en utilisant l’action **Ajouter des utilisateurs couplés à l’équipe**. Pour plus d’informations, voir [Synchronisation des données dans Business Central avec Dataverse](admin-synchronizing-business-central-and-sales.md).

## <a name="see-also"></a>Voir aussi
[À propos de [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-common-data-service.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
