---
title: Gérer, supprimer ou compresser des documents | Microsoft Docs
description: Conservez vos données historiques ou supprimez-les.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: 54cccb9df4daee3ad0811139dc2180d8a3072deb
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3186966"
---
# <a name="manage-documents"></a><span data-ttu-id="337b1-103">Gérer les documents</span><span class="sxs-lookup"><span data-stu-id="337b1-103">Manage Documents</span></span>
<span data-ttu-id="337b1-104">Un rôle central, par exemple un administrateur d'application, doit régulièrement gérer les documents accumulés au fil du temps en les supprimant ou en les compressant.</span><span class="sxs-lookup"><span data-stu-id="337b1-104">A central role, such as the application administrator, must regularly deal with accumulating historic documents by deleting or compressing them.</span></span>  

## <a name="delete-documents"></a><span data-ttu-id="337b1-105">Supprimer documents</span><span class="sxs-lookup"><span data-stu-id="337b1-105">Delete Documents</span></span>
<span data-ttu-id="337b1-106">Dans certains cas, vous pouvez souhaiter supprimer des commandes achat facturées qui n'ont pas été supprimées.</span><span class="sxs-lookup"><span data-stu-id="337b1-106">In certain situations, you may need to delete invoiced purchase orders that have not been deleted.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="337b1-107">vérifie que vous avez entièrement facturé les commandes achat supprimées.</span><span class="sxs-lookup"><span data-stu-id="337b1-107">checks that you have fully invoiced the deleted purchase orders.</span></span> <span data-ttu-id="337b1-108">Vous ne pouvez pas supprimer de commandes qui n'ont pas été entièrement facturées et reçues.</span><span class="sxs-lookup"><span data-stu-id="337b1-108">You cannot delete orders that you have not fully invoiced and received.</span></span>  

<span data-ttu-id="337b1-109">Les retours sont généralement supprimés après leur facturation.</span><span class="sxs-lookup"><span data-stu-id="337b1-109">Return orders are usually deleted after they are invoiced.</span></span> <span data-ttu-id="337b1-110">Lorsque vous reportez une facture, elle est transférée vers la page **Note de crédit achat reportée**.</span><span class="sxs-lookup"><span data-stu-id="337b1-110">When you post an invoice, it is transferred to the **Posted Purchase Credit Memo** page.</span></span> <span data-ttu-id="337b1-111">Si vous avez activé la case à cocher **Livraison retour sur note de crédit** sur la page **Configuration des achats et des comptes à payer**, la facture est transférée vers la page **Livraison retour reportée**.</span><span class="sxs-lookup"><span data-stu-id="337b1-111">If you selected the **Return Shipment on Credit Memo** check box on the **Purchases & Payable Setup** page, then the invoice is transferred to the **Posted Return Shipment** page.</span></span> <span data-ttu-id="337b1-112">Vous pouvez supprimer les documents à l'aide du traitement par lots **Supprimer les retours achat facturés**.</span><span class="sxs-lookup"><span data-stu-id="337b1-112">You can delete the documents using the **Delete Invd Purch. Ret. Orders** batch job.</span></span> <span data-ttu-id="337b1-113">Avant de procéder à la suppression, le traitement en lot vérifie que les retours achat ont été entièrement livrés et facturés.</span><span class="sxs-lookup"><span data-stu-id="337b1-113">Before deleting, the batch job checks if the purchase return orders are fully shipped and invoiced.</span></span>  

<span data-ttu-id="337b1-114">Les commandes ouvertes achat ne sont pas supprimées une fois que toutes les commandes achat associées ont été traitées et facturées.</span><span class="sxs-lookup"><span data-stu-id="337b1-114">Blanket purchase orders are not deleted after you have processed and invoiced all the related purchase orders.</span></span> <span data-ttu-id="337b1-115">Vous pouvez supprimer les commandes ouvertes à l'aide du traitement par lots **Supprimer commandes ouvertes achat facturées**.</span><span class="sxs-lookup"><span data-stu-id="337b1-115">You can delete blanket orders with the **Delete Invoiced Blanket Purchase Orders** batch job.</span></span>  

<span data-ttu-id="337b1-116">Les commandes service facturées sont habituellement supprimées automatiquement après avoir été entièrement facturées.</span><span class="sxs-lookup"><span data-stu-id="337b1-116">Invoiced service orders are usually deleted automatically after having been fully invoiced.</span></span> <span data-ttu-id="337b1-117">Lors du report d'une facture, une écriture correspondante est générée sur la page **Factures service reportées**.</span><span class="sxs-lookup"><span data-stu-id="337b1-117">When an invoice is posted, a corresponding entry is created on the **Posted Service Invoices** page.</span></span> <span data-ttu-id="337b1-118">Vous pouvez afficher le document reporté sur la page **Facture de service reportée**.</span><span class="sxs-lookup"><span data-stu-id="337b1-118">The posted document can be viewed on the **Posted Service Invoice** page.</span></span>  

<span data-ttu-id="337b1-119">Les commandes de service ne sont pas supprimées automatiquement, cependant, si la quantité totale sur la commande a été reportée, non pas à partir de la commande service proprement dite, mais à partir de la page **Facture service**.</span><span class="sxs-lookup"><span data-stu-id="337b1-119">Service orders are not deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** page.</span></span> <span data-ttu-id="337b1-120">Ensuite, il se peut que vous deviez supprimer des commandes facturées qui n'ont pas été supprimées.</span><span class="sxs-lookup"><span data-stu-id="337b1-120">Then you may need to delete invoiced orders that were not deleted.</span></span> <span data-ttu-id="337b1-121">Pour ce faire, exécutez le traitement par lots **Supprimer commandes service facturées**.</span><span class="sxs-lookup"><span data-stu-id="337b1-121">You can do this by running the **Delete Invoiced Service Orders** batch job.</span></span>  

## <a name="see-also"></a><span data-ttu-id="337b1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="337b1-122">See Also</span></span>  
[<span data-ttu-id="337b1-123">Administration</span><span class="sxs-lookup"><span data-stu-id="337b1-123">Administration</span></span>](admin-setup-and-administration.md)  
