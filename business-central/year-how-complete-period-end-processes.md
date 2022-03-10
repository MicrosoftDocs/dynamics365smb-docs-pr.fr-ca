---
title: Activités facultatives pour les périodes de fermeture
description: Cette rubrique décrit les processus et activités facultatifs pour la fermeture des périodes comptables dans Business Central.
author: jswymer
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: 3b2ab40e0386ced967ad3f389f70817321d9bd92
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8142734"
---
# <a name="overview-of-tasks-to-close-accounting-periods"></a>Aperçu des tâches de fermeture des périodes comptables

[!INCLUDE[prod_short](includes/prod_short.md)] ne vous oblige pas à clôturer les périodes. Toutefois, il existe de nombreuses activités de clôture de période (fin de mois) que vous pouvez effectuer. Cette rubrique présente un aperçu des activités et processus facultatifs pour la fermeture de périodes.  

## <a name="general-ledger"></a>Écritures comptables

* Spécifiez des périodes de report à l'échelle du système et spécifiques à l'utilisateur.  

    Cela spécifie les dates entre lesquelles les reports sont autorisés. En fonction des besoins de votre activité, vous pouvez autoriser le report au début de la période ou vers la fin. Pour plus d'informations, reportez vous à [Spécifier des périodes de report](finance-how-specify-posting-periods.md).  
* Effectuez tous les ajustements nécessaires dans le GL.  
* Mettez à jour et reportez les journaux récurrents.  
  <!--* Process Consolidations-->
* Exécutez les tableaux d'analyse comme suit :  
  * Ouvrez la page **Tableau d'analyse**, puis sélectionnez l'action **Imprimer**.  

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

## <a name="fixed-assets"></a>Immobilisations

* Vérifiez que tous les frais d'entretien ont été reportés via les journaux immobilisation ou les factures.
* Reportez les ajustements.
* Reportez l'appréciation.
* Reportez l'amortissement.
* Mettez à jour et reportez le journal immobilisations récurrentes.

## <a name="intercompany"></a>Intersociétés

* Traitement des transactions intersociétés

## <a name="calculate-and-process-sales-tax"></a>Calculez et traitez la taxe de vente.

* Renseignez les déclarations de TVA.  

## <a name="see-also"></a>Voir aussi

[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Clôture plans](year-close-books.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]