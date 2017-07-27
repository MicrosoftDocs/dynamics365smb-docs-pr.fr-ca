---
title: "Activités facultatives pour les périodes de fermeture | Microsoft Docs"
description: "Cette rubrique décrit les processus et les activités facultatives pour la fermeture des périodes comptables dans Financials."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments
ms.date: 06/02/2017
ms.author: jswymer
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 678cebc065594ed0ed6fea897676f109ff2c1dce
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="overview-of-tasks-to-close-accounting-periods"></a>Aperçu des tâches de fermeture des périodes comptables
[!INCLUDE[d365fin](includes/d365fin_md.md)] ne vous oblige pas à clôturer les périodes. Toutefois, il existe de nombreuses activités de clôture de période (fin de mois) que vous pouvez effectuer. Cette rubrique présente un aperçu des activités et processus facultatifs pour la fermeture de périodes.  

## <a name="general-ledger"></a>Écritures comptables
* Spécifiez des périodes de report à l'échelle du système et spécifiques à l'utilisateur.  

    Cela spécifie les dates entre lesquelles les reports sont autorisés. En fonction des besoins de votre activité, vous pouvez autoriser le report au début de la période ou vers la fin. Pour plus d'informations, reportez vous à [Procédure: spécifier des périodes de validation](finance-how-specify-posting-periods.md).  
* Effectuez tous les ajustements nécessaires dans le GL.  
* Mettez à jour et reportez les journaux récurrents.  
  <!--* Process Consolidations-->
* Exécutez les tableaux d'analyse comme suit :  
  * Ouvrez la fenêtre **Tableau d'analyse**, puis sélectionnez l'action **Imprimer**.  

## <a name="sales-and-receivables"></a>Ventes
* Reportez l'ensemble des documents de vente, factures, notes de crédit et retours vente.  
* Reportez l'ensemble des journaux des encaissements.  
* Mettez à jour et reportez les journaux récurrents associés aux ventes.  
* Rapprocher les comptes clients avec le grand livre.  
* Exécutez le traitement par lots **Supprimer cdes vente facturées**.  

## <a name="purchases-and-payables"></a>Achats
* Reportez l'ensemble des bons de commande, factures, notes de crédit et retours achat.  
* Reportez l'ensemble des journaux paiement.  
* Mettez à jour et validez les feuilles abonnement associées aux achats.  
* Générez l'état **Comptabilité fournisseur âgée** et rapprochez la comptabilité fournisseur de la comptabilité.  
* Exécutez le traitement par lots **Supprimer cdes achat facturées**.  

<!-- ### Fixed Assets
* Post all maintenance costs have been posted through the fixed asset journals or invoices.
* Post adjustments.
* Post appreciation.
* Post depreciation.
* Update and post the recurring fixed asset journal.-->

<!--### Intercompany
* Process Intercompany Postings.-->

## <a name="calculate-and-process-sales-tax"></a>Calculez et traitez la taxe de vente.
* Renseignez les déclarations de TVA.  

## <a name="see-also"></a>Voir aussi
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Clôture plans](year-close-books.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

