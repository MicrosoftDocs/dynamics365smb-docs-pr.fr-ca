---
title: "Vérifier et reporter l'écriture de fermeture de fin d'exercice | Microsoft Docs"
description: "Décrit comment ouvrir le journal spécifié dans le traitement en lot Fermer l'état des résultats, puis examiner et reporter l'écriture de fermeture de fin d'exercice."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 03/29/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 4263f6b3260dd5b8e8fad4f515dcdb61e12eb012
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="post-the-year-end-closing-entry"></a>Reporter l'écriture de fermeture d'exercice
Après avoir utilisé le traitement par lots **Solder les comptes de gestion** pour générer les écritures de clôture d'exercice, vous devez ouvrir la feuille spécifiée dans le traitement par lots, puis consulter et valider les écritures.

## <a name="to-post-the-year-end-closing-entry"></a>Pour reporter l'écriture de fermeture de fin d'exercice
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille comptabilité**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Feuille comptabilité**, dans le champ **Nom de la feuille**, sélectionnez la feuille qui contient les écritures de clôture.
3. Examinez les écritures.
4. Pour valider la feuille, sélectionnez l'action **Valider**.

> [!NOTE]  
>   En cas de détection d'une erreur, un message d'erreur s'affiche. Si le report réussit, les entrées reportées sont supprimées du journal. Une fois le report terminé, une entrée est reportée sur chaque compte état des résultats, de façon à ce que son solde indique zéro et à ce que les résultats de l'exercice soient transférés dans le bilan.

## <a name="see-also"></a>Voir aussi
[Fermer des périodes comptables](year-close-account-periods.md)  
[Clôture plans](year-close-books.md)  
[Clôturer exercice comptable](year-close-income-statement.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

