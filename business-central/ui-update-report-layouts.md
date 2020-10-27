---
title: Mise à jour d'une présentation de rapport | Microsoft Docs
description: Vous pouvez être amené à mettre à jour une présentation de rapport personnalisée qui est utilisée dans un rapport. Cela est nécessaire si une modification de conception a été apportée à l'ensemble de données de rapport, par exemple, si un champ utilisé dans la présentation a été supprimé de l'ensemble de données de rapport.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: de9f82e0de16649b9481018213fa048313d4fb96
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3925482"
---
# <a name="update-custom-report-layouts"></a>Mettre à jour les présentations de rapport personnalisées
À l'occasion, vous pouvez être amené à mettre à jour une présentation de rapport personnalisée qui est utilisée dans un rapport. Cela est nécessaire si une modification de conception a été apportée à l'ensemble de données de rapport, par exemple, si un champ utilisé dans la présentation a été supprimé de l'ensemble de données de rapport. Si une présentation de rapport requiert une mise à jour, vous obtiendrez un message d'erreur lorsque vous tentez de visualiser, d'imprimer ou d'enregistrer le rapport.  

Vous pouvez mettre à jour automatiquement une présentation de rapport à partir du message d'erreur qui s'affiche lorsque vous lancez le rapport en cliquant sur le bouton **Oui** du message d'erreur. Ou, avant l'exécution des rapports, vous pouvez mettre à jour des présentations de rapport spécifiques ou toutes les présentations de rapport personnalisées susceptibles d'être affectées par les modifications de l'ensemble de données.  

Vous pouvez aussi tester des mises à jour sans appliquer les modifications nécessaires aux présentations de rapport personnalisées. Vous pouvez ainsi visualiser les modifications qui seront appliquées à la présentation du rapport et identifier des problèmes éventuels pendant cette opération. À partir des résultats du test, vous pouvez ouvrir les présentations de rapport personnalisées directement pour résoudre les problèmes. Il est recommandé de tester les mises à jour de présentations de rapport avant de les appliquer.  

Certaines modifications de l'ensemble de données de rapport peuvent être automatiquement mises à jour dans les présentations de rapport. Certaines modifications nécessiteront de modifier manuellement la présentation de rapport. Pour plus d'informations, voir [Limitations de la mise à jour d'une présentation de rapport personnalisée](ui-update-report-layouts.md#UpdateLimitations).  

## <a name="to-update-one-or-more-custom-report-layouts"></a>Pour mettre à jour une ou plusieurs présentations de rapport personnalisées  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Présentations de rapport** , puis sélectionnez le lien associé.  

2.  Sur la page **Présentations rapport** , si vous souhaitez mettre à jour un rapport spécifique, sélectionnez la présentation dans la liste, puis choisissez l'action **Mettre à jour présentation** . Ou, si vous souhaitez mettre à jour toutes les présentations de rapport personnalisées pour la compagnie, choisissez l'action **Mettre à jour toutes les présentations** .  

Si aucune erreur ne se produit, la mise à jour est appliquée aux présentations de rapport. Si des erreurs se produisent, un message contenant les erreurs s'affiche. Vous devez ensuite modifier manuellement la présentation de rapport personnalisée pour corriger l'erreur. Pour plus d'informations, consultez [Résolution des erreurs](ui-update-report-layouts.md#FixErrors).  

## <a name="to-test-custom-report-layout-updates"></a>Pour tester les mises à jour de présentations de rapport personnalisées  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Sélection de présentation de rapport** , puis sélectionnez le lien associé.  

2.  Sur la page **Sélection présentation rapport** , choisissez l'action **Mises à jour présentation test** .  

 Les modifications des présentations de rapport sont testées mais pas appliquées aux présentations de rapport réelles. Une page **Journal mise à jour présentation rapport** s'affiche pour indiquer l'état des mises à jour potentielles pour chaque présentation de rapport. Si une présentation de rapport contient des erreurs, vous pouvez y accéder directement à partir du message pour résoudre les problèmes. Pour plus d'informations, consultez [Résolution des erreurs](ui-update-report-layouts.md#FixErrors).  

##  <a name="limitations-of-the-custom-report-layout-update"></a><a name="UpdateLimitations"></a> Limitations de la mise à jour d'une présentation de rapport personnalisée  
 Il existe plusieurs types de modifications que la mise à jour automatique peut appliquer à des présentations de rapport personnalisées, par exemple, un champ utilisé dans la présentation a été supprimé de l'ensemble de données du rapport. Toutefois, la mise à jour automatique ne peut pas gérer les modifications ci-après apportées à un ensemble de données de rapport.  

1.  Champs, étiquettes ou éléments de données supprimés.  

2.  Noms de champ en double dans la présentation de rapport lorsqu'un champ a été renommé dans l'ensemble de données. Ceci doit être traité comme une erreur de conception.  

3.  Scénarios de mise à niveau où plusieurs itérations d'une présentation de rapport engendrent plusieurs actions d'attribution d'un nouveau nom sur les mêmes champs, étiquettes ou éléments de données.  

 Si le processus de mise à jour détecte l'un de ces problèmes, la mise à jour ne peut pas être appliquée. Vous devez résoudre les problèmes manuellement, par exemple en modifiant la présentation de rapport dans Word, ou par programme à l'aide de codeunits de mise à niveau.  

##  <a name="fixing-errors"></a><a name="FixErrors"></a> Correction des erreurs  
 Si vous obtenez un message d'erreur lorsque vous mettez à jour ou testez des mises à jour de présentation de rapport, vous devez généralement modifier la présentation de rapport pour résoudre le problème. Lisez le message d'erreur pour déterminer la cause du problème.  

 Le problème le plus courant se pose lorsqu'un champ utilisé sur la présentation a été supprimé de l'ensemble de données de rapport. Dans ce cas, vous pouvez visualiser une ligne du message d'erreur indiquant qu'un article a été supprimé. Pour résoudre ce problème, vous devez modifier la présentation et supprimer le champ en question.  

 Pour plus d'informations, voir [Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md#ModifyCustomLayout).  

Une fois que vous avez modifié la présentation, essayez de mettre de nouveau à jour la présentation.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi  
 [Gestion des présentations de rapport](ui-manage-report-layouts.md)  
 [Utilisation des rapports, des traitements en lot et des objets XMLport](ui-work-report.md)  
