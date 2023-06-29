---
title: Utilisation des périodes comptables et exercices financiers
description: En savoir plus sur l'utilisation des périodes comptables pour définir le moment où votre compagnie fait état de ses performances financières.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 100
ms.date: 08/25/2022
ms.author: bholtorf
---
# <a name="work-with-accounting-periods-and-fiscal-years"></a><a name="work-with-accounting-periods-and-fiscal-years"></a>Utiliser des périodes comptables et des exercices financiers

Les périodes comptables, également appelées périodes de report, sont des périodes pour lesquelles une compagnie ou une organisation présente ses performances financières, en générant par exemple un état de ses résultats ou son bilan. Généralement, les périodes comptables sont liées à l'exercice financier de la compagnie, qui peut contenir plusieurs périodes comptables, telles que des mois ou des trimestres.

Pour de nombreuses compagnies, l’exercice financier ne correspond pas à l’année civile, par exemple lorsque l’exercice financier se termine le 30 juin au lieu du 31 décembre. Pour les compagnies que vous venez de créer, l’exercice financier peut même durer plus de 12 mois.  

[!INCLUDE[prod_short](includes/prod_short.md)] nécessite uniquement des périodes comptables si vous souhaitez fermer un état des résultats, ou exécuter des tâches de compression de données.

Vous pouvez utiliser des périodes comptables dans la génération de rapports, par exemple lorsque vous consultez les écritures reportées sur la page **Solde/budget** où l’intervalle de génération de rapports est spécifié. L’une des options consiste à spécifier la déclaration par période comptable. Vous pouvez également créer un rapport financier qui compare les résultats de différentes périodes comptables.

## <a name="creating-a-new-fiscal-year"></a><a name="creating-a-new-fiscal-year"></a>Création d'un exercice financier

Vous pouvez créer des périodes comptables en bloc, à l’aide du traitement en lot **Créer exercice financier**, ou manuellement.

### <a name="how-to-create-accounting-periods-in-bulk"></a><a name="how-to-create-accounting-periods-in-bulk"></a>Comment créer des périodes comptables en bloc

Utilisez le traitement en lot **Créer exercice financier** pour diviser un exercice financier en périodes de même durée.  

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Périodes comptables**, puis sélectionnez le lien associé.  
2. Choisissez l'action **Créer exercice**.
3. Dans le champ **Date début**, saisissez la date à laquelle l'exercice financier commence.  
4. Dans le champ **Nombre de périodes**, spécifiez le nombre de périodes comptables composant l'exercice financier. Il peut y avoir un maximum de 365 périodes dans une année.  
5. Dans le champ **Base période**, entrez une durée pour chaque période. Les identificateurs de durée sont 1M pour un mois, 1T pour un trimestre, et 1Y pour une année.  
6. Cliquez sur **OK**.  

### <a name="how-to-create-accounting-periods-manually"></a><a name="how-to-create-accounting-periods-manually"></a>Comment créer des périodes comptables manuellement

Si les périodes comptables de l’exercice financier ont différentes durées, comme le calendrier 4-4-5 utilisé dans la vente au détail, vous pouvez les configurer manuellement.  
  
1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Périodes comptables**, puis sélectionnez le lien associé.  
2. Dans le champ **Date début**, saisissez la date à laquelle l'exercice financier commence. Le champ **Nom** affiche à présent le nom du mois.  
3. Activez la case à cocher **Nouvel exercice financier** pour indiquer qu'il s'agit de la première période de l'exercice. [!INCLUDE[prod_short](includes/prod_short.md)] utilise cette période pour déterminer les périodes à fermer en fin d'exercice.
4. Répétez les étapes 2 et 3 pour chaque période restante.  

## <a name="closing-a-fiscal-year"></a><a name="closing-a-fiscal-year"></a>Fermeture d’un exercice financier

Fermer l'exercice financier est l'une des tâches pour fermer les livres. Une fois l'exercice financier fermé, les cases **Fermé** et **Verrouillage date** sont activées pour toutes les périodes de l'exercice. Vous ne pouvez pas rouvrir un exercice ou désactiver les cases.

> [!NOTE]  
> Vous devez toujours avoir au moins un exercice financier ouvert. Lorsque vous fermez un exercice, assurez-vous qu'un exercice a été créé. De plus, sachez que lorsque vous fermez un exercice, vous ne pouvez pas modifier la date début de l'exercice suivant.

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Périodes comptables**, puis sélectionnez le lien associé.  
2. Choisissez l'action **Clôturer exercice**.  

## <a name="posting-entries-to-a-closed-fiscal-year"></a><a name="posting-entries-to-a-closed-fiscal-year"></a>Report d’écritures dans un exercice financier fermé

Même si un exercice financier est fermé, vous pouvez toujours y reporter des écritures. Dans ce cas, les écritures sont marquées comme reportées dans un exercice financier fermé et la case à cocher **Écr. exercice précédent** est activée. Par défaut, la case à cocher n'est pas affichée sur la page, mais vous pouvez l'ajouter. Les étapes suivantes consistent à fermer les états des résultats traités et à transférer les résultats de l'année sur un compte de bilan. Répétez ces étapes chaque fois que vous reportez des écritures dans un exercice financier fermé.

## <a name="see-also"></a><a name="see-also"></a>Voir aussi .

[Fermeture des registres](year-close-books.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Comment utiliser les rapports financiers](bi-how-work-account-schedule.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
