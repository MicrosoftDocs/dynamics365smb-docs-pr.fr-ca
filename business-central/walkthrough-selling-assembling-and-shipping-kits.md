---
title: 'Vente, assemblage et expédition de kits'
description: 'Pour prendre en charge un inventaire juste-à-temps (JIT), des ordres d’assemblage peuvent être créés automatiquement et associés dès que la ligne document de vente est créée.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 06/24/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="walkthrough-selling-assembling-and-shipping-kits"></a>Procédure pas-à-pas : vente, assemblage et expédition de kits

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

Pour prendre en charge un inventaire juste-à-temps (JIT) et permettre la personnalisation des produits conformément aux demandes client, il est possible de créer des ordres d’assemblage et de les lier automatiquement dès que la ligne document de vente est créée. Le lien entre la demande vente et l’approvisionnement d’assemblage permet aux préparateurs de documents de vente de personnaliser l’article d’assemblage et de proposer des dates de livraison en fonction de la disponibilité des composantes. En outre, la consommation et le résultat d'assemblage sont reportés automatiquement avec la livraison du document de vente associé.  

La fonctionnalité spéciale permet de gérer l’expédition des quantités « assembler pour commande », dans des configurations d’entrepôt de base et avancées. Lorsque les travailleurs chargés de l'assemblage finissent d'assembler les pièces ou l'ensemble de la quantité à assembler pour commande, ils l'enregistrent dans le champ **Qté à livrer** de la ligne livraison entrepôt dans les configurations avancées et sélectionnent ensuite **Reporter livraison**. Par conséquent, le résultat d’assemblage correspondant est reporté, y compris la consommation de composantes liée, et une livraison vente de la quantité est reportée pour le document de vente lié. Cette procédure pas à pas présente le processus entrepôt avancé.  

Dans les configurations entrepôt de base, lorsqu’une quantité à assembler pour commande est prête à être livrée, l'employé d'entrepôt responsable reporte un prélèvement inventaire pour les lignes document de vente. Cela crée un mouvement d'inventaire pour les composantes et reporte le résultat d’assemblage et la livraison du document de vente. Pour plus d’informations, reportez-vous à [Traitement des articles assembler pour commande dans les prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas

Cette procédure pas à pas présente les tâches suivantes :  

### <a name="setting-up-assembly-items"></a>Configuration des articles d’assemblage

Les articles d’assemblage sont caractérisés par leur système de réapprovisionnement et la nomenclature d’assemblage. La politique d’assemblage de l’article peut être « assembler pour commande » ou « assembler pour inventaire ». Cette section couvre les tâches suivantes :  

-   Définition du système de réapprovisionnement et de la politique d’assemblage appropriés sur une nouvelle fiche d’article d’assemblage.  
-   Création d’une nomenclature d’assemblage qui répertorie les composantes d’assemblage et la ressource incluse dans l’article d’assemblage.  

### <a name="selling-customized-assembly-items"></a>Vente d’articles d’assemblage personnalisés

[!INCLUDE[prod_short](includes/prod_short.md)] offre la flexibilité d'entrer une quantité en inventaire et une quantité « assembler pour commande » sur une ligne document de vente. Cette section couvre les tâches suivantes :  

-   Création d'une ligne document de vente uniquement « assembler pour commande » lorsque la quantité totale n'est pas disponible et doit être assemblée avant la livraison.  
-   Personnalisation des articles « assembler pour commande ».  
-   Nouveau calcul du prix unitaire d’un article d’assemblage personnalisé.  
-   Création d’une ligne document de vente mixte à laquelle une partie de la quantité de ventes provient de l'inventaire et la partie restante doit être assemblée avant la livraison.  
-   Compréhension des avertissements de disponibilité des articles « assembler pour commande ».  

### <a name="planning-for-assembly-items"></a>Planification pour les articles d’assemblage

L’offre et la demande d’assemblage sont traitées par le système de planification, tout comme pour les achats, les transferts et la production. Cette section couvre les tâches suivantes :  

-   Exécution d’un planning régénératif pour les articles utilisant une demande de vente pour l’approvisionnement assemblé.  
-   Génération d’un ordre d’assemblage en vue de répondre à la quantité de la ligne vente au plus tard à la date livraison demandée.  

### <a name="assembling-items"></a>Assemblage des articles

Les ordres d'assemblage fonctionnent d'une manière similaire aux bons de production, sauf que la consommation et la production sont enregistrées et reportées directement à partir de la commande. Lorsque les articles sont assemblés pour inventaire, l’ouvrier d’assemblage a un accès total à tous les champs d’en-tête et de ligne. Lorsque les articles sont assemblés pour une commande lorsque la quantité et la date sont promises au client, certains champs de l’ordre d’assemblage ne sont pas modifiables. Dans ce cas, le report d'assemblage est exécuté à partir de la livraison entrepôt pour le document de vente associé. Cette section couvre les tâches suivantes.  

-   Enregistrement et report de la consommation d’assemblage et de la production dans l'inventaire.  
-   Accès à une ligne livraison entrepôt à partir d'un ordre d'assemblage pour commande pour enregistrer le travail d'assemblage.  
-   Accès à un ordre d'assemblage pour commande à partir d'une ligne livraison entrepôt pour afficher automatiquement les données entrées.  

### <a name="shipping-assembly-items-from-stock-and-assembled-to-order"></a>Expédition d’articles d’assemblage, à partir du stock et assemblés pour former une commande

Il existe une fonctionnalité spéciale qui permet de gérer l'expédition des quantités à assembler pour commande. Cette section couvre les tâches suivantes :  

-   Création d’un prélèvement entrepôt pour des articles d’assemblage d'inventaire et pour des composantes d’assemblage à assembler avant la livraison.  
-   Enregistrement des prélèvements entrepôt pour des composantes d’assemblage, puis pour des articles d’assemblage.  
-   Accès à un ordre d’assemblage à partir d’une livraison entrepôt pour afficher des composantes sélectionnées ou consommées.  
-   Expédition de quantités « assembler pour commande ».  
-   Livraison d’articles d’assemblage en inventaire.  

## <a name="roles"></a>Rôles

Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

-   Préparateur de commandes vente  
-   Planificateur  
-   Ouvrier d’assemblage  
-   Employé en charge du prélèvement  
-   Responsable expédition  

## <a name="prerequisites"></a>Conditions préalables

Avant d'exécuter cette procédure pas à pas, veuillez suivre les instructions ci-dessous :  

-   Installez [!INCLUDE[prod_short](includes/prod_short.md)].  
-   Devenez employé d'entrepôt dans un emplacement BLANC en procédant comme suit :  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2.  Choisissez le champ **Code utilisateur** et sélectionnez votre propre compte utilisateur sur la page **Utilisateurs**.  
3.  Dans le champ **Code d'emplacement**, entrez BLANC.  
4.  Sélectionnez le champ **Par défaut**.  

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

Préparez l'emplacement BLANC pour le traitement d’assemblage en procédant comme suit :  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2.  Ouvrez la fiche emplacement de l'emplacement BLANC.  
3.  Dans le raccourci **Zones**, entrez **W-10-0001** dans le champ **Code de zone vers assemblage**.  

    Lorsque vous entrez ce code zone qui n’est pas utilisé pour le prélèvement, toutes les lignes d’ordre d’assemblage sont prêtes à recevoir leurs composantes dans la zone.  

4.  Dans le champ **Code de zone depuis assemblage**, entrez **W-01-0001**.  

    Lorsque vous entrez ce code de zone de prélèvement, des articles d’assemblage finis sont sortis dans la zone.  

Supprimez le délai par défaut pour les processus internes en procédant comme suit :  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration production**, puis choisissez le lien associé.  
2.  Sur la page **Configuration fabrication**, sous le raccourci **Planification**, supprimez la valeur dans le champ **Délai de sécurité par défaut**.  

<!-- Create inventory for assembly components by following [Prepare Sample Data](walkthrough-selling-assembling-and-shipping-kits.md#prepare-sample-data).   -->

## <a name="story"></a>Scénario

Le 23 janvier, Susan, préparatrice de documents de vente, accepte une commande de The Device Shop pour trois unités de kit B, c’est-à-dire un article « assembler pour commande ». Les trois unités sont personnalisées et doivent contenir la carte graphique élevée et un bloc de RAM supplémentaire. Les lecteurs de disque sont mis à niveau vers DWD car les lecteurs de CD ne sont pas disponibles. Susan sait que les unités peuvent être assemblées immédiatement, et laisse la date de livraison suggérée du 23 janvier.  

En même temps, le client commande quinze unités du kit A avec une demande spéciale de cinq unités personnalisées contenant une carte graphique. Même si le kit A est généralement un article « assembler pour stock », le préparateur de commandes combine les quantités des lignes vente pour vendre dix unités du stock et assembler cinq unités personnalisées dans la commande. Les dix unités de kit A ne sont pas disponibles et doivent d’abord être fournies dans l'inventaire par un ordre d’assemblage en fonction de la politique d’assemblage de l’article. Susan apprend du département d’assemblage que les unités du kit A ne peuvent pas être fournies pour la semaine en cours. Susan définit la date de livraison de la deuxième ligne document de vente, pour la quantité « assembler pour commande » et la quantité en inventaire, sur le 27 janvier et informe le client que les 15 unités du kit A seront livrées quatre jours après les trois unités du kit B. Pour signaler au département livraison que ce document de vente requiert un processus d’assemblage, Susan crée le document livraison entrepôt depuis le document de vente.  

Eduardo, planificateur, exécute la feuille planification et génère un ordre d’assemblage pour dix unités standard du kit A avec une date d’échéance interne du 27 janvier.  

Sammy, responsable des livraisons, obtient trois lignes livraison entrepôt pour le document de vente : une ligne pour les trois unités « assembler pour commande » proprement dites, une ligne pour les cinq unités « assembler pour commande » de la ligne document de vente mixte et une ligne pour les dix unités « assembler pour inventaire » de la ligne document de vente mixte. Sammy crée un document prélèvement entrepôt pour toutes les composantes d’assemblage qui sont nécessaires pour assembler le total de huit unités « assembler pour commande » dans le document livraison entrepôt.  

Jean, employé en charge du prélèvement, récupère les composantes pour toutes les quantités « assembler pour commande » dans le document livraison entrepôt et les apporte à la zone d’assemblage. John indique la quantité d’articles à traiter et enregistre le prélèvement entrepôt.  

Linda assemble les trois unités « assembler pour commande » du kit B. Les composantes ont été prélevées, et elle n’enregistre pas les quantités de production et de sortie ou valide la commande, car les deux actions sont effectuées automatiquement via les lignes livraison entrepôt liées.  

Sammy enregistre la quantité assemblée sur la ligne livraison entrepôt et reporte la livraison des trois unités de kit B. La première ligne du document de vente est mise à jour comme étant livrée. L'ordre d'assemblage lié reste ouvert jusqu'à ce que le document de vente soit entièrement facturé. Les deux lignes livraison entrepôt, une « assembler pour commande » et une « assembler pour inventaire », pour le kit A avec des dates d'échéance (27 janvier) toujours ouvertes.  

Le 27 janvier, Linda traite deux ordres d’assemblage pour le kit A. Le premier ordre est la commande ATO de cinq unités, qu’elle traite différemment de la commande ATO pour le kit B qu’elle a traitée le 23 janvier. Dans le cadre de cette commande, Linda est autorisée à accéder à la ligne livraison entrepôt elle-même pour enregistrer le travail d’assemblage accompli. Les composantes nécessaires sont prêtes dans le département Assemblage, au fur et à mesure qu’elles ont été prélevées avec des composantes pour le kit B.  

Le second ordre d’assemblage est l’ordre « assembler pour stock » pour dix unités qui ont été créées par le système de planification. Dans cette commande « assembler pour stock », Linda exécute toutes les actions associées depuis l’ordre d’assemblage. Linda crée un document prélèvement entrepôt pour les composantes d’assemblage nécessaires pour assembler les dix unités. Lorsque les ordinateurs sont assemblés, Linda reporte l’ordre d’assemblage et signale par conséquent que les articles sont disponibles dans l'inventaire et peuvent être prélevés pour livraison.  

Sammy crée un document prélèvement entrepôt pour toutes les quantités qui restent avant que la livraison entrepôt puisse être reportée. Un document prélèvement est créé pour les dix unités de kit A juste terminées. Les composantes nécessaires pour assembler les cinq unités du kit A pour commande ont été prélevées le 23 janvier.  

Jean apporte les dix unités de kit A de l’entrepôt à la zone livraison spécifiée, enregistre la quantité à traiter, puis enregistre le prélèvement.  

Sammy emballe les dix unités « assembler pour stock » avec les cinq unités « assembler pour commande » que Linda a assemblées plus tôt dans la journée. Sammy renseigne la quantité à livrer sur les deux lignes, puis valide la dernière livraison pour The Device Shop. L'ordre d'assemblage associé pour les cinq unités du kit A est automatiquement reporté. La seconde ligne du document de vente est mise à jour comme étant livrée. Deux ordres d’assemblage liés restent ouverts jusqu’à ce que le document de vente soit facturé et fermé.  

Lorsque le document de vente est reporté ultérieurement comme étant entièrement facturé, le document de vente et les ordres d'assemblage associés sont supprimés.  

## <a name="prepare-sample-data"></a>Préparation d'exemples de données

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article entrepôt**, puis choisissez le lien associé.  
2.  Choisissez le champ **Nom de lot**, puis sélectionnez le journal par défaut.  
3.  Créez des ajustements positifs d'inventaire à l'emplacement BLANC à la date de travail, le 23 janvier, en entrant les informations suivantes.  

    |**N° d'article**|**Code zone**|**Code de zone**|**Quantité**|  
    |-----------------------------------|---------------------------------------|--------------------------------------|------------------------------------|  
    |80001|PRELEV.|W-01-0001|2.0|  
    |80005|PRELEV.|W-01-0001|2.0|  
    |80011|PRELEV.|W-01-0001|2.0|  
    |80014|PRELEV.|W-01-0001|20|  
    |80203|PRELEV.|W-01-0001|20|  
    |80209|PRELEV.|W-01-0001|20|  

4.  Choisissez l'action **Enregistrer**, puis cliquez sur le bouton **Oui**.  

    Ensuite, synchronisez les nouvelles écritures entrepôt avec l'inventaire.  

5.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article**, puis choisissez le lien associé. La page **Journal article** s'ouvre.  
6.  Sélectionnez l'action **Calculer ajustement entrepôt**.  
7.  Sur la page **Calculer ajustement entrepôt**, cliquez sur le bouton **OK** .  
8.  Sur la page **Journal article**, choisissez l'action **Reporter**, puis cliquez sur le bouton **Oui**.  

### <a name="creating-the-assembly-items"></a>Création des articles d’assemblage

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Créez le premier article d’assemblage sur la base des informations suivantes.  

    |Champ|Valeur|  
    |---------------------------------|-----------|  
    |**Description**|Kit A - PC de base|  
    |**Unité de mesure de base**|PCS|  
    |**Code de catégorie**|Divers|  
    |**Système de réapprovisionnement**|Assemblage|  
    |**Politique d'assemblage**|Assembler pour stock|  
    |**Politique réapprovisionnement**|Lot pour lot|  

    > [!NOTE]  
    >  Le kit A est généralement fourni par assemblage pour le stockage et a donc une méthode de réapprovisionnement pour le faire passer dans la planification générale de l’approvisionnement.  

4.  Choisissez l'action **Assemblage**, puis sélectionnez **Nomenclature d'assemblage**.  
5.  Définissez une nomenclature d’assemblage pour le kit A avec les informations suivantes.  

    |**Type**|**N°**|**Quantité par**|  
    |-------------------------------|------------------------------|---------------------------------------|  
    |Article|80001|1|  
    |Article|80011|1|  
    |Article|80209|1|  
    |Ressource|Linda|1|  

6.  Créez le second article d’assemblage sur la base des informations suivantes.  

    |Champ|Valeur|  
    |---------------------------------|-----------|  
    |**Description**|Kit B - PC pro|  
    |**Unité de mesure de base**|PCS|  
    |**Code de catégorie**|Divers|  
    |**Système de réapprovisionnement**|Assemblage|  
    |**Politique d'assemblage**|Assembler pour commande|  

    > [!NOTE]  
    >  Le kit B est généralement fourni par assemblage pour commande et donc n’a pas une méthode de réapprovisionnement, parce qu’il ne doit pas faire partie de la planification générale de l’approvisionnement.  

7.  Choisissez l'action **Assemblage**, puis sélectionnez **Nomenclature d'assemblage**.  
8.  Définissez une nomenclature d’assemblage pour le kit B avec les informations suivantes.  

    |**Type**|**N°**|**Quantité par**|  
    |-------------------------------|------------------------------|---------------------------------------|  
    |Article|80005|1|  
    |Article|80014|1|  
    |Article|80210|1|  
    |Ressource|Linda|1|  

### <a name="selling-the-assembly-items"></a>Vente des articles d’assemblage

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Créez deux lignes document de vente pour le client 62000, The Device Shop, à la date de travail avec les informations suivantes.  

    |**Type**|**Description**|**Quantité**|Qté vers Assembler pour commande|Date de livraison|  
    |--------------|---------------------|------------------|-------------------------------|-------------------|  
    |Article|Kit B - PC pro|3|3|23 janvier|  
    |Article|Kit A - PC de base|15|5|27 janvier|  

    > [!NOTE]  
    >  Le problème de disponibilité suivant existe pour la ligne document de vente pour le kit B :  
    >   
    >  -   La composante d’assemblage 80210 n’est pas disponible. Cela signifie que les trois unités spécifiées de kit B ne peuvent pas être assemblées, indiquées par **0** dans le champ **Capacité d'assembler** sur la page **Disponibilité assemblage**.  
    >   
    >  Le problème de disponibilité suivant existe pour la ligne document de vente pour le kit A :  
    >   
    >  -   Les dix unités de kit A ne sont pas disponibles. Ceci indique au système de planification que la quantité doit être assemblée pour l'inventaire.  

    Ensuite, personnalisez la document de vente.  

4.  Sélectionnez la ligne document de vente pour trois unités du kit B.  
5.  Sur le raccourci **Lignes**, sélectionnez **Ligne**, puis **Assembler pour commande** et **Lignes d'assemblage pour commande**.  
6.  Sur la page **Lignes Assembler pour commande**, sur la ligne d'ordre d'assemblage pour l'article 80014, entrez **2** dans le champ **Quantité par**.  
7.  Sur la ligne d'ordre d'assemblage pour l'article 80210, choisissez le champ **N°** , puis sélectionnez l'article 80209 à la place.  
8.  Créez une ligne ordre d’assemblage à l’aide des informations suivantes.  

    |Type|N°|Quantité par|  
    |----------|---------|------------------|  
    |Article|80203|1|  

9. Fermez la page **Lignes d'assemblage pour commande**.  

    Ensuite, mettez à jour le prix unitaire du kit B en fonction de la personnalisation que vous venez d’exécuter. Prenez note de la valeur actuelle dans le champ **Prix unitaire HT**.  

10. Sur le raccourci **Lignes**, sélectionnez **Ligne**, puis **Assembler pour commande** et **Prix relation**.  
11. Cliquez sur le bouton **Oui**. Prenez note de la valeur augmentée dans le champ **Prix unitaire HT**.  
12. Sélectionnez la ligne document de vente pour 15 unités du kit A.  
13. Sur le raccourci **Lignes**, sélectionnez **Ligne**, puis **Assembler pour commande** et **Lignes d'assemblage pour commande**.  
14. Sur la page **Lignes Assembler pour commande**, créez une ligne ordre d'assemblage à l'aide des informations suivantes.  

    |Type|N°|Quantité par|  
    |----------|---------|------------------|  
    |Article|80203|1|  

     Ensuite, modifiez la date de livraison de la deuxième ligne document de vente selon la programmation d'assemblage.  

15. Sur la ligne document de vente de 15 unités du kit A, entrez **01-27-2014** **Date de livraison**.  
16. Sélectionnez l'action **Lancer**.  
17. Choisissez l'action **Créer livraison entrepôt**.  
18. Fermez le document de vente.  

### <a name="planning-for-the-unavailable-ats-items"></a>Planification pour les articles « assembler pour stock » non disponibles

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille planification**, puis choisissez le lien associé.  
2.  Choisissez l'action **Calculer planning régénératif**.  
3.  Sur la page **Calculer planning**, définissez les filtres suivants.  

    |Date début|Date de fin|N°|  
    |-------------------|-----------------|---------|  
    |23-01-2014|27-01-2014|Kit A - PC de base|  

4.  Cliquez sur le bouton **OK**.  

    Une nouvelle ligne planification est créée pour l'ordre d'assemblage nécessaire de dix unités, dû le 27 janvier. Elle n'a besoin d'aucune modification ; vous pouvez créer la commande.  

5.  Choisissez l'action **Traiter message d'action**.  
6.  Sur la page **Traiter messages d’action**, choisissez le champ **Ordre d'assemblage**, puis sélectionnez **Créer des ordres d'assemblage**.  
7.  Cliquez sur le bouton **OK**.  

### <a name="assembling-and-shipping-the-first-ato-quantity"></a>Assemblage et expédition de la première quantité « assembler pour commande »

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraison entrepôt**, puis choisissez le lien associé.  

    > [!NOTE]  
    >  Dans cette section, la personne responsable de la livraison est chargée d'enregistrer le travail d'assemblage « assembler pour commande » effectué sur la ligne livraison entrepôt. Ce flux de travail peut apparaître dans des environnements où le travail d’assemblage est effectué par la personne responsable de l’expédition ou par des ouvriers d’assemblage dans l’emplacement expédition.  
    >   
    >  Dans cette section, des tâches de l'ordre d'assemblage sont exécutées indirectement à partir de la ligne livraison entrepôt. Pour plus d’informations sur la manière de traiter un ordre d’assemblage directement, reportez-vous à la section « Assemblage d’articles pour l'inventaire » dans cette procédure pas à pas.  

2.  Ouvrez la livraison entrepôt la plus récente créée à l'emplacement BLANC.  

    Remarquez les trois lignes livraison entrepôt : une ligne pour la quantité ATO du kit B, exigible le 23 janvier. Une ligne pour la quantité ATO du kit A, dû le 27 janvier. Une ligne pour la quantité en inventaire du kit A, dû le 27 janvier.  

    Le champ **Assembler pour commande** spécifie la méthode d'assemblage.

    Ensuite, créez un document prélèvement pour toutes les composantes d’assemblage « assembler pour commande » nécessaires pour la livraison entrepôt.  

3.  Choisissez l'action **Créer prélèvement**, puis cliquez sur le bouton **OK**.  

    Ensuite, effectuez la tâche de la personne en charge du prélèvement.  

4.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements**, puis choisissez le lien associé.  
5.  Ouvrez le document prélèvement entrepôt que vous avez créé à l’étape 3 de cette section.  

    Prenez note de la valeur du champ **Document origine** et que toutes les lignes prélèvement sont pour les composantes d’assemblage.  

    Ensuite, enregistrez le prélèvement sans modifier les informations par défaut.  

6.  Choisissez l'action **Remplir automatiquement la quantité à traiter**.  
7.  Choisissez l'action **Enregistrer prélèvement**.  

    Revenez à l’exécution des tâches d’expédition.  

8.  Rouvrez la page **Livraison entrepôt**.  

    Notez que le champ **Qté prélevée** est toujours blanc sur toutes les lignes. Ceci est dû au fait que vous n’avez toujours pas prélevé les articles à livrer, mais uniquement les composantes nécessaires pour assembler les quantités « assembler pour commande ».  

    Révisez l’ordre d’assemblage lié.  

9. Sélectionnez la ligne livraison pour trois unités du kit B.  
10. Sur le raccourci **Lignes**, sélectionnez **Ligne**, puis **Assembler pour commande**. La page **Ordre d'assemblage** s'ouvre.  

    Notez que plusieurs champs de l'ordre d'assemblage ne sont pas disponibles parce que la commande est liée à un document de vente.  

    Notez sur les lignes ordre d’assemblage que le champ **Qté prélevée** est renseigné. Ceci est dû au prélèvement que vous avez enregistré à l’étape 7 de cette section.  

11. Dans le champ **Quantité à assembler**, essayez d’entrer une valeur inférieure à  **3**.  

    Lire le message d'erreur expliquant pourquoi ce champ peut uniquement être renseigné par le champ **Qté à livrer** de la livraison liée.  

    Le champ **Quantité à assembler** est modifiable et permet de prendre en charge des situations où vous voulez livrer partiellement une quantité en inventaire au lieu d’assembler plusieurs unités pour la commande. Pour plus d’informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).  

12. Fermez la page **Ordre d'assemblage** pour revenir à la page **Livraison entrepôt**.  
13. Sur la ligne livraison pour trois unités du kit B, dans le champ **Qté à livrer**, entrez **3**.  
14. Choisissez l'action **Reporter livraison**, puis sélectionnez le bouton **Livrer**.  

    Avec ce report de la livraison entrepôt, l'ensemble de la consommation et des quantités produites de l'ordre d'assemblage associé est reporté et le champ **Quantité restante** est vide. La ligne document de vente pour le kit B est mise à jour pour indiquer que les trois unités sont livrées.  

    Les activités entrepôt pour répondre à la première ligne document de vente sont effectuées avant le 23 janvier. Ensuite, traitez les lignes document de vente qui seront livrées le 27 janvier  

### <a name="assembling-and-recording-the-second-ato-quantity"></a>Assemblage et enregistrement de la seconde quantité « assembler pour commande »

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ordres d’assemblage**, puis sélectionnez le lien associé.  

    Remarquez que la commande « assembler pour commande » pour les unités livrées du kit B se trouve toujours dans la liste, bien que le champ **Quantité restante** soit vide. Cela s'explique par le fait que le document de vente liée n'a toujours pas été entièrement facturé.  

    > [!NOTE]  
    >  Dans cette section, l'ouvrier d'assemblage est responsable de l'enregistrement du travail d'assemblage « assembler pour commande » effectué sur la ligne livraison entrepôt. Ce flux de travail peut apparaître dans des environnements dans lesquels le travail d'assemblage est effectué dans un département Assemblage séparé et les employés d'assemblage sont autorisés à modifier la ligne livraison entrepôt.  

2.  Ouvrez l’ordre d’assemblage « assembler pour commande » pour cinq unités de kit A.  

    Remarquez que les champs **Quantité à assembler** et **Quantité à consommer** sont vides car aucun travail n'est encore enregistré.  

    Notez sur les lignes ordre d’assemblage que le champ **Qté prélevée** est renseigné. Ceci est dû au prélèvement enregistré le 23 janvier.  

    Ensuite, enregistrez que l’ordre d’assemblage est terminé.  

3.  Choisissez l'action **Ligne expédition entrepôt Assembler pour commande**.  
4.  Sur la page **Ligne livraison entrepôt Assembler pour commande**, dans le champ **Qté à livrer**, entrez **5**, puis fermez la fenêtre.  

    Remarquez sur la page **Ordre d'assemblage** que les champs **Quantité à assembler** et **Quantité à consommer** sont renseignés par les quantités de sortie et les quantités consommées qui seront reportées avec la livraison.  

5.  Fermez la page **Ordre d'assemblage**.  

### <a name="assembling-the-ats-quantity"></a>Assemblage de la quantité « assembler pour stock »

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ordres d’assemblage**, puis sélectionnez le lien associé.  
2.  Ouvrez l’ordre d’assemblage pour dix unités de kit A.  

    Notez que le champ  **Quantité à assembler** est renseigné avec la quantité prévue.  

    Ensuite, créez un document prélèvement pour récupérer les composantes nécessaires.  

3.  Sélectionnez l'action **Lancer**.  
4.  Choisissez l'action **Créer prélèvement entrep.**, puis cliquez sur le bouton **OK**.  

    Ensuite, effectuez la tâche de la personne en charge du prélèvement.  

5.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements**, puis choisissez le lien associé.  
6.  Ouvrez le document prélèvement entrepôt que vous avez créé à l’étape 4 de cette section.  

     Enregistrez le prélèvement sans modifier les informations par défaut.  

7.  Choisissez l'action **Remplir automatiquement la quantité à traiter**.  
8.  Choisissez l'action **Enregistrer prélèvement**.  

    Revenez à l’ordre d’assemblage pour effectuer la dernière tâche d’assemblage.  

9. Dans **Ordre d'assemblage**, choisissez l'action **Reporter**, puis cliquez sur le bouton **Oui**.  

    Remarquez que l’ordre d’assemblage est supprimé de la liste des commandes ouvertes.  

### <a name="shipping-the-remaining-items-partly-from-stock-and-partly-assembled-to-the-order"></a>Expédition des autres articles, en partie du stock et en partie assemblés pour la commande

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraison entrepôt**, puis choisissez le lien associé.  
2.  Ouvrez la livraison entrepôt la plus récente créée à l'emplacement BLANC.  

    Notez que sur la ligne pour les dix unités de kit A les champs **Qté à livrer** et **Qté prélevée** sont vides.  

    Ensuite, prélevez les articles restants.  

3.  Choisissez l'action **Créer prélèvement**, puis cliquez sur le bouton **OK**.  

    Ensuite, effectuez la dernière tâche de la personne en charge du prélèvement pour cette livraison entrepôt.  

4.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements**, puis choisissez le lien associé.  
5.  Ouvrez le document prélèvement entrepôt que vous avez créé à l’étape 3 de cette section.  

    Remarquez que ce document prélèvement concerne l’article d’assemblage, pas les composantes d’assemblage.  

    Ensuite, enregistrez le prélèvement sans modifier les informations par défaut.  

6.  Choisissez l'action **Remplir automatiquement la quantité à traiter**.  
7.  Choisissez l'action **Enregistrer prélèvement**, puis cliquez sur le bouton **Oui**.  

    Revenez à la livraison entrepôt pour effectuer la dernière tâche.  

8.  Rouvrez la page **Livraison entrepôt**.  

    Sur la page **Livraison entrepôt**, sur la ligne pour dix unités de kit A, notez que les champs **Qté à livrer** et **Qté prélevée** contiennent désormais la valeur **10**.  

9. Choisissez l'action **Reporter livraison**, puis cliquez sur le bouton **Livrer**.  

    Le document livraison entrepôt a été supprimé, ce qui indique que les activités entrepôt impliquées sont terminées. Vérifiez ensuite que le document de vente a été traité.  

10. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
11. Ouvrez le document de vente pour The Device Shop.  

    Notez que le champ **Quantité livrée** affiche la quantité totale des deux lignes.  

    Lorsque The Device Shop paie pour la réception des 18 ordinateurs de CRONUS, le document de vente et ses ordres d’assemblage liés sont supprimés.  

## <a name="see-also"></a>Voir aussi .

 [Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md)   
 [Assembler des articles](assembly-how-to-assemble-items.md)   
 [Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
 [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md)   
 [Assembler des articles](assembly-how-to-assemble-items.md)   
 [Détails de conception : report d'un ordre d'assemblage](design-details-assembly-order-posting.md)   
 [Détails de conception : flux d'entrepôt internes](design-details-internal-warehouse-flows.md)   
 [Détails de conception : flux de désenlogement](design-details-outbound-warehouse-flow.md)   
<!--  [Walkthrough: Planning Supplies Automatically](walkthrough-planning-supplies-automatically.md) -->


[!INCLUDE[footer-include](includes/footer-banner.md)]
