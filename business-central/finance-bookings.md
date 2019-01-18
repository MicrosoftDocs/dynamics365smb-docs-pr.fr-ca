---
title: "Facturer vos réservations dans Business Central | Microsoft Docs"
description: "Apprenez comment vous pouvez effectuer des facturations en vrac à partir de Microsoft Bookings dans Business Central."
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: invoicing, bookings
ms.date: 10/01/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: fb288b0b318fefd5b9720516432b6a85bb7347dd
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="bulk-invoicing-for-microsoft-bookings-in-included365finincludesd365finmdmd"></a><span data-ttu-id="b4ab4-103">Facturation en vrac pour les réservations Microsoft dans [!INCLUDE[d365fin](includes/d365fin_md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ab4-103">Bulk Invoicing for Microsoft Bookings in [!INCLUDE[d365fin](includes/d365fin_md.md)]</span></span>
<span data-ttu-id="b4ab4-104">Si votre compagnie utilise l'application Bookings d'Office 365, vous pouvez effectuer la facturation en vrac des rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-104">If your company uses the Bookings app in Office 365, you can do bulk invoicing for appointments.</span></span> <span data-ttu-id="b4ab4-105">La page **Réservations non facturées** de [!INCLUDE[d365fin](includes/d365fin_md.md)] fournit une liste des réservations effectuées par la société.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-105">The **Uninvoiced Bookings** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] provides a list of the company's completed bookings.</span></span> <span data-ttu-id="b4ab4-106">Cette page vous permet de rapidement sélectionner les rendez-vous à facturer et de créer des factures provisoires pour les services fournis.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-106">In this page you can quickly select the appointments that you want to invoice and create draft invoices for the services provided.</span></span>  

## <a name="connect-to-bookings"></a><span data-ttu-id="b4ab4-107">Connexion à Réservations</span><span class="sxs-lookup"><span data-stu-id="b4ab4-107">Connect to Bookings</span></span>
<span data-ttu-id="b4ab4-108">Pour connecter votre [!INCLUDE[d365fin](includes/d365fin_md.md)] à Réservations, vous devez indiquer votre société Réservations, quoi synchroniser avec Réservations, la fréquence de la synchronisation et les modèles à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-108">To connect your [!INCLUDE[d365fin](includes/d365fin_md.md)] with Bookings, you must specify your Bookings company, what to synchronize with Bookings, how often to synchronize, and which templates to use.</span></span> <span data-ttu-id="b4ab4-109">Vous définissez ces informations sur la page **Configuration synch. réservations**, que vous pouvez lancer depuis la page **Configuration de la synchronisation Exchange**, que vous pouvez rechercher à l'aide de [Rechercher](ui-search.md).</span><span class="sxs-lookup"><span data-stu-id="b4ab4-109">You set up this information on the **Booking Sync. Setup** page, which you can launch from the **Exchange Sync. Setup** page, which you can find through [Search](ui-search.md).</span></span>  

<span data-ttu-id="b4ab4-110">Par exemple, si vous souhaitez synchroniser des clients entre Réservations et [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez spécifier le modèle par défaut à utiliser pour ajouter de nouveaux clients à [!INCLUDE[d365fin](includes/d365fin_md.md)] selon les clients de votre société de Réservations.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-110">For example, if you want to synchronize customers between Bookings and [!INCLUDE[d365fin](includes/d365fin_md.md)], you must specify the default template to use to add new customers in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on the customers in your Bookings company.</span></span>  

## <a name="invoice-appointments"></a><span data-ttu-id="b4ab4-111">Facturer les rendez-vous</span><span class="sxs-lookup"><span data-stu-id="b4ab4-111">Invoice Appointments</span></span>
<span data-ttu-id="b4ab4-112">Lorsqu'il est temps d'envoyer les factures pour les réservations terminées, vous consultez la page **Réservations non facturées**.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-112">When it is time to send invoices for the completed bookings, you go to the **Uninvoiced Bookings** page.</span></span> <span data-ttu-id="b4ab4-113">Selon le nombre de fois où les informations sont synchronisées, la liste est long ou courte.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-113">Depending on how often the information is synchronized, the list is long or short.</span></span> <span data-ttu-id="b4ab4-114">Vous pouvez créer des factures pour toutes les réservations de la liste ou une réservation à la fois.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-114">You can create invoices for all bookings in the list or one booking at a time.</span></span> <span data-ttu-id="b4ab4-115">Vous pouvez sélectionner une ou plusieurs écritures dans la liste et facturer celles-ci uniquement.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-115">You can select one or more entries in the list and invoice those only.</span></span>  

<span data-ttu-id="b4ab4-116">Le prise en charge de la facturation des rendez-vous dans Réservations est plus simple que le flux de travail plus complet consistant à utiliser des devis, des commandes vente, et des factures vente.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-116">The support for invoicing appointments from Bookings is simpler than the fuller workflow of working with sales quotes, sales orders, and sales invoices.</span></span> <span data-ttu-id="b4ab4-117">Pour plus d'informations, reportez-vous à [Facturer des ventes](sales-how-invoice-sales.md).</span><span class="sxs-lookup"><span data-stu-id="b4ab4-117">For more information, see [Invoice Sales](sales-how-invoice-sales.md).</span></span> <span data-ttu-id="b4ab4-118">Vous pouvez choisir de vendre vos services à l'aide de [!INCLUDE[d365fin](includes/d365fin_md.md)] ou d'utiliser Réservations, selon les besoins de votre activité.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-118">You can choose to sell your services using [!INCLUDE[d365fin](includes/d365fin_md.md)] or choose to use Bookings, depending on your business needs.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4ab4-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4ab4-119">See Also</span></span>
[<span data-ttu-id="b4ab4-120">Finance</span><span class="sxs-lookup"><span data-stu-id="b4ab4-120">Finance</span></span>](finance.md)  
[<span data-ttu-id="b4ab4-121">Facturer des ventes</span><span class="sxs-lookup"><span data-stu-id="b4ab4-121">Invoice Sales</span></span>](sales-how-invoice-sales.md)  
[<span data-ttu-id="b4ab4-122">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="b4ab4-122">Setting Up Sales</span></span>](sales-setup-sales.md)  
[<span data-ttu-id="b4ab4-123">Réservations Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4ab4-123">Microsoft Bookings</span></span>](https://products.office.com/en-us/business/scheduling-and-booking-app)  

