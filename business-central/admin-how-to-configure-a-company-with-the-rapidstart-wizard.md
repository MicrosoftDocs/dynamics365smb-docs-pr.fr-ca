---
title: Procédure de configuration d’une compagnie avec l’assistant RapidStart | Microsoft Docs
description: Vous pouvez rapidement configurer une nouvelle compagnie que vous avez créée à l’aide de l’Assistant Configuration de RapidStart Services.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 1a9d4c2a4a99ebec0aa1fc019871608948844b7a
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3187230"
---
# <a name="configure-a-company-with-the-rapidstart-wizard"></a>Configurer une compagnie avec l'assistant RapidStart
Vous pouvez rapidement configurer une nouvelle compagnie que vous avez créée à l’aide de l’Assistant Configuration de RapidStart Services.

Dans la procédure suivante, vous avez fourni au client un package configuration, qui est ensuite installé sur un ordinateur. Le client ouvre la nouvelle compagnie, qui ne contient aucune donnée client. Vous ou le client suivez les étapes de l’Assistant RapidStart Services, décrites dans cette procédure, pour spécifier des informations de base sur la compagnie. L’Assistant importe le package de configuration, puis l'affecte à la compagnie.  

## <a name="to-configure-a-new-company"></a>Pour configurer une nouvelle compagnie  
1. Dans le tableau de bord Responsable de l'implémentation de RapidStart Services, choisissez l'action **Assistant RapidStart**.  
2. Affichez le raccourci **Étape 1**, qui contient des informations générales sur la nouvelle compagnie. Entrez les informations appropriées sur la nouvelle compagnie dans les champs. Il existe un champ que vous devez renseigner : **Nom**. Les autres champs sont facultatifs.  
3. Affichez le raccourci **Étape 2**, qui contient des informations de communication et de contact pour la nouvelle société. Entrez les informations appropriées sur la nouvelle compagnie dans les champs.
4. Affichez le raccourci **Étape 3**, qui contient des informations sur le compte bancaire et sur le paiement pour la nouvelle société. Entrez les informations appropriées sur la nouvelle compagnie dans les champs.  
5. Développez le raccourci **Étape 4**. Choisissez le bouton **AssistEdit** pour sélectionner le colis configuration à lettrer. Le nom du colis configuration est affiché. Vous pouvez ensuite effectuer les actions suivantes, dans l’ordre déterminé :  

    1. Appliquez la configuration en sélectionnant l'action **Appliquer package**. Il importe le package de configuration et applique simultanément toutes les données de base de données du package.  

    2. Relisez la configuration après son affectation. Cette option vous permet d’étudier les détails de la configuration et les questionnaires fournis par le partenaire et d’importer des données de base requises pour votre compagnie. Sélectionnez l'action **Feuille configuration**. Pour plus d’informations, voir [Pour remplir le questionnaire de configuration](admin-gather-customer-setup-values.md#to-complete-the-configuration-questionnaire).  

6. Développez le raccourci **Étape 5**. Spécifiez quel tableau de bord sera la valeur par défaut pour la nouvelle compagnie.  

    > [!IMPORTANT]  
    >  Modifiez votre Tableau de bord uniquement après avoir effectué la configuration de la compagnie. Si vous avez d’autres informations de configuration à prendre en compte et à modifier, utilisez d’abord la feuille de configuration pour effectuer votre travail. Enfin, revenez à l’Assistant pour mettre à jour votre profil Tableau de bord, ou sélectionnez l'action **Configuration terminée**.

7. Cliquez sur le bouton **OK**.  
8. Pour vérifier que les informations de configuration ont été appliquées à la nouvelle compagnie, choisissez l'icône ![Ampoule qui ouvre la fonction Tell](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Informations compagnie**, puis sélectionnez le lien associé.

La page **Informations compagnie** contient les informations que vous avez spécifiées.   

Vous avez désormais configuré la compagnie, et des données lui ont été affectées.  

## <a name="see-also"></a>Voir aussi  
[Appliquer des configurations à de nouvelles compagnies](admin-apply-configuration-to-new-companies.md)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
