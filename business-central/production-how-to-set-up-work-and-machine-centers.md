---
title: Configurer des ateliers et des unités de production
description: 'Les fiches atelier organisent les exigences et les valeurs fixes des ressources de production, et régissent ainsi la production des ateliers.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: '99000754, 99000755, 99000756, 99000758, 99000760, 99000761, 99000762'
ms.date: 06/13/2024
ms.service: dynamics-365-business-central
---
# <a name="set-up-work-centers-and-machine-centers"></a>Configurer des ateliers et des unités de production

[!INCLUDE [prod_short](includes/prod_short.md)] distingue trois types de capacité. Ces capacités sont ordonnées de façon hiérarchique où chaque niveau contient les niveaux subordonnés.  

Le premier niveau correspond au groupe ateliers. Des ateliers sont affectés à des groupes d'ateliers. Chaque atelier ne peut appartenir qu'à un seul groupe ateliers.

Vous pouvez affecter plusieurs unités de production aux ateliers. Une unité de production ne peut appartenir qu’à un seul atelier.  

La capacité planifiée d’un atelier se compose de la disponibilité des unités de production correspondantes et de la disponibilité planifiée de l'atelier. La disponibilité planifiée du groupe ateliers correspond donc à la somme de toutes les disponibilités correspondantes des unités de production et des ateliers. La disponibilité est enregistrée dans les écritures calendrier.  

> [!IMPORTANT]
> Avant de configurer des ateliers ou des unités de production, vous devez configurer des calendriers usine. Pour plus d'informations, voir [Créer des calendriers usine](production-how-to-create-work-center-calendars.md).

## <a name="to-set-up-a-work-center"></a>Pour configurer un atelier

Les étapes suivantes décrivent comment configurer un atelier. La procédure de configuration d’un calendrier d'unité de production est similaire, sauf pour le raccourci **Configuration itinéraire**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ateliers**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Dans le champ **Code groupe ateliers**, sélectionnez le regroupement de ressources de niveau supérieur sous lequel l'atelier est organisé, au besoin. Choisissez l'action **Nouveau** dans la liste déroulante.  
5. Dans le champ **Autre atelier**, sélectionnez l'atelier à utiliser si cet atelier n'est pas disponible ou si la demande dépasse sa capacité. L’autre atelier est à titre informatif uniquement et n'est pas automatiquement inclus dans les processus de planification.
6. Sélectionnez le champ **Bloqué** pour empêcher le centre de charge d'être utilisé pour quelque traitement que ce soit. Cela signifie que la sortie ne peut pas être reportée pour un article produit dans l'atelier. Pour plus d'informations, voir [Reporter la production](production-how-to-post-output-quantity.md).
7. Dans le champ **Coût unitaire direct**, entrez le coût de production d'une unité de mesure dans le centre de charge, sans intégrer les autres éléments de coût. Ce coût est souvent appelé *frais de main-d'œuvre directs*.  
8. Dans le champ **% coût indirect**, entrez les coûts opératoires généraux de l'utilisation du centre de charge sous la forme d'un pourcentage du coût unitaire direct. Ce pourcentage est ajouté au coût direct lors du calcul du coût unitaire.  
9. Dans le champ **Frais généraux**, entrez tous les coûts non opérationnels, comme les frais d'entretien, de l'atelier sous la forme d’un montant absolu.  

    Le champ **Coût unitaire** affiche le résultat du calcul du coût unitaire de production d'une unité de mesure dans l'atelier. Tous les éléments de coût sont pris en compte comme suit :  

    Coût unitaire = Coût unitaire direct + (Coût unitaire direct x % coût indirect) + Frais généraux.  

10. Dans le champ **Unité de coût**, indiquez si le calcul de coût unitaire doit être basé sur le délai passé : Heure ou sur le nombre d’unités produites.  
11. Sélectionnez le champ **Coût unitaire spécifique** pour définir le coût unitaire de l'atelier sur la ligne itinéraire dans laquelle il est utilisé. Ce paramètre peut s’avérer utile pour les opérations dont les coûts capacité diffèrent de ceux normalement traités dans cet atelier.  
12. Dans le champ **Méthode consommation**, indiquez s'il faut calculer et reporter manuellement ou automatiquement la sortie dans cet atelier, de l’une des manières suivantes.

    |Option|Désignation|
    |------|-----------|
    |**Manuelle**| Reporter manuellement le temps utilisé, la sortie et le rebut dans le journal de sortie ou le journal production.|
    |**Aval**|Reporter automatiquement la sortie lorsque le bon de production est émis.|
    |**Post-déduction**|Reporter automatiquement la sortie lorsque le bon de production est terminé.|

    > [!NOTE]
    > Si nécessaire, vous pouvez modifier la méthode de consommation sélectionnée ici pour des opérations précises en modifiant le paramétrage des lignes itinéraire

13. Dans le champ **Code unité de mesure**, entrez l'unité de temps utilisée pour le calcul de coût et la planification de capacité de l'atelier.
    Pour contrôler en permanence la consommation, vous devez d’abord définir une méthode de mesure. Les unités que vous saisissez sont des unités de base. Par exemple, la durée de traitement est mesurée en heures et en minutes.

    > [!NOTE]  
    > Si vous utilisez Jours, n’oubliez pas qu’un jour dure 24 heures et non une journée de travail de huit heures.

14. Dans le champ **Capacité**, indiquez si le centre de charge a plusieurs postes ou personnes travaillant simultanément. Si votre [!INCLUDE[prod_short](includes/prod_short.md)] n’inclut pas la fonctionnalité d'unité de production, la valeur de ce champ doit être **1**.  
15. Dans le champ **Rendement**, entrez le pourcentage de la production standard prévue qui est réalisé par le centre de charge. Si vous entrez **100**, cela signifie que la production réelle du centre de charge est identique à la production standard.  
16. Activez le bouton à bascule **Calendrier consolidé** si vous utilisez également des unités de production. Ce paramètre garantit que les écritures calendrier sont générées à partir des calendriers d'unité de production.  
17. Dans le champ **Code calendrier usine**, sélectionnez un calendrier usine. Pour plus d'informations, voir [Créer des calendriers usine](production-how-to-create-work-center-calendars.md).  
18. Dans le champ **File d'attente**, spécifiez le délai fixe qui doit s'écouler avant que le travail attribué ne commence dans le centre de charge. 

> [!NOTE]
> Utilisez les file d'attentes pour fournir un tampon entre le moment où une composante arrive sur une unité de production ou un atelier et le moment où l’opération démarre réellement. Par exemple, une pièce est livrée à une unité de production à 10h00, mais il faut une heure pour la monter sur la machine, de sorte que l’opération ne démarre pas avant 11h00. Pour tenir compte de cette heure, la durée file d’attente serait d’une heure. La valeur du champ **Durée file d'attente** sur une fiche unité de production ou atelier plus la somme des valeurs des champs **Temps de préparation**, **Temps d'exécution**, **Temps d’attente** et **Temps de transfert** sur la ligne itinéraire article se combinent pour donner le délai de fabrication de l’article. Cela permet de fournir des temps de production globaux précis.  

## <a name="considerations-about-capacity"></a>Considérations sur la capacité

La capacité et l’efficacité des ateliers et des unités de production n’affectent pas seulement la capacité disponible. Les valeurs ont également un impact sur le temps de production global qui se compose du temps de préparation et du temps d’exécution, qui sont tous deux définis sur la ligne itinéraire.  

Lorsque vous affectez une ligne itinéraire à un atelier ou une unité de production, [!INCLUDE [prod_short](includes/prod_short.md)] calcule :

- Quelle capacité est nécessaire.
- Combien de temps prend l’opération pour se terminer.  

### <a name="run-time"></a>Temps d’exécution

Pour calculer le temps d’exécution, le système alloue le temps exact qui est défini dans le champ **Durée** de la ligne itinéraire. Ni l’efficacité ni la capacité n’affectent le temps alloué. Par exemple, si le temps d’exécution est défini sur 2 heures, le temps alloué est de 2 heures, quelles que soient les valeurs des champs d’efficacité et de capacité de l'atelier.  

> [!NOTE]
> La capacité utilisée dans les calculs est définie comme la valeur minimale entre la capacité définie dans l'atelier ou l'unité de production et la capacité concurrente définie pour la ligne itinéraire. Si un atelier a une capacité de 100, mais que la capacité concurrente de la ligne itinéraire est de 2, alors *2* sera utilisé dans les calculs.

La *durée* d’une opération, au contraire, considère à la fois l’efficacité et la capacité. La durée est calculée comme *Temps d’exécution / Efficacité / Capacité*. La liste suivante montre quelques exemples de calcul de durée pour un même temps d’exécution, qui est défini comme 2 heures pour la ligne itinéraire :

- Une efficacité de 80 % signifie que vous avez besoin de 2,5 heures au lieu de deux heures  
- Une efficacité de 200 % signifie que vous pouvez terminer le travail en une heure. Vous pouvez creuser le trou deux fois plus vite si vous avez une excavatrice deux fois plus grande que la plus petite  

    Vous pouvez obtenir le même résultat si vous utilisez deux pelles plus petites au lieu d’une grande. Utiliser *2* comme la capacité et *100 %* comme l’efficacité  

La capacité fractionnaire est délicate. Nous en discuterons plus tard dans cet article. 

### <a name="setup-time"></a>Temps de préparation

La répartition du temps pour le temps de préparation dépend de la capacité et est calculée comme *Temps de préparation * Capacité*. Par exemple, si la capacité est définie sur *2*, votre temps de préparation alloué est doublé, car vous devez configurer deux machines pour l’opération.  

La *Durée* du temps de préparation dépend de l’efficacité et est calculée comme *Temps de préparation / Efficacité*. 

- Une efficacité de 80 % signifie que vous avez besoin de 2,5 heures au lieu de deux heures à configurer.  
- Une efficacité de 200 % signifie que vous pouvez terminer la configuration en 1 heure au lieu des 2 heures définies dans la ligne itinéraire.  

La capacité fractale n’est utilisée que dans des cas précis.

### <a name="work-center-processing-multiple-orders-simultaneously"></a>Atelier traitant plusieurs commandes simultanément

Prenons l’exemple d’une cabine de peinture au pistolet. Elle a la même configuration et les mêmes temps d’exécution pour chaque lot traité. Mais chaque lot peut contenir plusieurs commandes individuelles peintes simultanément.  

Dans ce cas, le temps de préparation et la capacité concurrente gèrent les coûts alloués aux commandes. Nous vous recommandons de ne pas utiliser le temps d’exécution dans les lignes itinéraire.  

Le temps de préparation affecté pour chaque ordre individuel sera dans l’ordre inverse du nombre d’ordres (quantités) qui sont exécutés simultanément. Voici quelques autres exemples de calcul du temps préparation lorsqu’il est défini sur deux heures pour la ligne itinéraire :

- S’il y a deux ordres, la capacité concurrente dans la ligne itinéraire doit être définie sur 0,5.

    En conséquence, la capacité allouée pour chacune est d’une heure, mais la durée de chaque commande reste de deux heures.
- S’il y a deux ordres avec une quantité de un et quatre, respectivement, la capacité concurrente pour la ligne itinéraire du premier ordre est de 0,2 et de 0,8 pour la seconde.  

    En conséquence, la capacité allouée pour la première commande est de 24 min et pour la seconde de 96. La durée des deux ordres reste de deux heures.  

Dans les deux cas, le temps total affecté pour tous les ordres est de deux heures.


### <a name="efficient-resource-can-dedicate-only-part-of-their-work-date-to-productive-work"></a>Une ressource efficace ne peut consacrer qu’une partie de sa date de travail à un travail productif

> [!NOTE]
> Ce scénario n’est pas recommandé. Nous vous recommandons d’utiliser plutôt l’efficacité. 

L’un de vos ateliers représente un collaborateur expérimenté qui travaille avec 100 % d’efficacité sur les tâches. Mais il ne peut consacrer que 50 % de son temps de travail à des tâches, car le reste du temps, il résout des tâches administratives. Bien que ce collaborateur soit capable d’accomplir une tâche de deux heures en deux heures exactement, vous devez en moyenne attendre encore deux heures pendant que la personne s’occupe d’autres tâches.  

Le temps d’exécution affecté est de deux heures et la durée est de quatre heures.  

N’utilisez pas le temps de préparation pour de tels scénarios, car [!INCLUDE [prod_short](includes/prod_short.md)] n’alloue que 50 % du temps. Si le temps de préparation est défini sur *2*, le temps de préparation alloué est d’une heure et la durée est de deux heures.

### <a name="consolidated-calendar"></a>Calendrier consolidé

Lorsque le champ **Calendrier consolidé** est sélectionné, l'atelier n’a pas de capacité propre. Au lieu de cela, sa capacité est égale à la somme des capacités de toutes les unités de production qui sont affectées à l'atelier.  

> [!NOTE]
> L’efficacité de l'unité de production est convertie en capacité de l'atelier.

Par exemple, si vous disposez de deux unités de production avec un rendement de 80 et 70 respectivement, l’entrée de calendrier consolidée contient :

- Une efficacité de 100
- Une capacité de 1,5
- Une capacité totale de 12 heures (poste de huit heures * 1,5 capacité).

> [!NOTE]
> Utilisez le champ **Calendrier consolidé** lorsque vous structurez vos itinéraires pour programmer les opérations de production au niveau de l'unité de production, et non au niveau de l'atelier. Lorsque vous consolidez le calendrier, la page **Charge atelier** et les rapports deviennent une vue d’ensemble de la charge globale dans toutes les unités de production qui sont affectées à l'atelier.

### <a name="example---different-machine-centers-assigned-to-a-work-center"></a>Exemple – Différentes unités de production affectées à un atelier

Il est important de planifier quelles capacités constituent la capacité totale lorsque vous configurez des unités de production et des ateliers.

Si différentes unités de production (telles que 210 Table d’emballage 1, 310 Cabine de peinture...) sont affectées à un atelier, il convient de prendre en compte les capacités de chaque unité de production, car la panne de l’une des unités de production risque d’interrompre l’ensemble du processus. Vous pouvez saisir les groupes unités de production en fonction de leur capacité mais ils ne sont pas inclus dans la planification. Si vous désactivez le bouton à bascule **Calendrier consolidé**, seule la capacité de l'atelier est affectée dans la planification. La capacité de l'unité de production est exclue.

Toutefois, si vous combinez des unités de production identiques (tels que 210 Table d’emballage 1 et 220 Table d’emballage 2), vous pouvez considérer l'atelier comme somme des unités de production affectées. L'atelier est donc répertorié avec une capacité zéro. Si vous activez le bouton à bascule **Calendrier consolidé**, la capacité commune est affectée à l'atelier.

Si vous ne voulez pas que les capacités des ateliers contribuent à la capacité totale, spécifiez **0** dans le champ **Rendement**.

## <a name="to-set-up-a-capacity-constrained-machine-or-work-center"></a>Pour configurer un atelier ou une unité de production à contrainte de capacité

Vous devez configurer les ressources de production que vous considérez comme critique et de l'accepter comme une charge limitée au lieu de la charge illimitée par défaut que d'autres ressources de production acceptent. Une ressource à contrainte de capacité peut être un atelier ou une unité de production qui est un goulot d'étranglement et pour lequel vous souhaitez établir une charge limitée.

[!INCLUDE[prod_short](includes/prod_short.md)] ne prend pas en charge le contrôle détaillé d’atelier. Il prévoit une utilisation faisable des ressources via un calendrier approximatif, mais il ne crée pas et ne met pas à jour automatiquement des calendriers détaillés sur la base de priorités ou de règles d'optimisation.

Sur le **Ressources limitées en capacité**, vous pouvez créer une configuration pour éviter que les ressources ne soient surchargées. La configuration peut aussi garantir que la capacité n’est pas laissée non allouée, si cela pouvait augmenter le délai d’exécution d’un bon de production. Dans le champ **Seuil (% capacité totale)**, vous pouvez ajouter un seuil aux ressources afin de réduire la répartition des opérations. Ce paramètre permet au système de programmer la charge le dernier jour possible en dépassant légèrement le pourcentage de charge critique. Le dépassement du pourcentage de charge peut réduire le nombre d’opérations fractionnées.

Quand la planification avec des ressources avec capacité critique, [!INCLUDE [prod_short](includes/prod_short.md)] veille à ce que les ressources ne soient pas chargées au-dessus de leur capacité (charge critique). Il affecte chaque opération à l’emplacement du temps disponible le plus proche. Si le créneau n’est pas assez long pour effectuer toute l’opération, il divise l’opération en au moins deux parties placées dans les créneaux disponibles les plus proches.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Capacités critiques**, puis choisissez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Renseignez les champs selon vos besoins.

> [!NOTE]
> Les opérations des ateliers ou unités de production qui sont configurées comme ressources contraintes sont toujours planifiées en série. Cette planification signifie que si une ressource contrainte a plusieurs capacités, ces capacités doivent être planifiées dans l’ordre. Vous ne pouvez pas les planifier en parallèle comme ils le seraient si l'atelier ou l'unité de production n’était pas configuré(e) comme une ressource contrainte. Pour une ressource contrainte, le champ **Capacité** de l'atelier ou de l'unité de production est supérieur à **1**.

> En cas de répartition des opérations, le temps de configuration n’est affecté qu’une fois, car on suppose qu’un certain ajustement manuel est effectué pour optimiser le calendrier.

## <a name="see-also"></a>Voir aussi .

[Créer des calendriers usine](production-how-to-create-work-center-calendars.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Fabrication](production-manage-manufacturing.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
