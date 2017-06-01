---
title: "Procédure : fermer des périodes comptables | Microsoft Docs"
description: "Explique comment fermer des périodes comptables"
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 03/29/2017
ms.author: jswymer
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 69bea225084f239523c4ed67471b52ad91e914d9
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="how-to-close-accounting-periods"></a>Procédure : fermer des périodes comptables
Lorsqu'un exercice financier est terminé, vous devez fermer les périodes qui le composent.

## <a name="to-close-accounting-periods"></a>Pour fermer des périodes comptables
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Périodes comptables**, puis sélectionnez le lien associé.
2. Dans la fenêtre **Périodes comptables**, sélectionnez l'action **Clôturer exercice**.

    Si plusieurs exercices financiers sont ouverts, le plus ancien est automatiquement sélectionné pour la fermeture. Un message identifiant l'exercice qu'il compte fermer s'affiche et indique les conséquences de la fermeture.
3. Pour clôturer l'exercice, cliquez sur **Oui**.

L'exercice comptable est désormais clôturé, et les champs **Fermé** et **Verrouillage date** sont sélectionnés pour toutes les périodes de l'exercice. Vous ne pouvez pas rouvrir l'exercice comptable ni supprimer la coche des champs **Fermé** et **Verrouillage date**.

**Remarque :** vous ne pouvez pas clôturer un exercice comptable avant d'en créer un nouveau. Sachez que lorsqu'un exercice financier est fermé, vous ne pouvez pas modifier la date début de l'exercice financier suivant.

Même si un exercice financier a été fermé, vous pouvez toujours y reporter des écritures. Dans ce cas, les écritures sont marquées comme validées dans un exercice comptable clôturé et le champ **Ecr. exercice précédent** est activé.

Une fois qu'un exercice financier a été fermé, vous devez fermer les comptes d'état des résultats et transférer les résultats de l'exercice sur un compte du bilan. Vous pouvez répéter cette opération chaque fois que vous effectuez un report dans l'exercice financier fermé.

## <a name="see-also"></a>Voir aussi
[Clôture plans](year-close-books.md)  
[Procédure : valider l'écriture de clôture d'exercice](year-how-post-year-end-close-entry.md)  
[Procédure : ouverture d'un nouvel exercice comptable](finance-how-open-new-fiscal-year.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

