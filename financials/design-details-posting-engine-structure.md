---
title: "Détails de conception : structure du moteur de report | Microsoft Docs"
description: "L'interface de report et certaines autres fonctions dans le codeunit 12 utilisent des fonctions de moteur de report pour préparer et insérer l'écriture et les enregistrements d'écriture TVA. Le moteur de report est également chargé de la création du registre du grand livre."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: e5044183beeeaab5eb1269b17e60391a43a33f0c
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-posting-engine-structure"></a>Détails de conception : Structure du moteur de report
L'interface de report et certaines autres fonctions dans le codeunit 12 utilisent des fonctions de moteur de report pour préparer et insérer l'écriture et les enregistrements d'écriture TVA. Le moteur de report est également chargé de la création du registre du grand livre.  
  
 Les fonctions de la table suivante fournissent un cadre standard pour créer les procédures de report (par exemple le code, CustPostApplyCustledgEntry, VendPostApplyVendLedgEntry, UnapplyCustLedgEntry, et UnapplyVendLedgEntry et Reverse) et un accès exclusif à la table 17, Écriture du grand livre.  
  
|Routine|Description|  
|-------------|---------------------------------------|  
|StartPosting|Initialise le tampon de report TempGLEntryBuf, verrouille les tables Écriture GL et Écriture TVA et initialise la période comptable, le registre GL et le taux de change. Ne devrait être appelé qu'une fois, alors NextEntryNo est 0.|  
|ContinuePosting|Vérifie et reporte la TVA non réalisée pour le précédent incrément de transaction NextTransactionNo et prépare le report de la ligne suivante.|  
|FinishPosting|Renseigne le report en insérant des écritures à partir d'un tampon temporaire dans la table de base de données. Toujours utilisé avec StartPosting. Vérifie les incohérences.|  
|InitGLEntry|Utilisé pour lancer la nouvelle écriture pour Ligne journal général. Retourne GLEntry comme paramètre.|  
|InitGLEntryVAT|Semblable à InitGLEntry, mais affecte également Numéro de compte contrepartie et SummarizeVAT.|  
|InitGLEntryVATCopy|Semblable à InitGLEntryVAT, mais copie également les données des groupes de validation de l'écriture TVA avant SummarizeVAT.|  
|InsertGLEntry|La seule fonction qui insère l'écriture dans la table TempGLEntryBuf globale. Utilisez toujours cette fonction pour insérer.|  
|CreateGLEntry|Exécute InitGLEntry, affecte le montant des devises supplémentaires, puis exécute InsertGLEntry. Remplace plusieurs lignes de code avec un seul appel de fonction.|  
|CreateGLEntryBalAcc|Semblable à CreateGLEntry, mais affecte également Type de compte contrepartie et Numéro de compte contrepartie.|  
|CreateGLEntryVAT|Semblable à CreateGLEntry, mais avec le traitement supplémentaire pour les groupes de validation et l'enregistrement sur un tampon TVA temporaire :<br /><br /> `GLEntry.CopyPostingGroupsFromDtldCVBuf(DtldCVLedgEntryBuf,GenJnlLine."Gen. Posting Type");`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryVATCollectAdj|Semblable à CreateGLEntry, mais avec la collection supplémentaire des ajustements et l'enregistrement sur un tampon TVA temporaire :<br /><br /> `CollectAdjustment(AdjAmount,GLEntry.Amount,GLEntry."Additional-Currency Amount",OriginalDateSet);`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryFromVATEntry|Semblable à CreateGLEntry, mais copie également les groupes de validation à partir de l'écriture TVA.|  
  
## <a name="see-also"></a>Voir aussi  
 [Détails de conception : Structure de l'interface de validation](design-details-posting-interface-structure.md)
