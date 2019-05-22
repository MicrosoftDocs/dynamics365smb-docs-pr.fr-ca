---
title: À propos des ordres de fabrication | Microsoft Docs
description: Les ordres de fabrication permettent de gérer la conversion de matières achetées en articles fabriqués. La gamme de bons de production (bons de travail ou ordres de travail) utilise diverses fonctions (ateliers ou unités de production) de l'atelier.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: b02aa262089d5c341fb3b535f2af82c7085e99ee
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1252974"
---
# <a name="about-production-orders"></a>À propos des ordres de fabrication
Les ordres de fabrication permettent de gérer la conversion de matières achetées en articles fabriqués. La gamme de bons de production utilise divers ateliers ou unités de production dans l'atelier.  

Avant de commencer la production, la plupart des compagnies effectuent une planification des approvisionnements, généralement une fois par semaine, pour calculer le nombre de bons de production et de bons de commande à exécuter pour répondre à une demande de vente de la semaine en cours. Les commandes achat fournissent les composants requis en fonction de la nomenclature de production pour produire les produits finis.

Les ordres de fabrication sont les composants centraux de la fonctionnalité de fabrication du programme et contiennent les informations suivantes :  

-   produits planifiés pour fabrication ;  
-   matières requises pour les ordres de fabrication planifiés ;  
-   produits qui viennent d'être fabriqués ;  
-   matières déjà sélectionnées ;  
-   produits fabriqués par le passé ;  
-   matières utilisées dans des opérations de fabrication précédentes.  

Les ordres de fabrication sont les points de départ pour :  

-   Planification de la fabrication future  
-   le contrôle de la fabrication en cours ;  
-   la traçabilité de la fabrication terminée.  

## <a name="production-order-creation"></a>Création des bons de production  
Il est possible de créer des bons de production un par un manuellement sur la page **Bon de production** ou de les générer sur les pages **Planification document de vente** et/ou **Planification commande**. La page **Feuille planification** permet de générer plusieurs ordres.  

Les ordres de fabrication sont créés à l'aide d'informations provenant des éléments suivants :  

- Articles  
- Nomenclatures de production
- Itinéraires  
- postes de charge ;  
- centres de charge ;  

## <a name="limitations-on-production-order-creation"></a>Limitations de la création de bons de production  
Les ordres de fabrication sont automatiquement réservés et tracés sur leur source quand ils sont :  

-   créés à partir de la fenêtre **Feuille planification** ;  
-   Créés avec la fonction Commande sur la page **Planification document de vente** ;  
-   Créés sur la page **Planification commande** ;  
-   utilisés avec la fonction **Replanification** des ordres de fabrication.  

Pour plus d'informations, voir [Suivre les relations entre l'offre et la demande](production-how-track-demand-supply.md).

Les ordres de fabrication créés par d'autres moyens ne sont pas automatiquement réservés et tracés.   

## <a name="production-order-status"></a>État du bon de production  
L'état du bon de production contrôle la manière dont le bon de production se comporte dans le programme. La forme et le contenu de la production sont dictés par l'état de la commande. Les bons de production sont affichés sur différentes pages en fonction de leur état. Vous ne pouvez pas modifier le statut d'un ordre de fabrication manuellement ; vous devez utiliser la fonction **Modifier statut**.  

### <a name="simulated-production-order"></a>Bon de production simulé  
Le bon de production simulé est unique en raison des caractéristiques suivantes :  

- Comme son nom l'indique, il s'agit d'une simulation destinée principalement à l'établissement de devis et d'évaluations, par exemple si le département de recherche et développement souhaite obtenir une estimation de coût d'un article proposé. Un bon de production simulé fait office d'exemple d'un bon de production.  
- Il n'influence pas la planification des commandes. La planification (MPS et MRP) ne prend jamais en considération et n'est jamais affectée par les bons de production simulés. De même, un bon de production simulé ne peut pas être utilisé comme modèle parce qu'il disparaît lorsque vous modifiez son état.  

### <a name="planned-production-order"></a>Ordre de production planifié  
Le bon de production planifié est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production planifié à partir d'un document de vente.  
- Les bons de production calendriers sont semblables aux bons de production libérés. Ils contribuent à la planification des besoins en capacité en montrant les besoins totaux par atelier ou unité de production.  
- Un bon de production constitue la meilleure estimation du chargement futur de l'atelier ou de l'unité de production sur la base des informations disponibles. Généralement, ils sont générés à partir d'une planification, mais il est également possible de les créer manuellement. Comme ils sont effacés durant les générations de planification suivantes, la création manuelle n'est pas pratique.  
- Sa génération dans la planification produit une « libération prévue » suggérée qui inclut une quantité, une date de libération et une date d'échéance. La logique du système de planification est basée sur le système de réapprovisionnement, les méthodes de réapprovisionnement et les modificateurs d'ordre qu'il rencontre dans le processus de planification des besoins nets.  
- Pour afficher leur impact, examinez la charge de chaque atelier ou unité de production sur l'itinéraire du bon de production planifié.  

### <a name="firm-planned-production-order"></a>Bon de production planifié ferme  
Le bon de production planifié ferme est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production planifié ferme à partir d'un document de vente.  
- Un bon de production planifié ferme agit comme un espace réservé dans le calendrier pour un futur projet transféré à l'atelier.  
- Vous pouvez générer un bon de production planifié ferme à partir d'une planification, de documents de vente ou manuellement. Il n'est pas effacé durant la planification ultérieure.  
- Sa génération dans la planification produit une « libération prévue » suggérée qui inclut une quantité, une date de libération et une date d'échéance. La logique du système de planification est basée sur le système de réapprovisionnement, les méthodes de réapprovisionnement et les modificateurs d'ordre qu'il rencontre dans le processus de planification des besoins nets.  
- Pour afficher leur impact, examinez la charge de chaque atelier ou unité de production sur l'itinéraire du bon de production planifié ferme.  

### <a name="released-production-order"></a>Ordre de production envoyé  
Le bon de production libéré est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production libéré à partir d'un document de vente.  
- Le fait qu'un bon de production ait été libéré ne signifie pas nécessairement que les matières ont été prélevées ou que le projet a été déplacé physiquement vers la première opération qui y est associée.  
- Dans un environnement MTO (Prod. pour commande), il n'est pas rare de créer un bon de production libéré immédiatement après l'entrée du document de vente.  
- Vous pouvez enregistrer la consommation de matières et la production réelles manuellement avec un bon de production libéré. En outre, la consommation automatique de matières et de production n'intervient que pour les bons de production libérés.  

### <a name="finished-production-order"></a>Bon de production achevé  
Le bon de production terminé est unique en raison des caractéristiques suivantes :  

- Un bon de production terminé est généralement un ordre qui a été fabriqué.  
- L'achèvement du bon de production est une tâche importante dans l'évaluation du cycle de vie de l'article en cours de production. L'achèvement d'un bon de production permet d'ajuster et de rapprocher l'évaluation coût.  
- Les bons de production terminés sont utilisés pour générer des rapports statistiques et prendre en charge la possibilité de remonter à d'autres ordres (ventes, production et achat, par exemple). La possibilité de remonter à un bon de production terminé permet d'examiner l'historique détaillé.  
- Il n'est jamais possible de modifier des ordres de fabrication terminés.  

## <a name="production-order-execution"></a>Exécution d'un bon de production  
Après qu'un bon de production a été créé et programmé, il doit être libéré à l'atelier pour exécution. Durant l'exécution de l'ordre, vous enregistrez les éléments suivants :  

- matières prélevées et consommées ;  
- temps passé à travailler sur l'ordre ;  
- quantité d'articles parents produite.  

Ces informations peuvent être enregistrées manuellement ou via une génération d'état automatique, en fonction des articles définis dans le champ Méthode consommation.  

### <a name="material-consumption"></a>Consommation matière  
Le programme offre une série d'options concernant la manière dont une compagnie manufacturière peut enregistrer une consommation matière. Par exemple, une consommation matière peut être enregistrée manuellement, ce qui peut être souhaitable en cas de remplacements fréquents de composantes ou de rebuts plus importants que prévu.  

La consommation de matières peut être traitée via le journal consommation, mais peut également être enregistrée automatiquement par le programme à l'aide du processus de génération de rapport automatique. Les méthodes de génération de rapport sont les suivantes :  

-   Manuel  
-   Suivant  
-   Amont  

La génération de rapports de consommation manuelle utilise le journal consommation pour spécifier un prélèvement de matière.  

En aval, la génération de rapports de consommation est basée sur l'hypothèse que la quantité prévue de toutes les matières nécessaires à la commande entière est consommée à la libération du bon de production, sauf en cas d'utilisation de codes lien itinéraire. En cas d'utilisation de codes lien itinéraire, les matières consommées après le début de l'opération sont enregistrées dans le journal de sortie. Pour consommer en aval le bon de production entier, vous devez effectuer les deux opérations suivantes :  

- La consommation en aval doit être activée pour tous les articles de la nomenclature de production de niveau supérieur sur leur fiche article.  
- Tous les codes lien itinéraire dans la nomenclature de production doivent être supprimés.  

En amont, la génération d'états de consommation enregistre la quantité réelle des matières prélevées ou consommées lorsque le statut d'un ordre de fabrication passe à *Terminé*, sauf en cas d'utilisation de codes lien gamme. En cas d'utilisation de codes lien itinéraire, les matières sont consommées après qu'une quantité d'articles parents a été enregistrée pour l'opération dans le journal de sortie.  

Lors de l'actualisation du bon de production, la méthode consommation est copiée à partir de la fiche article. Comme la méthode consommation de chaque bon de production contrôle le mode et le moment d'enregistrement de la consommation, il est important de noter que vous pouvez modifier la méthode de consommation d'articles spécifiques directement dans le bon de production.  

#### <a name="automatic-consumption-posting-flushing"></a>Report de la consommation automatique (consommation)  
L'avantage de la consommation automatique est qu'elle réduit considérablement la saisie de données. La possibilité de consommer automatiquement une opération permet d'automatiser tout le processus d'enregistrement de la consommation et de la production. L'inconvénient de la consommation automatique est que vous risquez de ne pas enregistrer précisément voire d'omettre les rebuts. Les méthodes de génération de rapport automatique sont les suivantes :  

- Consommation en aval de l'ordre entier  
- Consommation en aval par opération  
- Consommation en amont par opération  
- Consommation en amont de l'ordre entier  

#### <a name="automatic-reporting---forward-flush-the-entire-order"></a>Génération de rapport automatique - Consommation en aval de l'ordre entier  
Si vous consommez en aval le bon de production au début du projet, le comportement du programme est très similaire à une consommation manuelle. La principale différence réside dans le fait que la consommation est effectuée automatiquement.  

- Le contenu entier de la nomenclature de production est consommé et déduit de l'inventaire lors de l'actualisation du bon de production libéré.  
- La quantité consommée est la quantité par assemblage indiquée dans la nomenclature de production, multipliée par le nombre d'articles parents que vous créez.  
- Il est inutile d'enregistrer des informations dans le journal consommation si tous les articles doivent être consommés.  
- Lors de la consommation d'articles de l'inventaire, le moment où sont créées les écritures journal de sortie est sans importance parce que le journal de sortie n'a pas d'effet sur ce mode de report de la consommation.  
- Aucun code lien itinéraire ne peut être défini.  

La consommation en aval d'une commande entière est appropriée dans des environnements de production présentant les caractéristiques suivantes :  

-   petit nombre de défauts ;  
-   petit nombre d'opérations ;  
-   Consommation importante de composantes dans les opérations précoces  

#### <a name="automatic-reporting---forward-flushing-by-operation"></a>Génération de rapport automatique - Consommation en aval par opération  
La consommation par opération permet de déduire l'inventaire durant une opération spécifique dans l'itinéraire de l'article parent. Les matières sont liées à l'itinéraire à l'aide de codes lien itinéraire qui correspondent aux codes lien itinéraire affectés aux composantes dans la nomenclature de production.  

La consommation a lieu au démarrage de l'opération auquel le code lien itinéraire correspond. Le démarrage intervient quand une certaine activité est enregistrée dans le journal de sortie pour cette opération. Cette activité peut être simplement l'entrée d'un délai de configuration.  

La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents créés (quantité prévue).  

Il est recommandé d'utiliser cette technique lorsqu'il y a de nombreuses opérations et que certains composants ne sont nécessaires que vers la fin de la séquence d'assemblage. En réalité, dans le cadre d'une configuration à flux tendu (Just-in-Time, JIT), il se peut que les articles ne soient pas disponibles au début de la RPO.  

Il est possible de consommer des matières durant les opérations à l'aide de codes lien itinéraire. Il se peut que certains composants ne soient pas utilisés avant les opérations d'assemblage finales, auquel cas ils ne doivent pas être soustraits du stock auparavant.  

#### <a name="automatic-reporting---back-flushing-by-operation"></a>Génération de rapport automatique - Consommation en amont par opération  
La post-consommation par opération enregistre la consommation après le report de l'opération dans le journal de sortie.  

L'avantage de cette méthode est que le nombre de pièces parentes finies dans l'opération est connu.  

Les matières dans la nomenclature de production sont liées aux enregistrements d'itinéraire à l'aide de codes lien itinéraire. La consommation en amont a lieu lors du report d'une opération avec un code lien itinéraire particulier avec une quantité terminée.  

La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents reportés comme quantité produite pour cette opération. Cette quantité peut différer de la quantité prévue.  

#### <a name="automatic-reporting---back-flushing-the-entire-order"></a>Génération de rapport automatique - Consommation en amont de l'ordre entier  
Cette méthode de génération de rapport ne tient pas compte des codes lien itinéraire.  

Aucun composant n'est prélevé tant que le statut de l'ordre de fabrication lancé n'est pas *Terminé*. La quantité consommée est calculée pour la quantité par assemblage sur la nomenclature de production multipliée par le nombre d'articles parents terminés et introduits dans l'inventaire.  

La consommation en amont du bon de production tout entier requiert la même configuration que pour la consommation en aval : la méthode de génération de rapport doit être définie sur amont dans la fiche article de tous les articles de la nomenclature parente pour que le rapport soit généré. En outre, tous les codes lien itinéraire doivent être supprimés de la nomenclature de production.  

### <a name="production-output"></a>Production  
Le programme offre la possibilité de suivre le temps consacré à un ordre de fabrication, en plus de l'enregistrement de la quantité produite. Ces informations permettent de déterminer plus précisément les coûts de production. De même, les fabricants utilisant un système d'évaluation standard peuvent souhaiter enregistrer des informations réelles afin de pouvoir développer de meilleures normes.  

La sortie peut être traitée via le journal de sortie, mais aussi enregistrée automatiquement par le programme. Le programme copie la méthode de consommation de la fiche unité de production ou atelier vers l'itinéraire du bon de production lors de l'actualisation. Comme pour la consommation matière, trois méthodes de génération de rapport s'appliquent à la production :  

- Manuel  
- Suivant  
- Amont  

La méthode manuelle utilise le journal de sortie pour spécifier le temps consommé et la quantité produite.  

En aval, cette méthode enregistre la sortie prévue (et le temps), qui est automatiquement enregistrée lors de la libération d'un bon de production. Les codes lien itinéraire n'interviennent pas comme facteurs dans la consommation en aval de la production.  

En amont, cette méthode enregistre la production prévue (et le temps), qui est automatiquement enregistrée à la fin d'un ordre de fabrication. Les codes lien itinéraire n'interviennent pas comme facteurs dans la consommation en amont de la production.  

### <a name="posting-consumption-and-output"></a>Report de la consommation et de la production  
Vous pouvez utiliser toute combinaison d'informations de consommation automatique et enregistrées manuellement tant pour la consommation que pour la production. Par exemple, vous pouvez consommer automatiquement en aval des composantes, tout en utilisant le journal consommation pour enregistrer les rebuts. De même, vous pouvez enregistrer automatiquement la production tout en utilisant le journal de sortie pour enregistrer les rebuts de l'article parent ou le temps supplémentaire consacré au traitement de l'ordre.  

Enfin, si vous entrez une consommation et une production manuellement, vous devez déterminer l'ordre dans lequel vous allez enregistrer ces informations. Vous pouvez commencer par enregistrer une consommation, puis utiliser une méthode de raccourci pour entrer les informations, basée sur une quantité de production prévue. Vous pouvez également commencer par entrer une production en utilisant la fonction **Éclater gamme**. Vous enregistrez ensuite une consommation sur la base de la quantité de production réelle.  

### <a name="production-journal"></a>Journal de production  
Le journal production combine les fonctions du journal consommation et des journaux production dans un seul journal, directement accessible depuis le bon de production libéré.  

Le journal production a pour fonction de fournir une interface unique pour l'enregistrement de la consommation et de la production à partir d'un bon de production.  

Le journal production présente une vue simple et offre les possibilités suivantes :  

- enregistrement aisé de la production et de la consommation en relation avec un bon de production ;  
- mise en relation de composants et d'opérations ;  
- mise en relation de données d'opération réelles avec les estimations standard des lignes de composante et d'itinéraire de bon de production ;  
- Report et impression d'un aperçu des données d'opération enregistrées pour le bon de production.  

Le journal production exécute un grand nombre des fonctions des journaux consommation et production. Les dimensions, la traçabilité et le contenu emplacement sont gérés de la même manière sur les feuilles consommation et production.  

Toutefois, le journal production diffère des journaux production et consommation sur les plans suivants :  

- Elle est appelée directement depuis une ligne bon de production libéré et prédéfinie avec les données appropriées.  
- Il permet de définir les types de composantes à gérer sur la base du filtre de méthode de consommation du journal.  
- Les quantités et les heures déjà reportées pour l'ordre s'affichent au bas du journal comme des écritures réelles.  
- Les champs dont les données ne sont pas pertinentes sont vides et non modifiables.  
- L'utilisateur peut configurer la manière dont les quantités sorties sont prédéfinies dans le journal ; par exemple, que la quantité sortie de la dernière opération doit être zéro.  
- Si vous fermez le journal involontairement sans reporter les modifications, un message de demande s'affiche pour vous permettre de ne pas fermer le journal.  
- Elle affiche les opérations et composants dans une structure logique qui donne un aperçu du processus de production.  

Dans le journal production, les quantités consommées sont reportées comme écritures article négatives, les quantités sorties sont reportées comme écritures positives et les heures passées sont reportées comme écritures du grand livre de capacité.  

## <a name="see-also"></a>Voir aussi
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
