---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 05/27/2021
ms.author: edupont
ms.openlocfilehash: 59376b96dcd6f755040b07784ceca53e157bcf14
ms.sourcegitcommit: f9a190933eadf4608f591e2f1b04c69f1e5c0dc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/28/2021
ms.locfileid: "6116038"
---
<span data-ttu-id="62990-101">Sur les documents et les journaux achat, vous pouvez spécifier un numéro de document faisant référence au système de numérotation du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="62990-101">On purchase documents and journals, you can specify a document number that refers to the vendor's numbering system.</span></span> <span data-ttu-id="62990-102">Utilisez ce champ pour enregistrer le numéro que le fournisseur a attribué à la commande, à la facture ou à la note de crédit.</span><span class="sxs-lookup"><span data-stu-id="62990-102">Use this field to record the number that the vendor assigned to the order, invoice, or credit memo.</span></span> <span data-ttu-id="62990-103">Vous pouvez utiliser ce numéro ultérieurement, si vous avez besoin de retrouver l’écriture reportée à l’aide de ce numéro.</span><span class="sxs-lookup"><span data-stu-id="62990-103">You can then use the number later if, for some reason, you need to search for the posted entry using this number.</span></span>

<span data-ttu-id="62990-104">Le champ **N° doc. ext. obligatoire** de la page **Configuration achats et à payer** précise s’il est obligatoire de saisir un numéro de document externe dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="62990-104">The **Ext. Doc. No. Mandatory** field in the **Purchases & Payables Setup** page specifies whether it is mandatory to enter an external document number in the following situations:</span></span>

* <span data-ttu-id="62990-105">Dans le champ **N° de facture fournisseur**, dans le champ **N° commande fournisseur**</span><span class="sxs-lookup"><span data-stu-id="62990-105">In the **Vendor Invoice No.** field, **Vendor Order No.**</span></span> <span data-ttu-id="62990-106">ou dans le champ **N° avoir fournisseur**</span><span class="sxs-lookup"><span data-stu-id="62990-106">field, or the **Vendor Cr. Memo No.**</span></span> <span data-ttu-id="62990-107">d’un en-tête achat.</span><span class="sxs-lookup"><span data-stu-id="62990-107">field on a purchase header</span></span>

* <span data-ttu-id="62990-108">Dans le champ **N° doc. externe** d’une ligne journal général, dans laquelle la valeur du champ **Type document** est *Facture*, *Note de crédit* ou *Note de frais financiers*, et la valeur du champ **Type compte** est *Fournisseur*.</span><span class="sxs-lookup"><span data-stu-id="62990-108">In the **External Document No.** field on a general journal line, where the **Document Type** field is set to *Invoice*, *Credit Memo*, or *Finance Charge Memo*, and the **Account Type** field is set to *Vendor*.</span></span>

<span data-ttu-id="62990-109">Si vous sélectionnez ce champ, il est impossible de reporter une facture, une note de crédit ou le type de ligne journal général décrite plus avant sans numéro de document externe.</span><span class="sxs-lookup"><span data-stu-id="62990-109">If you select this field, it will not be possible to post an invoice, a credit memo, or the type of general journal line described above without an external document number.</span></span>

<span data-ttu-id="62990-110">Le numéro de document externe est inclus dans les documents reportés où vous pouvez effectuer une recherche d’après le numéro pertinent.</span><span class="sxs-lookup"><span data-stu-id="62990-110">The external document number is included in posted documents where you can search by the relevant number.</span></span> <span data-ttu-id="62990-111">Vous pouvez également effectuer une recherche à l’aide du numéro de document externe lors de la navigation sur les écritures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="62990-111">You can also search using the external document number when navigating on vendor ledger entries.</span></span>

<span data-ttu-id="62990-112">Une autre façon de gérer les numéros de document externe consiste à utiliser le champ **Votre référence**.</span><span class="sxs-lookup"><span data-stu-id="62990-112">A different way to handle external document numbers is to use the **Your Reference** field.</span></span> <span data-ttu-id="62990-113">Si vous utilisez le champ **Votre référence**, le numéro sera inclus dans les documents reportés, et vous pouvez le rechercher de la même manière que vous recherchez les valeurs dans les champs **N° de document externe**.</span><span class="sxs-lookup"><span data-stu-id="62990-113">If you use the **Your Reference** field, the number will be included in posted documents, and you can search by it in the same way as for values from **External Document No.** fields.</span></span> <span data-ttu-id="62990-114">Mais le champ n’est pas disponible sur les lignes journal.</span><span class="sxs-lookup"><span data-stu-id="62990-114">But the field is not available on journal lines.</span></span>
