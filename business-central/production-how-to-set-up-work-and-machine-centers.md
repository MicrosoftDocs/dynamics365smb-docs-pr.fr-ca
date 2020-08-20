---
title: 'Procédure : configurer des ateliers et des unités de production | Microsoft Docs'
description: Les fiches **centre de charge** organisent les exigences et les valeurs fixes des ressources de production, et régissent ainsi la production des centres de charge.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 08/10/2020
ms.author: sgroespe
ms.openlocfilehash: 4e3a6c646605d5c1da26ff0d0795413a53fabe82
ms.sourcegitcommit: 007b331b6974983ee614db0406f00777da359ecb
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/10/2020
ms.locfileid: "3677293"
---
# <a name="set-up-work-centers-and-machine-centers"></a>Configurer des ateliers et des unités de production

L'application distingue trois types de capacité. Ces capacités sont ordonnées de façon hiérarchique. Chaque niveau contient les niveaux subordonnés.  

Le premier niveau correspond au groupe ateliers. Des ateliers sont affectés aux groupes ateliers. Chaque atelier ne peut appartenir qu'à un seul groupe ateliers.

Vous pouvez affecter plusieurs unités de production à chaque atelier. Une unité de production ne peut appartenir qu'à un seul atelier.  

La capacité planifiée d'un atelier comprend la disponibilité des unités de production correspondantes et la disponibilité planifiée supplémentaire de l'atelier. La disponibilité planifiée du groupe ateliers correspond donc à la somme de toutes les disponibilités correspondantes des unités de production et des ateliers.  

La disponibilité est enregistrée dans les écritures calendrier. Avant de configurer des ateliers ou des unités de production, vous devez configurer des calendriers usine. Pour plus d'informations, voir [Créer des calendriers usine](production-how-to-create-work-center-calendars.md).  

## <a name="to-set-up-a-work-center"></a>Pour configurer un atelier

La procédure suivante décrit essentiellement comment configurer un atelier. La procédure de configuration d'un calendrier unité de production est similaire, sauf pour le raccourci **Configuration itinéraire**.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Ateliers**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Dans le champ **Groupe ateliers**, sélectionnez le regroupement de ressources de niveau supérieur sous lequel l'atelier est organisé, le cas échéant. Choisissez l'action **Nouveau** dans la liste déroulante.  
5. Sélectionnez le champ **Bloqué** pour empêcher le centre de charge d'être utilisé pour quelque traitement que ce soit. Cela signifie que la sortie ne peut pas être reportée pour un article produit dans l'atelier. Pour plus d'informations, voir [Reporter la production](production-how-to-post-output-quantity.md).
6. Dans le champ **Coût unitaire direct**, entrez le coût de production d'une unité de mesure dans le centre de charge, sans intégrer les autres éléments de coût. Ce coût est souvent appelé *frais de main-d'œuvre directs*.  
7. Dans le champ **% coût indirect**, entrez les coûts opératoires généraux de l'utilisation du centre de charge sous la forme d'un pourcentage du coût unitaire direct. Ce pourcentage est ajouté au coût direct lors du calcul du coût unitaire.  
8. Dans le champ **Frais généraux**, entrez tous les coûts non opératoires, comme les frais d'entretien, de l'atelier sous la forme d'un montant absolu.  

    Le champ **Coût unitaire** affiche le résultat du calcul du coût unitaire de production d'une unité de mesure dans l'atelier. Tous les éléments de coût sont pris en compte comme suit :  

    Coût unitaire = Coût unitaire direct + (Coût unitaire direct x % coût indirect) + Frais généraux.  

9. Dans le champ **Unité de coût**, indiquez si le calcul ci-dessus doit être basé sur le délai passé : **Heure** ou sur le nombre d'unités produites : **Unités**.  
10. Sélectionnez le champ **Coût unitaire spécifique** pour définir le coût unitaire de l'atelier sur la ligne itinéraire dans laquelle il est utilisé. Ceci peut s'avérer utile pour les opérations dont les coûts capacité diffèrent radicalement de ceux normalement traités dans l'atelier.  
11. Dans le champ **Méthode consommation**, indiquez si la validation de production du centre de charge doit être calculée et validée manuellement ou automatiquement, de l'une des manières suivantes.

    |Option|Description|
    |------|-----------|
    |**Manuel**|La consommation est reportée manuellement dans le journal de sortie ou de production.|
    |**Aval**|La consommation est calculée et reportée automatiquement lorsque le bon de production est libéré.|
    |**Amont**|La consommation est calculée et reportée automatiquement lorsque le bon de production est terminé.|

    > [!NOTE]
    > Si nécessaire, vous pouvez modifier la méthode de consommation sélectionnée ici et sur la fiche **Article** pour des opérations spécifiques en modifiant le paramètre des lignes itinéraire

12. Dans le champ **Code unité de mesure**, entrez l'unité de temps utilisée pour le calcul de coût et la planification de capacité de l'atelier.
    Pour contrôler en permanence la consommation, vous devez d'abord définir une méthode de mesure. Les unités que vous saisissez sont des unités de base. Par exemple, la durée de traitement est mesurée en heures et en minutes.

    > [!NOTE]  
    > Si vous choisissez d'utiliser Jours, n'oubliez pas qu'1 jour = 24 heures et non 8 (heures de travail).

13. Dans le champ **Capacité**, indiquez si le centre de charge a plusieurs postes ou personnes travaillant simultanément. Si votre installation de [!INCLUDE[d365fin](includes/d365fin_md.md)] n'inclut pas la fonctionnalité Unité de production, la valeur de ce champ doit être **1**.  
14. Dans le champ **Rendement**, entrez le pourcentage de la production standard prévue qui est réalisé par le centre de charge. Si vous entrez **100**, cela signifie que la production réelle du centre de charge est identique à la production standard.  
15. Cochez la case **Calendrier consolidé** si vous utilisez également des unités de production. Ainsi, les écritures calendrier sont générées à partir des calendriers d'unité de production.  
16. Dans le champ **Code calendrier usine**, sélectionnez un calendrier usine. Pour plus d'informations, voir [Créer des calendriers usine](production-how-to-create-work-center-calendars.md).  
17. Dans le champ **File d'attente**, spécifiez le délai fixe qui doit s'écouler avant que le travail attribué ne commence dans le centre de charge. Notez que la file d'attente ainsi définie est ajoutée aux autres éléments de temps non productifs, tels que le temps d'attente et le temps de transfert, définis sur les lignes itinéraire utilisant cet atelier.  

## <a name="example---different-machine-centers-assigned-to-a-work-center"></a>Exemple - Plusieurs unités de production sont affectées à un atelier

Lors de la configuration des postes et des centres de charge, il convient de planifier les capacités constituant la capacité totale.

Si différentes unités de production (par exemple, 210 Table d'emballage 1, 310 Cabine de peinture...) sont affectées à un atelier, il convient de prendre en compte les capacités de chaque unité de production, car la panne de l'une de ces unités risque d'interrompre l'ensemble du processus. Vous pouvez saisir les groupes postes en fonction de leur capacité, mais vous ne pouvez pas les inclure dans la planification. Lorsque vous désactivez le champ **Calendrier consolidé**, seule la capacité du centre de charge est affectée au planning, pas le poste de charge.

Toutefois, lorsqu'un atelier combine des unités de production identiques (par exemple, 210 Table d'emballage 1 et 220 Table d'emballage 2), il convient de prendre en compte cet atelier comme la somme des unités de production affectées. L'atelier est donc répertorié avec une capacité zéro. La capacité commune est affectée au centre de charge lorsque vous activez le champ **Calendrier consolidé**.

Lorsque les capacités des ateliers n'ajoutent en rien à la capacité totale, vous pouvez paramétrer Rendement = 0.

## <a name="to-set-up-a-capacity-constrained-machine-or-work-center"></a>Pour configurer un atelier ou une unité de production à contrainte de capacité

Vous devez configurer les ressources de production que vous considérez comme critique et de l'accepter comme une charge limitée au lieu de la charge illimitée par défaut que d'autres ressources de production acceptent. Une ressource à contrainte de capacité peut être un atelier ou une unité de production que vous avez identifié comme étant un goulot d'étranglement et pour lequel vous souhaitez établir une charge limitée.

[!INCLUDE[d365fin](includes/d365fin_md.md)] ne prend pas en charge le contrôle détaillé d'atelier. Il prévoit une utilisation faisable des ressources via un calendrier approximatif, mais il ne crée pas et ne met pas à jour automatiquement des calendriers détaillés sur la base de priorités ou de règles d'optimisation.

Sur la page **Ressources contraintes de capacité**, vous pouvez effectuer des configurations qui évitent la surcharge de ressources spécifiques et permettent de s'assurer qu'aucune capacité n'est laissée non affectée si elle peut augmenter le délai d'exécution d'un bon de production. Dans le champ **Seuil (% capacité totale)**, vous pouvez ajouter un seuil aux ressources afin de réduire la répartition des opérations. Cela permet au système de programmer une charge sur le dernier jour possible en dépassant légèrement le pourcentage de charge critique si ceci peut réduire le nombre d'opérations qui sont divisées.

Lors de la planification avec des ressources avec contraintes de capacité, le système veille à ce qu'aucune ressource ne soit chargée au-dessus de sa capacité définie (charge critique). Ceci est effectué en affectant chaque opération à l'emplacement du temps disponible le plus proche. Si le créneau n'est pas assez long pour effectuer toute l'opération, l'opération est répartie en au moins deux parties placées dans les créneaux disponibles les plus proches.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Capacités critiques**, puis choisissez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Renseignez les champs selon vos besoins.

> [!NOTE]
> Les opérations d'ateliers ou d'unités de production qui sont configurés comme ressources contraintes sont toujours planifiées en série. Cela signifie que même si une ressource contrainte a plusieurs capacités, ces capacités ne peuvent être planifiées que dans l'ordre, pas en parallèle, comme c'est le cas si l'atelier ou l'unité de production n'a pas été défini en tant que ressource contrainte. Dans une ressource contrainte, le champ Capacité de l'atelier ou de l'unité de production est supérieur à 1.

> En cas de répartition des opérations, le temps de préparation n'est affecté qu'une fois car on suppose qu'un certain ajustement manuel est effectué pour optimiser le calendrier.

## <a name="see-also"></a>Voir aussi

[Créer des calendriers usine](production-how-to-create-work-center-calendars.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
