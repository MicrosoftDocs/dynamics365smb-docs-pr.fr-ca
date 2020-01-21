---
title: Rapprocher des comptes bancaires et affecter des paiements | Microsoft Docs
description: Décrit les tâches de rapprochement de vos comptes bancaires, client et fournisseur, reporter des règlements ou des frais et affecter des paiements automatiquement.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 01/13/2020
ms.author: sgroespe
ms.openlocfilehash: 85f7feccd0eefa7c709ce077a8b01b049fc675c8
ms.sourcegitcommit: ead69ebe5b29927876a4fb23afb6c066f8854591
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/14/2020
ms.locfileid: "2954071"
---
# <a name="applying-payments-automatically-and-reconciling-bank-accounts"></a>Lettrage automatique des paiements et rapprochement des comptes bancaires
Vous devez régulièrement rapprocher vos comptes bancaires, créances client et créances fournisseur en affectant les paiements enregistrés au niveau de la banque à leurs factures impayées et notes de crédit associées ou à d'autres écritures ouvertes dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Vous pouvez effectuer cette tâche sur la page **Journal rapprochement bancaire**, par exemple, en important un fichier ou un flux de relevé bancaire pour enregistrer rapidement les paiements. Les paiements sont affectés aux écritures client ou fournisseur ouvertes selon les correspondances entre le texte de paiement et les informations d'écriture. Vous pouvez réviser et modifier les affectations automatiques avant de reporter le journal. Vous pouvez choisir de fermer les écritures de compte bancaire ouvertes associées aux écritures affectées lorsque vous reportez le journal. Le compte bancaire est automatiquement rapproché lorsque tous les paiements sont affectés.

La logique qui gère la correspondance automatique du texte de paiement avec les informations d'écriture est configurée sur la page **Règles affectation paiement** comme une série de règles hiérarchisées que vous pouvez modifier.

Vous pouvez également rapprocher des comptes bancaires sans rapprocher simultanément des paiements. Vous effectuez ce travail sur la page **Rapprochement bancaire**. Pour plus d'informations, voir [Rapprocher des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md).   

Pour importer des relevés bancaires en tant que flux bancaire, vous devez d'abord configurer et activer le service Envestnet Yodlee Bank Feeds, puis associer vos comptes bancaires aux comptes bancaires connexes en ligne. Pour plus d'informations, voir [Configurer le service Envestnet Yodlee Bank Feeds](bank-how-setup-bank-statement-service.md).  

Vous pouvez également utiliser l'extension AMC Banking 365 Fundamentals pour convertir un fichier de relevé bancaire, à partir de n'importe quel format, en flux de données que vous pouvez importer dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. Pour plus d'informations, voir [Utilisation de l'extension AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md).  

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.  

| À | Voir |
| --- | --- |
| Affecter des paiements aux écritures client ou fournisseur ouvertes en important un relevé de compte bancaire, et rapprocher le compte bancaire lorsque tous les paiements sont affectés. |[Rapprocher les paiements à l'aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md) |
| Appliquer manuellement les paiements en affichant des informations détaillées sur les données de correspondance et des suggestions d'écritures ouvertes candidates auxquelles affecter des paiements. |[Réviser ou affecter les paiements après une affectation automatique](receivables-how-review-apply-payments-auto-application.md) |
| Résoudre les paiements qui ne peuvent pas être affectés automatiquement à leurs écritures ouvertes associées. Par exemple, si les montants sont différents ou si une écriture associée n'existe pas. |[Rapprocher les paiements qui ne peuvent pas être affectés automatiquement](receivables-how-reconcile-payments-cannot-apply-auto.md) |
| Lier le texte des paiements à des comptes client, fournisseur ou grand livre spécifiques, pour toujours reporter les dépenses ou réceptions récurrentes en liquide sur ces comptes quand elles ne peuvent être affectées à aucun document. |[Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md) |
|Configurez les règles pour définir comment les paiements/transactions bancaires doivent être automatiquement affectés à leurs écritures ouvertes associées lorsque vous utilisez la fonction **Affecter automatiquement** sur la page **Journal rapprochement bancaire**.|[Configurer des règles pour l'affectation automatique des paiements](receivables-how-set-up-payment-application-rules.md)|

## <a name="see-related-training-at-microsoft-learnlearnmodulesuse-journals-dynamics-365-business-centralindex"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/use-journals-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Rapprochement des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
