---
title: "Procédure de configuration de nouvelles compagnies à l'aide d'une applet de commande | Microsoft Docs"
description: "Dans un certain nombre de scénarios, vous pouvez vouloir facturer et importer un package configuration sans impliquer vos utilisateurs ni utiliser l'interface utilisateur RapidStart Services. Vous pouvez le faire à l'aide d'une applet de commande Windows PowerShell."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 8b91c3b91e07f5ad96dcfc65152062054fc13c01
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="configure-new-companies-using-a-cmdlet"></a><span data-ttu-id="d7696-104">Configurer de nouvelles compagnies à l'aide d'une applet de commande</span><span class="sxs-lookup"><span data-stu-id="d7696-104">Configure New Companies using a Cmdlet</span></span>
<span data-ttu-id="d7696-105">Dans un certain nombre de scénarios, vous pouvez vouloir facturer et importer un package configuration sans impliquer vos utilisateurs ni utiliser l'interface utilisateur RapidStart Services.</span><span class="sxs-lookup"><span data-stu-id="d7696-105">In a number of scenarios, you may want to load and import a configuration package without involving your users or using the RapidStart Services user interface.</span></span> <span data-ttu-id="d7696-106">Vous pouvez le faire à l'aide d'une applet de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7696-106">You can do so by using a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="d7696-107">Les scénarios où cela peut être utile sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d7696-107">Scenarios where this may be useful include:</span></span>  

- <span data-ttu-id="d7696-108">Importer des données dans plusieurs installations de [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7696-108">Performing data import across multiple [!INCLUDE[d365fin](includes/d365fin_md.md)] installations.</span></span>
- <span data-ttu-id="d7696-109">Configurer les modules supplémentaires pour plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="d7696-109">Configuring additional application areas for multiple customers.</span></span>  

## <a name="to-deploy-a-configuration-package-using-a-cmdlet"></a><span data-ttu-id="d7696-110">Pour déployer un colis de configuration à l'aide d'un cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7696-110">To deploy a configuration package using a cmdlet</span></span>  

1. <span data-ttu-id="d7696-111">Préparez un package RapidStart Services.</span><span class="sxs-lookup"><span data-stu-id="d7696-111">Prepare a RapidStart Services package.</span></span> <span data-ttu-id="d7696-112">Par exemple, vous pouvez créer un module pour importer certaines valeurs et les noms de la table et des champs pour insérer ces valeurs dedans.</span><span class="sxs-lookup"><span data-stu-id="d7696-112">For example, you can create a package to import certain values and the names of the table and the fields to insert these values into.</span></span>  
2. <span data-ttu-id="d7696-113">Placez le module sur un ordinateur où vous allez lancer l'applet de commande.</span><span class="sxs-lookup"><span data-stu-id="d7696-113">Place the package on a computer where you will run the cmdlet.</span></span>  
3. <span data-ttu-id="d7696-114">Ouvrez l'interpréteur de commandes d'administration de [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7696-114">Open the [!INCLUDE[d365fin](includes/d365fin_md.md)] administration shell.</span></span>  
4. <span data-ttu-id="d7696-115">Saisissez **Invoke-NAVCodeUnit** et spécifiez des informations similaires à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="d7696-115">Enter **Invoke-NAVCodeUnit**, and specify information similar to the following example.</span></span>  
    ```  
    Invoke-NAVCodeunit -Tenant Default -CompanyName "CRONUS International Ltd." -CodeunitId 8620 -MethodName ImportRapidStartPackage -Argument "C:TEMPRS_CONFIG.rapidstart" -ServerInstance DynamicsNAV71  

    ```
<span data-ttu-id="d7696-116">L'applet de commande importe le module dans chaque compagnie.</span><span class="sxs-lookup"><span data-stu-id="d7696-116">The cmdlet imports the package into each company.</span></span> <span data-ttu-id="d7696-117">Les utilisateurs peuvent commencer à utiliser la nouvelle fonctionnalité immédiatement.</span><span class="sxs-lookup"><span data-stu-id="d7696-117">Users can start to use the new functionality immediately.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d7696-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7696-118">See Also</span></span>  
[<span data-ttu-id="d7696-119">Configurer de nouvelles compagnies</span><span class="sxs-lookup"><span data-stu-id="d7696-119">Configure New Companies</span></span>](admin-how-to-configure-new-companies.md)  
[<span data-ttu-id="d7696-120">Appliquer des configurations à de nouvelles compagnies</span><span class="sxs-lookup"><span data-stu-id="d7696-120">Apply Configurations to New Companies</span></span>](admin-apply-configuration-to-new-companies.md)  
[<span data-ttu-id="d7696-121">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="d7696-121">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="d7696-122">Administration</span><span class="sxs-lookup"><span data-stu-id="d7696-122">Administration</span></span>](admin-setup-and-administration.md)  
[<span data-ttu-id="d7696-123">Applets de commande Windows PowerShell Microsoft Dynamics NAV</span><span class="sxs-lookup"><span data-stu-id="d7696-123">Microsoft Dynamics NAV Windows PowerShell Cmdlets</span></span>](/dynamics-nav/microsoft-dynamics-nav-windows-powershell-cmdlets)
