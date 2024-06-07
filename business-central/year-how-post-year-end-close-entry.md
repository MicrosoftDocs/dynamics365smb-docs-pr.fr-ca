---
title: Reporter l'écriture de fermeture d'exercice
description: 'Décrit comment ouvrir le journal spécifié dans le traitement en lot Fermer l''état des résultats, puis examiner et reporter l''écriture de fermeture de fin d''exercice.'
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: 'year closing, close accounting period, close fiscal year, bank account detailed trial balance'
ms.search.form: 100
ms.date: 06/25/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Report de l’écriture de fermeture d’exercice

Après avoir utilisé le traitement par lots **Solder les comptes de gestion** pour générer les écritures de clôture d'exercice, vous devez ouvrir la feuille spécifiée dans le traitement par lots, puis consulter et valider les écritures.  

> [!TIP]
> En fonction des processus de travail de votre organisation, vous pouvez choisir de fermer ou non les périodes comptables et les exercices financiers dans [!INCLUDE [prod_short](includes/prod_short.md)]. La procédure suivante suppose que vous avez fermé l’exercice financier en utilisant l’option *Périodes comptables*, généré une écriture de fermeture de fin d’exercice à l’aide du traitement en lot **Fermer état des résultats** et que vous êtes maintenant prêt à reporter l’écriture de fermeture de fin d’exercice avec la compensation des écritures de compte de fonds propres. Votre organisation peut choisir de travailler différemment, par exemple reporter l’écriture de fermeture de fin d’exercice dans le cadre de la fermeture de l’exercice financier.

## Pour reporter l'écriture de fermeture de fin d'exercice

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général**, puis choisissez le lien associé.
2. Sur la page **Journal général**, dans le champ **Nom de lot**, sélectionnez le lot qui contient les écritures de fermeture.
3. Examinez les écritures.
4. Pour valider la feuille, sélectionnez l'action **Valider**.

> [!NOTE]  
> En cas de détection d'une erreur, un message d'erreur s'affiche. Si le report réussit, les entrées reportées sont supprimées du journal. Une fois le report terminé, une entrée est reportée sur chaque compte état des résultats, de façon à ce que son solde indique zéro et à ce que les résultats de l'exercice soient transférés dans le bilan.

## Voir aussi

[Fermer des périodes comptables](year-close-account-periods.md)  
[Clôture plans](year-close-books.md)  
[Clôturer exercice comptable](year-close-income-statement.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]