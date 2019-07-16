---
title: Extension Envoyer un avis de remise | Microsoft Docs
description: Décrit l'extension Envoyer un avis de remise, qui permet d'envoyer par courriel un avis de remise à partir du journal paiement et de le renvoyer à partir des écritures fournisseur.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, stream, remittance, advice
ms.date: 06/06/2019
ms.author: sgroespe
ms.openlocfilehash: 9caa026f9edec42e56a035cf8d99228ca18c3c36
ms.sourcegitcommit: 04581558f6c5488c705a7ac392cf297be10b5f4f
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/06/2019
ms.locfileid: "1621262"
---
# <a name="send-remittance-advice"></a><span data-ttu-id="0c82e-103">Envoyer un avis de remise</span><span class="sxs-lookup"><span data-stu-id="0c82e-103">Send Remittance Advice</span></span>
<span data-ttu-id="0c82e-104">Lorsqu'un avis de remise est utilisé pour informer les fournisseurs des paiements effectués, vous pouvez désormais envoyer par courriel un avis de remise en bloc à partir du journal paiement et le renvoyer une fois les paiements effectués à partir des écritures fournisseur à l'aide de profils d'envoi de documents.</span><span class="sxs-lookup"><span data-stu-id="0c82e-104">Where remittance advice is used to notify vendors of payments being made, you can now email remittance advice in bulk from the payment journal as well as resend after payments are made from vendor ledger entries by using document sending profiles.</span></span>

> [!NOTE]
> <span data-ttu-id="0c82e-105">Cette fonctionnalité est uniquement prise en charge dans Business Central en ligne et local dans les pays suivants : Royaume-Uni, États-Unis, Canada, Australie, Nouvelle Zélande et Afrique du Sud.</span><span class="sxs-lookup"><span data-stu-id="0c82e-105">This functionality is only supported in Business Central online and on-premises in following countries: United Kingdom, United States, Canada, Australia, New Zealand, and South Africa.</span></span>  

<span data-ttu-id="0c82e-106">Vous pouvez envoyer des avis de remise de deux manières différentes :</span><span class="sxs-lookup"><span data-stu-id="0c82e-106">You can send remittance advice in two different ways:</span></span>

* <span data-ttu-id="0c82e-107">Dans la page **Journal paiement**, choisissez **Naviguer**, **Paiements**, **Envoyer un avis de paiement** pour envoyer par courriel un avis de remise pour une ou plusieurs lignes journal paiement</span><span class="sxs-lookup"><span data-stu-id="0c82e-107">In the **Payment Journal** page, choose **Navigate**, **Payments**, **Send Remittance Advice** to email remittance advice for one or multiple payment journal lines</span></span>
* <span data-ttu-id="0c82e-108">Dans la page **Écritures fournisseur**, sélectionnez Action, Fonctions, Envoyer un avis de remise pour envoyer par courriel un avis de remise après report des paiements fournisseur, pour une ou plusieurs écritures fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c82e-108">I the **Vendor Ledger Entries** page, choose Action, Functions, Send Remittance Advice to email remittance advice after posting of vendor payments, for one of multiple vendor ledger entries</span></span>

## <a name="see-also"></a><span data-ttu-id="0c82e-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c82e-109">See Also</span></span>
[<span data-ttu-id="0c82e-110">Proposer paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c82e-110">Suggest Vendor Payments</span></span>](payables-how-suggest-vendor-payments.md)  
<span data-ttu-id="0c82e-111">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions ](ui-extensions.md)  </span><span class="sxs-lookup"><span data-stu-id="0c82e-111">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions ](ui-extensions.md)  </span></span>  
<span data-ttu-id="0c82e-112">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="0c82e-112">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>