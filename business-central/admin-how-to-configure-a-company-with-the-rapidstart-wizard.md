---
title: "Procédure de configuration d'une compagnie avec l’assistant RapidStart | Microsoft Docs"
description: "Vous pouvez rapidement configurer une nouvelle compagnie que vous avez créée à l’aide de l’assistant de configuration de RapidStart Services."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 264788142ab4f2a84df3e1c9da6e39503a7e820f
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="configure-a-company-with-the-rapidstart-wizard"></a>Configurer une compagnie avec l'assistant RapidStart
Vous pouvez rapidement configurer une nouvelle compagnie que vous avez créée à l’aide de l’assistant de configuration de RapidStart Services.

Dans la procédure suivante, vous avez fourni au client un colis configuration, qui est ensuite installé sur un ordinateur. Le client ouvre la nouvelle compagnie, qui ne contient aucune donnée client. Le client ou vous-même suivez ensuite les étapes de l’Assistant RapidStart Services, décrites dans cette procédure, pour spécifier des informations de base sur la compagnie. L’Assistant importe le package de configuration, puis l'affecte à la compagnie.  

## <a name="to-configure-a-new-company"></a>Pour configurer une nouvelle compagnie  
1. Dans le tableau de bord Responsable de l'implémentation de RapidStart Services, sélectionnez l'action **Assistant RapidStart**.  
2. Affichez le raccourci **Étape 1**, qui contient des informations générales sur la nouvelle société. Entrez les informations appropriées sur la nouvelle compagnie dans les champs. Il existe un champ que vous devez renseigner : **Nom**. Les autres champs sont facultatifs.  
3. Affichez le raccourci **Étape 2**, qui contient des informations de communication et de contact pour la nouvelle société. Entrez les informations appropriées sur la nouvelle compagnie dans les champs.
4. Affichez le raccourci **Étape 3**, qui contient des informations sur le compte bancaire et sur le paiement pour la nouvelle société. Entrez les informations appropriées sur la nouvelle compagnie dans les champs.  
5. Développez le raccourci **Étape 4**. Choisissez le bouton **AssistEdit** pour sélectionner le colis configuration à lettrer. Le nom du colis configuration est affiché. Vous pouvez ensuite effectuer les actions suivantes, dans l’ordre déterminé :  

    1. Appliquez la configuration en sélectionnant l'action **Appliquer package**. Il importe le package de configuration et applique simultanément toutes les données de base de données du package.  

    2. Relisez la configuration après son affectation. Cette option vous permet d’étudier les détails de la configuration et les questionnaires fournis par le partenaire et d’importer des données de base requises pour votre compagnie. Sélectionnez l'action **Feuille configuration**. Pour plus d'informations, voir la section « Pour remplir le questionnaire de configuration » dans [Collecter les valeurs de configuration client](admin-gather-customer-setup-values.md).  

6. Développez le raccourci **Étape 5**. Spécifiez quel Tableau de bord sera la valeur par défaut pour la nouvelle compagnie.  

    > [!IMPORTANT]  
    >  Modifiez votre Tableau de bord uniquement après avoir effectué la configuration de la compagnie. Si vous avez d’autres informations de configuration à prendre en compte et à modifier, utilisez d’abord la feuille de configuration pour effectuer votre travail. Enfin, revenez à l’Assistant pour mettre à jour votre profil Tableau de bord, ou sélectionnez l'action **Configuration terminée**.

7. Cliquez sur le bouton **OK**.  
8. Pour vérifier que les informations de configuration ont été appliquées à la nouvelle compagnie, choisissez ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Informations compagnie**, puis sélectionnez le lien associé.

La fenêtre **Informations société** contient les informations que vous avez spécifiées.   

Vous avez désormais configuré la compagnie, et des données lui ont été affectées.  

## <a name="see-also"></a>Voir aussi  
[Appliquer des configurations à de nouvelles compagnies](admin-apply-configuration-to-new-companies.md)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)

