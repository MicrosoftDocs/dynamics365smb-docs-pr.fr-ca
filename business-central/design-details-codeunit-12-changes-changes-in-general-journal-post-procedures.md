---
title: Modifications dans les procédures de report de journal général dans le Codeunit 12
description: Dans les versions précédentes, codeunit 12 a été modifié pour aider à améliorer les performances de report à partir du journal général. Découvrez les modifications apportées aux procédures de report dans cet article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/28/2020
ms.author: edupont
ms.openlocfilehash: 43232e1c38176bc947d33b5e3f55b7535afbcad4
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5390559"
---
# <a name="historical-changes-to-codeunit-12-changes-in-general-journal-post-procedures"></a>Historique des modifications du Codeunit 12 : modifications des procédures de report de journal général

Les modifications suivantes ont été mises en œuvre dans les versions de [!INCLUDE [navnow_md](includes/navnow_md.md)].  

|**Microsoft Dynamics NAV 2009 R2**|**Microsoft Dynamics NAV 2013 R2**|**Commentaires**|  
|----------------------------------------|----------------------------------------|-----------------|  
|GetGLReg|GetGLReg|Mis à jour|  
|RunWithCheck|RunWithCheck|Mis à jour|  
|RunWithoutCheck|RunWithoutCheck|Mis à jour|  
|Code|Code|Mis à jour|  
||PostGenJnlLine|Ajouté|  
||InitAmounts|Ajouté|  
||InitLastDocDate|Ajouté|  
|InitVAT|InitVAT|Mis à jour|  
|PostVAT|PostVAT|Mis à jour|  
|InsertVAT|InsertVAT|Mis à jour|  
|SummarizeVAT|SummarizeVAT|Mis à jour|  
|InsertSummarizedVAT|InsertSummarizedVAT|Mis à jour|  
|PostGLAcc|PostGLAcc|Mis à jour|  
|PostCust|PostCust|Mis à jour|  
|PostVend|PostVend|Mis à jour|  
|PostBankAcc|PostBankAcc|Mis à jour|  
|PostFixedAsset|PostFixedAsset|Mis à jour|  
|PostICPartner|PostICPartner|Mis à jour|  
|InitCodeUnit|StartPosting|Mis à jour|  
||ContinuePosting|Ajouté|  
|FinishCodeunit|FinishPosting|Mis à jour|  
||PostUnrealizedVAT|Ajouté|  
||CheckPostUnrealizedVAT|Ajouté|  
||ExchangeAccounts|Ajouté|  
|InitGLEntry|InitGLEntry|Mis à jour|  
||InitGLEntryVAT|Ajouté|  
||InitGLEntryVATCopy|Ajouté|  
|InsertGLEntry|InsertGLEntry|Mis à jour|  
||CreateGLEntry|Ajouté|  
||CreateGLEntryBalAcc|Ajouté|  
||CreateGLEntryVAT|Ajouté|  
||CreateGLEntryVATCollectAdj|Ajouté|  
||CreateGLEntryFromVATEntry|Ajouté|  
||UpdateCheckAmounts|Ajouté|  
|ApplyCustLedgEntry|ApplyCustLedgEntry|Mis à jour|  
||CalcPmtDiscPossible|Ajouté|  
||CalcPmtTolerancePossible|Ajouté|  
|CalcPmtTolerance|CalcPmtTolerance|Mis à jour|  
|CalcPmtDisc|CalcPmtDisc|Mis à jour|  
|CalcPmtDiscIfAdjVAT|CalcPmtDiscIfAdjVAT|Mis à jour|  
|CalcPmtDiscTolerance|CalcPmtDiscTolerance|Mis à jour|  
||CalcPmtDiscVATBases|Ajouté|  
||CalcPmtDiscVATAmounts|Ajouté|  
||InsertPmtDiscVATForVATEntry|Ajouté|  
||InsertPmtDiscVATForGLEntry|Ajouté|  
|CalcCurrencyApplnRounding|CalcCurrencyApplnRounding|Mis à jour|  
|FindAmtForAppln|FindAmtForAppln|Mis à jour|  
|CalcCurrencyUnrealizedGainLoss|CalcCurrencyUnrealizedGainLoss|Mis à jour|  
|CalcCurrencyRealizedGainLoss|CalcCurrencyRealizedGainLoss|Mis à jour|  
|CalcApplication|CalcApplication|Mis à jour|  
|CalcRemainingPmtDisc|CalcRemainingPmtDisc|Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CalcAmtLCYAdjustment|CalcAmtLCYAdjustment|Ajouté|  
|InitNewCVLedgEntry|InitFromGenJnlLine|Déplacé dans le tableau 383 Tampon écriture comptable CF détaillée|  
|InitOldCVLedgEntry|CopyFromCVLedgEntryBuf|Déplacé dans le tableau 383 Tampon écriture comptable CF détaillée|  
|InsertDtldCVLedgEntry|InsertDtldCVLedgEntry|Déplacé dans le tableau 383 Tampon écriture comptable CF détaillée|  
||InitBankAccLedgEntry|Ajouté|  
||InitCheckLedgEntry|Ajouté|  
||InitCustLedgEntry|Ajouté|  
||InitVendLedgEntry|Ajouté|  
||InsertDtldCustLedgEntry|Ajouté|  
||InsertDtldVendLedgEntry|Ajouté|  
|CustUnrealizedVAT|CustUnrealizedVAT|Mis à jour|  
|CustPostApplyCustLedgEntry|CustPostApplyCustLedgEntry|Mis à jour|  
||PrepareTempCustLedgEntry|Ajouté|  
|UnapplyCustLedgEntry|UnapplyCustLedgEntry|Mis à jour|  
|TransferCustLedgEntry|CopyFromGenJnlLine|Déplacé dans la table 21 Écriture client|  
|PostDtldCustLedgEntries|PostDtldCustLedgEntries|Mis à jour|  
||PostDtldCustLedgEntry|Ajouté|  
||PostDtldCustLedgEntryUnapply|Ajouté|  
||GetDtldCustLedgEntryAccNo|Ajouté|  
|ZeroTransNoDtldCustLedgEntries|SetZeroTransNo|Déplacé dans le tableau 379 Écriture comptable client détaillée|  
|AutoEntrForDtldCustLedgEntries||Remanié vers PostDtldCustLedgEntryUnapply|  
|CustUpdateDebitCredit|UpdateDebitCredit|Déplacé dans le tableau 379 Écriture comptable client détaillée|  
|ApplyVendLedgEntry|ApplyVendLedgEntry|Mis à jour|  
||PrepareTempVendLedgEntry|Ajouté|  
|VendPostApplyVendLedgEntry|VendPostApplyVendLedgEntry|Mis à jour|  
|UnapplyVendLedgEntry|UnapplyVendLedgEntry|Mis à jour|  
|TransferVendLedgEntry|CopyFromGenJnlLine|Déplacé dans le tableau 25 Écriture fournisseur|  
|PostDtldVendLedgEntries|PostDtldVendLedgEntries|Mis à jour|  
||PostDtldVendLedgEntry|Ajouté|  
||PostDtldVendLedgEntryUnapply|Ajouté|  
||GetDtldVendLedgEntryAccNo|Ajouté|  
||PostDtldCVLedgEntry|Ajouté|  
||PostDtldCustVATAdjustment|Ajouté|  
||PostDtldVendVATAdjustment|Ajouté|  
|ZeroTransNoDtldVendLedgEntries|SetZeroTransNo|Déplacé dans le tableau 380 Écriture comptable fournisseur détaillée|  
|AutoEntrForDtldVendLedgEntries||Remanié vers PostDtldVendLedgEntryUnapply|  
|VendUpdateDebitCredit|UpdateDebitCredit|Déplacé dans le tableau 380 Écriture comptable fournisseur détaillée|  
|VendUnrealizedVAT|VendUnrealizedVAT|Mis à jour|  
||PostUnrealVATEntry|Ajouté|  
||PostApply|Ajouté|  
|PostUnrealVATByUnapply|PostUnrealVATByUnapply|Mis à jour|  
||PostUnapply|Ajouté|  
||InsertDtldCustLedgEntryUnapply|Ajouté|  
||InsertDtldVendLedgEntryUnapply|Ajouté|  
||InsertTempVATEntry|Ajouté|  
||ProcessTempVATEntry|Ajouté|  
||UpdateCustLedgEntry|Ajouté|  
||UpdateVendLedgEntry|Ajouté|  
|UpdateCalcInterest|UpdateCalcInterest|Mis à jour|  
|UpdateCalcInterest2|UpdateCalcInterest2|Mis à jour|  
|GLCalcAddCurrency|GLCalcAddCurrency|Mis à jour|  
|HandleAddCurrResidualGLEntry|HandleAddCurrResidualGLEntry|Mis à jour|  
|CalcLCYToAddCurr|CalcLCYToAddCurr|Mis à jour|  
|CalcAddCurrFactor||Supprimé|  
|GetCurrencyExchRate|GetCurrencyExchRate|Mis à jour|  
|ExchAmount|ExchangeAmount|Déplacé dans le tableau 330 Taux de change devise|  
|ExchangeAmtLCYToFCY2|ExchangeAmtLCYToFCY2|Mis à jour|  
|CalcAddCurrForUnapplication|CalcAddCurrForUnapplication|Mis à jour|  
|CheckNonAddCurrCodeOccurred|CheckNonAddCurrCodeOccurred|Mis à jour|  
|CheckCalcPmtDisc||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscCVCust||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscCust||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscGenJnlCust||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscCVVend||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscVend||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|CheckCalcPmtDiscGenJnlVend||Déplacé dans Codeunit 426 Gestion de tolérance de règlement|  
|Inverser|Inverser|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ReverseCustLedgEntry|ReverseCustLedgEntry|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ReverseVendLedgEntry|ReverseVendLedgEntry|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ReverseBankAccLedgEntry|ReverseBankAccLedgEntry|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ReverseVAT|ReverseVAT|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|SetReversalDescription|SetReversalDescription|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ApplyCustLedgEntryByReversal|ApplyCustLedgEntryByReversal|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|ApplyVendLedgEntryByReversal|ApplyVendLedgEntryByReversal|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
|PostPmtDiscountVATByUnapply|PostPmtDiscountVATByUnapply|Déplacé dans Codeunit 17 Gen. Jnl.-Report inversé|  
||CheckDimComb|Ajouté à Codeunit 17 Gen. Jnl.-Report inversé|  
||CopyCustLedgEntry|Ajouté à Codeunit 17 Gen. Jnl.-Report inversé|  
||CopyVendLedgEntry|Ajouté à Codeunit 17 Gen. Jnl.-Report inversé|  
||CopyBankAccLedgEntry|Ajouté à Codeunit 17 Gen. Jnl.-Report inversé|  
|HandlDtlAddjustment|HandleDtldAdjustment|Mis à jour|  
|CollectAddjustment|CollectAdjustment|Mis à jour|  
|SetOverDimErr|SetOverDimErr|Mis à jour|  
|PostJob|PostJob|Mis à jour|  
|InsertVATEntriesFromTemp|InsertVATEntriesFromTemp|Mis à jour|  
|CaptureOrRefundCreditCardPmnt|CaptureOrRefundCreditCardPmnt|Mis à jour|  
|UpdateDOPaymentTransactEntry|UpdateDOPaymentTransactEntry|Mis à jour|  
|ABSMin|ABSMin|Mis à jour|  
|GetApplnRoundPrecision|GetApplnRoundPrecision|Mis à jour|  
|CheckDimValueForDisposal|CheckDimValueForDisposal|Mis à jour|  
|CalculateCurrentBalance|CalculateCurrentBalance|Mis à jour|  
|IncludeVATAmount||Déplacé dans Table 81 Gen. Ligne journal|  
|CalcVATAmountFromVATEntry|CalcVATAmountFromVATEntry|Mis à jour|  
||TotalVATAmountOnJnlLines|Ajouté|  
||SetGLRegReverse|Ajouté|  
||GetGLSetup|Ajouté|  
||ReadGLSetup|Ajouté|  
||CheckSalesExtDocNo|Ajouté|  
||CheckPurchExtDocNo|Ajouté|  
||CheckGLAccDimError|Ajouté|  
||GetCurrency|Ajouté|  
||PostDtldAdjustment|Ajouté|  
||GetNextEntryNo|Ajouté|  
||GetNextTransactionNo|Ajouté|  
||GetNextVATEntryNo|Ajouté|  
||IncrNextVATEntryNo|Ajouté|  
||IsNotPayment|Ajouté|  
||IsTempGLEntryBufEmpty|Ajouté|  
||IsVATAdjustment|Ajouté|  
||IsVATExcluded|Ajouté|  
||Mettre à jour dimensions|Ajouté|  
||UpdateDimensionsFromCustLedgEntry|Ajouté|  
||UpdateDimensionsFromVendLedgEntry|Ajouté|  
||UpdateTotalAmounts|Ajouté|  
||CreateGLEntriesForTotalAmounts|Ajouté|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : modifications du codeunit 12 : variables globales de mappage pour la ligne de report de journal général](design-details-codeunit-12-changes-mapping-global-variables-for-general-journal-post-line.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]