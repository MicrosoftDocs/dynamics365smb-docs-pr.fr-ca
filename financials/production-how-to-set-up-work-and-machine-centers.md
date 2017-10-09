---
title: "Procédure : configurer des ateliers et des unités de production | Microsoft Docs"
description: "Les fiches **Atelier** organisent les exigences et les valeurs fixes des ressources de production, et régissent ainsi la production de l'atelier."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/04/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 8a7af6821affcef2c81499e904f2ed9520086323
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-work-centers-and-machine-centers"></a>Procédure : configurer des ateliers et des unités de production
L'application distingue trois types de capacité. Ces capacités sont ordonnées de façon hiérarchique. Chaque niveau contient les niveaux subordonnés.  

Le premier niveau correspond au groupe ateliers. Des ateliers sont affectés aux groupes ateliers. Chaque atelier ne peut appartenir qu'à un seul groupe ateliers.

Vous pouvez affecter plusieurs unités de production à chaque atelier. Une unité de production ne peut appartenir qu'à un seul atelier.  

La capacité planifiée d'un atelier comprend la disponibilité des unités de production correspondantes et la disponibilité planifiée supplémentaire de l'atelier. La disponibilité planifiée du groupe ateliers correspond donc à la somme de toutes les disponibilités correspondantes des unités de production et des ateliers.  

La disponibilité est enregistrée dans les écritures calendrier. Avant de configurer des ateliers ou des unités de production, vous devez configurer des calendriers usine. Pour plus d'informations, voir [Procédure : créer des calendriers usine](production-how-to-create-work-center-calendars.md).  

## <a name="to-set-up-a-work-center"></a>Pour configurer un atelier
La procédure suivante décrit essentiellement comment configurer un atelier. La procédure de configuration d'un calendrier unité de production est similaire, sauf pour le raccourci **Configuration itinéraire**.  

1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Centres de charge**, puis sélectionnez le lien connexe.  
2.  Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  Dans le champ **Groupe ateliers**, sélectionnez le regroupement de ressources de niveau supérieur sous lequel l'atelier est organisé, le cas échéant. Choisissez l'action **Nouveau** dans la liste déroulante.  
5.  Sélectionnez le champ **Bloqué** pour empêcher le centre de charge d'être utilisé pour quelque traitement que ce soit. Cela signifie que la sortie ne peut pas être reportée pour un article produit dans l'atelier. Pour plus d'informations, voir [Procédure : reporter la sortie de production](production-how-to-post-output-quantity.md).
6.  Dans le champ **Coût unitaire direct**, entrez le coût de production d'une unité de mesure dans le centre de charge, sans intégrer les autres éléments de coût. Ce coût est souvent appelé *frais de main-d'œuvre directs*.  
7.  Dans le champ **% coût indirect**, entrez les coûts opératoires généraux de l'utilisation du centre de charge sous la forme d'un pourcentage du coût unitaire direct. Ce pourcentage est ajouté au coût direct lors du calcul du coût unitaire.  
8.  Dans le champ **Frais généraux**, entrez tous les coûts non opératoires, comme les frais d'entretien, de l'atelier sous la forme d'un montant absolu.  

    Le champ **Coût unitaire** affiche le résultat du calcul du coût unitaire de production d'une unité de mesure dans l'atelier. Tous les éléments de coût sont pris en compte comme suit :  

    Coût unitaire = Coût unitaire direct + (Coût unitaire direct x % coût indirect) + Frais généraux.  

9.  Dans le champ **Unité de coût**, indiquez si le calcul ci-dessus doit être basé sur le délai passé : **Heure** ou sur le nombre d'unités produites : **Unités**.  
10.  Sélectionnez le champ **Coût unitaire spécifique** pour définir le coût unitaire du centre de charge sur la ligne gamme dans laquelle il est utilisé. Ceci peut s'avérer utile pour les opérations dont les coûts capacité diffèrent radicalement de ceux normalement traités dans l'atelier.  
11.  Dans le champ **Méthode consommation**, indiquez si la validation de production du centre de charge doit être calculée et validée manuellement ou automatiquement, de l'une des manières suivantes.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Manuel**|La consommation est reportée manuellement dans le journal de sortie ou le journal de production.|
    |**Aval**|La consommation est calculée et reportée automatiquement lorsque le bon de production est libéré.|  
    |**Amont**|La consommation est calculée et reportée automatiquement lorsque le bon de production est terminé.|  

    > [!NOTE]  
    >  Si nécessaire, vous pouvez modifier la méthode de consommation sélectionnée ici et sur la fiche **article** pour des opérations précises en modifiant le paramétrage des lignes gamme.

12.  Dans le champ **Code unité**, entrez l'unité de temps utilisée pour le calcul de coût et la planification de capacité du centre de charge.
    Pour contrôler en permanence la consommation, vous devez d'abord définir une méthode de mesure. Les unités que vous saisissez sont des unités de base. Par exemple, la durée de traitement est mesurée en heures et en minutes.

    > [!NOTE]  
    > Si vous choisissez d'utiliser Jours, n'oubliez pas qu'1 jour = 24 heures et non 8 (heures de travail).

13.  Dans le champ **Capacité**, indiquez si le centre de charge a plusieurs postes ou personnes travaillant simultanément. Si votre installation de **Nom du produit** n'inclut pas la fonctionnalité Unité de production, la valeur de ce champ doit être **1**).  
14.  Dans le champ **Rendement**, entrez le pourcentage de la production standard prévue qui est réalisé par le centre de charge. Si vous entrez **100**, cela signifie que la production réelle du centre de charge est identique à la production standard.  
15. Cochez la case **Calendrier consolidé** si vous utilisez également des unités de production. Ainsi, les écritures calendrier sont générées à partir des calendriers d'unité de production.  
16.  Dans le champ **Code calendrier usine**, sélectionnez un calendrier usine. Pour plus d'informations, voir [Procédure : créer des calendriers usine](production-how-to-create-work-center-calendars.md).  
17.  Dans le champ **File d'attente**, spécifiez le délai fixe qui doit s'écouler avant que le travail attribué ne commence dans le centre de charge. Notez que la file d'attente ainsi définie est ajoutée aux autres éléments de temps non productifs, tels que le temps d'attente et le temps de transfert, définis sur les lignes itinéraire utilisant cet atelier.  

## <a name="example---different-machine-centers-assigned-to-a-work-center"></a>Exemple - Plusieurs unités de production sont affectées à un atelier
Lors de la configuration des postes et des centres de charge, il convient de planifier les capacités constituant la capacité totale.

Si différentes unités de production (par exemple, 210 Table d'emballage 1, 310 Cabine de peinture...) sont affectées à un atelier, il convient de prendre en compte les capacités de chaque unité de production, car la panne de l'une de ces unités risque d'interrompre l'ensemble du processus. Vous pouvez saisir les groupes postes en fonction de leur capacité, mais vous ne pouvez pas les inclure dans la planification. Lorsque vous désactivez le champ **Calendrier consolidé**, seule la capacité du centre de charge est affectée au planning, pas le poste de charge.

Toutefois, lorsqu'un atelier combine des unités de production identiques (par exemple, 210 Table d'emballage 1 et 220 Table d'emballage 2), il convient de prendre en compte cet atelier comme la somme des unités de production affectées. L'atelier est donc répertorié avec une capacité zéro. La capacité commune est affectée au centre de charge lorsque vous activez le champ **Calendrier consolidé**.

Lorsque les capacités des ateliers n'ajoutent en rien à la capacité totale, vous pouvez paramétrer Rendement = 0.

## <a name="see-also"></a>Voir aussi  
[Procédure : créer des calendriers usine](production-how-to-create-work-center-calendars.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Planification](production-planning.md)   
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

