---
title: "Comment configurer des entrepôts de base avec les zones d'opérations | Microsoft Docs"
description: "Si des zones d'opérations internes telles que la production ou l'assemblage existent dans les configurations entrepôt de base dans lesquelles les emplacements utilisent le champ de configuration **Zone obligatoire** et éventuellement les champs **Prélèvement requis** et **Rangement requis**, vous pouvez utiliser trois documents d'entrepôt de base suivants pour enregistrer vos activités entrepôt pour des zones d'opérations internes."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 31f057f862b72cd21ecb2c1fb59674c6485a960d
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-basic-warehouses-with-operations-areas"></a>Configurer des entrepôts de base avec les zones d'opérations
Si les zones Opérations internes telles que la production ou l'assemblage existent dans les configurations entrepôt de base dans lesquelles les emplacements utilisent le champ de configuration **Zone obligatoire** et éventuellement les champs **Prélèvement requis** et **Rangement requis**, vous pouvez utiliser les documents d'entrepôt de base suivants pour enregistrer vos activités entrepôt pour des zones Opérations internes :  

- Fenêtre **Mouvement de stock**.  
- Fenêtre**Prélèvement stock**.  
- Fenêtre **Rangement inventaire.**

> [!NOTE]
> Bien que les paramètres soient appelés **Prélèvement requis** et **Rangement requis**, vous pouvez quand même reporter les réceptions et les livraisons directement à partir des documents commerciaux sources dans les emplacements où vous cochez ces cases.  

Pour utiliser ces fenêtres avec des opérations internes, par exemple pour prélever et déplacer des composants vers la production, vous devez effectuer tout ou partie des étapes de configuration suivantes, en fonction du contrôle que vous souhaitez exercer :  

- Activez les documents de prélèvement, mouvement et rangement inventaire.  
- Définir les structures de zone par défaut pour les composantes et les produits finis s'écoulant depuis ou vers les ressources opérationnelles.  
- Créez des zones de destination et d'origine réservées à des ressources opérationnelles spécifiques pour empêcher le prélèvement des articles pour les documents sortants.

Les codes de zone qui sont configurés dans les fiches emplacement définissent un flux entrepôt par défaut pour des activités spécifiques, telles que les composantes d'un département assemblage. Des fonctionnalités supplémentaires existent pour s'assurer que des articles placés dans une zone en particulier ne peuvent ni être déplacés vers d'autres activités, ni être prélevés pour ces dernières. Pour plus d'informations, voir la section « Créer des zones composante réservées ».

Les procédures suivantes sont basées sur la configuration d'activités entrepôt de base autour d'une zone de production. Les étapes sont similaires pour d'autres zones Opérations, telles que l'assemblage, la gestion des services et les projets.  

> [!NOTE]  
>  Dans la procédure suivante, le champ de configuration **Emplacement obligatoire** dans les fiches magasin est sélectionné en tant que condition préalable car il est considéré comme point de départ de tout niveau de gestion d'entrepôt.  

## <a name="to-enable-inventory-documents-for-internal-operation-activities"></a>Pour activer les documents d'inventaire pour les opérations internes  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche emplacement que vous voulez configurer.  
3.  Sur le raccourci **Entrepôt**, cochez la case **Rangement requis** pour indiquer que lorsqu'un document source entrant ou interne avec un code de zone est libéré, il est possible de créer un document rangement inventaire ou mouvement d'inventaire.  
4.  Cochez la case **Prélèvement requis** pour indiquer que lorsqu'un document source sortant ou interne avec un code de zone est créé, il est obligatoire de créer un document prélèvement inventaire ou mouvement d'inventaire.  

## <a name="to-define-a-default-bin-structure-in-the-production-area"></a>Pour définir une structure de zone par défaut dans la zone de production  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Ouvrez l'emplacement que vous voulez configurer.  
3.  Sur le raccourci **Emplacements**, dans le champ **Code empl. atelier ouvert**, entrez le code de l'emplacement dans la zone de production comportant des composants en nombre suffisant que l'opérateur machine peut consommer sans demander une activité entrepôt pour les apporter à l'emplacement. Les articles qui sont stockés dans cette zone sont habituellement configurés pour le report automatique ou la consommation. Cela signifie que le champ **Méthode consommation** indique **Aval** ou **Amont**.  
4. Dans le champ **Code de zone avant production**, saisissez le code de la zone dans la zone de production où les composantes qui sont prélevées pour la production dans cet emplacement sont stockées par défaut avant de pouvoir être consommées. Les articles qui sont stockés dans cette zone sont habituellement configurés pour le report manuel de la consommation. Cela signifie que le champ **Méthode consommation** indique **Manuel**, **Prélèvement + Aval** ou **Prélèvement + Amont** pour les prélèvements entrepôt et les mouvements d'inventaire.  

    > [!NOTE]  
    >  Lorsque vous utilisez des prélèvements stock, le champ **Code emplacement** sur une ligne composant d'ordre de fabrication. définit l'emplacement de *prélèvement* où les composants sont déduits lors de la validation de la consommation. Lorsque vous utilisez des mouvements de stock, le **Code emplacement** sur des lignes composant d'ordre cde fabrication définit l'emplacement *placement* dans la zone Opérations où l'employé du magasin doit placer les composants.  

5. Sur le raccourci **Zones**, dans le champ **Code de zone post-production**, entrez le code de la zone dans la zone de production où les produits finis sont extraits par défaut si le processus implique une activité entrepôt. Dans les configurations entrepôt de base, l'activité est enregistrée en tant que rangement inventaire ou mouvement d'inventaire.  

Désormais, les lignes composante bon de production présentant ce code de zone par défaut nécessitent que les composantes consommées en aval soient stockées à cet emplacement. Toutefois, jusqu'à la consommation des composantes de cette zone, d'autres demandes de composantes peuvent y effectuer un prélèvement ou une consommation, car elles sont encore considérées comme du contenu zone disponible. Pour vous assurer que le contenu de la zone soit uniquement disponible pour une demande de composante qui utilise cette zone avant production, vous devez sélectionner le champ **Dédié** sur la ligne de ce code de zone dans la fenêtre **Zones** à laquelle vous accédez à partir de la fiche emplacement.

Ce graphique indique comment le champ **Code emplacement** sur les lignes composant O.F. est renseigné en fonction de votre configuration.  

![Organigramme Flux d'emplacement](media/binflow.png "BinFlow")    

## <a name="to-define-a-default-bin-structure-in-the-assembly-area"></a>Pour définir une structure de zone par défaut dans la zone d'assemblage
Les composantes pour les commandes d'assemblage ne peuvent pas être prélevées ni reportées avec des prélèvements inventaire. À la place, utilisez la fenêtre **Mouvement d'inventaire**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

En cas de prélèvement et de livraison de quantités de lignes vente assemblées pour commande, vous devez suivre certaines règles en créant les lignes prélèvement inventaire. Pour plus d'informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les prélèvements stock » dans [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).

Pour plus d'informations, voir [Gestion d'assemblage](assembly-assemble-items.md).

### <a name="to-set-up-that-an-inventory-movement-is-automatically-created-when-the-inventory-pick-for-the-assembly-item-is-created"></a>Pour configurer la création automatique d'un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration d'assemblage**, puis sélectionnez le lien associé.
2. Cochez la case **Créer des mouvements automatiquement**.

### <a name="to-set-up-the-bin-in-the-assembly-area-where-components-are-placed-by-default-before-they-can-be-consumed-in-assembly"></a>Pour configurer la zone dans la zone d'assemblage où les composantes sont stockées par défaut avant de pouvoir être consommées dans l'assemblage
La valeur de ce champ est automatiquement insérée dans le champ **Code de zone** des lignes d'ordre d'assemblage lorsque ce emplacement est saisi dans le champ **Code d'emplacement** de la ligne d'ordre d'assemblage.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Ouvrez l'emplacement que vous voulez configurer.
3. Renseignez le champ **Code de zone vers assemblage**.

### <a name="to-set-up-the-bin-in-the-assembly-area-where-finished-assembly-items-are-posted-to-when-they-are-assembled-to-stock"></a>Pour configurer la zone dans la zone d'assemblage où les éléments d'assemblage finis sont reportés lorsqu'ils sont assemblés pour stock
La valeur de ce champ est automatiquement insérée dans le champ **Code de zone** des en-têtes d'ordre d'assemblage lorsque ce code d'emplacement est entré dans le champ **Code d'emplacement** de l'en-tête d'ordre d'assemblage.

Les codes de zone qui sont configurés dans les fiches emplacement définissent un flux entrepôt par défaut pour des activités entrepôt spécifiques, telles que la consommation des composantes d'une zone d'assemblage. Des fonctionnalités supplémentaires existent pour s'assurer que des articles placés dans une zone par défaut ne peuvent ni être déplacés vers d'autres activités, ni être prélevés pour ces dernières.

> [!NOTE]
> Cette configuration s'applique uniquement aux emplacements pour lesquels le champ Zone obligatoire est sélectionné.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Ouvrez l'emplacement que vous voulez configurer.
3. Renseignez le champ **Code de zone depuis assemblage**.

### <a name="to-set-up-the-bin-where-finished-assembly-items-are-posted-to-when-they-are-assembled-to-a-linked-sales-order"></a>Pour configurer la zone au niveau de laquelle les éléments d'assemblage terminés sont reportés lorsqu'ils sont associés à un document de vente
À partir de cette zone, les articles d'assemblage sont livrés immédiatement via un prélèvement inventaire, afin d'honorer le document de vente.

> [!NOTE]
> Ce champ n'est pas disponible si l'emplacement est configuré pour utiliser les prélèvement et rangement suggérés.

Le code de zone est copié de la ligne document de vente vers l'en-tête ordre d'assemblage pour indiquer aux travailleurs à la chaîne où placer la production pour préparer sa livraison. Il est également copié dans la ligne prélèvement inventaire pour indiquer aux employés d'entrepôt où le récupérer au moment de la livraison.

> [!NOTE]
> La zone Livraison Assembler pour commande est toujours vide. Lorsque vous reportez une ligne vente assembler pour commande, le contenu de la zone fait d'abord l'objet d'un ajustement positif basé sur le résultat d'assemblage. Ensuite, il fait immédiatement l'objet d'un ajustement négatif basé sur la quantité livrée.

La valeur de ce champ est automatiquement insérée dans le champ Code de zone des lignes document de vente dont le champ **Qté à assembler pour commande** contient une quantité. Cela se produit également si le champ a la valeur **Assembler pour commande** dans le champ **Système réappro.**.

Si le champ **Code de zone livr. ass. pr comm.** est vide, alors le champ **Code de zone depuis assemblage** est utilisé. Si vous laissez les deux champs de configuration vides, la dernière zone utilisée incluant du contenu est reprise dans le champ **Code de zone** des lignes document de vente.

Le même code de zone est également copié vers le champ **Code de zone** de la ligne prélèvement inventaire qui gère la livraison de la quantité à assembler pour commande. Pour plus d'informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les prélèvements stock » dans [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Ouvrez l'emplacement que vous voulez configurer.
3. Renseignez le champ **Code de zone livr. ass. pr comm.**.

## <a name="to-create-dedicated-component-bins"></a>Pour créer des zones composante réservées
Vous pouvez spécifier que les quantités d'une zone soient protégées des prélèvements d'autres demandes que la demande de leurs objectifs actuels.

Les quantités des zones réservées peuvent encore être réservées. Par conséquent, les quantités figurant dans des zones réservées sont incluses dans le champ **Quantité totale disponible** de la fenêtre **Réservation**.

Par exemple, si un atelier est configuré avec un code de zone dans le champ **Code de zone avant production**. Les lignes composante bon de production présentant ce code de zone nécessitent que les composantes consommées en aval soient stockées à cet emplacement. Toutefois, jusqu'à la consommation des composantes de cette zone, d'autres demandes de composantes peuvent y effectuer un prélèvement ou une consommation, car elles sont encore considérées comme du contenu zone disponible. Pour vous assurer que le contenu de la zone soit uniquement disponible pour une demande de composante qui utilise cette zone avant production, vous devez sélectionner le champ **Dédié** sur la ligne de ce code de zone dans la fenêtre **Zones** à laquelle vous accédez à partir de la fiche emplacement.

La réservation d'une zone fournit une fonctionnalité similaire à l'utilisation des types de zone uniquement disponibles dans l'entreposage avancé. Pour plus d'informations, voir [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).

> [!Caution]
> Les articles situés dans des zones réservées ne sont pas protégés lorsqu'ils sont prélevés et consommés comme composantes de production à l'aide de la fenêtre Prélèvement inventaire.

1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe. Sélectionnez l'emplacement à mettre à jour.  
2.  Choisissez l'action **Zones**.  
3.  Sélectionnez le champ **Dédié** pour chaque emplacement à utiliser exclusivement pour certaines opérations internes et si vous souhaitez que les quantités soient réservées pour ces opérations internes une fois placées à cet endroit.  

> [!NOTE]  
>  L'emplacement doit être vide avant que vous puissiez sélectionner ou désactiver le champ **Dédié**.

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

