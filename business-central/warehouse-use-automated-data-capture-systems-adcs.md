---
title: Utiliser des systèmes de saisie automatisée (ADCS) | Microsoft Docs
description: Vous pouvez utiliser votre système de saisie automatisée (ADCS) pour enregistrer le mouvement des articles dans l'entrepôt et certaines activités du journal, notamment les ajustements de quantité dans le journal article entrepôt et les inventaires physiques.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: barcode
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: c575dcc54ff192b2c39c1d1c2d582477a4e4361c
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3195946"
---
# <a name="use-automated-data-capture-systems-adcs"></a>Utilisation des systèmes de saisie automatisée (ADCS)

> [!NOTE]
> La solution ADCS offre un moyen pour [!INCLUDE[d365fin](includes/d365fin_md.md)] de communiquer avec des appareils portables via des services Web. Vous devez travailler avec un partenaire Microsoft qui peut fournir le lien entre le service Web et l'appareil portable spécifique. 

Vous pouvez utiliser votre système de saisie automatisée (ADCS) pour enregistrer le mouvement des articles dans l'entrepôt et certaines activités du journal, notamment les ajustements de quantité dans le journal article entrepôt et les inventaires physiques. ADCS implique généralement la numérisation des codes à barres.

Pour utiliser votre système de saisie automatisée, vous devez attribuer un identificateur article à chaque article stocké dans l'entrepôt. Vous devez également configurer les écrans, fonctions de portable, échanges de données, et spécifier des paramètres pour les champs contrôlant l'ADCS. Vous spécifiez s'il faut utiliser l'ADCS sur la fiche emplacement d'un entrepôt.

En fonction des besoins de votre entrepôt, définissez la quantité d'informations affichées dans la configuration des mini-formulaires pour un terminal de saisie portable donné. Voici des exemples d'informations que vous pouvez afficher :  

- Données des tables dans [!INCLUDE[d365fin](includes/d365fin_md.md)], par exemple la liste des documents prélèvement à partir desquels l'utilisateur peut effectuer une sélection.  
- Trier les informations.  
- Messages affichant les confirmations ou erreurs sur les activités effectuées et enregistrées par l'utilisateur de périphérique mobile.

## <a name="to-enable-web-services-for-adcs"></a>Pour activer les services Web pour ADCS
Pour utiliser Automated Data Capture System, vous devez activer le service Web ADCS.  

## <a name="to-enable-and-publish-the-adcs-web-service"></a>Pour activer et publier le service Web ADCS  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Services Web**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.  
3. Sur la page **Services Web**, entrez les informations suivantes sur une nouvelle ligne :  

    |Champ|Valeur|  
    |---------------------------------|-----------|  
    |**Type d'objet**|Codeunit|  
    |**Code objet**|7714|  
    |**Nom du service**|ADCS **Important :** Vous devez nommer le service **ADCS**.|  

5. Cochez la case **Publié**.  
6. Choisissez le bouton **OK**.  

## <a name="to-set-up-a-warehouse-to-use-adcs"></a>Pour configurer le module Gestion d'entrepôt  
Pour utiliser le système de saisie automatisée, vous devez indiquer quels entrepôts utilisent cette technologie.  

> [!NOTE]  
>  Il est recommandé de ne pas configurer un entrepôt pour qu'il utilise la saisie automatisée si cet entrepôt utilise également une stratégie de capacité de zone.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **emplacements**, puis sélectionnez le lien associé.
2.  Sélectionnez un entrepôt dans la liste pour laquelle vous souhaitez activer la saisie automatisée, puis sélectionnez l'action **Modifier**.
3. Sur la page **Fiche emplacement**, cochez la case **Saisie automatisée**.  

## <a name="to-specify-an-item-to-use-adcs"></a>Pour spécifier un article pour utiliser votre système de saisie automatisée  
À chaque article entrepôt que vous souhaitez utiliser avec le système de saisie automatisée doit être affecté un code d'identification pour le lier à son numéro. Par exemple, vous pouvez utiliser le code barre de l'article comme code d'identification. Un article peut également avoir plusieurs codes d'identification. Cela peut s'avérer utile dans le cas où un article est disponible dans plusieurs unités de mesure (par exemple, des pièces et des palettes). Dans ce cas, il convient d'affecter un code à chaque identificateur.    

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2.  Sélectionnez un élément dans la liste qui fait partie de votre solution ADCS, puis sélectionnez l'action **Modifier**.
3. Sur la page **Fiche article**, sélectionnez l'action **Identificateurs**.
4. Sur la page **Identificateurs article**, sélectionnez l'action **Nouveau**.
5. Dans le champ **Code**, spécifiez l'identifiant de l'article. Par exemple, il peut s'agir du numéro de code barre de l'article.  

    Vous pouvez également entrer un **code variante** et le code **unité de mesure**.  

6. Si nécessaire, entrez plusieurs codes pour chaque article.
7. Cliquez sur le bouton **OK**.  
8.  Pour consulter les informations, choisissez le champ **Code identificateur** pour ouvrir la page **Identificateurs article**.

## <a name="to-add-an-adcs-user"></a>Pour ajouter un utilisateur ADCS  
Vous pouvez ajouter n'importe quel utilisateur pour l'utilisation d'un système de saisie automatisé (ADCS). Dans ce cas, l'utilisateur doit également fournir un mot de passe. Éventuellement, vous pouvez également indiquer une connexion qui identifie l'utilisateur ADCS en tant que magasinier. Le mot de passe de l'utilisateur ADCS peut être différent du mot de passe d'ouverture de session Windows de l'utilisateur. Pour en savoir plus, voir [Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md).

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Utilisateurs ADCS**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **Nom**, entrez un nom pour l'utilisateur. Le nom ne peut pas contenir plus de 20 caractères, espaces compris.  
4.  Entrez un mot de passe dans le champ **Mot de passe**. Le mot de passe est masqué.  

### <a name="to-specify-that-a-warehouse-employee-is-an-adcs-user"></a>Pour spécifier qu'un employé d'entrepôt est un utilisateur ADCS  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Employés d'entrepôt**, puis sélectionnez le lien associé.  
2.  Si nécessaire, ajoutez un nouveau magasinier. Pour plus d'informations, voir [Configurer des employés d'entrepôt](warehouse-how-to-set-up-warehouse-employees.md).  
3.  Choisissez l'action **Modifier la liste**.  
4.  Sélectionnez un magasinier dans la liste. Dans le champ **Utilisateur ADCS**, cliquez sur la flèche déroulante, puis sélectionnez le nom d'un utilisateur ADCS dans la liste.  

> [!NOTE]  
>  L'entrepôt par défaut de l'employé doit utiliser la saisie automatisée.

## <a name="to-create-and-customize-miniforms"></a>Pour créer et personnaliser des mini-formulaires
Vous utilisez des écrans pour décrire les informations que vous souhaitez présenter sur un terminal de saisie portable. Par exemple, vous pouvez créer des écrans pour prendre en charge l'activité entrepôt de prélèvement des articles. Après avoir créé un mini-formulaire, vous pouvez lui ajouter des fonctions pour les tâches qu'un utilisateur effectue couramment avec des terminaux de saisie portables, par exemple, déplacer une ligne vers le haut ou vers le bas.  

> [!NOTE] 
> Pour appliquer ou modifier la fonctionnalité d'une fonction mini-formulaire, vous devez créer un codeunit pour le champ **Codeunit gestion** pour exécuter l'action ou la réponse requise. Vous pouvez en savoir plus sur la fonctionnalité ADCS en examinant les unités de codage, telles que 7705, 7706, 7712 et 7713.  

### <a name="to-create-a-miniform-for-adcs"></a>Pour créer un mini-formulaire de saisie automatisée  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Mini-formulaires**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **Code**, saisissez le code du mini-formulaire. Entrez éventuellement des valeurs dans tous les autres champs.  

    Sélectionnez le champ **Mettre à la volée l'écran** pour indiquer que l'écran est le premier formulaire que l'utilisateur voit à l'ouverture de session.  

4.  Sur le raccourci **Lignes**, définissez les champs figurant sur le mini-formulaire. L'ordre dans lequel vous saisissez les lignes est celui dans lequel les lignes apparaîtront sur le terminal de saisie portable.  

Après avoir créé un mini-formulaire, vous devez créer des fonctions et associer une fonctionnalité aux différentes entrées de clavier.  

### <a name="to-customize-miniform-functions"></a>Pour personnaliser les fonctions de mini-formulaire  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Mini-formulaires**, puis sélectionnez le lien associé.  
2.  Sélectionnez un mini-formulaire dans la liste, puis sélectionnez l'action **Modifier**.  
3.  Choisissez l'action **Fonctions**.  
4.  Dans la liste déroulante **Code fonction**, sélectionnez un code pour représenter la fonction que vous souhaitez associer au mini-formulaire. Par exemple, vous pouvez sélectionner ESC, qui associe une fonctionnalité à l'appui sur la touche Échap.  

## <a name="see-also"></a>Voir aussi  
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
