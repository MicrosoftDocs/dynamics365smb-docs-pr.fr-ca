---
title: Consommer en aval des composantes en fonction de la production réalisée
description: Cette rubrique décrit comment rincer les composantes en fonction de la sortie de l’opération ainsi que d’autres méthodes de rinçage impliquées.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/22/2021
ms.author: edupont
---
# <a name="flush-components-according-to-operation-output" />Consommer en aval des composantes en fonction de la production réalisée
Vous pouvez définir différentes stratégies de consommation, pour automatiser l'enregistrement de la consommation des composantes. 

Cette fonctionnalité est utile pour les motifs suivants :  

- **Évaluation de l'inventaire**

    Les écritures de valeur de production et de consommation sont créées parallèlement à la progression du bon de production. Sans les codes lien itinéraire, la valeur de l'inventaire augmente lorsque la production est reportée, puis réduite ultérieurement lorsque la valeur de la consommation des composantes est reportée en même temps que le bon de production terminé.  
- **Disponibilité de l'inventaire**

    Avec un report progressif de la consommation, la disponibilité des composantes est mieux actualisée, ce qui est important pour conserver l’équilibre interne entre l’offre et la demande. Sans les codes lien itinéraire, les autres demandeurs de la composante peuvent croire qu'elle est disponible tant que le report de sa consommation reste en attente.  
- **À flux tendu**

    Si vous pouvez personnaliser les produits en fonction des demandes client, vous pouvez réduire les rebuts en vous organisant pour que les procédures de travail et les systèmes ne soient modifiés que lorsque c’est nécessaire.  

- **Réduire la saisie de données**

    La possibilité de consommer automatiquement une opération permet d'automatiser tout le processus d'enregistrement de la consommation et de la production. L'inconvénient de la consommation automatique est que vous risquez de ne pas enregistrer précisément voire d'omettre les rebuts.

## <a name="automatic-consumption-posting-flushing-methods" />Méthodes de report de la consommation automatique (consommation)

- Consommation en aval de l'ordre entier  
- Consommation en aval par opération  
- Consommation en amont par opération  
- Consommation en amont de l'ordre entier  

### <a name="automatic-reporting---forward-flush-the-entire-order" />Génération de rapport automatique - Consommation en aval de l'ordre entier
Si vous consommez en aval le bon de production au début du projet, le comportement de l'application est très similaire à une consommation manuelle. La principale différence réside dans le fait que la consommation est effectuée automatiquement.  

- Le contenu entier de la nomenclature de production est consommé et déduit de l'inventaire lors de l'actualisation du bon de production libéré.  
- La quantité consommée est la quantité par assemblage indiquée dans la nomenclature de production, multipliée par le nombre d'articles parents que vous créez.  
- Il est inutile d'enregistrer des informations dans le journal consommation si tous les articles doivent être consommés.  
- Lors de la consommation d'articles de l'inventaire, le moment où sont créées les écritures journal de sortie est sans importance parce que le journal de sortie n'a pas d'effet sur ce mode de report de la consommation.  
- Aucun code lien itinéraire ne peut être défini.  

La consommation en aval d'une commande entière est appropriée dans des environnements de production présentant les caractéristiques suivantes :  

-   petit nombre de défauts ;  
-   petit nombre d'opérations ;  
-   Consommation importante de composantes dans les opérations précoces  

### <a name="automatic-reporting---forward-flushing-by-operation" />Génération de rapport automatique - Consommation en aval par opération
La consommation par opération permet de déduire l'inventaire durant une opération spécifique dans l'itinéraire de l'article parent. Les matières sont liées à l'itinéraire à l'aide de codes lien itinéraire qui correspondent aux codes lien itinéraire affectés aux composantes dans la nomenclature de production.  

La consommation a lieu au démarrage de l'opération auquel le code lien itinéraire correspond. Le démarrage intervient quand une certaine activité est enregistrée dans le journal de sortie pour cette opération. Cette activité peut être simplement l'entrée d'un délai de configuration.  

La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents créés (quantité prévue).  

Il est recommandé d'utiliser cette technique lorsqu'il y a de nombreuses opérations et que certains composants ne sont nécessaires que vers la fin de la séquence d'assemblage. En réalité, dans le cadre d'une configuration à flux tendu (Just-in-Time, JIT), il se peut que les articles ne soient pas disponibles au début de la RPO.  

Il est possible de consommer des matières durant les opérations à l'aide de codes lien itinéraire. Il se peut que certains composants ne soient pas utilisés avant les opérations d'assemblage finales, auquel cas ils ne doivent pas être soustraits du stock auparavant.  

### <a name="automatic-reporting---back-flushing-by-operation" />Génération de rapport automatique - Consommation en amont par opération
La post-consommation par opération enregistre la consommation après le report de l'opération dans le journal de sortie.  

L'avantage de cette méthode est que le nombre de pièces parentes finies dans l'opération est connu.  

Les matières dans la nomenclature de production sont liées aux enregistrements d'itinéraire à l'aide de codes lien itinéraire. La consommation en amont a lieu lors du report d'une opération avec un code lien itinéraire particulier avec une quantité terminée.  

La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents reportés comme quantité produite pour cette opération. Cette quantité peut différer de la quantité prévue.  

### <a name="automatic-reporting---back-flushing-the-entire-order" />Génération de rapport automatique - Consommation en amont de l'ordre entier
Cette méthode de génération de rapport ne tient pas compte des codes lien itinéraire.  

Aucun composant n'est prélevé tant que le statut de l'ordre de fabrication lancé n'est pas *Terminé*. La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents terminés et introduits dans l'inventaire.  

La consommation en amont du bon de production tout entier requiert la même configuration que pour la consommation en aval : la méthode de génération de rapport doit être définie sur amont dans la fiche article de tous les articles de la nomenclature parente pour que le rapport soit généré. En outre, tous les codes lien itinéraire doivent être supprimés de la nomenclature de production. 



Par exemple, si un bon de production de 800 mètres nécessite pour son exécution 8 kilogrammes d'une composante, lorsque vous reportez 200 mètres de production, 2 kilogrammes sont automatiquement reportés comme étant consommés. Pour y parvenir, combinez la méthode de consommation en amont et les codes lien itinéraire pour que la quantité consommée par chaque opération soit proportionnelle à la production réelle de cette opération terminée. Pour les articles créés avec la méthode de consommation en amont le comportement par défaut est de calculer et de valider la consommation de composants lorsque vous affectez à l'ordre de fabrication lancé le statut **Terminé**. Si vous définissez également les codes lien itinéraire, le calcul et le report ont lieu lorsque chaque opération est terminée et que la quantité effectivement consommée au cours de l'opération est reportée. Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).  

## <a name="to-flush-components-according-to-operation-output" />Pour consommer en aval des composants en fonction de la production réalisée

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2.  Choisissez l'action **Modifier**.  
3.  Sur le raccourci **Réapprovisionnement**, dans le champ **Méthode consommation**, sélectionnez **En amont**.  

    > [!NOTE]  
    >  Sélectionnez **Prélèvement + Amont** si la composante est utilisée dans un emplacement configuré pour un prélèvement et un rangement suggérés.  

4.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Itinéraires**, puis sélectionnez le lien associé.  
5.  Définir les codes lien itinéraire pour chaque opération qui consomme la composante. Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).  
    > [!IMPORTANT]  
    > N'utilisez pas le même lien d'itinéraire pour différentes opérations dans l'itinéraire, car cela entraînera l'enregistrement de la consommation de composante pour chaque opération liée.  
6.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Nomenclature de production**, puis choisissez le lien associé.  
7.  Associe aux codes lien itinéraire de chaque instance de la composante l'opération dans laquelle elle est consommée.

La consommation sera reportée automatiquement lorsque vous enregistrez la sortie. Pour plus d’informations, voir [Reporter en lot la production et les temps d’exécution](production-how-to-post-output-quantity.md)

## <a name="flushing-methods" />Méthodes consommation

Le tableau suivant décrit les options de méthode de consommation disponibles que vous pouvez spécifier sur les fiches **Article** et **Unité de stock**.

|Option|Description|
|------------|-------------|  
|Manuel|Requiert d'entrer et de reporter manuellement la consommation dans le journal consommation.|
|Suivant|Reporte automatiquement la consommation en fonction des lignes composante bon de production. <br><br>Par défaut, le report de la consommation de composantes se produit lorsque vous basculez l'état d'un bon de production sur **Libéré**. Toutefois, si vous utilisez le champ Code **Lien itinéraire** sur des lignes composante Bon de production, le report est effectué par opération lorsque l'opération commence. Pour plus d'informations, reportez-vous à [Comment créer des liens itinéraire](production-how-to-create-routings.md#to-create-routing-links). <br><br> **Remarque**<br>Pour la consommation en aval, le report propre à chaque opération que vous obtenez avec des codes lien itinéraire est basé sur la quantité prévue définie sur la ligne composante. Pour plus d'informations sur la consommation en aval propre à l'opération sur la production réelle, reportez-vous à la description de **Amont** dans cette rubrique.<br><br>Si l'emplacement ou les ressources utilisant cette composante sont créés avec une structure de zone par défaut, l'article est consommé à partir du **Code de zone d'atelier ouvert**. Pour plus d'informations, voir [Procédure : configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md). <br><br> **Important** <br>La consommation en aval se produit aussi lorsque vous choisissez **Actualiser** sur un bon de production libéré créé à partir de zéro. Sur ces bons de production libérés directement créés, vous ne pouvez pas modifier les informations de zone car les lignes composante bon de production sont générées lors de l'actualisation de la commande avec consommation en aval simultanée des composantes. Toutefois, si vous souhaitez modifier les informations de zone sur les lignes composante bon de production avant que la consommation en aval se produise, cette commande doit être créée avec l'état *Planifié* ou *Planifié ferme*.|
|Amont|Calcule et reporte automatiquement la consommation en fonction des lignes composante Bon de production.<br><br> Par défaut, le calcul et le report de la consommation de composantes se produisent lorsque vous basculez l'état du bon de production libéré sur **Terminé**. Toutefois, si vous utilisez le champ **Code lien itinéraire** sur lignes composante Bon de production, le calcul et le report sont effectués à la fin de chaque opération.<br><br> **Remarque** <br>Les codes de consommation en amont et de lien itinéraire peuvent être combinés afin que la quantité consommée par opération soit proportionnelle à la production réelle de cette opération. Pour plus d'informations, voir [Procédure : consommer en aval des composantes en fonction de la production réalisée](#to-flush-components-according-to-operation-output).<br><br> Si l'emplacement ou l'unité de production utilisant cette composante sont créés avec une structure de zone par défaut, l'article est consommé à partir du **Code de zone d'atelier ouvert**.|
|Prélèvement + Aval|Identique à la méthode de consommation aval, sauf qu’elle ne fonctionne que pour les emplacements qui utilisent une configuration d’entrepôt avancée ou une configuration d’entrepôt de base avec des zones obligatoires.<br><br> La consommation est calculée et reportée à partir de la zone définie dans le champ **Code de zone avant production** sur l'emplacement ou l'unité de production après le prélèvement de la composante de l'entrepôt.<br><br> **Remarque** <br>Si une composante est configurée avec le prélèvement et la méthode de consommation en aval, vous ne pouvez pas avoir un code lien itinéraire pour une opération configurée avec la méthode de consommation en aval. La composante est ensuite automatiquement consommée lorsque l'opération commence, rendant impossible toute demande d'activité de prélèvement.|
|Prélèvement + Amont|Identique à la méthode de consommation amont, sauf qu’elle ne fonctionne que pour les emplacements qui utilisent une configuration d’entrepôt avancée ou une configuration d’entrepôt de base avec des zones obligatoires.<br><br> La consommation est calculée et reportée à partir de la zone définie dans le champ **Code de zone avant production** sur l'emplacement ou l'unité de production après le prélèvement de la composante de l'entrepôt.|

## <a name="see-also" />Voir aussi

[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
