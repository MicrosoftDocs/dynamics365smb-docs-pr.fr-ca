---
title: Méthodes amortissement pour les immobilisations
description: En savoir plus sur les différentes méthodes intégrées pour amortir ou déprécier des immobilisations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'write down, depreciate, depreciation'
ms.search.form: '5629, 5633'
ms.date: 03/25/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# <a name="depreciation-methods-for-fixed-assets"></a>Méthodes amortissement pour les immobilisations

[!INCLUDE [prod_short](includes/prod_short.md)] prend en charge huit méthodes différentes d’amortissement des immobilisations :

* Linéaire (SL)
* Dégressif 1 (DB1)
* Dégressif 2 (DB2)
* Dég.1/Lin.
* Dég.2/Lin.
* Règle de la demi-année
* Manuelle
* Amortissement défini par l’utilisateur

## <a name="straight-line-depreciation"></a>Amortissement linéaire

Avec l’amortissement linéaire, vous dépréciez la valeur de l’actif soit avec un pourcentage annuel fixe, soit avec un montant annuel fixe sur la période d’amortissement. Lorsque vous utilisez la méthode linéaire, vous devez indiquer l'une des options suivantes dans le registre amortissement immobilisation :  

* Période de l'amortissement (en années ou en mois) ou date fin de l'amortissement  
* Pourcentage annuel fixe  
* Montant annuel fixe  
* Période d'amortissement  

### <a name="depreciation-period"></a>Période d'amortissement

Si vous saisissez la période d'amortissement (nombre d'années ou de mois d'amortissement, ou date fin d'amortissement), la formule suivante calcule le montant de l'amortissement :  

* Montant de l'amortissement = ((valeur comptable - valeur résiduelle) x nombre de jours d'amortissement)/jours d'amortissement restants*  

Le nombre de jours d’amortissement restants correspond au nombre de jours d’amortissement moins le nombre de jours compris entre la date début de l’amortissement et la date de la dernière écriture immobilisation.  

La valeur comptable peut être diminuée d’un montant d’appréciation, de dépréciation, ou personnalisé 1 ou 2 reporté, selon l’état (activé/désactivé) des champs **Inclure dans calcul amort.** et **Élément valeur comptable** sur la page **Type paramètre report immo**. Ce calcul garantit l'amortissement complet de l'immobilisation à la date fin de l'amortissement.  

### <a name="fixed-yearly-percentage"></a>Pourcentage annuel fixe

Si vous saisissez un pourcentage annuel fixe, [!INCLUDE [prod_short](includes/prod_short.md)] utilise la formule suivante pour calculer le montant de l’amortissement :  

* Montant de l’amortissement = (% linéaire x base amortissement x nombre de jours d’amortissement)/(100 x 360)*  

### <a name="fixed-yearly-amount"></a>Montant annuel fixe

Si vous saisissez un montant annuel fixe, [!INCLUDE [prod_short](includes/prod_short.md)] utilise la formule suivante pour calculer le montant de l’amortissement :  

* Montant de l’amortissement = (montant d’amortissement fixe x nombre de jours d’amortissement)/360*  

### <a name="example---straight-line-depreciation"></a>Exemple - Amortissement linéaire

Une immobilisation a un coût d'acquisition de 100 000 $. Sa durée de vie est estimée à huit ans. Le traitement par lots **Calculer amortissement** est exécuté tous les semestres.  

Pour cet exemple, l'écriture immobilisation se présente comme suit :  

| Date | Type de report immo. | Jours | Montant | Valeur comptable |
| ---- | --------------- | ---- | ------ | ---------- |
| 01/01/20 |Coût acquisition |(Date début amortissement) |100,000.00 |100,000.00 |
| 30/06/20 |Amortissement |180 |-6 250,00 |93,750.00 |
| 31/12/20 |Amortissement |180 |-6 250,00 |87,500.00 |
| 30/06/21 |Amortissement |180 |-6 250,00 |81,250.00 |
| 12/31/21 |Amortissements |180 |-6 250,00 |75,000.00 |
| ...      |             |    |          |          |
| 06/30/27 |Amortissements |180 |-6 250,00 |6,250.00  |
| 12/31/27 |Amortissements |180 |-6 250,00 |0         |

## <a name="declining-balance-1-depreciation"></a>Amortissement dégressif 1

Il s’agit d’une méthode d’amortissement qui ventile la plus grande portion du coût d’une immobilisation sur les premières années de sa durée de vie. Si vous utilisez cette méthode, vous devez saisir un pourcentage annuel fixe.  

La formule suivante calcule les montants d'amortissement :  

* Montant de l’amortissement = (% dégressif x nombre de jours d’amortissement x base amortissement)/(100 x 360)*  

La base amortissable est calculée comme la valeur comptable au début de l’année. Le nombre de jours d’amortissement correspond au nombre de jours entre la date de report et la dernière date d’amortissement. [!INCLUDE [prod_short](includes/prod_short.md)] calcule l’amortissement en supposant que tout amortissement effectué au cours de l’exercice financier est effectué avec cette formule.  

Le montant de l'amortissement reporté peut contenir des écritures avec divers types de report (dépréciation, paramétrable 1 et paramétrable 2) reportés depuis la date de début de l'exercice financier en cours. Ces types de report sont inclus dans le montant d'amortissement reporté si vous avez coché les champs **Type amortissement** et **Élément valeur comptable** sur la page **Config. type report immo**.  

### <a name="example-1---declining-balance-1-depreciation"></a>Exemple 1 - Amortissement dégressif 1

Une immobilisation a un coût d'acquisition de 100 000 $. Le champ **% dégressif** indique la valeur 25. Le traitement par lots **Calculer amortissement** est exécuté tous les semestres.  

Le tableau suivant montre à quoi ressemblent les écritures immobilisations.  

| Date | Type de report immo. | Jours | Montant | Valeur comptable |
| ---- | --------------- | ---- | ------ | ---------- |
| 01/01/20 |Coûts d'acquisition |(Date début amortissement) |100,000.00 |100,000.00 |
| 30/06/20 |Amortissement |180 |-12 500,00 |87,500.00 |
| 31/12/20 |Amortissement |180 |-12 500,00 |75,000.00 |
| 30/06/21 |Amortissement |180 |-9 375,00 |65,625.00 |
| 31/12/21 |Amortissement |180 |-9 375,00 |56,250.00 |
| 30/06/22 |Amortissement |180 |-7 031,25 |49,218.75 |
| 31/12/22 |Amortissement |180 |-7 031,25 |42,187.50 |
| 30/06/23 |Amortissement |180 |-5 273,44 |36,914.06 |
| 31/12/23 |Amortissement |180 |-5 273,44 |31,640.62 |
| 30/06/24 |Amortissement |180 |-3 955,08 |27,685.54 |
| 12/31/24 |Amortissements |180 |-3 955,08 |23,730.46 |
| ...      |             |    |          |          |

Méthode de calcul :  

* Année 1 : *25 % de 100 000 = 25 000 = 12 500 + 12 500*
* Année 2 : *25 % de 75 000 = 18 750 = 9 375 + 9 375*
* Année 3 : *25 % de 56 250 = 14 062,50 = 7 031,25 + 7 031,25*
* ...

Le calcul continue jusqu'à ce que la valeur comptable soit égale à la valeur résiduelle ou au montant final arrondissement que vous avez saisi.  

### <a name="example-2---declining-balance-1-depreciation"></a>Exemple 2 - Amortissement dégressif 1

La valeur comptable d’un actif est de 100 000 au 31/12/2022. Vous reportez un amortissement de 1 778 le 02/02/2023, ce qui correspond au montant (proportionnel) prévu de l’amortissement de l’année à 32 jours. Si vous exécutez l’amortissement le 30/06/2023, [!INCLUDE [prod_short](includes/prod_short.md)] suggérera 8 222, car il y a 148 jours entre le 02/02/2023 et le 30/06/2023. L’amortissement restant prévu pour le 30/06/2023 est calculé à l’aide de la formule suivante :

* *148/360 x 0,20 x 100 000 = 8 222*

### <a name="example-3---declining-balance-1-depreciation"></a>Exemple 3 - Amortissement dégressif 1

Si vous reportez un montant qui ne correspond pas à la méthode d’amortissement dégressif 1, par exemple, 5 000, [!INCLUDE [prod_short](includes/prod_short.md)] suggère le reste du montant attendu.

La valeur comptable d’un actif est de 100 000 au 31/12/2022. Vous reportez un amortissement de 5 000 le 02/02/2023, ce qui est supérieur au montant (proportionnel) prévu le 02/02/2023 à 32 jours. Si vous exécutez l’amortissement le 30/06/2023, [!INCLUDE [prod_short](includes/prod_short.md)] suggérera 8 222, car il y a 148 jours entre le 02/02/2023 et le 30/06/2023. L’amortissement restant prévu pour le 30/06/2023 est calculé à l’aide de la formule suivante :

* *148/360 x 0,20 x 100 000 = 8 222*

### <a name="example-4---declining-balance-1-depreciation"></a>Exemple 4 - Amortissement dégressif 1

La valeur comptable d’un actif est de 100 000 au 31/12/2023. Vous reportez un amortissement de 95 000 le 02/02/2023, qui dépasse le montant d’amortissement autorisé pour l’année. Si vous exécutez l’amortissement le 30/06/2023, [!INCLUDE [prod_short](includes/prod_short.md)] suggérera 5 000, car il y a 148 jours entre le 02/02/2023 et le 30/06/2023. L’amortissement restant prévu pour le 30/06/2023 est calculé à l’aide de la formule suivante : 

* *148/360 x 0,20 x 100 000 = 8 222*

Cependant, la valeur comptable restante n’est que de 5 000, donc [!INCLUDE [prod_short](includes/prod_short.md)] suggérera 5 000 car une valeur comptable ne peut pas être négative.

## <a name="declining-balance-2-depreciation"></a>Amortissement dégressif 2

Les méthodes Dégressif 1 et Dégressif 2 calculent le même montant d'amortissement total chaque année. Toutefois, si vous lancez le traitement en lot **Calculer amortissement** plusieurs fois par an, la méthode Dégressif 1 permet d’obtenir des montants d’amortissement équitables pour chaque période d’amortissement. En revanche, la méthode Dégressif 2 permet d’obtenir des montants d’amortissement qui sont dégressifs pour chaque période.  

### <a name="example---declining-balance-2-depreciation"></a>Exemple - Amortissement dégressif 2

Une immobilisation a un coût d'acquisition de 100 000 $. Le champ **% dégressif** indique la valeur 25. Le traitement par lots **Calculer amortissement** est exécuté tous les semestres. Les écritures immobilisations se présentent comme suit :  

| Date     | Type de report immo.  | Jours                       | Montant    | Valeur comptable |
| -------- | ---------------- | -------------------------  | --------- | ---------- |
| 01/01/20 |Coûts d'acquisition |(Date début amortissement)|100,000.00 |100,000.00 |
| 30/06/20 |Amortissement      |180                         |-13 397,46 | 86,602.54 |
| 31/12/20 |Amortissement      |180                         |-11 602,54 | 75,000.00 |
| 30/06/21 |Amortissement      |180                         |-10 048,09 | 64,951.91 |
| 12/31/21 |Amortissements      |180                         |-8 701,91  | 56,250.00 |
| ...      |                  |                            |           |           |

Méthode de calcul :  

* *VC* = Valeur comptable  
* *NJ* = Nombre de jours d’amortissement  
* *PD* = Pourcentage dégressif  
* *P* = *PD*/100  
* *J* = *NJ*/360  

La formule de calcul des montants d’amortissement est la suivante :  

* *MA* = *VC* x (1 - (1 - P)<sup>J</sup>)

Les valeurs d'amortissement sont les suivantes :  

| Date     | Calcul                                                |
| -------- | -----------                                                |
| 30/06/20 |MA = 100 000,00 (1 - (1 - 0,25)<sup>0,5</sup>) = 13 397,46 |
| 31/12/20 |MA = 86 602,54 x (1 - (1 - 0,25)<sup>0,5</sup>) = 11 602,54 |
| 30/06/21 |MA = 75 000,00 x (1 - (1 - 0,25)<sup> 0,5</sup>) = 10 048,09 |
| 12/31/21 |MA = 64 951,91 x (1 - (1 - 0,25)<sup> 0,5</sup>) = 8 701,91  |
| ...      |                                                            |

## <a name="db1sl-depreciation"></a>Amortissement Dégr1/Lin

Dégr1/Lin est l'abréviation combinée de Dégressif 1 et de Linéaire. Le calcul continue jusqu'à ce que la valeur comptable soit égale à la valeur résiduelle ou au montant final arrondissement que vous avez saisi.  

Le traitement en lot **Calculer amortissement** calcule un montant linéaire et un montant dégressif, mais seul le montant le plus élevé des deux est transmis au journal.  

Vous pouvez utiliser divers pourcentages pour calculer le montant dégressif.  

Si vous utilisez cette méthode, saisissez la durée de vie estimée et un pourcentage dégressif sur la page **Registres amortissement immo.**.  

> [!NOTE]
> Si vous utilisez l’une des méthodes d’amortissement dégressif et vous souhaitez exécuter l’amortissement sur plusieurs années, vous devez exécuter l’amortissement de chaque année séparément. Si vous exécutez l’amortissement sur toute la période allant de la date d’acquisition jusqu’à la fin du dernier exercice financier ou de la dernière période comptable, il est probable que les résultats seront incorrects. Par exemple, vous souhaitez peut-être l’exécuter sur plusieurs années si vous avez importé des données héritées et vous utilisez les dates d’acquisition réelles de vos actifs et vous souhaitez récupérer l’amortissement cumulé. Pour les méthodes d’amortissement dégressif, [!INCLUDE [prod_short](includes/prod_short.md)] calcule l’amortissement autorisé par an, à partir de la valeur comptable enregistrée pour chaque année. Il ne peut pas effectuer un amortissement sur plusieurs années en une seule étape.
>
> Le rapport **Immobilisations - Valeur projetée** peut projeter des amortissements sur des périodes de plusieurs années, ce qui peut prêter à confusion par rapport aux résultats que vous obtenez si vous exécutez des amortissements sur plusieurs années en utilisant l’une des méthodes d’amortissement dégressif. 

### <a name="example---db1-sl-depreciation"></a>Exemple - Amortissement Dégr1/Lin

Une immobilisation a un coût d'acquisition de 100 000 $. Sur la page **Registres amortissement immo.**, le champ **% dégressif** indique la valeur 25 et le champ **Nombre années amortissement** indique la valeur **8**. Le traitement par lots **Calculer amortissement** est exécuté tous les semestres.  

Les écritures immobilisations se présentent comme suit :  

| Date | Type de report immo. | Jours | Montant | Valeur comptable |
| --- | --- | --- | --- | --- |
| 01/01/20 |Coûts d'acquisition |(Date début amortissement) |100,000.00 |100,000.00 |
| 30/06/20 |Amortissement |180 |-12 500,00 |87,500.00 |
| 31/12/20 |Amortissement |180 |-12 500,00 |75,000.00 |
| 30/06/21 |Amortissement |180 |-9 375,00 |65,625.00 |
| 31/12/21 |Amortissement |180 |-9 375,00 |56,250.00 |
| 30/06/22 |Amortissement |180 |-7 031,25 |49,218.75 |
| 31/12/22 |Amortissement |180 |-7 031,25 |42,187.50 |
| 30/06/23 |Amortissement |180 |-5 273,44 |36,914.06 |
| 31/12/23 |Amortissement |180 |-5 273,44 |31,640.62 |
| 30/06/24 |Amortissement |180 |-3 955,08 |27,685.54 |
| 31/12/24 |Amortissement |180 |-3 955,08 |23,730.46 |
| 30/06/25 |Amortissement |180 |-3 955,08 |19.775,38 Lin. |
| 31/12/25 |Amortissement |180 |-3 955,08 |15.820,30 Lin. |
| 30/06/26 |Amortissement |180 |-3 955,08 |11.865,22 Lin. |
| 31/12/26 |Amortissement |180 |-3 955,07 |7.910,15 Lin. |
| 30/06/27 |Amortissement |180 |-3 955,08 |3.955,07 Lin. |
| 31/12/27 |Amortissement |180 |-3 955,07 |0,00 Lin. |

La mention `SL` qui suit la valeur comptable indique que la méthode linéaire a été utilisée.  

Méthode de calcul :  

* Année 1 (2020) :  

    *Montant dégressif : 25 % de 100 000 = 25 000 = 12 500 + 12 500*  

    *Montant linéaire = 100 000 / 8 = 12 500 = 6 250 + 6 250*  

    Le montant dégressif est utilisé car il s’agit de la valeur la plus élevée.  
* ...
* Année 5 (2025) :  

    *Montant dégressif : 25 % de 23 730,46 = 4 943,85 = 2 471,92 + 2 471,92*  

    *Montant linéaire = 23 730,46/3 = 7 910,15 = 3 995,07 + 3 995,08*  

    Le montant linéaire est utilisé car il s'agit de la valeur la plus élevée.  

## <a name="half-year-convention-depreciation"></a>Amortissement selon la règle de la demi-année

La méthode Convention semestrielle n’est appliquée que si vous activez le bouton à bascule **Utiliser la Convention semestrielle** pour l’immobilisation sur la page **Fiche Immobilisation**.  

Utilisez Cette méthode d’amortissement avec les méthodes d’amortissement suivantes :  

* Linéaire  
* Dégressif 1  
* Dég.1/Lin.  

Lorsque vous appliquez la méthode de la règle de la demi-année, une immobilisation a un amortissement de six mois lors du premier exercice financier, quelle que soit la valeur du champ **Date début amortissement**.  

> [!NOTE]  
> Avec la règle de la demi-année, la durée de vie restante estimée pour l'immobilisation à la fin de l'exercice financier indique toujours une demi-année. Par conséquent, pour que la méthode Utiliser règle de la demi-année soit appliquée correctement, le champ **Date fin amortissement** de la page **Registre amortissement immo.** doit toujours contenir une date antérieure de six mois à la date de fin de l'exercice financier au cours duquel l'immobilisation sera complètement amortie.  

### <a name="example---half-year-convention-depreciation"></a>Exemple - Amortissement selon la règle de la demi-année

Une immobilisation a un coût d'acquisition de 100 000 $. Le champ **Date début amortissement** indique la valeur 01/03/20. La durée de vie est estimée à cinq ans, ce qui implique que le champ **Date fin amortissement** doit impérativement être paramétré sur la valeur 30/06/25. Le traitement par lots **Calculer amortissement** est exécuté tous les ans. Cet exemple est basé sur un exercice financier.  

Les écritures immobilisations se présentent comme suit :  

| Date | Type de report immo. | Jours | Montant | Valeur comptable |
| --- | --- | --- | --- | --- |
| 01/03/20 |Coût acquisition |(Date début amortissement) |100,000.00 |100,000.00 |
| 31/12/20 |Amortissement |270 |-10 000,00 |90,000.00 |
| 31/12/21 |Amortissement |360 |-20 000,00 |70,000.00 |
| 31/12/22 |Amortissement |360 |-20 000,00 |50,000.00 |
| 31/12/23 |Amortissement |360 |-20 000,00 |30,000.00 |
| 31/12/24 |Amortissement |360 |-20 000,00 |10,000.00 |
| 12/31/25 |Amortissements |180 |-10 000,00 |0.00 |

## <a name="example---db1sl-depreciation-using-half-year-convention"></a>Exemple - Amortissement dégressif 1/linéaire selon la règle de la demi-année

Une immobilisation a un coût d'acquisition de 100 000 $. Le champ **Date début amortissement** indique la valeur 01/11/20. La durée de vie est estimée à cinq ans, ce qui implique que le champ **Date fin amortissement** doit impérativement être paramétré sur la valeur 30/06/25. Sur la page **Registres amortissement immo.**, le champ **% dégressif** indique la valeur 40. Le traitement par lots **Calculer amortissement** est exécuté tous les ans. Cet exemple est basé sur un exercice financier.  

Les écritures immobilisations se présentent comme suit :  

| Date | Type de report immo. | Jours | Montant | Valeur comptable |
| --- | --- | --- | --- | --- |
| 01/11/20 |Coût acquisition |(Date début amortissement) |100,000.00 |100,000.00 |
| 31/12/20 |Amortissement |60 |-20 000,00 |80,000.00 |
| 31/12/21 |Amortissement |360 |-32 000,00 |48,000.00 |
| 31/12/22 |Amortissement |360 |-19 200,00 |28,800.00 |
| 31/12/23 |Amortissement |360 |-11 520,00 |17,280.00 |
| 31/12/24 |Amortissement |360 |-11 520,00 |5.760,00 Lin. |
| 31/12/25 |Amortissement |180 |  -5 760,00 |0,00 Lin. |

La mention `SL` qui suit la valeur comptable indique que la méthode linéaire a été utilisée.  

Méthode de calcul :  

* Année 1 :  

    *Montant dégressif = Montant total année = 40 % de 100 000 = 40 000.* Soit pour une demi-année 40 000 / 2 = 20 000  

    *Montant linéaire = Montant total année = 100 000/5 = 20 000.* Soit pour une demi-année = 20 000 / 2 =10 000  

    Le montant dégressif est utilisé car il s’agit de la valeur la plus élevée.  
* ...
* Année 5 (2024) :  

    *Montant dégressif = 40 % de 17 280,00 = 6 912,00*  

    *Montant linéaire = 28 800 / 1,5 = 11 520,00*  

    Le montant linéaire est utilisé car il s'agit de la valeur la plus élevée.  

## <a name="duplicate-entries-to-other-depreciation-books"></a>Dupliquer des écritures dans d’autres registres amortissement

Si vous disposez de trois registres amortissement, B1, B2 et B3, et que vous souhaitiez dupliquer des écritures de B1 vers B2 et B3, vous pouvez activer le bouton à bascule **Inclure dans liste duplication** sur les fiches registre amortissement de B2 et de B3. Par exemple, ce paramètre peut êtree utile dans les situations suivantes :

* Le registre amortissement B1 s’intègre au grand livre et utilise le journal GL immobilisation.
* Les registres amortissement B2 et B3 ne s’intègrent pas au grand livre et utilisent le journal immobilisation.  

Lorsque vous saisissez une écriture pour B1 dans le journal report immobilisation et activez le bouton à bascule **Inclure dans liste duplication** , [!INCLUDE [prod_short](includes/prod_short.md)] duplique l’écriture des registres B2 et B3 dans le journal immobilisation lors du report de l’écriture.  

> [!NOTE]  
> Vous ne pouvez pas effectuer la duplication dans le même journal et lot journal que celui à partir duquel vous dupliquez. Si vous reportez des écritures dans le journal GL immobilisation, vous pouvez les dupliquer dans le journal immobilisation ou dans le journal GL immobilisation en utilisant un autre lot.  

> [!NOTE]  
> Vous ne pouvez pas utiliser la même série de numéros dans le journal GL immobilisation et le journal immobilisation. Lorsque vous reportez des écritures dans le journal GL immobilisations, vous devez laisser le champ **N° document** vide. Si vous saisissez un numéro dans le champ, il est copié dans le journal immobilisation. Vous devez modifier manuellement le numéro de document avant de pouvoir reporter le journal.  

## <a name="manual-depreciation"></a>Amortissement manuel

Utilisez cette méthode manuelle pour les immobilisations qui ne font pas l’objet d’un amortissement, par exemple les terrains. Vous devez saisir l'amortissement dans le journal GL immobilisation. Le traitement en lot **Calculer amortissement** ignore les immobilisations qui utilisent la méthode d'amortissement manuelle.

## <a name="user-defined-depreciation"></a>Amortissement défini par l’utilisateur

Si les méthodes d’amortissement intégrées ne répondent pas à vos besoins, vous pouvez définir votre propre méthode d’amortissement à l’aide de tables d’amortissement. Pour en savoir plus sur l’application d’une méthode d’amortissement définie par l’utilisateur, voir [Configurer la méthode d’amortissement définie par l’utilisateur](fa-how-setup-user-defined-depreciation-method.md).

## <a name="see-also"></a>Voir aussi .

[Vue d’ensemble des immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
