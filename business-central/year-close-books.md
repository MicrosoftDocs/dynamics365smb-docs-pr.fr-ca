---
title: Aperçu des tâches pour fermer les registres | Microsoft Docs
description: En savoir plus sur le processus de fermeture des registres d'un exercice financier ou d'une période fiscale, et ce qui a lieu après la fermeture, à la fin d'un exercice.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: e9cf8a89599c3fa73801bca40720221f05ffaf11
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5776627"
---
# <a name="closing-the-books"></a>Fermeture des registres
Après vous être assuré que tous vos comptes sont à jour et avoir affecté les coûts et les bénéfices, vous pouvez fermer la comptabilité d'un exercice financier ou d'une période comptable.

Vous n'êtes pas obligé de fermer un exercice, mais cela vous aidera à travailler plus facilement dans le système parce que vous serez en mesure de bénéficier des options de filtrage pratiques mises à votre disposition. Vous ne devez pas non plus vous préoccuper de la perte de détails de transactions lors de la fermeture parce que tous les détails sont conservés, même après la fermeture de l'exercice.

## <a name="closing-book-process"></a>Processus de fermeture des registres
Le processus de fermeture d'un registre inclut les tâches principales suivantes :

1. Fermeture de la période comptable.

    Un exercice financier est défini comme une ou plusieurs périodes, telles qu'elles sont définies sur la page **Périodes comptables**. Un exercice financier type contient 12 périodes d'un mois chacune, mais vous pouvez également choisir un autre mode de définition des exercices.

    Pour plus d'informations, voir [Fermer des périodes comptables](year-close-account-periods.md).
2. Enregistrement des écritures de l'exercice précédent.

    Lorsque vous fermez un exercice financier, vous devez saisir un certain nombre de transactions administratives (telles que les articles prépayés ou accumulés). Ces transactions sont appelées écritures d'ajustement. Il n'existe pas de règles spécifiques pour la validation de ces écritures et, comme pour les autres écritures, le champ **Écr. exercice précédent** de ces écritures est activé si elles sont validées dans une date d'un exercice comptable clôturé. Même si un exercice financier a été fermé, vous pouvez toujours y reporter des écritures.
3. Transfert des soldes des comptes état des résultats dans le bilan.

    Une fois qu'un exercice financier a été fermé et que toutes les écritures de l'exercice précédent ont été reportées, les comptes d'état des résultats doivent être fermés et le revenu net de l'exercice doit être transféré sur un compte sous capitaux propres dans le bilan. Pour cela, utilisez le traitement en lot Fermer l'état des résultats. Le traitement en lot traite tous les comptes du grand livre de type État des revenus et crée des écritures qui inversent leurs soldes. Ces écritures sont placées dans un journal à partir duquel elles peuvent être reportées. Le traitement en lot ne les reporte pas automatiquement, sauf lorsqu'une devise de report additionnelle est utilisée. Lorsque vous utilisez une devise de report additionnelle, le traitement en lot reporte directement dans le grand livre.

    Pour plus d'informations, reportez-vous à [Solder les comptes de gestion](year-close-income-statement.md).
4. Report de l'écriture de fermeture de fin d'exercice avec les écritures de compte de fonds d'équité de compensation.

    Lorsque le traitement en lot Fermer l'état des résultats est terminé, vous reportez les écritures générées par le traitement. Si vous n'avez pas spécifié de compte de bénéfices non répartis dans le traitement en lot, saisissez une ligne avec une écriture de contrepartie qui reporte le revenu net sur le compte du grand livre correct sous capitaux propres dans le bilan. Pour terminer, reportez le journal.

    Pour plus d'informations, voir [Reporter une écriture de fermeture d'exercice](year-how-post-year-end-close-entry.md).

## <a name="what-happens-when-you-close"></a>Ce qui se produit lorsque vous fermez
Lors de la fermeture en fin d'exercice, le système déplace vos bénéfices des bénéfices calculés vers le compte Bénéfices non répartis. Le système marque également l'exercice financier comme « fermé » et toutes les écritures suivantes pour l'exercice fermé comme « écritures de l'exercice précédent ».

Le système génère ensuite une écriture de fermeture mais ne la reporte pas automatiquement. Vous avez la possibilité de créer une ou plusieurs écritures de compte de fonds d'équité de compensation qui vous permettent de choisir la manière dont vous voulez affecter votre écriture de fermeture. Par exemple, si votre compagnie comprend plusieurs départements, vous pouvez laisser le système générer une écriture de fermeture unique pour tous les départements et créer une écriture de compensation pour le compte de fonds propres de chaque département.

Vous pouvez effectuer le report dans un exercice financier précédent, même après la fermeture des comptes d'état des résultats, si vous réexécutez le traitement en lot Fermer l'état des résultats par la suite.

## <a name="see-also"></a>Voir aussi

[Utiliser des périodes et exercices financiers comptables](finance-accounting-periods-and-fiscal-years.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]