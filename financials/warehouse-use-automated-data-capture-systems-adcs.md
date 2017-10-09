---
title: "Utiliser des systèmes de saisie automatisée (ADCS) | Microsoft Docs"
description: "Vous pouvez utiliser votre système de saisie automatisée (ADCS) pour enregistrer le mouvement des articles dans l'entrepôt et certaines activités du journal, notamment les ajustements de quantité dans le journal article entrepôt et les inventaires physiques."
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/18/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 56d191c465b611c1764cf3c97e507c4952fe6287
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-enable-automated-data-capture-systems-adcs"></a>Procédure : activer les systèmes de saisie automatisée (ADCS)
Vous pouvez utiliser votre système de saisie automatisée (ADCS) pour enregistrer le mouvement des articles dans l'entrepôt et certaines activités du journal, notamment les ajustements de quantité dans le journal article entrepôt et les inventaires physiques.  

Pour utiliser votre système de saisie automatisée, vous devez attribuer un identificateur article à chaque article de l'entrepôt. Vous devez également configurer les écrans, fonctions de portable, échanges de données, et spécifier des paramètres pour les champs contrôlant l'ADCS. Vous spécifiez s'il faut utiliser l'ADCS sur la fiche emplacement d'un entrepôt.

En fonction des besoins de votre entrepôt, définissez la quantité d'informations affichées dans la configuration des mini-formulaires pour un terminal de saisie portable donné. Voici des exemples d'informations que vous pouvez afficher :  

- Données des tables dans [!INCLUDE[d365fin](includes/d365fin_md.md)], par exemple la liste des documents prélèvement à partir desquels l'utilisateur peut effectuer une sélection.  
- Trier les informations.  
- Messages affichant les confirmations ou erreurs sur les activités effectuées et enregistrées par l'utilisateur de périphérique mobile.

Pour plus d'informations, voir [Configuration d'un système de saisie automatisée](https://msdn.microsoft.com/en-us/library/dd338742.aspx) sur MSDN.

## <a name="to-set-up-a-warehouse-to-use-adcs"></a>Pour configurer le module Gestion d'entrepôt  
Pour utiliser le système de saisie automatisée, vous devez indiquer quels entrepôts utilisent cette technologie.  

> [!NOTE]  
>  Il est recommandé de ne pas configurer un entrepôt pour qu'il utilise la saisie automatisée si cet entrepôt utilise également une stratégie de capacité de zone.

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Emplacements**, puis sélectionnez le lien associé.
2.  Sélectionnez un entrepôt dans la liste pour laquelle vous souhaitez activer la saisie automatisée, puis sélectionnez l'action **Modifier**.
3. Dans la fenêtre **Fiche emplacement**, cochez la case **Saisie automatisée**.  

## <a name="to-specify-an-item-to-use-adcs"></a>Pour spécifier un article pour utiliser votre système de saisie automatisée  
À chaque article entrepôt que vous souhaitez utiliser avec le système de saisie automatisée doit être affecté un code d'identification pour le lier à son numéro. Par exemple, vous pouvez utiliser le code barre de l'article comme code d'identification. Un article peut également avoir plusieurs codes d'identification. Cela peut s'avérer utile dans le cas où un article est disponible dans plusieurs unités de mesure (par exemple, des pièces et des palettes). Dans ce cas, il convient d'affecter un code à chaque identificateur.    

1.  Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.  
2.  Sélectionnez un élément dans la liste qui fait partie de votre solution ADCS, puis sélectionnez l'action **Modifier**.
3. Dans la fenêtre **Fiche article**, sélectionnez l'action **Identificateurs**.
4. Dans la fenêtre **Identificateurs article**, sélectionnez l'action **Nouveau**.
5. Dans le champ **Code**, spécifiez l'identifiant de l'article. Par exemple, il peut s'agir du numéro de code barre de l'article.  

    Vous pouvez également entrer un **code variante** et le code **unité de mesure**.  

6. Si nécessaire, entrez plusieurs codes pour chaque article.
7. Cliquez sur le bouton **OK**.  
8.  Pour consulter les informations, choisissez le champ **Code identificateur** pour ouvrir la fenêtre **Identificateurs article**.

## <a name="to-add-an-adcs-user"></a>Pour ajouter un utilisateur ADCS  
Vous pouvez ajouter n'importe quel utilisateur pour l'utilisation d'un système de saisie automatisé (ADCS). Dans ce cas, l'utilisateur doit également fournir un mot de passe. Éventuellement, vous pouvez également indiquer une connexion qui identifie l'utilisateur ADCS en tant que magasinier. Le mot de passe de l'utilisateur ADCS peut être différent du mot de passe d'ouverture de session Windows de l'utilisateur. Pour en savoir plus, reportez-vous à [Procédure : gérer les utilisateurs et les autorisations](ui-how-users-permissions.md).

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Utilisateurs ADCS**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **Nom**, entrez un nom pour l'utilisateur. Le nom ne peut pas contenir plus de 20 caractères, espaces compris.  
4.  Entrez un mot de passe dans le champ **Mot de passe**. Le mot de passe est masqué.  

### <a name="to-specify-that-a-warehouse-employee-is-an-adcs-user"></a>Pour spécifier qu'un employé d'entrepôt est un utilisateur ADCS  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2.  Si nécessaire, ajoutez un nouveau magasinier. Pour plus d'informations, reportez vous à [Procédure : configurer des employés d'entrepôt](warehouse-how-to-set-up-warehouse-employees.md).  
3.  Choisissez l'action **Modifier la liste**.  
4.  Sélectionnez un magasinier dans la liste. Dans le champ **Utilisateur ADCS**, cliquez sur la flèche déroulante, puis sélectionnez le nom d'un utilisateur ADCS dans la liste.  

> [!NOTE]  
>  L'entrepôt par défaut de l'employé doit utiliser la saisie automatisée.

## <a name="to-create-and-customize-miniforms"></a>Pour créer et personnaliser des mini-formulaires
Vous utilisez des écrans pour décrire les informations que vous souhaitez présenter sur un terminal de saisie portable. Par exemple, vous pouvez créer des écrans pour prendre en charge l'activité entrepôt de prélèvement des articles. Après avoir créé un mini-formulaire, vous pouvez lui ajouter des fonctions pour les tâches qu'un utilisateur effectue couramment avec des terminaux de saisie portables, par exemple, déplacer une ligne vers le haut ou vers le bas.  

Pour appliquer ou modifier la fonctionnalité d'une fonction mini-formulaire, vous devez créer un codeunit ou en modifier un existant pour exécuter la tâche ou la réponse requise. Pour en savoir plus sur la fonctionnalité de saisie automatisée, examinez les codeunits tels que 7705, qui permet de gérer la fonctionnalité de connexion. Le codeunit 7705 indique comment fonctionne un mini-formulaire de type fiche.  

### <a name="to-create-a-miniform-for-adcs"></a>Pour créer un mini-formulaire de saisie automatisée  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Mini-formulaires**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **Code**, saisissez le code du mini-formulaire. Entrez éventuellement des valeurs dans tous les autres champs.  

    Sélectionnez le champ **Mettre à la volée l'écran** pour indiquer que l'écran est le premier formulaire que l'utilisateur voit à l'ouverture de session.  

4.  Sur le raccourci **Lignes**, définissez les champs figurant sur le mini-formulaire. L'ordre dans lequel vous saisissez les lignes est celui dans lequel les lignes apparaîtront sur le terminal de saisie portable.  

Après avoir créé un mini-formulaire, vous devez créer des fonctions et associer une fonctionnalité aux différentes entrées de clavier.  

### <a name="to-add-support-for-a-function-key"></a>Pour ajouter la prise en charge d'une touche de fonction  
1.  Ajoutez le code similaire à l'exemple suivant au fichier the.xsl du plug-in. Cela crée une fonction pour la touche **F6**. Les informations de séquence des touches peuvent être obtenues auprès du fabricant du périphérique.  
    ```  
    <xsl:template match="Function[.='F6']">  
      <Function Key1="27" Key2="91" Key3="49" Key4="55" Key5="126" Key6="0"><xsl:value-of select="."/></Function>  
    </xsl:template>  

    ```  
2.  Dans l'environnement de développement [!INCLUDE[d365fin](includes/d365fin_md.md)], ouvrez la table 7702 et ajoutez un code représentant la nouvelle touche. Dans cet exemple, créez une clé nommée **F6**.  
3.  Ajoutez le code C/AL à la fonction appropriée du codeunit spécifique du mini-formulaire afin de gérer la touche de fonction.  

### <a name="to-customize-miniform-functions"></a>Pour personnaliser les fonctions de mini-formulaire  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Mini-formulaires**, puis sélectionnez le lien associé.  
2.  Sélectionnez un mini-formulaire dans la liste, puis sélectionnez l'action **Modifier**.  
3.  Choisissez l'action **Fonctions**.  
4.  Dans la liste déroulante **Code fonction**, sélectionnez un code pour représenter la fonction que vous souhaitez associer au mini-formulaire. Par exemple, vous pouvez sélectionner ESC, qui associe une fonctionnalité à l'appui sur la touche Échap.  

Dans l'environnement de développement [!INCLUDE[d365fin](includes/d365fin_md.md)], modifiez le code du champ **Traité par Codeunit** pour créer ou modifier le code visant à exécuter l'action ou la réponse requise.

Pour plus d'informations, voir [Configuration d'un système de saisie automatisée](https://msdn.microsoft.com/en-us/library/dd338742.aspx) sur MSDN.

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

