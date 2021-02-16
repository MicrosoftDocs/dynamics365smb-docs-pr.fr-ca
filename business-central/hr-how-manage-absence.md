---
title: Gérer les absences des employés | Microsoft Docs
description: Décrit comment enregistrer les absences des salariés et analyser les statistiques d'indisponibilité.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: b9371127ca692ae636f93e44b202608684acaedb
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4746543"
---
# <a name="manage-employee-absence"></a>Gérer les absences des employés
Pour gérer l'absence d'un employé, vous devez l'enregistrer sur la page **Saisie des absences**. Elle peut alors être affichée de différentes façons à des fins d'analyse ou de génération de rapport.

Vous pouvez afficher les absences des employés sur deux pages différentes :

* La page **Saisie des absences** est la fenêtre dans laquelle vous enregistrez les absences de tous les employés, avec une ligne par absence.
* La page **Absences employé** affiche les absences d'un seul employé. Les informations affichées sont celles que vous avez entrées sur la page **Saisie des absences**, filtrées pour cet employé.

Pour obtenir des statistiques significatives, vous devez toujours utiliser la même unité de mesure (heure ou jour) lors de l'enregistrement des absences des employés.

## <a name="to-register-employee-absence"></a>Pour enregistrer les absences des employés
Vous pouvez enregistrer les absences des employés quotidiennement ou à un autre intervalle qui répond aux besoins de votre organisation.

1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche**, entrez **Saisie des absences**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**.
3. Renseignez une ligne pour chaque absence employé que vous souhaitez enregistrer.
4. Fermez la page.

    > [!Tip]
    > Pour obtenir des statistiques pertinentes, utilisez toujours la même unité de mesure, heure ou journée, lors de l'enregistrement des absences.

## <a name="to-view-an-individual-employees-absence"></a>Pour visualiser les absences d'un employé
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche**, entrez **Employés**, puis sélectionnez le lien connexe.
2. Sélectionnez l'employé concerné, puis cliquez sur **Absences**.

    La page **Absences employés** affiche toutes les absences et les dates de début et de fin.

## <a name="to-view-an-employees-absence-by-categories"></a>Pour afficher les absences d'un employé par catégorie
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche**, entrez **Employés**, puis sélectionnez le lien connexe.
2. Sélectionnez l'employé concerné, puis cliquez sur **Absences par catégories**.
3. Sur la page **Absences salariés par cat.**, renseignez les champs selon vos besoins, puis cliquez sur **Afficher matrice**.

    La page **Matrice Abs. Salariés par Cat.** s'ouvre et affiche toutes les absences, classées par motif d'absence.

## <a name="to-view-all-employee-absences-by-category"></a>Pour afficher toutes les absences des employés par catégorie
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche**, entrez **Saisie des absences**, puis sélectionnez le lien connexe.
2. Sur la page **Saisie des absences**, cliquez sur **Détail par catégorie**.
3. Sur la page **Détail absences par catégorie**, définissez un filtre dans le champ **Filtre n° employé** afin de visualiser les absences d'un individu ou d'un groupe d'employés.
4. Choisissez l'action **Afficher matrice**.

    La page **Détail absences par catégorie** s'ouvre et affiche les absences des employés par motif d'absence.

## <a name="to-view-all-employee-absences-by-period"></a>Pour afficher toutes les absences des employés par période
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche**, entrez **Saisie des absences**, puis sélectionnez le lien connexe.
   Sur la page **Saisie des absences**, cliquez sur **Détail par période**.
2. Sur la page **Détail absences par période**, définissez un filtre dans le champ **Filtre motif absence** afin de visualiser les absences des employés liées à un motif particulier.
3. Choisissez l'action **Afficher matrice**.

    La page **Détail absences par période** s'ouvre et affiche les absences des employés réparties par période.

## <a name="see-also"></a>Voir aussi
[Gérer les ressources humaines](hr-manage-human-resources.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)
