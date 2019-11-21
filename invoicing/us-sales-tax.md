---
title: Taux de taxe américaine | Invoicing
description: Découvrez comment ajouter une taxe de vente dans Invoicing. Ajoutez un taux de taxe par défaut basé sur votre propre adresse, puis ajoutez des taux de taxe pour vos clients.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: tax rates
ms.date: 10/01/2019
ms.author: edupont
ms.openlocfilehash: 180e31d293ae706dd70ffb9e2befe133128a8695
ms.sourcegitcommit: a64e1abcc3c1974c87fe3e33fa6983ea7fbbb3ff
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778131"
---
# <a name="us-tax-rates-in-included365inv_longincludesd365inv_longmd"></a><span data-ttu-id="b9425-104">Taux de taxe américaine dans [!INCLUDE[d365inv_long](includes/d365inv_long.md)]</span><span class="sxs-lookup"><span data-stu-id="b9425-104">US tax rates in [!INCLUDE[d365inv_long](includes/d365inv_long.md)]</span></span>
> [!Note]
> [!INCLUDE[d365inv_discont](includes/d365inv_discont.md)]

<span data-ttu-id="b9425-105">Vous pouvez ajouter des taux de taxe à la volée lorsque vous créez des estimations et des factures.</span><span class="sxs-lookup"><span data-stu-id="b9425-105">You can add tax rates on the fly when you create estimates and invoices.</span></span> <span data-ttu-id="b9425-106">Vous pouvez voir les taux de taxe que vous avez déjà ajoutés dans les paramètres de Microsoft Invoicing, et vous pouvez également ajouter de nouveaux taux de taxe.</span><span class="sxs-lookup"><span data-stu-id="b9425-106">You can see the tax rates that you've already added in the settings for Microsoft Invoicing, and you can add new tax rates there as well.</span></span>  

<span data-ttu-id="b9425-107">Vous pouvez également gérer les taux de taxe nécessaires dans la page **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b9425-107">You can also manage the tax rates that you need in the **Settings** page.</span></span> <span data-ttu-id="b9425-108">C'est également dans cette page que vous définissez vos propres informations de taxe.</span><span class="sxs-lookup"><span data-stu-id="b9425-108">This is also where you set up your own tax information.</span></span> <span data-ttu-id="b9425-109">Le taux de taxe par défaut est celui que vous spécifiez pour votre adresse professionnelle.</span><span class="sxs-lookup"><span data-stu-id="b9425-109">The default tax rate is the one that you specify for your business address.</span></span>  

<span data-ttu-id="b9425-110">Chaque taux de taxe est basé sur un emplacement géographique spécifique.</span><span class="sxs-lookup"><span data-stu-id="b9425-110">Each tax rate is based on a particular geographic location.</span></span> <span data-ttu-id="b9425-111">Par exemple, le taux de taxe de Miami, Floride, comprend trois juridictions pour la taxe de vente : la ville (Miami), le comté (Dade) et la province (Floride).</span><span class="sxs-lookup"><span data-stu-id="b9425-111">For example, the Miami, Florida, tax rate includes three sales tax jurisdictions: city (Miami), county (Dade), and state (Florida).</span></span>  

<span data-ttu-id="b9425-112">Si vous configurez de nouveaux taux de taxe, vous devez veiller à bien remplir les champs correctement.</span><span class="sxs-lookup"><span data-stu-id="b9425-112">If you set up new tax rates, you must make sure that you fill in the fields correctly.</span></span> <span data-ttu-id="b9425-113">Aux États-Unis, les états, les comtés, les villes et les localités peuvent prélever la taxe de vente.</span><span class="sxs-lookup"><span data-stu-id="b9425-113">In the United States, states, counties, cities, and localities can charge sales tax.</span></span> <span data-ttu-id="b9425-114">Les compagnies recueillent la taxe de vente et la versent aux autorités gouvernementales pour les produits vendus aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="b9425-114">Companies collect and remit sales tax to these government authorities for products sold to end users.</span></span> <span data-ttu-id="b9425-115">La taxe de vente peut également être facturée sur une taxe de vente existante.</span><span class="sxs-lookup"><span data-stu-id="b9425-115">Sales tax can also be charged to existing sales tax.</span></span> <span data-ttu-id="b9425-116">Par exemple, la taxe peut être calculée sur un montant facture vente qui comprend déjà la taxe imposée par d'autres autorités.</span><span class="sxs-lookup"><span data-stu-id="b9425-116">For example, tax can be calculated on a sales invoice amount that already includes the tax from other jurisdictions.</span></span>  

## <a name="to-add-a-tax-rate-on-an-invoice-or-estimate"></a><span data-ttu-id="b9425-117">Pour ajouter un taux de taxe à une facture ou une estimation</span><span class="sxs-lookup"><span data-stu-id="b9425-117">To add a tax rate on an invoice or estimate</span></span>

1. <span data-ttu-id="b9425-118">Créez une facture ou une estimation.</span><span class="sxs-lookup"><span data-stu-id="b9425-118">Create an invoice or estimate.</span></span> <span data-ttu-id="b9425-119">Pour plus d'informations, voir [Créer une facture pour un nouveau client](send-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="b9425-119">For more information, see [Create an invoice for a new customer](send-invoice.md).</span></span>  
2. <span data-ttu-id="b9425-120">Dans la section **Détails**, si le client est imposable, choisissez l'icône AssistEdit > en regard du champ **Taux de taxe client**.</span><span class="sxs-lookup"><span data-stu-id="b9425-120">In the **Details** section, if the customer is tax liable, choose the AssistEdit icon > next to the **Customer tax rate** field.</span></span> <span data-ttu-id="b9425-121">Ce champ est déjà renseigné avec le taux de taxe par défaut, mais vous pouvez choisir une autre valeur.</span><span class="sxs-lookup"><span data-stu-id="b9425-121">This field is already filled in with your default tax rate, but you can choose another.</span></span>  
3. <span data-ttu-id="b9425-122">Dans la fenêtre **Taux de taxe**, choisissez un taux de taxe ou ajoutez-en un nouveau.</span><span class="sxs-lookup"><span data-stu-id="b9425-122">In the **Tax Rates** window, choose a tax rate or add a new.</span></span>  
4. <span data-ttu-id="b9425-123">Saisissez le nom et le taux pour la ville et la province, puis fermez la fenêtre **Taux de taxe**.</span><span class="sxs-lookup"><span data-stu-id="b9425-123">Enter the name and rate for both city and state and close the **Tax Rates** window.</span></span>  
5. <span data-ttu-id="b9425-124">Vous pouvez également cliquer ou appuyer sur **Définir comme taux de taxe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b9425-124">You can optionally click or tap **Set as default tax rate**.</span></span> <span data-ttu-id="b9425-125">Le taux par défaut est automatiquement appliqué à tout document ou article imposable.</span><span class="sxs-lookup"><span data-stu-id="b9425-125">The default rate is automatically applied to any taxable document or item.</span></span>  

## <a name="to-add-a-tax-rate-from-the-settings"></a><span data-ttu-id="b9425-126">Pour ajouter un taux de taxe à partir des paramètres</span><span class="sxs-lookup"><span data-stu-id="b9425-126">To add a tax rate from the settings</span></span>

1. <span data-ttu-id="b9425-127">Dans [!INCLUDE[d365inv](includes/d365inv.md)], dans le coin supérieur droit, cliquez sur le symbole d'engrenage, puis choisissez **Mes paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b9425-127">In [!INCLUDE[d365inv](includes/d365inv.md)], in the top right corner, choose the gear symbol, and then choose **My Settings**.</span></span>  
2. <span data-ttu-id="b9425-128">Faites défiler jusqu'à la section **Taux de taxe**.</span><span class="sxs-lookup"><span data-stu-id="b9425-128">Scroll to the **Tax Rates** section.</span></span> <span data-ttu-id="b9425-129">Cliquez sur **Ajouter un nouveau taux de taxe** pour ajouter un nouveau taux.</span><span class="sxs-lookup"><span data-stu-id="b9425-129">Click **Add new tax rate** to add a new rate.</span></span> <span data-ttu-id="b9425-130">Cliquez ou appuyez sur les points de suspension pour modifier un taux de taxe existant.</span><span class="sxs-lookup"><span data-stu-id="b9425-130">Click or tap the ellipses to modify an existing tax rate.</span></span>  
3. <span data-ttu-id="b9425-131">Saisissez le nom et le taux pour la ville et la province, puis fermez le formulaire **Taux de taxe**.</span><span class="sxs-lookup"><span data-stu-id="b9425-131">Enter the name and rate for both city and state and close the **Tax Rate** form.</span></span>  

<span data-ttu-id="b9425-132">Vous pouvez également cliquer ou appuyer sur **Définir comme taux de taxe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b9425-132">You can optionally click or tap **Set as default tax rate**.</span></span> <span data-ttu-id="b9425-133">Le taux par défaut est automatiquement appliqué à tout document ou article imposable.</span><span class="sxs-lookup"><span data-stu-id="b9425-133">The default rate is automatically applied to any taxable document or item.</span></span>  

<span data-ttu-id="b9425-134">Si vous ou vos clients résidez dans un pays qui utilise la taxe sur la valeur ajoutée (TVA), comme le Royaume-Uni, consultez [Ajouter la taxe sur la valeur ajoutée (TVA) à vos factures](add-vat.md).</span><span class="sxs-lookup"><span data-stu-id="b9425-134">If you or your customers are in a country that uses valued added tax (VAT), such as the United Kingdom, see [Add value added tax (VAT) to your invoices](add-vat.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="b9425-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9425-135">See Also</span></span>

[<span data-ttu-id="b9425-136">Configurer les informations sur votre entreprise</span><span class="sxs-lookup"><span data-stu-id="b9425-136">Set up your business information</span></span>](set-up-business-profile.md)  
[<span data-ttu-id="b9425-137">Envoyer une facture à un nouveau client</span><span class="sxs-lookup"><span data-stu-id="b9425-137">Send an invoice to a new customer</span></span>](send-invoice.md)  
