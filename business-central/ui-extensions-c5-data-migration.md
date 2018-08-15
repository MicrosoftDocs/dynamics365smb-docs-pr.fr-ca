---
title: Utilisation de l'extension C5 Data Migration | Microsoft Docs
description: Utilisez cette extension pour migrer des clients, des fournisseurs, des articles et des comptes GL de Microsoft Dynamics C5 2012 vers Business Central.
services: project-madeira
documentationcenter: 
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, migrate, data, C5, import
ms.date: 04/09/208
ms.author: bholtorf
ms.translationtype: HT
ms.sourcegitcommit: fa6779ee8fb2bbb453014e32cb7f3cf8dcfa18da
ms.openlocfilehash: 698bde6949c6053501881d07135586810fc81bdd
ms.contentlocale: fr-ca
ms.lasthandoff: 04/11/2018

---

# <a name="the-c5-data-migration-extension-for-business-central"></a><span data-ttu-id="339c0-103">Extension C5 Data Migration pour Business Central</span><span class="sxs-lookup"><span data-stu-id="339c0-103">The C5 Data Migration Extension for Business Central</span></span>
<span data-ttu-id="339c0-104">Cette extension facilite la migration de clients, de fournisseurs, d'articles et de vos comptes GL de Microsoft Dynamics C5 2012 vers [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="339c0-104">This extension makes it easy to migrate customers, vendors, items, and your general ledger accounts from Microsoft Dynamcis C5 2012 to [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="339c0-105">Vous pouvez également migrer des écritures historiques pour des comptes GL.</span><span class="sxs-lookup"><span data-stu-id="339c0-105">You can also migrate historical entries for general ledger accounts.</span></span>

> [!Note]
> <span data-ttu-id="339c0-106">La compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)] ne doit pas contenir de données.</span><span class="sxs-lookup"><span data-stu-id="339c0-106">The company in [!INCLUDE[d365fin](includes/d365fin_md.md)] must not contain any data.</span></span> <span data-ttu-id="339c0-107">En outre, après avoir commencé une migration, ne créez pas de clients, de fournisseurs, d'articles, ou de comptes jusqu'à la fin de la migration.</span><span class="sxs-lookup"><span data-stu-id="339c0-107">Additionally, after you start a migration, do not create customers, vendors, items, or accounts until the migration finishes.</span></span>

## <a name="what-data-is-migrated"></a><span data-ttu-id="339c0-108">Quelles données sont migrées ?</span><span class="sxs-lookup"><span data-stu-id="339c0-108">What Data is Migrated?</span></span>
<span data-ttu-id="339c0-109">Les données suivantes sont migrées pour chaque entité :</span><span class="sxs-lookup"><span data-stu-id="339c0-109">The following data is migrated for each entity:</span></span>

<span data-ttu-id="339c0-110">**Clients**</span><span class="sxs-lookup"><span data-stu-id="339c0-110">**Customers**</span></span>
* <span data-ttu-id="339c0-111">Magasin</span><span class="sxs-lookup"><span data-stu-id="339c0-111">Location</span></span>
* <span data-ttu-id="339c0-112">Pays</span><span class="sxs-lookup"><span data-stu-id="339c0-112">Country</span></span>
* <span data-ttu-id="339c0-113">Dimensions client (service, centre, objectif)</span><span class="sxs-lookup"><span data-stu-id="339c0-113">Customer dimensions (department, center, purpose)</span></span>
* <span data-ttu-id="339c0-114">Méthode de livraison</span><span class="sxs-lookup"><span data-stu-id="339c0-114">Shipment method</span></span>
* <span data-ttu-id="339c0-115">Vendeur</span><span class="sxs-lookup"><span data-stu-id="339c0-115">Sales Person</span></span>
* <span data-ttu-id="339c0-116">Modalités de paiement</span><span class="sxs-lookup"><span data-stu-id="339c0-116">Payment terms</span></span>
* <span data-ttu-id="339c0-117">Mode de règlement</span><span class="sxs-lookup"><span data-stu-id="339c0-117">Payment method</span></span>
* <span data-ttu-id="339c0-118">Groupe prix client</span><span class="sxs-lookup"><span data-stu-id="339c0-118">Customer price group</span></span>
* <span data-ttu-id="339c0-119">Escompte facture client</span><span class="sxs-lookup"><span data-stu-id="339c0-119">Customer invoice discount</span></span>

<span data-ttu-id="339c0-120">Si vous migrez des comptes, les données suivantes sont également migrées :</span><span class="sxs-lookup"><span data-stu-id="339c0-120">If you migrate accounts, the following data is also migrated:</span></span>

* <span data-ttu-id="339c0-121">Configuration du report client</span><span class="sxs-lookup"><span data-stu-id="339c0-121">Customer posting setup</span></span>
* <span data-ttu-id="339c0-122">Lot journal général</span><span class="sxs-lookup"><span data-stu-id="339c0-122">General journal batch</span></span>
* <span data-ttu-id="339c0-123">Transactions ouvertes (écritures client)</span><span class="sxs-lookup"><span data-stu-id="339c0-123">Open transactions (customer ledger entries)</span></span>

<span data-ttu-id="339c0-124">**Fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="339c0-124">**Vendors**</span></span>
* <span data-ttu-id="339c0-125">Magasin</span><span class="sxs-lookup"><span data-stu-id="339c0-125">Location</span></span>
* <span data-ttu-id="339c0-126">Pays</span><span class="sxs-lookup"><span data-stu-id="339c0-126">Country</span></span>
* <span data-ttu-id="339c0-127">Dimensions fournisseur (service, centre, objectif)</span><span class="sxs-lookup"><span data-stu-id="339c0-127">Vendor dimensions (department, center, purpose)</span></span>
* <span data-ttu-id="339c0-128">Escompte de la facture</span><span class="sxs-lookup"><span data-stu-id="339c0-128">Invoice discount</span></span>
* <span data-ttu-id="339c0-129">Méthode de livraison</span><span class="sxs-lookup"><span data-stu-id="339c0-129">Shipment method</span></span>
* <span data-ttu-id="339c0-130">Acheteur</span><span class="sxs-lookup"><span data-stu-id="339c0-130">Purchaser</span></span>
* <span data-ttu-id="339c0-131">Modalités de paiement</span><span class="sxs-lookup"><span data-stu-id="339c0-131">Payment terms</span></span>
* <span data-ttu-id="339c0-132">Mode de règlement</span><span class="sxs-lookup"><span data-stu-id="339c0-132">Payment method</span></span>
* <span data-ttu-id="339c0-133">Escompte de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="339c0-133">Vendor invoice discount</span></span>

<span data-ttu-id="339c0-134">Si vous migrez des comptes, les données suivantes sont également migrées :</span><span class="sxs-lookup"><span data-stu-id="339c0-134">If you migrate accounts, the following data is also migrated:</span></span>

* <span data-ttu-id="339c0-135">Configuration du report fournisseur</span><span class="sxs-lookup"><span data-stu-id="339c0-135">Vendor posting setup</span></span>
* <span data-ttu-id="339c0-136">Lot journal général</span><span class="sxs-lookup"><span data-stu-id="339c0-136">General journal batch</span></span>
* <span data-ttu-id="339c0-137">Transactions ouvertes (écritures fournisseur)</span><span class="sxs-lookup"><span data-stu-id="339c0-137">Open transactions (vendor ledger entries)</span></span>

<span data-ttu-id="339c0-138">**Articles**</span><span class="sxs-lookup"><span data-stu-id="339c0-138">**Items**</span></span>
* <span data-ttu-id="339c0-139">Magasin</span><span class="sxs-lookup"><span data-stu-id="339c0-139">Location</span></span>
* <span data-ttu-id="339c0-140">Pays</span><span class="sxs-lookup"><span data-stu-id="339c0-140">Country</span></span>
* <span data-ttu-id="339c0-141">Dimensions article (service, centre, objectif)</span><span class="sxs-lookup"><span data-stu-id="339c0-141">Item dimensions (department, center, purpose)</span></span>
* <span data-ttu-id="339c0-142">Escomptes de ligne de vente</span><span class="sxs-lookup"><span data-stu-id="339c0-142">Sales line discounts</span></span>
* <span data-ttu-id="339c0-143">Groupes escompte client</span><span class="sxs-lookup"><span data-stu-id="339c0-143">Customer discount groups</span></span>
* <span data-ttu-id="339c0-144">Groupes d'escompte sur article</span><span class="sxs-lookup"><span data-stu-id="339c0-144">Item discount groups</span></span>
* <span data-ttu-id="339c0-145">Prix vente</span><span class="sxs-lookup"><span data-stu-id="339c0-145">Sales price</span></span>
* <span data-ttu-id="339c0-146">Nomenclature produits</span><span class="sxs-lookup"><span data-stu-id="339c0-146">Tariff number</span></span>
* <span data-ttu-id="339c0-147">Unités de mesure</span><span class="sxs-lookup"><span data-stu-id="339c0-147">Units of measure</span></span>
* <span data-ttu-id="339c0-148">Code traçabilité</span><span class="sxs-lookup"><span data-stu-id="339c0-148">Item tracking code</span></span>
* <span data-ttu-id="339c0-149">Groupe prix client</span><span class="sxs-lookup"><span data-stu-id="339c0-149">Customer price group</span></span>

<span data-ttu-id="339c0-150">Si vous migrez des comptes, les données suivantes sont également migrées :</span><span class="sxs-lookup"><span data-stu-id="339c0-150">If you migrate accounts, the following data is also migrated:</span></span>

* <span data-ttu-id="339c0-151">Configuration du report d'inventaire</span><span class="sxs-lookup"><span data-stu-id="339c0-151">Inventory posting setup</span></span>
* <span data-ttu-id="339c0-152">Configuration report général</span><span class="sxs-lookup"><span data-stu-id="339c0-152">General posting setup</span></span>
* <span data-ttu-id="339c0-153">Lot journal article</span><span class="sxs-lookup"><span data-stu-id="339c0-153">Item journal batch</span></span>
* <span data-ttu-id="339c0-154">Transactions ouvertes (écritures article)</span><span class="sxs-lookup"><span data-stu-id="339c0-154">Open transactions (item ledger entries)</span></span>

> [!Note]
> <span data-ttu-id="339c0-155">S'il existe des transactions ouvertes qui utilisent des devises étrangères, les taux de change pour les devises sont également migrés.</span><span class="sxs-lookup"><span data-stu-id="339c0-155">If there are open transactions that use foreign currencies, the exchange rates for those currencies are also migrated.</span></span> <span data-ttu-id="339c0-156">Les autres taux de change ne sont pas migrés.</span><span class="sxs-lookup"><span data-stu-id="339c0-156">Other exchange rates are not migrated.</span></span>

<span data-ttu-id="339c0-157">**Plan comptable**</span><span class="sxs-lookup"><span data-stu-id="339c0-157">**Chart of Accounts**</span></span>  
* <span data-ttu-id="339c0-158">Dimensions standard : département, centre de coût, objectif</span><span class="sxs-lookup"><span data-stu-id="339c0-158">Standard dimensions: Department, Cost Center, Purpose</span></span>  
* <span data-ttu-id="339c0-159">Transactions GL historiques</span><span class="sxs-lookup"><span data-stu-id="339c0-159">Historical G/L transactions</span></span>  

> [!Note]
> <span data-ttu-id="339c0-160">Les transactions GL historiques sont traitées un peu différemment.</span><span class="sxs-lookup"><span data-stu-id="339c0-160">Historical G/L transactions are treated a little differently.</span></span> <span data-ttu-id="339c0-161">Lorsque vous migrez des données, vous définissez un paramètre **Période courante**.</span><span class="sxs-lookup"><span data-stu-id="339c0-161">When you migrate data you set a **Current Period** parameter.</span></span> <span data-ttu-id="339c0-162">Ce paramètre spécifie comment traiter les transactions GL.</span><span class="sxs-lookup"><span data-stu-id="339c0-162">This parameter specifies how to process G/L transactions.</span></span> <span data-ttu-id="339c0-163">Les transactions postérieures à cette date sont migrées individuellement.</span><span class="sxs-lookup"><span data-stu-id="339c0-163">Transactions after this date are migrated individually.</span></span> <span data-ttu-id="339c0-164">Les transactions antérieures à cette date sont regroupées par compte et migrées en tant que montant unique.</span><span class="sxs-lookup"><span data-stu-id="339c0-164">Transactions before this date are aggregated per account and migrated as a single amount.</span></span> <span data-ttu-id="339c0-165">Par exemple, supposons qu'il existe des transactions en 2015, 2016, 2017, 2018 et que vous spécifiez le 01 janvier 2017 dans le champ Période courante.</span><span class="sxs-lookup"><span data-stu-id="339c0-165">For example, let's say there are transactions in 2015, 2016, 2017, 2018, and you specify January 01, 2017 in the Current Period field.</span></span> <span data-ttu-id="339c0-166">Pour chaque compte, les montants des transactions effectuées au plus tard le 31 décembre 2106 sont regroupés sur une ligne journal général unique pour chaque compte du grand livre.</span><span class="sxs-lookup"><span data-stu-id="339c0-166">For each account, amounts for transactions on or before December 31, 2106, will be aggregated in a single general journal line for each G/L account.</span></span> <span data-ttu-id="339c0-167">Toutes les transactions postérieures à cette date sont migrées individuellement.</span><span class="sxs-lookup"><span data-stu-id="339c0-167">All trascations after this date will be migrated individually.</span></span>

## <a name="to-migrate-data"></a><span data-ttu-id="339c0-168">Pour migrer des données</span><span class="sxs-lookup"><span data-stu-id="339c0-168">To migrate data</span></span>
<span data-ttu-id="339c0-169">Quelques étapes suffisent pour exporter des données de C5 et les importer dans [!INCLUDE[d365fin](includes/d365fin_md.md)]:</span><span class="sxs-lookup"><span data-stu-id="339c0-169">There are just a few steps to export data from C5, and import it in [!INCLUDE[d365fin](includes/d365fin_md.md)]:</span></span>  

1. <span data-ttu-id="339c0-170">Dans C5, utilisez la fonctionnalité **Exporter la base de données** pour exporter les données.</span><span class="sxs-lookup"><span data-stu-id="339c0-170">In C5, use the **Export Database** feature to export the data.</span></span> <span data-ttu-id="339c0-171">Envoyez ensuite le fichier d'exportation vers un fichier compressé (zippé).</span><span class="sxs-lookup"><span data-stu-id="339c0-171">Then send the export folder to a compressed (zipped) folder.</span></span>  
2. <span data-ttu-id="339c0-172">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche"), entrez **Migration de données**, puis sélectionnez **Migration de données**.</span><span class="sxs-lookup"><span data-stu-id="339c0-172">In [!INCLUDE[d365fin](includes/d365fin_md.md)], choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Migration**, and then choose **Data Migration**.</span></span>  
3. <span data-ttu-id="339c0-173">Exécutez les étapes du guide de configuration assistée.</span><span class="sxs-lookup"><span data-stu-id="339c0-173">Complete the steps in the assisted setup guide.</span></span> <span data-ttu-id="339c0-174">Veillez à choisir **Importer à partir de Microsoft Dynamcis C5 2012** comme source de données.</span><span class="sxs-lookup"><span data-stu-id="339c0-174">Make sure to choose **Import from Microsoft Dynamcis C5 2012** as the data source.</span></span>  

> [!Note]
> <span data-ttu-id="339c0-175">Les compagnies ajoutent souvent des champs pour personnaliser C5 pour leur secteur d'activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="339c0-175">Companies often add fields to customize C5 for their specific line of business.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="339c0-176"> n'effectue pas la migration de données à partir des champs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="339c0-176"> does not migrate data from custom fields.</span></span> <span data-ttu-id="339c0-177">En outre, la migration échouera si vous avez plus de 10 champs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="339c0-177">Also, migration will fail if you have more than 10 custom fields.</span></span>

## <a name="viewing-the-status-of-the-migration"></a><span data-ttu-id="339c0-178">Affichage de l'état de la migration</span><span class="sxs-lookup"><span data-stu-id="339c0-178">Viewing the Status of the Migration</span></span>
<span data-ttu-id="339c0-179">Utilisez la page **Vue d’ensemble de la migration des données** pour contrôler la réussite de la migration.</span><span class="sxs-lookup"><span data-stu-id="339c0-179">Use the **Data Migration Overview** page to monitor the success of the migration.</span></span> <span data-ttu-id="339c0-180">La page affiche des informations telles que le nombre d'entités incluses dans la migration, l'état de la migration, ainsi que le nombre d'articles qui ont été migrés et l'état de réussite de leur migration.</span><span class="sxs-lookup"><span data-stu-id="339c0-180">The page shows information such as the number of entities that the migration will include, the status of the migration, and the number of items that have been migrated and whether they were successfull.</span></span> <span data-ttu-id="339c0-181">Elle affiche également le nombre d'erreurs, ce qui vous permet d'étudier ce qui ne s'est pas passé correctement et, si possible, d'accéder facilement à l'entité pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="339c0-181">It also shows the number of errors, lets you investigate what went wrong and, when possible, makes it easy to go to the entity to fix the issues.</span></span> <span data-ttu-id="339c0-182">Pour plus d'informations, voir la section suivante de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="339c0-182">For more information, see the next section in this topic.</span></span>  

> [!Note]
> <span data-ttu-id="339c0-183">Pendant que vous attendez les résultats de la migration, vous devez actualiser la page pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="339c0-183">While you are waiting for the results of the migration, you must refresh the page to display the results.</span></span>

## <a name="how-to-avoid-double-posting"></a><span data-ttu-id="339c0-184">Comment éviter le double report</span><span class="sxs-lookup"><span data-stu-id="339c0-184">How to Avoid Double-Posting</span></span>
<span data-ttu-id="339c0-185">Pour éviter le double report dans le grand livre, les comptes de solde suivants sont utilisés pour les transactions ouvertes :</span><span class="sxs-lookup"><span data-stu-id="339c0-185">To help avoid double-posting to the general ledger, the following balance accounts are used for open transactions:</span></span>  
  
* <span data-ttu-id="339c0-186">Pour les fournisseurs, nous utilisons le compte Comptabilité fournisseur dans le groupe de report fournisseur.</span><span class="sxs-lookup"><span data-stu-id="339c0-186">For vendors, we use the A/P account from the vendor posting group.</span></span>  
* <span data-ttu-id="339c0-187">Pour les clients, nous utilisons le compte Comptabilité client dans le groupe de report client.</span><span class="sxs-lookup"><span data-stu-id="339c0-187">For customers, we use the A/R account from the customer posting group.</span></span>  
* <span data-ttu-id="339c0-188">Pour les articles, nous créons une configuration de report générale dans laquelle le compte ajustement est le compte spécifié comme compte inventaire dans la configuration du report d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="339c0-188">For items, we create a general posting setup where the adjustment account is the account specified as the inventory account on the inventory posting setup.</span></span>  

## <a name="correcting-errors"></a><span data-ttu-id="339c0-189">Correction des erreur</span><span class="sxs-lookup"><span data-stu-id="339c0-189">Correcting Errors</span></span>
<span data-ttu-id="339c0-190">Si quelque chose se passe mal et qu'une erreur survient, le champ **État** affiche **Terminé avec des erreurs**, et le champ **Nombre d'erreurs** en indique le nombre.</span><span class="sxs-lookup"><span data-stu-id="339c0-190">If something goes wrong and an error occurs, the **Status** field will show **Completed with Errors**, and the **Error Count** field will show how many.</span></span> <span data-ttu-id="339c0-191">Pour afficher la liste des erreurs, vous pouvez ouvrir la page **Erreurs de migration des données** en sélectionnant :</span><span class="sxs-lookup"><span data-stu-id="339c0-191">To view a list of the errors, you can open the **Data Migration Errors** page by choosing:</span></span>  

* <span data-ttu-id="339c0-192">le nombre dans le champ **Nombre d'erreurs** pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="339c0-192">The number in the **Error Count** field for the entity.</span></span>  
* <span data-ttu-id="339c0-193">l'entité, puis l'action **Afficher les erreurs**.</span><span class="sxs-lookup"><span data-stu-id="339c0-193">The entity, and then the **Show Errors** action.</span></span>  

<span data-ttu-id="339c0-194">Dans la page **Erreurs de migration des données**, pour corriger une erreur vous pouvez sélectionner un message d'erreur, puis **Modifier l'enregistrement** pour ouvrir une page qui affiche les données migrées pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="339c0-194">On the **Data Migration Errors** page, to fix an error you can choose an error message, then choose **Edit Record** to open a page that shows the migrated data for the entity.</span></span> <span data-ttu-id="339c0-195">Après avoir corrigé une ou plusieurs erreurs, vous pouvez sélectionner **Migrer** pour migrer uniquement les entités que vous avez corrigées, sans entièrement redémarrer la migration.</span><span class="sxs-lookup"><span data-stu-id="339c0-195">After you fix one or more errors, you can choose **Migrate** to migrate only the entities you fixed, without having to completely restart the migration.</span></span>  

> [!Tip]
> <span data-ttu-id="339c0-196">Si vous avez corrigé plusieurs erreur, vous pouvez utiliser la fonctionnalité **Sélectionner davantage** pour sélectionner plusieurs lignes à migrer.</span><span class="sxs-lookup"><span data-stu-id="339c0-196">If you have fixed more than one error, you can use the **Select More** feature to select multiple lines to migrate.</span></span> <span data-ttu-id="339c0-197">Sinon, s'il existe des erreurs qu'il n'est pas important de corriger, vous pouvez les sélectionner, puis cliquer sur **Ignorer les sélections**.</span><span class="sxs-lookup"><span data-stu-id="339c0-197">Alternatively, if there are errors that are not important to fix, you can choose them and then choose **Skip Selections**.</span></span>

> [!Note]
> <span data-ttu-id="339c0-198">Si vous avez des articles inclus dans une nomenclature, vous pouvez être amené à effectuer la migration plus d'une fois si l'article d'origine n'est pas créé avant les variantes qui y font référence.</span><span class="sxs-lookup"><span data-stu-id="339c0-198">If you have items that are included in a BOM, you might need to migrate more than once if the original item is not created before the variants that reference it.</span></span> <span data-ttu-id="339c0-199">Si une variante article est créée en premier lieu, la référence à l'article d'origine peut entraîner un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="339c0-199">If an item variant is created first, the reference to the original item can cause an error message.</span></span>  

## <a name="verifying-data-after-migrating"></a><span data-ttu-id="339c0-200">Vérifier les données après avoir effectué une migration</span><span class="sxs-lookup"><span data-stu-id="339c0-200">Verifying Data After Migrating</span></span>
<span data-ttu-id="339c0-201">Si vous souhaitez vérifier que vos données ont été migrées correctement, vous pouvez consulter les pages suivantes dans C5 et [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="339c0-201">One way to verify that your data migrated correctly is to look at the following pages in C5 and [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>

|<span data-ttu-id="339c0-202">Microsoft Dynamics C5 2012</span><span class="sxs-lookup"><span data-stu-id="339c0-202">Microsoft Dynamcis C5 2012</span></span> | [!INCLUDE[d365fin](includes/d365fin_md.md)]| <span data-ttu-id="339c0-203">Traitement en lot à utiliser</span><span class="sxs-lookup"><span data-stu-id="339c0-203">Batch Job to Use</span></span> |
|-----|-----|-----|
|<span data-ttu-id="339c0-204">Écritures client</span><span class="sxs-lookup"><span data-stu-id="339c0-204">Customer Entries</span></span>| <span data-ttu-id="339c0-205">Journaux généraux</span><span class="sxs-lookup"><span data-stu-id="339c0-205">General Journals</span></span>| <span data-ttu-id="339c0-206">CUSTMIGR</span><span class="sxs-lookup"><span data-stu-id="339c0-206">CUSTMIGR</span></span> |
|<span data-ttu-id="339c0-207">Écritures fournisseur</span><span class="sxs-lookup"><span data-stu-id="339c0-207">Vendor Entries</span></span>| <span data-ttu-id="339c0-208">Journaux généraux</span><span class="sxs-lookup"><span data-stu-id="339c0-208">General Journals</span></span>| <span data-ttu-id="339c0-209">VENDMIGR</span><span class="sxs-lookup"><span data-stu-id="339c0-209">VENDMIGR</span></span>|
|<span data-ttu-id="339c0-210">Ecritures article</span><span class="sxs-lookup"><span data-stu-id="339c0-210">Item Entries</span></span>| <span data-ttu-id="339c0-211">Journaux d'articles</span><span class="sxs-lookup"><span data-stu-id="339c0-211">Item Journals</span></span>| <span data-ttu-id="339c0-212">ITEMMIGR</span><span class="sxs-lookup"><span data-stu-id="339c0-212">ITEMMIGR</span></span> |
|<span data-ttu-id="339c0-213">Écritures</span><span class="sxs-lookup"><span data-stu-id="339c0-213">G/L Entries</span></span>| <span data-ttu-id="339c0-214">Journaux généraux</span><span class="sxs-lookup"><span data-stu-id="339c0-214">General Journals</span></span>| <span data-ttu-id="339c0-215">GLACMIGR</span><span class="sxs-lookup"><span data-stu-id="339c0-215">GLACMIGR</span></span> |

## <a name="stopping-data-migration"></a><span data-ttu-id="339c0-216">Arrêter la migration des données</span><span class="sxs-lookup"><span data-stu-id="339c0-216">Stopping Data Migration</span></span>
<span data-ttu-id="339c0-217">Vous pouvez arrêter de migrer les données en sélectionnant **Arrêter toutes les migrations**.</span><span class="sxs-lookup"><span data-stu-id="339c0-217">You can stop migrating data by choosing **Stop All Migrations**.</span></span> <span data-ttu-id="339c0-218">Si vous le faites, toutes les migrations en attente sont également arrêtées.</span><span class="sxs-lookup"><span data-stu-id="339c0-218">If you do, all pending migrations are also stopped.</span></span>

## <a name="see-also"></a><span data-ttu-id="339c0-219">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="339c0-219">See Also</span></span>
<span data-ttu-id="339c0-220">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="339c0-220">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)</span></span>  
[<span data-ttu-id="339c0-221">Mise en route</span><span class="sxs-lookup"><span data-stu-id="339c0-221">Getting Started</span></span>](product-get-started.md) 
