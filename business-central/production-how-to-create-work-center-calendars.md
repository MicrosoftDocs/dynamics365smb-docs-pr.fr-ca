---
title: Paramétrer des calendriers usine
description: La création et l’activation d’un calendrier d’atelier impliquent plusieurs tâches, notamment la configuration des calendriers d’atelier et la création de quarts de travail.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 9291, 9293, 9295, 99000750, 99000751, 99000752, 99000753, 99000759, 99000769, 99000770, 99000771, 99000772, 99000920
ms.date: 06/22/2021
ms.author: edupont
ms.openlocfilehash: a39df1fc7ccff9d3f4fcfbf76e7d6a57a7801bce
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8131337"
---
# <a name="set-up-shop-calendars"></a>Paramétrer des calendriers usine

Les calendriers d'atelier ou de poste de charge spécifient les jours ouvrés et les heures de travail, les équipes, les jours fériés et les absences déterminant la capacité disponible brute de l'atelier, mesurée en unités de temps, en fonction des valeurs d'efficacité et de capacité définies.

Avant de calculer un calendrier d'unité de production ou d'atelier spécifique, vous devez configurer un ou plusieurs calendriers usine généraux. Les calendriers usine définissent la semaine de travail standard en fonction des heures de début et de fin de chaque jour ouvré et des changements d'équipe. En outre, ils déterminent les jours fériés fixes de l'année.  

La procédure suivante décrit comment configurer des calendriers d'atelier. Les étapes sont similaires lorsque vous configurez des calendriers d'unité de production.  

## <a name="to-create-work-shifts"></a>Pour créer des équipes  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Équipes**, puis choisissez le lien associé.  
2.  Sur une ligne blanche, entrez le numéro d'identification de l'équipe, par exemple, **1**, dans le champ **Code**.  
3.  Dans le champ **Désignation**, entrez la désignation de l'équipe, par exemple, **1ère équipe**.  
4.  Vous pouvez également renseignez les lignes d'une deuxième ou troisième équipe.  

Même si vos centres de charge n'ont pas recours à diverses équipes, entrez au moins un code équipe.  

## <a name="to-set-up-a-shop-calendar"></a>Pour configurer un calendrier usine  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Calendriers usine**, puis choisissez le lien associé.  
2.  Sur une ligne blanche, entrez le numéro d'identification du calendrier usine dans le champ **Code**.  
3.  Dans le champ **Désignation**, entrez la désignation du calendrier usine.  
4.  Choisissez l'action **Jours ouvrés**.
5.  Sur la page **Jours ouvrés calendrier usine**, définissez une semaine de travail complète, avec les heures de début et de fin pour chaque jour.  

    Dans le champ **Code équipe**, sélectionnez l'une des équipes que vous avez défini précédemment. Ajoutez une ligne pour chaque jour ouvré et chaque équipe. Par exemple :  

    Lundi  07:00 15:00 1   
    Mardi 07:00 15:00 1  

    Si vous avez besoin d'un calendrier usine intégrant deux équipes, vous devez le remplir de la manière suivante :  

    Lundi 07:00 15:00 1   
    Lundi 07:00 15:00 2  
    Mardi 07:00 15:00 1  
    Mardi 15:00 23:00 2  

    Les jours non définis dans le calendrier usine, comme le samedi et le dimanche, sont considérés comme des jours chômés : une capacité disponible nulle leur est attribuée dans le calendrier d'atelier.  

    Une fois tous les jours ouvrés de la semaine définis, fermez la page **Jours ouvrés calendrier usine** et passez aux jours fériés.  

6.  Sur la page **Calendriers usine**, sélectionnez le calendrier usine, puis choisissez l'action **Jours fériés**.
7. Sur la page **Jours fériés calendrier usine**, définissez les jours fériés de l'année en indiquant la date et l'heure de début, l'heure de fin et la description de chaque jour férié sur une ligne distincte. Par exemple :  

    04/07/14 0:00:00 23:59:00 Vacances d'été  
    05/07/14 0:00:00 23:59:00 Vacances d'été  
    06/07/14 0:00:00 23:59:00 Vacances d'été  

Une capacité disponible nulle est attribuée aux jours fériés définis dans le calendrier de l'atelier.  

Le calendrier usine peut ensuite être attribué à un atelier pour calculer le calendrier usine qui régira la programmation de toutes les opérations dans le temps à l'atelier.  

## <a name="to-calculate-a-work-center-calendar"></a>Pour calculer un calendrier d'atelier  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ateliers**, puis choisissez le lien associé.
2. Ouvrez l'atelier que vous voulez mettre à jour.  
3. Dans le champ **Code calendrier usine**, sélectionnez le calendrier usine à utiliser comme base pour le calendrier d'atelier.  
4. Sélectionnez l'action **Calendrier**.  
5. Sur la page **Calendrier atelier**, choisissez l'action **Afficher matrice**.  

    Le côté gauche de la page de matrice répertorie les ateliers configurés. Le côté droit contient un calendrier horaire indiquant les capacités disponibles pour chaque jour ouvré dans l'unité de mesure choisie, par exemple, **480** (minutes). Chaque ligne correspond au calendrier d'un atelier.  

    > [!NOTE]  
    >  Vous pouvez également choisir d'afficher les valeurs de capacité pour chaque semaine ou mois en modifiant la sélection dans le champ **Afficher par** de la page **Calendrier atelier**.  

    Le nouveau calendrier usine doit d'abord être calculé pour être répercuté dans une ligne de l'atelier sélectionné.  

6.  Choisissez l'action **Calculer**.  
7.  Sur le raccourci **Centre de charge**, vous pouvez définir un filtre de manière à n'effectuer le calcul que pour un centre de charge. Si vous ne définissez pas de filtre, tous les calendriers d'atelier existants seront calculés.  
8.  Définissez les dates début et fin de la période de calendrier à calculer, par exemple, une année comprise entre le 01/01/14 et le 31/12/14.
9. Cliquez sur le bouton **OK** pour calculer la capacité.  

Vous venez de créer ou de mettre à jour les écritures calendrier. Elles indiquent la capacité disponible pour chaque période en fonction des trois ensembles de données de base suivants :  

- L'équipe et les jours ouvrés définis dans le calendrier usine attribué.  
- la valeur du champ **Capacité** de la fiche centre de charge.  
- la valeur du champ **Rendement** de la fiche centre de charge.  

Le calendrier d'atelier calculé définit ensuite la période de disponibilité et la quantité de la capacité de l'atelier. Il contrôle la programmation détaillée des opérations effectuées dans l'atelier.  

## <a name="to-record-work-center-absence"></a>Pour enregistrer les absences de l'atelier  
1.  Sur la page **Calendrier atelier**, choisissez l'action **Afficher matrice**.
2. Sur la page **Matrice Calendrier atelier**, sélectionnez l'atelier et le jour de calendrier correspondant au moment où l'absence doit être enregistrée, puis choisissez l'action **Indisponibilité**.  
3.  Sur la page **Indisponibilité**, définissez les heures de début et de fin, et la description de l'absence du jour. Par exemple :  

    25/01/01 08:00 10:00 Entretien  

4.  Choisissez l'action **Mettre à jour**, puis fermez la page **Indisponibilité**.  

La capacité du jour sélectionné est réduite conformément aux heures d'absence enregistrées.  

## <a name="see-also"></a>Voir aussi  
[Configurer des calendriers principaux](across-how-to-assign-base-calendars.md)  
[Configurer les ateliers et les unités de production](production-how-to-set-up-work-and-machine-centers.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]