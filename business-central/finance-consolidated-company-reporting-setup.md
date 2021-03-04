---
title: Configurer la consolidation de la compagnie
description: Découvrez comment vous pouvez configurer la manière dont les données de différentes compagnies dans Business Central sont transmises à une compagnie de consolidation.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: consolidation, subsidiaries, consolidate
ms.date: 10/01/2020
ms.author: bholtorf
ms.openlocfilehash: d733b8000d5ea476d32a96bcccdceebc32e0f43c
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4750990"
---
# <a name="set-up-company-consolidation"></a>Configurer la consolidation de la compagnie

Avant de pouvoir consolider les écritures de deux ou plusieurs compagnies distinctes (filiales) dans une compagnie consolidée, vous devez préparer le plan comptable et la compagnie de consolidation.  

En fonction de la complexité de vos entreprises, il existe deux façons de configurer la consolidation :

* Si les paramètres avancés ne sont pas nécessaires, par exemple l'ajout d'une compagnie que vous détenez uniquement en partie, vous pouvez utiliser le guide de configuration assistée **Consolidation de la compagnie** pour configurer rapidement une consolidation. Le guide vous aide à effectuer les étapes de base.
* Si d'autres paramètres avancés sont nécessaires, vous pouvez configurer vous-même la compagnie consolidée et les unités fonctionnelles.
  * Dans chaque unité fonctionnelle, spécifiez les comptes GL devant être inclus dans la consolidation, et spécifiez la méthode de conversion de la consolidation pour chaque compte.
  * Dans la compagnie consolidée, configurez une fiche unité fonctionnelle pour chaque compagnie devant être incluse dans la consolidation. La fiche unité fonctionnelle contient des informations, telles que les dates de l’exercice financier de l'unité fonctionnelle et le pourcentage de chaque compte devant être inclus dans la consolidation.

## <a name="simple-consolidation-setup"></a>Configuration d’une consolidation simple

Si votre consolidation est simple, car vous détenez en totalité les unités fonctionnelles à consolider, le guide de configuration assistée **Consolidation de la compagnie** vous aide à effectuer les étapes suivantes :

* Choisissez si vous souhaitez créer une compagnie consolidée, ou consolider les données dans une compagnie que vous avez déjà créée pour la consolidation. La compagnie ne doit pas contenir de transactions.
* Affichez un aperçu des résultats. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie que les données de base et les transactions peuvent être transférées avec succès vers la compagnie consolidée.

Pour utiliser le guide de configuration assistée, procédez comme suit :

1. Dans le tableau de bord **Comptable**, choisissez l'action **Configuration assistée**.
2. Choisissez **Configurer la génération de rapports de consolidation**, puis effectuez chaque étape du guide de configuration assistée.

## <a name="advanced-consolidation-setup"></a>Configuration d’une consolidation avancée

Si des paramètres plus avancés sont nécessaires pour votre consolidation, vous pouvez configurer manuellement la consolidation. Par exemple, si vous détenez partiellement des compagnies, ou si vous ne souhaitez pas inclure des compagnies dans la consolidation.  

### <a name="set-up-the-consolidated-company"></a>Configurer la compagnie consolidée

D’abord, vous devez définir la compagnie consolidée. Vous configurez la compagnie consolidée de la même manière que vous configurez d'autres compagnies. Pour plus d'informations, voir [Préparation aux activités commerciales](ui-get-ready-business.md).  

La liste suivante illustre les principaux aspects de la compagnie consolidée.

1. Configurer le plan comptable

    Pour plus d’informations, voir [Configuration ou modification du plan comptable](finance-setup-chart-accounts.md).  

    Le plan comptable peut être identique entre une unité fonctionnelle et la compagnie consolidée, ou la compagnie consolidée peut avoir un autre plan comptable. Si le plan comptable d’une unité fonctionnelle est différent de celui de la compagnie consolidée, vous devez spécifier le mappage entre les comptes sur les comptes de l'unité fonctionnelle. Pour plus d’informations, voir la section [Préparer les comptes GL pour la consolidation](#glacc).

2. Ajouter des unités fonctionnelles

    Pour consolider les données financières de plusieurs compagnies dans une compagnie consolidée, vous devez entrer des informations sur la filiale, telles que les unités fonctionnelles à inclure et la mesure dans laquelle leurs chiffres seront inclus.

    Pour plus d’informations, voir la section [Ajouter des unités fonctionnelles](#busunit).
3. Vous pouvez spécifier des taux de change lors de la consolidation des états financiers d'unités fonctionnelles si les états financiers sont en devise étrangère.

    Les trois taux de change utilisés sont **Taux moyen (manuel)**, **Taux de fermeture** et **Dernier taux de fermeture**. Pour plus d’informations, voir la section [Spécifier les taux de change pour les consolidations](#exchrates).
4. Vous pouvez consolider des informations de dimension et des comptes GL.

    Pour plus d’informations, voir la section [Inclure ou exclure des dimensions](#dim).

### <a name="add-business-units"></a><a name="busunit"></a>Ajouter des unités fonctionnelles

[!INCLUDE[prod_short](includes/prod_short.md)] vous permet de créer une liste d'unités fonctionnelles à consolider, de vérifier les données comptables avant leur consolidation, d’importer des fichiers et de générer des rapports de consolidation.  

1. Connectez-vous à la compagnie consolidée.
2. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Unités fonctionnelles**, puis sélectionnez le lien associé.  
3. Sélectionnez **Nouveau**, puis renseignez les champs requis. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!IMPORTANT]
    > Lorsque vous renseignez les champs **Date début** et **Date de fin**, assurez-vous de vous conformer aux règles GAAP concernant les périodes fiscales de l'unité fonctionnelle par rapport à la compagnie mère.
4. Répétez l’étape 3 pour chaque unité fonctionnelle supplémentaire

Si votre unité fonctionnelle utilise une devise étrangère, indiquez le taux de change à utiliser dans la consolidation. Vous devez également entrer des informations de consolidation sur les comptes du grand livre de l'unité fonctionnelle. Ces processus sont décrits dans les sections suivantes.

### <a name="prepare-general-ledger-accounts-for-consolidation"></a><a name="glacc"></a>Préparer les comptes GL pour la consolidation

Le plan comptable d’une compagnie qui sera consolidée doit spécifier des comptes pour consolidation. Vous devez spécifier chaque compte GL de report de chaque compagnie dans la compagnie consolidée vers laquelle le solde sera transféré lors de la consolidation. Il s’agit d’un mappage permettant la consolidation de compagnies dont les plans comptables diffèrent.

Si le plan comptable de l'unité fonctionnelle diffère de celui de la compagnie consolidée, vous devez préparer les comptes GL pour la consolidation. Vous pouvez spécifier les comptes sur lesquels reporter les débits et crédits et la méthode à utiliser pour convertir des devises dans la compagnie consolidée. Par exemple, cela est utile si vous exécutez souvent le rapport.

1. Dans [!INCLUDE [prod_short](includes/prod_short.md)] de chaque unité fonctionnelle, choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Plan comptable**, puis sélectionnez le lien associé.  
2. Ouvrez la fiche du compte, puis renseignez les champs du raccourci **Consolidation**. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="specify-exchange-rates-for-consolidations"></a><a name="exchrates"></a>Indiquer des taux de change pour les consolidations

Si une unité fonctionnelle utilise une devise différente de celle de la compagnie consolidée, vous devez spécifier des méthodes de conversion de taux de change pour chaque compte avant la consolidation. Pour chaque compte, la valeur du champ **Consolider la méthode de traduction** détermine le taux de change. Dans la compagnie consolidée, sur chaque fiche unité fonctionnelle, dans le champ **Table Taux de change devise**, vous spécifiez si la consolidation utilise les taux de change de l'unité fonctionnelle ou de la compagnie consolidée. Si vous utilisez les taux de change de la compagnie consolidée, vous pouvez les modifier pour une unité fonctionnelle. Pour les unités fonctionnelles, si le champ **Table Taux de change devise** de la fiche unité fonctionnelle contient la valeur **Local**, vous pouvez modifier le taux de change à partir de la fiche unité fonctionnelle. Les taux de change sont copiés à partir de la table **Taux de change devise**, mais vous pouvez les modifier avant la consolidation.

Le tableau suivant décrit les méthodes de conversion de taux de change que vous pouvez utiliser pour les comptes.

|Taux de change | Utilisation courante |
|---|---|
|Taux moyen (manuel) | Vous calculez manuellement le taux moyen pour la période à consolider. Calculez une moyenne arithmétique ou une estimation au plus près, puis spécifiez le résultat pour chaque unité fonctionnelle. Utilisé pour les comptes état des résultats.|
|Taux de fermeture | Utilisé pour les comptes de bilan.|
|Dernier taux de fermeture | Taux valide sur le marché des changes à la date pour laquelle le bilan ou l'état des résultats est préparé. Entrez ce taux pour chaque unité fonctionnelle. Utilisé pour les comptes de bilan.|
|Taux historique | Taux de change valide au moment de la transaction.|
|Taux composite | Les montants de la période en cours sont convertis au taux moyen et ajoutés au solde précédemment enregistré dans la compagnie consolidée. Cette méthode est généralement utilisée pour les comptes bénéfices non répartis, car ils incluent des montants provenant de périodes différentes et constituent donc un composé des montants convertis avec différents taux de change.|
|Taux des fonds propres | Il est similaire au **Taux composite**. Les différences sont reportées sur des comptes GL distincts.|

Pour spécifier des taux de change pour les unités fonctionnelles, procédez comme suit :

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Unités fonctionnelles**, puis sélectionnez le lien associé.  
2. Sur la page **Liste des unités fonctionnelles**, choisissez l'unité fonctionnelle, puis choisissez l'action **Taux moyen (manuel)**.  
3. Sur la page **Modifier taux de change**, la valeur du champ **Montant taux de change lié** est copiée à partir de la table **Taux de change devise**, mais vous pouvez la modifier. Fermez la page.  
4. Choisissez l'action **Taux de fermeture**.  
5. Dans le champ **Montant taux de change lié**, saisissez le taux de change.

### <a name="include-or-exclude-dimensions"></a><a name="dim"></a>Inclure ou exclure des dimensions

Vous pouvez consolider des informations de dimension et des comptes GL.

* Sur les dimensions pertinentes, spécifiez le champ **Code de consolidation**, ou laissez-le vide
  * Pour exclure une dimension de la consolidation, laissez le champ **Code de consolidation** vide sur la dimension et ne choisissez pas les dimensions dans les champs **Copier les dimensions** dans toutes les fonctions ou rapports de consolidation.
  * Pour inclure les informations de dimension dans la consolidation, laissez le champ **Code de consolidation** vide. Toutefois, la consolidation ne fonctionne que si les valeurs de dimension de l'unité fonctionnelle sont les mêmes que celles de la compagnie consolidée.
  * Pour consolider le code valeur de dimension dans l'unité fonctionnelle avec un autre code valeur de dimension dans la compagnie consolidée renseignez le champ **Code consolidé** sur les dimensions pertinentes.  
* Ajouter les dimensions pertinentes aux comptes GL pertinents

### <a name="exclude-a-company-from-consolidation"></a><a name="exclude"></a>Exclure une compagnie de la consolidation

Si vous ne souhaitez pas inclure une unité fonctionnelle dans la consolidation, vous pouvez l'exclure. Pour ce faire, accédez à la fiche unité fonctionnelle et désactivez la case à cocher **Consolider**.

### <a name="include-a-partially-owned-company-in-consolidation"></a><a name="include"></a>Inclure une compagnie partiellement détenue dans la consolidation

Si vous détenez une compagnie en partie, vous pouvez ajouter un pourcentage de chaque transaction qui correspond au pourcentage de la compagnie que vous détenez. Par exemple, si vous possédez 70 % de la compagnie, la consolidation inclut 70 $ d'une facture de 100 $. Pour spécifier le pourcentage de la compagnie que vous détenez, accédez à la fiche unité fonctionnelle et saisissez le pourcentage dans le champ **% consolidation**.  

## <a name="see-also"></a>Voir aussi

[Consolidation des données financières de plusieurs compagnies](finance-consolidated-company-reporting.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]