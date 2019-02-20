---
title: Configuration du plan comptable
description: "Vous modifiez les comptes par défaut dans le plan comptable, et vous pouvez ajouter de nouveaux comptes."
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: COA, cha of acc
ms.date: 12/10/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 8a73de1aa2f4a0f633c401ea341bb7bde6579723
ms.openlocfilehash: 962f0b81d39e8e79fb7273ee93417b01be8d9e5a
ms.contentlocale: fr-ca
ms.lasthandoff: 12/11/2018

---
# <a name="setting-up-or-changing-the-chart-of-accounts"></a><span data-ttu-id="a3dbd-103">Configuration ou modification du plan comptable</span><span class="sxs-lookup"><span data-stu-id="a3dbd-103">Setting Up or Changing the Chart of Accounts</span></span>
<span data-ttu-id="a3dbd-104">Le plan comptable affiche les comptes généraux qui stockent vos données financières.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-104">The chart of accounts shows the ledger accounts that store your financial data.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="a3dbd-105">inclut un plan comptable standard prêt à prendre en charge votre société.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-105">includes a standard chart of accounts that is ready to support your business.</span></span>
<span data-ttu-id="a3dbd-106">Cependant, vous pouvez modifier les comptes par défaut, et vous pouvez ajouter de nouveaux comptes.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-106">However, you can change the default accounts, and you can add new accounts.</span></span>  

## <a name="adding-or-changing-accounts"></a><span data-ttu-id="a3dbd-107">Ajout ou modification de comptes</span><span class="sxs-lookup"><span data-stu-id="a3dbd-107">Adding or Changing Accounts</span></span>
<span data-ttu-id="a3dbd-108">À partir du plan comptable, vous pouvez ouvrir chaque compte du grand livre et ajouter ou modifier des paramètres.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-108">From the chart of accounts, you can open each G/L account and add or change settings.</span></span>

> [!NOTE]  
>   <span data-ttu-id="a3dbd-109">Vous pouvez supprimer un compte GL.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-109">You can delete a general ledger account.</span></span> <span data-ttu-id="a3dbd-110">Toutefois, avant que de le supprimer, les conditions suivantes doivent être réunies :</span><span class="sxs-lookup"><span data-stu-id="a3dbd-110">However, before you delete it, the following must be true:</span></span>  
>  
>   * <span data-ttu-id="a3dbd-111">Le solde du compte doit être nul.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-111">The balance on the account must be zero.</span></span>  
>   * <span data-ttu-id="a3dbd-112">Le champ **Perm. sup. ctes gr. liv. avant** doit être défini sur la page **Configuration du grand livre**, et le compte ne doit pas comporter d'écritures à cette date ou après celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-112">The **Allow G/L Acc. Deletion Before** field must be set on the **General Ledger Setup** page, and the account must not have ledger entries on or after that date.</span></span>  
>   * <span data-ttu-id="a3dbd-113">Si le champ **Vérifier utilisation cpte GL** de la page **Configuration du grand livre** est sélectionné, le compte ne doit pas être utilisé dans les groupes de report ni dans la configuration de report.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-113">If the **Check G/L Account Usage** field on the **General Ledger Setup** page is selected, then the account must not be used in any posting groups or posting setup.</span></span>  

[!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="a3dbd-114">vous empêchera de supprimer un compte général qui stocke les données nécessaires au plan comptable.</span><span class="sxs-lookup"><span data-stu-id="a3dbd-114">will prevent you from deleting a general ledger account that stores data that is needed in the chart of accounts.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a3dbd-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3dbd-115">See Also</span></span>
[<span data-ttu-id="a3dbd-116">Les écritures comptables et le plan comptable</span><span class="sxs-lookup"><span data-stu-id="a3dbd-116">The General Ledger and the Chart of Accounts</span></span>](finance-general-ledger.md)  
[<span data-ttu-id="a3dbd-117">Gestion des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="a3dbd-117">Managing Bank Accounts</span></span>](bank-manage-bank-accounts.md)  
[<span data-ttu-id="a3dbd-118">Utilisation des axes analytiques</span><span class="sxs-lookup"><span data-stu-id="a3dbd-118">Working with Dimensions</span></span>](finance-dimensions.md)  
<span data-ttu-id="a3dbd-119">[Importation de données à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)(across-import-data-configuration-packages.md)</span><span class="sxs-lookup"><span data-stu-id="a3dbd-119">[Importing Data from Other Finance Systems](across-import-data-configuration-packages.md)(across-import-data-configuration-packages.md)</span></span>  
[<span data-ttu-id="a3dbd-120">Utilisation des tableaux d'analyse</span><span class="sxs-lookup"><span data-stu-id="a3dbd-120">Work with Account Schedules</span></span>](bi-how-work-account-schedule.md)  
<span data-ttu-id="a3dbd-121">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a3dbd-121">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]

