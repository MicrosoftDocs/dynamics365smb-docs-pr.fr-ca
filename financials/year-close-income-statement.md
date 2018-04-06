---
title: "Fermeture des comptes de l'état des résultats | Microsoft Docs"
description: "À la fermeture de l'exercice, vous devez exécuter le traitement en lot Fermer l'état des résultats afin de refermer les périodes comptables de l'exercice financier."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 06/02/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 237c03e2ba6408bde65aba5f652468a3b700fa0a
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="close-income-statement-accounts"></a>Fermer les comptes état des résultats
Lorsqu'un exercice financier est terminé, vous devez fermer les périodes qui le composent. Vous exécutez pour cela le traitement par lots **Solder les comptes de gestion**. Ce projet transfère le résultat de l'exercice sur un compte du bilan et ferme les comptes état des résultats. Vous créez des lignes dans un journal, que vous pouvez reporter par la suite.

## <a name="to-run-the-close-income-statement-batch-job"></a>Pour exécuter le traitement en lot Fermer l'état des résultats
1. Fermez l'exercice financier. L'exercice financier doit être fermé avant l'exécution du traitement en lot. Pour plus d'informations, voir [Fermer des périodes comptables](year-close-account-periods.md).
2. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Solder les comptes de gestion**, puis sélectionnez le lien connexe.
3. Pour lancer le traitement par lots, cliquez sur le bouton **OK**.

## <a name="about-the-close-income-statement-batch-job"></a>À propos du traitement en lot Fermer l'état des résultats
Le traitement en lot traite tous les comptes du grand livre de type État des résultats et crée des écritures qui annulent leurs soldes respectifs. C'est-à-dire, chaque écriture représente la somme de toutes les écritures du compte de l'exercice financier. Ces nouvelles écritures sont placées dans un journal, dans lequel vous devez spécifier un compte de contrepartie et un compte de bénéfices avant de reporter. Lorsque vous reportez le journal, une écriture est reportée sur chaque compte état des résultats afin que son solde soit égal à zéro et en même temps le résultat de l'exercice est transféré dans le bilan.

Vous devez reporter le journal vous-même. Le traitement en lot ne reporte pas les écritures automatiquement, sauf lorsqu'une devise de report additionnelle est utilisée. Lorsque vous utilisez une devise de report additionnelle, le traitement en lot reporte les écritures directement dans le grand livre.

La date sur les lignes insérées par le traitement en lot dans le journal est toujours une date de fermeture pour l'exercice financier. La date de fermeture est une date fictive située entre le dernier jour de l'exercice financier précédent et le premier jour du nouvel exercice. L'avantage de reporter sur une date de fermeture est que vous maintenez les soldes corrects pour les dates ordinaires de l'exercice financier.

Le traitement par lots **Solder les comptes de gestion** peut être utilisé à plusieurs reprises. Vous pouvez effectuer le report dans un exercice financier précédent, même après la fermeture des comptes d'état des résultats, si vous réexécutez le traitement en lot.

## <a name="see-also"></a>Voir aussi
[Clôture plans](year-close-books.md)  
[Reporter l'écriture de fermeture d'exercice](year-how-post-year-end-close-entry.md)  
[Ouvrir un nouvel exercice financier](finance-how-open-new-fiscal-year.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

