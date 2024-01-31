---
title: À propos des ordres de fabrication
description: Découvrez les bons de production et la manière dont ils sont utilisés pour gérer la conversion de matières achetées en articles fabriqués.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: '99000813, 99000814, 99000815, 99000816, 99000829, 99000830, 99000831, 99000832, 99000833, 99000838, 99000839, 99000867, 99000868, 99000882, 99000897, 99000898, 99000900, 99000912, 99000913, 99000914, 99000917'
ms.date: 06/22/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# À propos des ordres de fabrication

Les ordres de fabrication permettent de gérer la conversion de matières achetées en articles fabriqués. La gamme de bons de production utilise divers ateliers ou unités de production dans l'atelier.  

Avant de commencer la production, la plupart des compagnies effectuent une planification des approvisionnements, généralement une fois par semaine, pour calculer le nombre de bons de production et de bons de commande à exécuter pour répondre à une demande de vente de la semaine en cours. Les commandes achat fournissent les composants requis en fonction de la nomenclature de production pour produire les produits finis.

Les bons de production sont les composantes centrales de la fonctionnalité de fabrication de l'application et contiennent les informations suivantes :  

- produits planifiés pour fabrication ;  
- matières requises pour les ordres de fabrication planifiés ;  
- produits qui viennent d'être fabriqués ;  
- matières déjà sélectionnées ;  
- produits fabriqués par le passé ;  
- matières utilisées dans des opérations de fabrication précédentes.  

Les ordres de fabrication sont les points de départ pour :  

- Planification de la fabrication future  
- le contrôle de la fabrication en cours ;  
- la traçabilité de la fabrication terminée.  

## Création des bons de production  
Il est possible de créer des bons de production un par un manuellement sur la page **Bon de production** ou de les générer sur les pages **Planification document de vente** et/ou **Planification commande**. La page **Feuille planification** permet de générer plusieurs ordres.  

Les ordres de fabrication sont créés à l'aide d'informations provenant des éléments suivants :  

- Articles  
- Nomenclatures de production
- Itinéraires  
- postes de charge ;  
- centres de charge ;  

## Limitations de la création de bons de production  
Les ordres de fabrication sont automatiquement réservés et tracés sur leur source quand ils sont :  

- créés dans la **[Feuille planification](production-how-to-run-mps-and-mrp.md)**  
- créés sur la page **[Planification document de vente](production-how-to-create-production-orders-from-sales-orders.md)**  
- créés sur la page **[Planification commande](production-how-to-plan-for-new-demand.md)**  
- Utilisation de la fonction **[Replanification](production-how-to-replan-refresh-production-orders.md)** des bons de production  

Pour plus d'informations, voir [Suivre les relations entre l'offre et la demande](production-how-track-demand-supply.md).

Les ordres de fabrication créés par d'autres moyens ne sont pas automatiquement réservés et tracés.   

## État du bon de production  
L'état du bon de production contrôle la manière dont le bon de production se comporte dans l'application. La forme et le contenu de la production sont dictés par l'état de la commande. Les bons de production sont affichés sur différentes pages en fonction de leur état. Vous ne pouvez pas modifier l'état d’un bon de production manuellement ; vous devez utiliser la fonction **Modifier état** dans le bon de production individuel ou dans la fenêtre **Changer état Bon de production**.  

### Bon de production simulé  
Le bon de production simulé est unique en raison des caractéristiques suivantes :  

- Comme son nom l'indique, il s'agit d'une simulation destinée principalement à l'établissement de devis et d'évaluations, par exemple si le département de recherche et développement souhaite obtenir une estimation de coût d'un article proposé. Un bon de production simulé fait office d'exemple d'un bon de production.  
- Il n'influence pas la planification des commandes. La planification (MPS et MRP) ne prend jamais en considération et n'est jamais affectée par les bons de production simulés. De même, un bon de production simulé ne peut pas être utilisé comme modèle parce qu'il disparaît lorsque vous modifiez son état.  

### Ordre de production planifié  
Le bon de production planifié est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production planifié à partir d'un document de vente.  
- Les bons de production calendriers sont semblables aux bons de production libérés. Ils contribuent à la planification des besoins en capacité en montrant les besoins totaux par atelier ou unité de production.  
- Un bon de production constitue la meilleure estimation du chargement futur de l'atelier ou de l'unité de production sur la base des informations disponibles. Généralement, ils sont générés à partir d'une planification, mais il est également possible de les créer manuellement. Comme ils sont effacés durant les générations de planification suivantes, la création manuelle n'est pas pratique.  
- Sa génération dans la planification produit une « libération prévue » suggérée qui inclut une quantité, une date de libération et une date d'échéance. La logique du système de planification est basée sur le système de réapprovisionnement, les méthodes de réapprovisionnement et les modificateurs d'ordre qu'il rencontre dans le processus de planification des besoins nets.  
- Pour afficher leur impact, examinez la charge de chaque atelier ou unité de production sur l'itinéraire du bon de production planifié.  

### Bon de production planifié ferme  
Le bon de production planifié ferme est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production planifié ferme à partir d'un document de vente.  
- Un bon de production planifié ferme agit comme un espace réservé dans le calendrier pour un futur projet transféré à l'atelier.  
- Vous pouvez générer un bon de production planifié ferme à partir d'une planification, de documents de vente ou manuellement. Il n'est pas effacé durant la planification ultérieure.  
- Sa génération dans la planification produit une « libération prévue » suggérée qui inclut une quantité, une date de libération et une date d'échéance. La logique du système de planification est basée sur le système de réapprovisionnement, les méthodes de réapprovisionnement et les modificateurs d'ordre qu'il rencontre dans le processus de planification des besoins nets.  
- Pour afficher leur impact, examinez la charge de chaque atelier ou unité de production sur l'itinéraire du bon de production planifié ferme.  

### Ordre de production envoyé  
Le bon de production libéré est unique en raison des caractéristiques suivantes :  

- Vous pouvez créer automatiquement un bon de production libéré à partir d'un document de vente.  
- Le fait qu'un bon de production ait été libéré ne signifie pas nécessairement que les matières ont été prélevées ou que le projet a été déplacé physiquement vers la première opération qui y est associée.  
- Dans un environnement MTO (Prod. pour commande), il n'est pas rare de créer un bon de production libéré immédiatement après l'entrée du document de vente.  
- Vous pouvez enregistrer la consommation de matières et la production réelles manuellement avec un bon de production libéré. En outre, la consommation automatique de matières et de production n'intervient que pour les bons de production libérés.  

### Bon de production achevé  
Le bon de production terminé est unique en raison des caractéristiques suivantes :  

- Un bon de production terminé est généralement un ordre qui a été fabriqué.  
- L'achèvement du bon de production est une tâche importante dans l'évaluation du cycle de vie de l'article en cours de production. L'achèvement d'un bon de production permet d'ajuster et de rapprocher l'évaluation coût.  
- Les bons de production terminés sont utilisés pour générer des rapports statistiques et prendre en charge la possibilité de remonter à d'autres ordres (ventes, production et achat, par exemple). La possibilité de remonter à un bon de production terminé permet d'examiner l'historique détaillé.  
- Il n'est jamais possible de modifier des ordres de fabrication terminés.  

## Exécution d'un bon de production  
Après qu'un bon de production a été créé et programmé, il doit être libéré à l'atelier pour exécution. Durant l'exécution de l'ordre, vous enregistrez les éléments suivants :  

- matières prélevées et consommées ;  
- temps passé à travailler sur l'ordre ;  
- quantité d'articles parents produite.  

Ces informations peuvent être enregistrées manuellement ou via une génération de rapport automatique, en fonction des articles définis dans le champ Méthode consommation de l’article et de l'atelier.  

### Consommation matière  
L'application offre une série d'options concernant la manière dont une compagnie manufacturière peut enregistrer une consommation matière. Par exemple, une consommation matière peut être enregistrée manuellement, ce qui peut être souhaitable en cas de remplacements fréquents de composantes ou de rebuts plus importants que prévu.  

La consommation de matières peut être traitée via le [journal consommation](production-how-to-post-consumption.md), mais peut également être enregistrée automatiquement par l’application à l’aide du processus de génération de rapport automatique (consommation). Les méthodes de génération de rapport sont les suivantes :  

- Manuel  
- Suivant  
- Amont  

La génération de rapports de consommation manuelle utilise le journal consommation pour spécifier un prélèvement de matière.  

En aval, la génération de rapports de consommation est basée sur l'hypothèse que la quantité prévue de toutes les matières nécessaires à la commande entière est consommée à la libération du bon de production, sauf en cas d'utilisation de codes lien itinéraire. En cas d'utilisation de codes lien itinéraire, les matières consommées après le début de l'opération sont enregistrées dans le journal de sortie. Pour consommer en aval le bon de production entier, vous devez effectuer les deux opérations suivantes :  

- La consommation en aval doit être activée pour tous les articles de la nomenclature de production de niveau supérieur sur leur fiche article.  
- Tous les codes lien itinéraire dans la nomenclature de production doivent être supprimés.  

En amont, la génération d'états de consommation enregistre la quantité réelle des matières prélevées ou consommées lorsque le statut d'un ordre de fabrication passe à *Terminé*, sauf en cas d'utilisation de codes lien gamme. En cas d'utilisation de codes lien itinéraire, les matières sont consommées après qu'une quantité d'articles parents a été enregistrée pour l'opération dans le journal de sortie.  

Lors de l'actualisation du bon de production, la méthode consommation est copiée à partir de la fiche article. Comme la méthode consommation de chaque bon de production contrôle le mode et le moment d'enregistrement de la consommation, il est important de noter que vous pouvez modifier la méthode de consommation d'articles spécifiques directement dans le bon de production. 

Pour plus d’informations, voir [Consommer en aval des composantes en fonction de la production réalisée](production-how-to-flush-components-according-to-operation-output.md).

### Production  
L'application offre la possibilité de suivre le temps consacré à un bon de production, en plus de l'enregistrement de la quantité produite. Ces informations permettent de déterminer plus précisément les coûts de production. De même, les fabricants utilisant un système d'évaluation standard peuvent souhaiter enregistrer des informations réelles afin de pouvoir développer de meilleures normes.  

La production peut être traitée via le [journal de sortie](production-how-to-post-output-quantity.md), mais aussi enregistrée automatiquement par l’application. L'application copie la méthode de consommation de la fiche unité de production ou atelier vers l'itinéraire du bon de production lors de l'actualisation. Comme pour la consommation matière, trois méthodes de génération de rapport s'appliquent à la production :  

- Manuel  
- Suivant  
- Amont  

La méthode manuelle utilise le journal de sortie pour spécifier le temps consommé et la quantité produite.  

En aval, cette méthode enregistre la sortie prévue (et le temps), qui est automatiquement enregistrée lors de la libération d'un bon de production. Les codes lien itinéraire n'interviennent pas comme facteurs dans la consommation en aval de la production.  

En amont, cette méthode enregistre la production prévue (et le temps), qui est automatiquement enregistrée à la fin d'un ordre de fabrication. Les codes lien itinéraire n'interviennent pas comme facteurs dans la consommation en amont de la production.  

### Report de la consommation et de la production  
Vous pouvez utiliser toute combinaison d'informations de consommation automatique et enregistrées manuellement tant pour la consommation que pour la production. Par exemple, vous pouvez consommer automatiquement en aval des composantes, tout en utilisant le journal consommation pour enregistrer les rebuts. De même, vous pouvez enregistrer automatiquement la production tout en utilisant le journal de sortie pour enregistrer les rebuts de l'article parent ou le temps supplémentaire consacré au traitement de l'ordre.  

Enfin, si vous entrez une consommation et une production manuellement, vous devez déterminer l'ordre dans lequel vous allez enregistrer ces informations. Vous pouvez commencer par enregistrer une consommation, puis utiliser une méthode de raccourci pour entrer les informations, basée sur une quantité de production prévue. Vous pouvez également commencer par entrer une production en utilisant la fonction **Éclater gamme**. Vous enregistrez ensuite une consommation sur la base de la quantité de production réelle.  

### Journal de production  
Le [journal production](production-how-to-register-consumption-and-output.md) combine les fonctions du journal consommation et des journaux de sortie dans un seul journal, directement accessible depuis le bon de production libéré.  

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

## Voir aussi
[Production](production-manage-manufacturing.md)
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
