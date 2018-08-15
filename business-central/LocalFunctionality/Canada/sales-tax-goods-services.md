---
title: Taxe de vente au Canada| Microsoft Docs
description: En savoir plus sur la taxe de vente et la taxe sur les biens et les services au Canada.
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales tax, local
ms.date: 08/11/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 4f735d5f53d245934f3077a4da1aace29d558089
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="reporting-sales-tax-and-goodsservices-tax-in-canada"></a><span data-ttu-id="97dc6-103">Déclaration de la taxe de vente et taxe sur les biens/services au Canada</span><span class="sxs-lookup"><span data-stu-id="97dc6-103">Reporting Sales Tax and Goods/Services Tax in Canada</span></span>
<span data-ttu-id="97dc6-104">Au Canada, si un fournisseur n'a pas de présence commerciale dans la province dans laquelle les achats sont effectués, le fournisseur facture la taxe sur les biens et des services (Goods and Services Tax - GST) ou la taxe de vente harmonisée (Harmonized Sales Tax - HST) uniquement.</span><span class="sxs-lookup"><span data-stu-id="97dc6-104">In Canada, when a vendor does not have a business presence in the province in which purchases are made, the vendor will charge the Goods and Services Tax (GST) or Harmonized Sales Tax (HST) only.</span></span> <span data-ttu-id="97dc6-105">Toutefois, si la province applique une taxe de vente provinciale (Provincial Sales Tax - PST), l'acheteur doit tout de même calculer le montant de la PST et le payer directement à la province.</span><span class="sxs-lookup"><span data-stu-id="97dc6-105">However, if the province has a Provincial Sales Tax (PST), then the purchaser must still calculate the PST and pay it directly to the province.</span></span> <span data-ttu-id="97dc6-106">Lorsqu'un code zone de recouvrement provincial est sélectionné, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] l'utilise pour calculer la PST et la valider de sorte que l'impôt à payer apparaisse à la fois dans la comptabilité et dans les enregistrement d'écriture TVA.</span><span class="sxs-lookup"><span data-stu-id="97dc6-106">When a Provincial Tax Area Code is selected, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] uses it to calculate the PST and post it so that there is a tax liability in both the general ledger and the tax entry records.</span></span> <span data-ttu-id="97dc6-107">Par conséquent, le code région fiscale sélectionné ici doit uniquement inclure la PST et non la GST.</span><span class="sxs-lookup"><span data-stu-id="97dc6-107">Therefore, the tax area code selected here should be one where only the PST is included, not the GST.</span></span>  

## <a name="submitting-the-gsthst-file"></a><span data-ttu-id="97dc6-108">Envoi du fichier GST/HST</span><span class="sxs-lookup"><span data-stu-id="97dc6-108">Submitting the GST/HST File</span></span>
<span data-ttu-id="97dc6-109">Les informations sur les taxes dans les documents achat permettent de générer un transfert de fichier GST/HST en ligne que vous devez transmettre aux autorités fiscales.</span><span class="sxs-lookup"><span data-stu-id="97dc6-109">The tax information in purchase documents is used to generate a GST/HST online file transfer that you must provide to the tax authorities.</span></span> <span data-ttu-id="97dc6-110">Ce champ inclut la taxe sur les biens et les services (GST) et la taxe de vente harmonisée (HST).</span><span class="sxs-lookup"><span data-stu-id="97dc6-110">This file includes goods and services tax (GST) and harmonized sales tax (HST).</span></span> <span data-ttu-id="97dc6-111">Le fichier est créé dans un format de fichier .tax, qui peut être transféré en ligne.</span><span class="sxs-lookup"><span data-stu-id="97dc6-111">The file is created in a .tax file format, which can be transferred online.</span></span>  

## <a name="see-also"></a><span data-ttu-id="97dc6-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97dc6-112">See Also</span></span>
[<span data-ttu-id="97dc6-113">Fonctionnalités locales Canada</span><span class="sxs-lookup"><span data-stu-id="97dc6-113">Canada Local Functionality</span></span>](canada-local-functionality.md)  
[<span data-ttu-id="97dc6-114">Finance</span><span class="sxs-lookup"><span data-stu-id="97dc6-114">Finance</span></span>](../../finance.md)  
[<span data-ttu-id="97dc6-115">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="97dc6-115">Setting Up Finance</span></span>](../../finance-setup-finance.md)  
[<span data-ttu-id="97dc6-116">Déclaration de la taxe de vente au Canada</span><span class="sxs-lookup"><span data-stu-id="97dc6-116">Reporting Sales Tax in Canada</span></span>](ca-sales-tax.md)  
<span data-ttu-id="97dc6-117">[Utilisation de [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="97dc6-117">[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)</span></span>
