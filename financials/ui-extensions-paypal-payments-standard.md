---
title: Utilisation de l'extension PayPal Payments Standard | Microsoft Docs
description: "Décrit comment utiliser l'extension pour permettre aux clients d'effectuer des paiements avec Paypal."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize
ms.date: 03/29/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: fcbba8ecb2d63ab780a54aa4784a30b7fa5020fa
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="the-paypal-payments-standard-extension-to-dynamics-365-for-financials"></a><span data-ttu-id="b6237-103">Extension PayPal Payments Standard pour Dynamics 365 for Financials</span><span class="sxs-lookup"><span data-stu-id="b6237-103">The PayPal Payments Standard Extension to Dynamics 365 for Financials</span></span>
<span data-ttu-id="b6237-104">Les clients sont toujours plus exigeants en ce qui concerne le service clientèle, en termes de qualité de produits mais aussi en termes d'options de livraison et de paiement.</span><span class="sxs-lookup"><span data-stu-id="b6237-104">Customers continuously require higher customer service, both in terms of product quality but also in terms of delivery and payment options.</span></span> <span data-ttu-id="b6237-105">Le service PayPal Payments Standard vous aide à développer votre service clientèle.</span><span class="sxs-lookup"><span data-stu-id="b6237-105">The PayPal Payments Standard service helps you increase your customer service.</span></span>

<span data-ttu-id="b6237-106">Au lieu de collecter des paiements par l'intermédiaire de transferts bancaires ou de cartes de crédit, vous pouvez proposer à vos clients de vous payer via leur compte Paypal.</span><span class="sxs-lookup"><span data-stu-id="b6237-106">As an alternative to collecting payments through bank transfer or credit cards, you can offer your customers to pay you through their PayPal account.</span></span> <span data-ttu-id="b6237-107">Lorsque vous envoyez une facture vente ou un document de vente par courriel, le corps du message et le document PDF en pièce jointe contiennent un lien Paypal.</span><span class="sxs-lookup"><span data-stu-id="b6237-107">When you send a sales invoice or sales order by email, there is a PayPal link in the email body and in the attached PDF document.</span></span> <span data-ttu-id="b6237-108">Lorsque le client clique sur le lien, la page de service de leur compte Paypal s'ouvre et affiche les détails de paiement pour la vente.</span><span class="sxs-lookup"><span data-stu-id="b6237-108">When the customer chooses the link, the service page for their PayPal account appears showing the payment details for the sale.</span></span> <span data-ttu-id="b6237-109">Le client peut ensuite payer la facture comme tout autre paiement Paypal.</span><span class="sxs-lookup"><span data-stu-id="b6237-109">The customer can then pay the invoice as any other PayPal payment.</span></span>

<span data-ttu-id="b6237-110">Le service PayPal Payments Standard fournit les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="b6237-110">The PayPal Payments Standard service provides the following benefits:</span></span>

* <span data-ttu-id="b6237-111">Les paiements client arrivent plus rapidement sur votre compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="b6237-111">Customer payments arrive faster in your bank account.</span></span>
* <span data-ttu-id="b6237-112">Les clients disposent de davantage de méthodes de paiement de leurs factures.</span><span class="sxs-lookup"><span data-stu-id="b6237-112">Customers have more ways to pay invoices.</span></span>
* <span data-ttu-id="b6237-113">Paypal offre un service de paiement fiable, que les clients apprécient plutôt que de devoir saisir leurs données de carte de crédit sur des sites Web.</span><span class="sxs-lookup"><span data-stu-id="b6237-113">PayPal offers a trustworthy payment service, which customers prefer to entering credit card information on web sites.</span></span>
* <span data-ttu-id="b6237-114">Paypal propose plusieurs méthodes de gestion des paiements, y compris le traitement de cartes de crédit, les comptes Paypal, ainsi que d'autres sources.</span><span class="sxs-lookup"><span data-stu-id="b6237-114">PayPal offers multiple ways of handling payments, including credit card processing, PayPal accounts, and other sources.</span></span>
* <span data-ttu-id="b6237-115">Le lien Paypal peut être ajouté aux documents vente automatiquement ou manuellement par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6237-115">The PayPal link can be added automatically to sales documents or manually by the user.</span></span>
* <span data-ttu-id="b6237-116">Le service PayPal Payments Standard n'implique aucuns frais mensuels ni de frais de configuration.</span><span class="sxs-lookup"><span data-stu-id="b6237-116">The PayPal Payments Standard service does not involve monthly fees or setup fees.</span></span>
* <span data-ttu-id="b6237-117">Étant donné qu'il s'agit d'une extension, vous pouvez facilement activer le service PayPal Payment Standard si votre activité l'exige et au moment de votre choix.</span><span class="sxs-lookup"><span data-stu-id="b6237-117">Because it is an extension, you can easily enable the PayPal Payment Standard service when and if your business requires it.</span></span>  

<span data-ttu-id="b6237-118">Pour plus d'informations, reportez-vous à [Procédure : activer les paiements client via Paypal](sales-how-enable-payment-service-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="b6237-118">For more information, see [How to: Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6237-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6237-119">See Also</span></span>
<span data-ttu-id="b6237-120">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="b6237-120">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)</span></span>  
[<span data-ttu-id="b6237-121">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="b6237-121">Setting Up Sales</span></span>](sales-setup-sales.md)  
<span data-ttu-id="b6237-122">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="b6237-122">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
