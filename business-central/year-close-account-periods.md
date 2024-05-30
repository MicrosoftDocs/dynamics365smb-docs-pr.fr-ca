---
title: Fermer des périodes comptables pour un exercice financier
description: Cet article décrit comment fermer les périodes comptables de l’exercice financier comptable pour la fermeture de l’exercice.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'year closing, close accounting period, close fiscal year, bank account detailed trial balance'
ms.search.form: '100,'
ms.date: 05/07/2024
ms.service: dynamics-365-business-central
---
# Fermer des périodes comptables

Lorsqu'un exercice financier est terminé, vous devez fermer les périodes qui le composent.

## Pour fermer des périodes comptables

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Périodes comptables**, puis sélectionnez le lien associé.
2. Sur la page **Périodes comptables**, sélectionnez l'action **Fermer exercice**.

    Si plusieurs exercices financiers sont ouverts, le plus ancien est automatiquement sélectionné pour la fermeture. Un message identifie l’exercice à fermer et les résultats de sa fermeture.
3. Pour clôturer l'exercice, cliquez sur **Oui**.

L'exercice comptable est désormais clôturé, et les champs **Fermé** et **Verrouillage date** sont sélectionnés pour toutes les périodes de l'exercice. Vous ne pouvez pas rouvrir l'exercice comptable ni supprimer la coche des champs **Fermé** et **Verrouillage date**.

> [!NOTE]  
> Vous ne pouvez pas fermer un exercice financier avant d'en avoir créé un nouveau. Sachez que lorsqu’un exercice financier est fermé, vous ne pouvez pas modifier la date début de l’exercice financier suivant.

Même si un exercice financier est fermé, vous pouvez toujours y reporter des écritures. Dans ce cas, les écritures sont marquées comme reportées dans un exercice financier fermé et le champ **Écr. exercice précédent** est sélectionné.

Une fois qu'un exercice financier a été fermé, vous devez fermer les comptes d'état des résultats et transférer les résultats de l'exercice sur un compte du bilan. Vous pouvez répéter cette opération chaque fois que vous effectuez un report dans l'exercice financier fermé.

## Voir aussi .

[Clôture plans](year-close-books.md)  
[Reporter l’écriture de fermeture de fin d’exercice](year-how-post-year-end-close-entry.md)  
[Utiliser des périodes comptables et des exercices financiers](finance-accounting-periods-and-fiscal-years.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]