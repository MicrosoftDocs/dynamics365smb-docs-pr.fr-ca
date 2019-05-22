---
title: Familiarisation avec le report des documents vente | Microsoft Docs
description: En savoir plus sur les différentes fonctions de report pour reporter des documents vente.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
ms.openlocfilehash: d1b2d29c4c5b8397bd6e9e05088e7ea50d68fd20
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1247922"
---
# <a name="posting-sales"></a><span data-ttu-id="55f84-103">Report des ventes</span><span class="sxs-lookup"><span data-stu-id="55f84-103">Posting Sales</span></span>
<span data-ttu-id="55f84-104">Dans le groupe **Validation** sur un document vente, vous pouvez faire votre choix parmi les fonctions de validation suivantes :</span><span class="sxs-lookup"><span data-stu-id="55f84-104">In the **Posting group** on a sales document, you can choose between the following posting functions:</span></span>

* <span data-ttu-id="55f84-105">**Valider**</span><span class="sxs-lookup"><span data-stu-id="55f84-105">**Post**</span></span>
* <span data-ttu-id="55f84-106">**Impression test**</span><span class="sxs-lookup"><span data-stu-id="55f84-106">**Test Report**</span></span>
* <span data-ttu-id="55f84-107">**Valider et envoyer**</span><span class="sxs-lookup"><span data-stu-id="55f84-107">**Post and Send**</span></span>
* <span data-ttu-id="55f84-108">**Valider et Imprimer**</span><span class="sxs-lookup"><span data-stu-id="55f84-108">**Post and Print**</span></span>
* <span data-ttu-id="55f84-109">**Valider et envoyer par e-mail**</span><span class="sxs-lookup"><span data-stu-id="55f84-109">**Post and Email**</span></span>
* <span data-ttu-id="55f84-110">**Valider par lot**</span><span class="sxs-lookup"><span data-stu-id="55f84-110">**Post Batch**</span></span>
* <span data-ttu-id="55f84-111">**Aperçu compta.**</span><span class="sxs-lookup"><span data-stu-id="55f84-111">**Preview Posting**</span></span>

<span data-ttu-id="55f84-112">Lorsque vous avez renseigné toutes les lignes et entré toutes les informations du document de vente, vous pouvez le reporter.</span><span class="sxs-lookup"><span data-stu-id="55f84-112">When you have completed all the lines and entered all the information on the sales order, you can post it.</span></span> <span data-ttu-id="55f84-113">Cela crée une livraison et une facture.</span><span class="sxs-lookup"><span data-stu-id="55f84-113">This creates a shipment and an invoice.</span></span>

<span data-ttu-id="55f84-114">Lorsqu’un document de vente est reporté, le compte du client, le grand livre et les écritures article sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="55f84-114">When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.</span></span>

<span data-ttu-id="55f84-115">Pour chaque commande vente, une écriture vente est créée dans la table **Écriture comptable**.</span><span class="sxs-lookup"><span data-stu-id="55f84-115">For each sales order, a sales entry is created in the **G/L Entry** table.</span></span> <span data-ttu-id="55f84-116">Une écriture est également créée dans le compte client de la table **Écriture comptable client** et une écriture comptable est créée dans le compte client approprié.</span><span class="sxs-lookup"><span data-stu-id="55f84-116">An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account.</span></span> <span data-ttu-id="55f84-117">De plus, le report de la commande peut avoir pour résultat la création d’une écriture TVA et d’une écriture pour le montant de l'escompte.</span><span class="sxs-lookup"><span data-stu-id="55f84-117">In addition, posting the order may result in a VAT entry and a general ledger entry for the discount amount.</span></span> <span data-ttu-id="55f84-118">Le report d’une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la page **Configuration des ventes et des comptes à recevoir**.</span><span class="sxs-lookup"><span data-stu-id="55f84-118">Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Sales & Receivables Setup** page.</span></span>

<span data-ttu-id="55f84-119">Pour chaque ligne commande vente, une écriture comptable article est créée dans la table **Écriture comptable article** (si les lignes vente contiennent des numéros des articles) ou une écriture comptable est créée dans la table **Écriture comptable** (si les lignes vente contiennent un compte général).</span><span class="sxs-lookup"><span data-stu-id="55f84-119">For each sales order line, an item ledger entry will be created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account).</span></span> <span data-ttu-id="55f84-120">En outre, les commandes vente sont toujours enregistrées dans les tables **En-tête expédition vente** et **En-tête facture vente**.</span><span class="sxs-lookup"><span data-stu-id="55f84-120">In addition to this, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.</span></span>

> [!IMPORTANT]  
>   <span data-ttu-id="55f84-121">Lorsque vous reportez une commande, vous pouvez créer une livraison et une facture.</span><span class="sxs-lookup"><span data-stu-id="55f84-121">When you post an order, you can create both a shipment and an invoice.</span></span> <span data-ttu-id="55f84-122">Ceci peut être effectué de manière simultanée ou indépendante.</span><span class="sxs-lookup"><span data-stu-id="55f84-122">These can be done at the same time or independently.</span></span> <span data-ttu-id="55f84-123">Vous pouvez également créer une expédition partielle et une facture partielle en renseignant les champs **Qté à expédier** et **Qté à facturer** sur chaque ligne commande vente avant la validation.</span><span class="sxs-lookup"><span data-stu-id="55f84-123">You can also create a partial shipment and a partial invoice by completing the **Qty. to Ship** and **Qty. to Invoice** fields on the individual sales order lines before you post.</span></span> <span data-ttu-id="55f84-124">Notez que vous ne pouvez pas créer de facture pour un article qui n'est pas livré.</span><span class="sxs-lookup"><span data-stu-id="55f84-124">Note that you cannot create an invoice for something that is not shipped.</span></span> <span data-ttu-id="55f84-125">C'est-à-dire que, avant de pouvoir facturer, vous devez avoir reporté une livraison, ou vous devez choisir de livrer et de facturer en même temps.</span><span class="sxs-lookup"><span data-stu-id="55f84-125">That is, before you can invoice, you must have recorded a shipment, or you must choose to ship and invoice at the same time.</span></span>

<span data-ttu-id="55f84-126">Lorsque le report est terminé, les lignes vente reportées sont supprimées de la commande.</span><span class="sxs-lookup"><span data-stu-id="55f84-126">When the posting is completed, the posted sales lines are removed from the order.</span></span> <span data-ttu-id="55f84-127">Un message vous indique lorsque le report est terminé.</span><span class="sxs-lookup"><span data-stu-id="55f84-127">A message tells you when the posting is completed.</span></span> <span data-ttu-id="55f84-128">Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent les écritures reportées, telles que **Écritures client**, **Écritures**, **Écritures article**, **Livraisons vente reportées** et **Factures vente reportées**.</span><span class="sxs-lookup"><span data-stu-id="55f84-128">After this, you will be able to see the posted entries in the various pages that contain posted entries, such as the **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Posted Sales Shipments**, and **Posted Sales Invoices** pages.</span></span>

## <a name="see-also"></a><span data-ttu-id="55f84-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55f84-129">See Also</span></span>
[<span data-ttu-id="55f84-130">Ventes</span><span class="sxs-lookup"><span data-stu-id="55f84-130">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="55f84-131">Envoyer des documents par courriel</span><span class="sxs-lookup"><span data-stu-id="55f84-131">Send Documents by Email</span></span>](ui-how-send-documents-email.md)  
<span data-ttu-id="55f84-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="55f84-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

