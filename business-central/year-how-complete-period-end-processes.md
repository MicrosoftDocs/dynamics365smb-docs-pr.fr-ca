---
title: Activités facultatives pour les périodes de fermeture
description: Cette rubrique décrit les processus et activités facultatifs pour la fermeture des périodes comptables dans Business Central.
author: jswymer
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments'
ms.date: 08/29/2022
ms.author: jswymer
ms.service: dynamics-365-business-central
---
# Aperçu des tâches de fermeture des périodes comptables

[!INCLUDE[prod_short](includes/prod_short.md)] ne vous oblige pas à clôturer les périodes. Toutefois, il existe de nombreuses activités de clôture de période (fin de mois) que vous pouvez effectuer. Cette rubrique présente un aperçu des activités et processus facultatifs pour la fermeture de périodes.  

## Grand livre

* Spécifiez des périodes de report à l'échelle du système et spécifiques à l'utilisateur.  

    Cela spécifie les dates entre lesquelles les reports sont autorisés. En fonction des besoins de votre activité, vous pouvez autoriser le report au début de la période ou vers la fin. Pour en savoir plus, voir [Spécifier les périodes comptables](finance-how-specify-posting-periods.md).  
* Effectuez tous les ajustements du grand livre (GL) nécessaires.  
* Mettez à jour et reportez les journaux récurrents.  
  <!--* Process Consolidations-->
* Exécutez les rapports financiers comme suit :  
  * Ouvrez la page **Rapports financiers**, puis sélectionnez l’action **Imprimer**.  

## Ventes

* Reportez l'ensemble des documents de vente, factures, notes de crédit et retours vente.  
* Reportez l'ensemble des journaux des encaissements.  
* Mettez à jour et reportez les journaux récurrents relatifs aux ventes.  
* Rapprocher les comptes clients avec le grand livre.  
* Exécutez le traitement par lots **Supprimer cdes vente facturées**.  

## Achats

* Reportez l'ensemble des bons de commande, factures, notes de crédit et retours achat.  
* Reportez l'ensemble des journaux paiement.  
* Mettez à jour et reportez les journaux récurrents relatifs aux achats.  
* Générez l'état **Comptabilité fournisseur âgée** et rapprochez la comptabilité fournisseur de la comptabilité.  
* Exécutez le traitement par lots **Supprimer cdes achat facturées**.  

## Immobilisations

* Reportez tous les coûts d'entretien qui ont été reportés via les journaux immobilisation ou les factures.
* Reportez les ajustements.
* Reportez l'appréciation.
* Reportez l'amortissement.
* Mettez à jour et reportez le journal immobilisations récurrentes.

## Intercompanie

* Traitez les transactions intersociétés.

## Calculer et traiter la taxe de vente

* Renseignez les déclarations de TVA.  

## Voir aussi .

[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Clôture plans](year-close-books.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
