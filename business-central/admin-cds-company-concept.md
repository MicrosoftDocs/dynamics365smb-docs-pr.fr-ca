---
title: Mappage des compagnies et des unités fonctionnelles | Microsoft Docs
description: Les compagnies sont des entités à la fois juridiques et commerciales, qui permettent de sécuriser et visualiser les données métier.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: CDS, Common Data Service, integration, sync
ms.date: 01/17/2020
ms.author: bholtorf
ms.openlocfilehash: ccd371711a53c598279fcc981c5581be5ee9bdaf
ms.sourcegitcommit: d67328e1992c9a754b14c7267ab11312c80c38dd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3196925"
---
# <a name="data-ownership-models"></a>Modèles de propriété de données
[!INCLUDE[d365fin](includes/cds_long_md.md)] nécessite que vous indiquiez un propriétaire pour les données que vous stockez. Pour en savoir plus, consultez [Propriété d'entité](https://docs.microsoft.com/powerapps/maker/common-data-service/types-of-entities#entity-ownership) dans la documentation Power Apps. Lorsque vous configurez l'intégration entre [!INCLUDE[d365fin](includes/cds_long_md.md)] et [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez choisir l'un des deux modèles de propriété pour les enregistrements synchronisés :

* Équipe 
* Personne (utilisateur)

Les actions pouvant être effectuées sur ces enregistrements peuvent être contrôlées au niveau de l'utilisateur. Pour en savoir plus, consultez [Entités Utilisateur et Équipe](https://docs.microsoft.com/powerapps/developer/common-data-service/user-team-entities). Nous vous recommandons le modèle de propriété Équipe, car il facilite la gestion de la propriété pour plusieurs personnes.

## <a name="team-ownership"></a>Propriété Équipe
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], une compagnie est une entité juridique et commerciale qui permet de sécuriser et visualiser les données métier. Les utilisateurs travaillent toujours dans le cadre d'une compagnie. L'élément de [!INCLUDE[d365fin](includes/cds_long_md.md)] le plus proche de ce concept est l'entité Unité fonctionnelle, qui n'a aucune implication juridique ou commerciale.

Comme les unités fonctionnelles n'ont aucune implication juridique ou commerciale, vous ne pouvez pas forcer un mappage un à un (1:1) pour synchroniser les données entre une compagnie et une unité fonctionnelle, que la synchronisation soit unidirectionnelle ou bidirectionnelle. Pour rendre la synchronisation possible, lorsque vous activez la synchronisation pour une compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)], ce qui suit se produit dans [!INCLUDE[d365fin](includes/cds_long_md.md)] :

* Nous créons une entité compagnie équivalente à l'entité compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. Le nom de la compagnie est suivi de « Code compagnie BC ». Par exemple, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Nous créons une unité fonctionnelle par défaut qui porte le même nom que la compagnie. Par exemple, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Nous créons une équipe propriétaire distincte portant le même nom que la compagnie et l'associons à l'unité fonctionnelle. Le nom de l'équipe est précédé de « BCI - ». Par exemple, BCI - Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Les enregistrements créés et synchronisés avec [!INCLUDE[d365fin](includes/cds_long_md.md)] sont affectés à l'équipe « Propriétaire BCI » associée à l'unité fonctionnelle.

L'image suivante montre un exemple de cette configuration de données dans [!INCLUDE[d365fin](includes/cds_long_md.md)].

![L'unité fonctionnelle racine est en haut, les équipes au centre, puis les compagnies en bas.](media/cds_bu_team_company.png)

Dans cette configuration, les enregistrements associés à la compagnie Cronus US appartiennent à une équipe associée à l'unité fonctionnelle Cronus US <ID> dans [!INCLUDE[d365fin](includes/cds_long_md.md)]. Les utilisateurs pouvant accéder à cette unité fonctionnelle au moyen d'un rôle de sécurité défini sur la visibilité au niveau de l'unité fonctionnelle dans [!INCLUDE[d365fin](includes/cds_long_md.md)] peuvent maintenant voir ces enregistrements. L'exemple suivant montre comment utiliser des équipes pour fournir l'accès à ces enregistrements.

* Le rôle de responsable commercial est attribué aux membres de l'équipe commerciale de Cronus US.
* Les utilisateurs ayant le rôle de responsable commercial peuvent accéder aux enregistrements de compte pour les membres de la même unité fonctionnelle.
* L'équipe commerciale de Cronus US est associée à l'unité fonctionnelle de Cronus US mentionnée précédemment. Les membres de l'équipe commerciale de Cronus US peuvent voir tout compte appartenant à l'utilisateur Cronus US <ID>, qui proviendrait de l'entité compagnie Cronus US dans [!INCLUDE[d365fin](includes/d365fin_md.md)].

Cependant, le mappage 1:1 entre l'unité fonctionnelle, la compagnie et l'équipe n'est qu'un point de départ, comme le montre l'image suivante.

![Le rôle de sécurité contrôle la visibilité des données.](media/cds_bu_team_company_2.png)

Dans cet exemple, une nouvelle unité fonctionnelle racine EUR (Europe) est créée dans [!INCLUDE[d365fin](includes/cds_long_md.md)] en tant que parent pour Cronus DE (Allemagne) et Cronus ES (Espagne). L'unité fonctionnelle EUR n'est pas associée à la synchronisation. Cependant, il peut donner aux membres de l'équipe commerciale EUR l'accès aux données de compte dans Cronus DE et Cronus ES en définissant la visibilité des données sur **Centre de profit parent/enfant** sur le rôle de sécurité associé dans [!INCLUDE[d365fin](includes/cds_long_md.md)].

La synchronisation détermine l'équipe devant posséder les enregistrements. Ceci est contrôlé par le champ **Équipe propriétaire par défaut** sur l'enregistrement BCI - <ID>. Lorsqu'un enregistrement BCI - <ID> est activé pour la synchronisation, nous créons automatiquement l'unité fonctionnelle associée et l'équipe propriétaire (si elle n'existe pas déjà), et définissons le champ **Équipe propriétaire par défaut**. Lorsque la synchronisation est activée pour une entité, les administrateurs peuvent changer d'équipe propriétaire, mais une équipe doit toujours être affectée.

> [!NOTE]
> Les enregistrements passent en lecture seule après l'ajout et la sauvegarde d'une compagnie. Veillez donc à choisir la compagnie adéquate.

### <a name="choosing-a-different-business-unit"></a>Choix d'une autre unité fonctionnelle
Vous pouvez modifier l'unité fonctionnelle sélectionnée. Si vous choisissez un autre centre, par exemple un que vous avez créé précédemment dans CDS, il conserve son nom initial. Autrement dit, elle n'est pas suivi du code compagnie. Nous allons créer une équipe qui utilise la convention de nommage.

## <a name="person-ownership"></a>Propriété Personne
Si vous choisissez le modèle de propriété Personne, vous devez indiquer chaque représentant qui possédera de nouveaux enregistrements. L'unité fonctionnelle et l'équipe sont créées comme décrit dans la section précédente.  

## <a name="see-also"></a>Voir aussi
[À propos de [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-common-data-service.md)