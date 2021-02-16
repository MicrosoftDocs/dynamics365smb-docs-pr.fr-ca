---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 01/20/2021
ms.author: edupont
ms.openlocfilehash: 718845561c1a18701d20b93ebdc8339308ce7ac8
ms.sourcegitcommit: adf1a87a677b8197c68bb28c44b7a58250d6fc51
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035805"
---
<span data-ttu-id="60575-101">Lorsque tous les articles ont été entrés sur les lignes document de vente, vous pouvez calculer l'escompte sur facture pour l’ensemble du document vente en choisissant l’action **Calculer escompte facture**.</span><span class="sxs-lookup"><span data-stu-id="60575-101">When all the items have been entered on the sales order lines, you can calculate the invoice discount for the entire sales document by choosing the **Calculate Invoice Discount** action.</span></span>

<span data-ttu-id="60575-102">Si le champ **Calculer escompte facture** est sélectionné dans la fenêtre **Configuration des ventes**, l'escompte facture est calculé automatiquement lorsque vous effectuez l’une des actions suivantes sur un document vente :</span><span class="sxs-lookup"><span data-stu-id="60575-102">If the **Calc. Inv. Discount** field is selected in the **Sales and Receivables Setup** window, then the invoice discount is calculated automatically when you do either of the following on a sales document:</span></span>

* <span data-ttu-id="60575-103">Afficher les statistiques</span><span class="sxs-lookup"><span data-stu-id="60575-103">View statistics</span></span>
* <span data-ttu-id="60575-104">Afficher un rapport de test</span><span class="sxs-lookup"><span data-stu-id="60575-104">View a test report</span></span>
* <span data-ttu-id="60575-105">Imprimer</span><span class="sxs-lookup"><span data-stu-id="60575-105">Print</span></span>
* <span data-ttu-id="60575-106">Report</span><span class="sxs-lookup"><span data-stu-id="60575-106">Post</span></span>

<span data-ttu-id="60575-107">L'escompte est réparti sur toutes les lignes du document vente pour les articles et les ressources pour lesquels le champ **Escompte facture autorisé** de la ligne document de vente indique **Oui**.</span><span class="sxs-lookup"><span data-stu-id="60575-107">The discount is apportioned over all the lines in the sales document for items where the **Allow Invoice Disc.** field on the sales order line contains **Yes**.</span></span> <span data-ttu-id="60575-108">C’est la configuration par défaut pour les articles.</span><span class="sxs-lookup"><span data-stu-id="60575-108">This is the default setting for items.</span></span>

<span data-ttu-id="60575-109">Les conditions d'escompte facture sont définies sur la page **Escomptes facture client** pour calculer l'escompte facture.</span><span class="sxs-lookup"><span data-stu-id="60575-109">The invoice discount terms are defined in the **Cust. Invoice Discounts** page to calculate the invoice discount.</span></span> <span data-ttu-id="60575-110">Le code devise du document vente est utilisé pour trouver les conditions escompte facture dans la devise correspondante.</span><span class="sxs-lookup"><span data-stu-id="60575-110">The currency code on the sales document is used to find the invoice discount terms in the corresponding currency.</span></span>

<span data-ttu-id="60575-111">Si vous n’avez pas défini d'escompte facture pour les devises, les conditions d'escompte facture définies sur la page **Escomptes facture client** avec des montants dans votre devise locale et le taux de change à la date de report du document vente sont utilisés pour calculer l'escompte facture en devise étrangère.</span><span class="sxs-lookup"><span data-stu-id="60575-111">If invoice discounts have not been defined for foreign currencies, then the invoice discount terms defined in the **Cust. Invoice Discounts** page with amounts in your local currency and the exchange rate on the posting date on the sales document are used to calculate the invoice discount in the foreign currency.</span></span>
