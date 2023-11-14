---
title: Comment configurer des emplacements de sorte qu’ils utilisent des zones
description: Les emplacements représentent la structure d'entrepôt de base et sont utilisés pour faire des propositions relatives à l'emplacement des articles.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/28/2023
ms.custom: bap-template
---

# Configurer des emplacements de sorte qu'ils utilisent des zones

Les zones représentent la structure de base de l’entrepôt et peuvent suggérer où placer les articles. Lorsque vous avez créé vos zones, vous pouvez définir leur contenu ou elles sont utilisées en tant que zones dynamiques sans contenu spécifié.

Pour utiliser la fonctionnalité de zone liée à l’emplacement, activez le bouton à bascule **Zone obligatoire** sur la page fiche **Zone**. Après avoir activé le bouton à bascule, le **Code de zone** et le **Code emplacement** sont disponibles sur les documents suivants :

* En-tête réception entrepôt
* Lignes réception entrepôt
* Lignes rangement entrepôt
* En-tête livraison entrepôt
* Lignes livraison entrepôt
* Lignes rangement entrepôt

Ensuite, vous définissez la circulation des articles dans la zone en spécifiant les codes de zone dans les champs de configuration qui représentent les différents flux.  

> [!NOTE]  
> Avant de pouvoir spécifier les codes de zone sur un emplacement, vous devez les créer. Pour plus d'informations, voir [Créer zones](warehouse-how-to-create-individual-bins.md).  

## Pour configurer un emplacement de sorte qu'il utilise des zones

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2. Sélectionnez l'emplacement dans lequel vous souhaitez utiliser des zones.  
3. Choisissez l'action **Modifier**.  
4. Sur le raccourci **Entrepôt**, cochez la case **Zone obligatoire**.  
5. Si vous n’avez pas recours à un prélèvement et à un rangement suggérés dans la zone, renseignez le champ **Sélection zone par déf** en y indiquant la méthode d’attribution d’une zone par défaut à un article que [!INCLUDE [prod_short](includes/prod_short.md)] doit utiliser.  
6. Ouvrez la fiche de l'emplacement pour lequel vous souhaitez configurer des zones.
7. Sur le raccourci **Zones**, sélectionnez les zones que vous voulez utiliser par défaut pour les réceptions, les livraisons, les zones entrantes et sortantes, ainsi que pour les zones atelier ouvertes.  

    Les codes de zone que vous indiquez ici s’affichent automatiquement dans les en-têtes et sur les lignes de différents documents entrepôt. Les emplacements par défaut définissent tous les placements de début ou de fin des articles dans l'entrepôt.  
8. En cas d’utilisation d’un prélèvement et d’un rangement suggérés, sélectionnez une zone pour les ajustements entrepôt. Le code de zone du champ **Code de zone ajustement** définit la zone virtuelle dans laquelle le programme enregistre les différences d’inventaire lorsque vous enregistrez :

    * Lorsque vous observez des différences enregistrées dans le journal article de l’entrepôt
    * Différences que le programme calcule lorsque vous enregistrez un inventaire entrepôt  
9. En option : Sur le raccourci **Politiques de zones**, renseignez les champs. Les champs les plus importants sont les suivants : **Politique capacité zone**, **Autoriser déconditionnement** et **Code modèle rangement**.  
10. Sur les champs **Entrepôt**, renseignez les champs **Délai désenlogement**, **Délai enlogement** et **Code calendrier principal**. Pour en savoir plus, rendez-vous sur [Configurer les calendriers de base](across-how-to-assign-base-calendars.md).

## Renseigner la zone consommation

Ce graphique indique comment le champ **Code de zone** sur les lignes composante Bon de production est renseigné en fonction de la configuration de votre zone.

:::image type="content" source="media/binflow.png" alt-text="Champ de code de zone sur les lignes de composante de bon de production.":::

## Voir aussi .

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
