---
title: Utilisation de l'extension Importer le fichier de paie de QuickBooks | Microsoft Docs
description: Cette rubrique décrit comment utiliser l'extension pour importer des transactions de salaire et de paie à partir de QuickBooks.
services: project-madeira
documentationcenter: ''
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, salary, wage
ms.date: 04/01/2021
ms.author: bholtorf
ms.openlocfilehash: 838095fe81af36a421a49f19400b0abd5cdce17b
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5784775"
---
# <a name="the-quickbooks-payroll-file-import-extension"></a>Extension Importer le fichier de paie de QuickBooks
Utilisez l'extension d'importation de fichier de paie de QuickBooks pour importer des transactions paie de QuickBooks vers des comptes GL dans [!INCLUDE[prod_short](includes/prod_short.md)]. Par exemple, cela est utile lorsque vous passez QuickBooks vers [!INCLUDE[prod_short](includes/prod_short.md)], ou si vous externalisez votre paie mais que vous souhaitez également en effectuer le suivi dans [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="steps-to-import-payroll-data"></a>Procédures pour importer des données de paie
La première étape consiste pour vous, ou peut-être votre comptable, à utiliser les fonctionnalités d'exportation dans QuickBooks pour exporter les données de la paie dans un fichier .IIF. La deuxième étape permet d'ouvrir la page **Journaux généraux** dans [!INCLUDE[prod_short](includes/prod_short.md)] et d'utiliser l'action **Importer les transactions de paie** pour importer le fichier. Au cours du processus d'importation, vous mappez les comptes GL de QuickBooks aux comptes correspondants dans [!INCLUDE[prod_short](includes/prod_short.md)]. L'étape finale consiste à reporter les transactions de paie dans [!INCLUDE[prod_short](includes/prod_short.md)] en fonction du mappage de compte. 

Pour plus d'informations, voir [Importer les transactions de paie](finance-how-import-payroll-transactions.md).

## <a name="see-also"></a>Voir aussi
[Personnalisation de [!INCLUDE[prod_short](includes/prod_short.md)] à l'aide des extensions ](ui-extensions.md)    
[Finances](finance.md)    
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]