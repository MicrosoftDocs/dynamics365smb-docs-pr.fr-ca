---
title: "Aperçu des tâches de configuration des processus de vente | Microsoft Docs"
description: "Décrit les tâches permettant de configurer des règles et des valeurs pour définir vos stratégies et vos processus de vente."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade, sell, configure
ms.date: 10/26/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 00e83452109c6fa31c3eb56d5631f972e5239314
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="setting-up-sales"></a><span data-ttu-id="a5d17-103">Définition des ventes.</span><span class="sxs-lookup"><span data-stu-id="a5d17-103">Setting Up Sales</span></span>
<span data-ttu-id="a5d17-104">Avant de pouvoir gérer les processus vente, vous devez configurer les règles et valeurs qui définissent les stratégies de vente de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="a5d17-104">Before you can manage sales processes, you must configure the rules and values that define the company's sales policies.</span></span>

<span data-ttu-id="a5d17-105">Vous devez définir la configuration générale, notamment les documents vente requis et le mode de report des valeurs correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a5d17-105">You must define the general setup, such as which sales documents are required and how their values are posted.</span></span> <span data-ttu-id="a5d17-106">Celle-ci a généralement lieu une seule fois au cours de la phase initiale de l'implémentation.</span><span class="sxs-lookup"><span data-stu-id="a5d17-106">This general setup is typically performed once during the initial implementation.</span></span>

<span data-ttu-id="a5d17-107">Une série de tâches distincte en relation avec l'enregistrement de nouveaux clients consiste à enregistrer les ententes spéciales sur les prix ou escomptes établies avec chaque client.</span><span class="sxs-lookup"><span data-stu-id="a5d17-107">A separate series of tasks related to registering new customers is to record any special price or discount agreements that you have with each customer.</span></span>

<span data-ttu-id="a5d17-108">La configuration des ventes en relation avec les finances, comme les modes de règlement et les devises, sont traitées dans la section Paramètres financiers.</span><span class="sxs-lookup"><span data-stu-id="a5d17-108">Finance-related sales setup, such as payment methods and currencies, are covered in the Finance Setup section.</span></span> <span data-ttu-id="a5d17-109">Pour plus d'informations, reportez-vous à [Configuration de Finance](finance-setup-finance.md).</span><span class="sxs-lookup"><span data-stu-id="a5d17-109">For more information, see [Setting Up Finance](finance-setup-finance.md).</span></span>

| <span data-ttu-id="a5d17-110">À</span><span class="sxs-lookup"><span data-stu-id="a5d17-110">To</span></span> | <span data-ttu-id="a5d17-111">Voir</span><span class="sxs-lookup"><span data-stu-id="a5d17-111">See</span></span> |
| --- | --- |
| <span data-ttu-id="a5d17-112">Créer une fiche client pour chaque client auquel vous vendez des éléments.</span><span class="sxs-lookup"><span data-stu-id="a5d17-112">Create a customer card for each customer that you sell to.</span></span> |[<span data-ttu-id="a5d17-113">Enregistrer de nouveaux clients</span><span class="sxs-lookup"><span data-stu-id="a5d17-113">Register New Customers</span></span>](sales-how-register-new-customers.md) |
| <span data-ttu-id="a5d17-114">Autoriser les clients à payer via Paypal en sélectionnant le logo Paypal sur les documents vente.</span><span class="sxs-lookup"><span data-stu-id="a5d17-114">Enable customers to pay through PayPal by choosing the PayPal logo on sales documents.</span></span> |[<span data-ttu-id="a5d17-115">Activer les paiements client via Paypal</span><span class="sxs-lookup"><span data-stu-id="a5d17-115">Enable Customer Payment Through PayPal</span></span>](sales-how-enable-payment-service-extensions.md) |
| <span data-ttu-id="a5d17-116">Entrer les différentes remises et prix spéciaux accordés aux clients en fonction de l'article, des quantités et/ou de la date.</span><span class="sxs-lookup"><span data-stu-id="a5d17-116">Enter the different discounts and special prices that you grant to customers depending on item, quantities, and/or date.</span></span> |[<span data-ttu-id="a5d17-117">Enregistrement des prix de vente, des remises et des accords sur les paiements</span><span class="sxs-lookup"><span data-stu-id="a5d17-117">Record Sales Price, Discount, and Payment Agreements</span></span>](sales-how-record-sales-price-discount-payment-agreements.md) |
| <span data-ttu-id="a5d17-118">Configurer les représentants de sorte à pouvoir les affecter aux contacts client ou à évaluer les performances des représentants et vous en servir comme base pour calculer la commission et les bonus.</span><span class="sxs-lookup"><span data-stu-id="a5d17-118">Set up salespeople so that you can assign them to customer contacts or measure salespeople's performance as a basis for calculating the sales commission or bonus.</span></span> |[<span data-ttu-id="a5d17-119">Configurer des représentants</span><span class="sxs-lookup"><span data-stu-id="a5d17-119">Set Up Salespeople</span></span>](sales-how-setup-salespeople.md) |
| <span data-ttu-id="a5d17-120">Spécifier pour différents clients ou pour tous les clients le moyen par lequel les documents vente sont envoyés par défaut lorsque vous sélectionnez l'action **Valider et envoyer**.</span><span class="sxs-lookup"><span data-stu-id="a5d17-120">Specify for individual customers or for all customers how sales documents are sent by default when you choose the **Post and Send** action.</span></span> |[<span data-ttu-id="a5d17-121">Configurer des profils d'envoi de documents</span><span class="sxs-lookup"><span data-stu-id="a5d17-121">Set Up Document Sending Profiles</span></span>](sales-how-setup-document-send-profiles.md) |
| <span data-ttu-id="a5d17-122">Configurez votre messagerie de sorte qu'elle contienne un résumé des informations du document de vente qui est envoyé.</span><span class="sxs-lookup"><span data-stu-id="a5d17-122">Set your email up to contain a summary of information in the sales document that is being sent.</span></span> |<span data-ttu-id="a5d17-123">[Envoyer des documents par courriel](ui-how-send-documents-email.md).</span><span class="sxs-lookup"><span data-stu-id="a5d17-123">[Send Documents by Email](ui-how-send-documents-email.md).</span></span> |
|<span data-ttu-id="a5d17-124">Utilisez un service Web UE pour vérifier le numéro d'immatriculation de TVA d'un client.</span><span class="sxs-lookup"><span data-stu-id="a5d17-124">Use an EU web service to verify a customer's VAT registration number.</span></span>|[<span data-ttu-id="a5d17-125">Vérifier les numéros d'identification TVA</span><span class="sxs-lookup"><span data-stu-id="a5d17-125">Verify VAT Registration Numbers</span></span>](finance-setup-vat.md)|
|<span data-ttu-id="a5d17-126">Entrer des informations sur les différents transporteurs utilisés, notamment un lien vers les prestations de traçabilité des colis.</span><span class="sxs-lookup"><span data-stu-id="a5d17-126">Enter information about the different transportation vendors you use, including a link to their package tracking service.</span></span>|[<span data-ttu-id="a5d17-127">Configurer des agents de livraison</span><span class="sxs-lookup"><span data-stu-id="a5d17-127">Set Up Shipping Agents</span></span>](sales-how-to-set-up-shipping-agents.md)|

## <a name="see-also"></a><span data-ttu-id="a5d17-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5d17-128">See Also</span></span>
[<span data-ttu-id="a5d17-129">Ventes</span><span class="sxs-lookup"><span data-stu-id="a5d17-129">Sales</span></span>](sales-manage-sales.md)  
<span data-ttu-id="a5d17-130">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a5d17-130">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
