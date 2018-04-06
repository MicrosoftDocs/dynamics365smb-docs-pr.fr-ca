---
title: "Mise à jour des taux de change des devises| Microsoft Docs"
description: "Pour utiliser plusieurs devises dans votre société, vous pouvez définir un code pour chaque devise et utiliser un service externe de taux de change, par exemple FloatRates."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies
ms.date: 01/25/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 973e2559b5cbf3e21bb735267ac800f87fa5a7f6
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="update-currency-exchange-rates"></a>Mettre à jour des taux de change devise
Vous devez définir un code pour chaque devise utilisée si vous achetez ou vendez dans des devises différentes de votre devise locale, si vous disposez de comptes client ou fournisseur dans d'autres devises, ou si vous enregistrez des transactions GL dans des devises différentes.  

Les compagnies opérant dans un nombre croissant de pays/régions, il est de plus en plus important qu'elles puissent consulter ou générer des rapports financiers dans plusieurs devises. Le programme prend en charge l'utilisation de plusieurs devises. Dans le programme, votre grand livre est configuré pour utiliser votre devise locale ($) et une autre devise est configurée comme devise additionnelle, à laquelle est affecté un taux de change courant.  

 Si vous désignez une deuxième devise comme devise de report additionnelle, [!INCLUDE[d365fin](includes/d365fin_md.md)] enregistre automatiquement les montants en $ et dans cette devise de report additionnelle pour chaque écriture GL, ainsi que d'autres écritures, telles que les écritures TVA. Lorsque les montants écriture sont calculés dans une devise de report additionnelle, les informations de la fenêtre **Taux de change devise** permettent de rechercher le taux de change approprié.  

> [!WARNING]  
>  Il est déconseillé d'utiliser la fonctionnalité de devise de report additionnelle comme base pour une conversion de rapport financier. Cet outil ne permet pas d'effectuer une conversion d'états financiers de filiale étrangère dans le cadre d'une consolidation de compagnie. La fonctionnalité de devise de report additionnelle permet uniquement de préparer des rapports dans une autre devise, comme s'il s'agissait de la devise locale.

## <a name="adjusting-exchange-rates"></a>Ajustement des taux de change  
Comme les taux de change ne cessent de fluctuer, il convient d'ajuster périodiquement les équivalents devise supplémentaires de votre système. À défaut d'effectuer ces ajustements, les montants convertis à partir de devises étrangères (ou additionnelles) et reportés dans le grand livre en $ risquent d'être erronés. En outre, les écritures quotidiennes reportées avant la saisie d'un taux de change quotidien dans le programme doivent être mises à jour après la saisie quotidienne des informations de taux de change. Le traitement par lots Ajuster taux de change permet d'ajuster les taux de change d'écritures client, fournisseur et compte bancaire validées. D'autres montants en devise de report additionnelle peuvent également être mis à jour dans les écritures.  

## <a name="displaying-reports-and-amounts-in-the-additional-reporting-currency"></a>Affichage de rapports et de montants dans la devise de report additionnelle  
L'utilisation d'une devise de report additionnelle peut faciliter le processus de génération de rapports d'une compagnie dans les cas suivants :  

- Compagnies situées dans des pays/régions extérieur(e)s à l'UE qui effectuent un grand nombre de transactions avec des compagnies situées dans des pays/régions de l'UE. Dans ce cas, la compagnie extérieure à l'UE peut vouloir générer des rapports financiers en euros afin qu'ils soient plus lisibles pour ses partenaires commerciaux de l'UE.  

- Compagnies qui souhaitent pouvoir générer des rapports financiers dans une devise davantage utilisée au niveau commerce étranger que leur devise locale.  

Plusieurs rapports dans le module Grand livre sont basés sur les écritures. Pour afficher les données financières dans le rapport en devise de report additionnelle, sélectionnez simplement le champ **Afficher dans la devise add.** dans la fenêtre du rapport GL approprié.  

## <a name="to-set-up-a-currency-exchange-rate-service"></a>Configurer un service de taux de change des devises
Vous pouvez utiliser un service externe pour tenir vos taux de change des devises à jour, par exemple FloatRates.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Services de taux de change devise**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**.
3. Dans la fenêtre **Service de taux de change devise**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Activez la case à cocher **Activé** pour activer le service.

## <a name="to-update-currency-exchange-rates-through-a-service"></a>Pour mettre à jour les taux de change des devises à partir d'un service
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Devises**, puis sélectionnez le lien connexe.
2. Choisissez l'option **Mettre à jour les taux de change**.

La valeur dans le champ **Taux de change** de la fenêtre **Devises** est mise à jour avec le dernier taux de change des devises.

## <a name="see-also"></a>Voir aussi
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

