---
title: Afficher les informations sur les tables
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2020
ms.author: jswymer
ms.openlocfilehash: de93063a60e6b64405b1491a67489c8bfa4657ad
ms.sourcegitcommit: 99915b493a7e49d12c530f2f9fda1fcedb518b6e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275328"
---
# <a name="viewing-table-information"></a><span data-ttu-id="71bdd-102">Affichage d'informations sur les tables</span><span class="sxs-lookup"><span data-stu-id="71bdd-102">Viewing Table Information</span></span>

<span data-ttu-id="71bdd-103">La page **Informations sur les tables 8700** fournit des informations sur toutes les tables système et métier d'une solution Business Central.</span><span class="sxs-lookup"><span data-stu-id="71bdd-103">The page **8700 Table Information** provides information about all system and business tables in a Business Central solution.</span></span> <span data-ttu-id="71bdd-104">En particulier, la page affiche des informations sur la quantité de données contenues dans les tables.</span><span class="sxs-lookup"><span data-stu-id="71bdd-104">In particular, the page displays information about the amount of data the tables contain.</span></span>

<span data-ttu-id="71bdd-105">Ces informations sont utiles pour résoudre les problèmes de performances, car nous allons voir la répartition de la taille des données entre les tables.</span><span class="sxs-lookup"><span data-stu-id="71bdd-105">This information is useful for troubleshooting performance problems, because let's you see the distribution of data size across tables.</span></span>

## <a name="viewing-table-information"></a><span data-ttu-id="71bdd-106">Affichage d'informations sur les tables</span><span class="sxs-lookup"><span data-stu-id="71bdd-106">Viewing table information</span></span>

<span data-ttu-id="71bdd-107">Pour ouvrir cette page, choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche"), entrez **Informations sur la table**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="71bdd-107">To open this page, select the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Table Information**, and then choose the related link.</span></span>

<span data-ttu-id="71bdd-108">Le tableau suivant décrit les informations fournies pour chaque table :</span><span class="sxs-lookup"><span data-stu-id="71bdd-108">The following table describes the information provided for each table:</span></span>

|<span data-ttu-id="71bdd-109">Colonne</span><span class="sxs-lookup"><span data-stu-id="71bdd-109">Column</span></span>|<span data-ttu-id="71bdd-110">Description</span><span class="sxs-lookup"><span data-stu-id="71bdd-110">Description</span></span>|
|------|-----------|
|<span data-ttu-id="71bdd-111">Nom de la compagnie</span><span class="sxs-lookup"><span data-stu-id="71bdd-111">Company Name</span></span>|<span data-ttu-id="71bdd-112">Nom de la compagnie, le cas échéant, à laquelle appartient la table.</span><span class="sxs-lookup"><span data-stu-id="71bdd-112">The name of the company, if any, that the table belongs to.</span></span>|
|<span data-ttu-id="71bdd-113">Nom de la table</span><span class="sxs-lookup"><span data-stu-id="71bdd-113">Table Name</span></span>|<span data-ttu-id="71bdd-114">Nom de la table.</span><span class="sxs-lookup"><span data-stu-id="71bdd-114">The name of the table.</span></span>|
|<span data-ttu-id="71bdd-115">N° table</span><span class="sxs-lookup"><span data-stu-id="71bdd-115">Table No.</span></span>|<span data-ttu-id="71bdd-116">Code de la table</span><span class="sxs-lookup"><span data-stu-id="71bdd-116">The ID of the table</span></span>|
|<span data-ttu-id="71bdd-117">Non.</span><span class="sxs-lookup"><span data-stu-id="71bdd-117">No.</span></span> <span data-ttu-id="71bdd-118">d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="71bdd-118">of Records</span></span>|<span data-ttu-id="71bdd-119">Nombre total d'enregistrements stockés dans la table.</span><span class="sxs-lookup"><span data-stu-id="71bdd-119">The total number of records stored in the table.</span></span>|
|<span data-ttu-id="71bdd-120">Taille enregistrement</span><span class="sxs-lookup"><span data-stu-id="71bdd-120">Record Size</span></span>|<span data-ttu-id="71bdd-121">La taille d'enregistrement moyenne en Ko/enregistrement.</span><span class="sxs-lookup"><span data-stu-id="71bdd-121">The average record size in KB/record.</span></span> <span data-ttu-id="71bdd-122">La valeur est calculée à l'aide de la formule suivante : 1024 (Taille)/Nbre</span><span class="sxs-lookup"><span data-stu-id="71bdd-122">The value is calculated using the following formula: 1024(Size)/(No.</span></span> <span data-ttu-id="71bdd-123">d'enregistrements).</span><span class="sxs-lookup"><span data-stu-id="71bdd-123">of Records)\`.</span></span> |

## <a name="see-also"></a><span data-ttu-id="71bdd-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71bdd-124">See Also</span></span>

[<span data-ttu-id="71bdd-125">Inspection des pages</span><span class="sxs-lookup"><span data-stu-id="71bdd-125">Inspecting Pages</span></span>](across-inspect-page.md)  
[<span data-ttu-id="71bdd-126">Articles sur les performances pour les développeurs</span><span class="sxs-lookup"><span data-stu-id="71bdd-126">Performance Articles For Developers</span></span>](/dynamics365/business-central/dev-itpro/performance/performance-developer)  
