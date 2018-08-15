---
title: Utilisation de Business Central avec Outlook | Microsoft Docs
description: "Ce service bénéficie d'une intégration complète à Office 365, ce qui vous permet de gérer tous vos interactions et courriels d'affaires avec les clients et les fournisseurs directement dans Outlook."
author: edupont04
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Office 365
ms.date: 03/16/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: 7013cfa615174953660aa291abd62fa327e6f3ab
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="using-business-central-as-your-business-inbox-in-outlook"></a><span data-ttu-id="e689c-103">Utilisation de Business Central en tant que boîte de réception professionnelle dans Outlook</span><span class="sxs-lookup"><span data-stu-id="e689c-103">Using Business Central as your Business Inbox in Outlook</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="e689c-104"> vous permet désormais de gérer les interactions commerciales avec vos clients et fournisseurs, directement dans Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-104"> introduces the ability to manage business interactions with your customers and vendors, directly in Microsoft Outlook.</span></span> <span data-ttu-id="e689c-105">Avec le complément Outlook de [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez afficher des informations financières associées à des clients et des fournisseurs, ainsi que créer et envoyer des documents financiers, comme des devis et des factures.</span><span class="sxs-lookup"><span data-stu-id="e689c-105">With the [!INCLUDE[d365fin](includes/d365fin_md.md)] Outlook add-ins, you can see financial data related to customers and vendors, as well as create and send financial documents, such as quotes and invoices.</span></span>  

## <a name="getting-the-add-in"></a><span data-ttu-id="e689c-106">Obtention du complément</span><span class="sxs-lookup"><span data-stu-id="e689c-106">Getting the Add-in</span></span>
<span data-ttu-id="e689c-107">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], l'une des étapes de la configuration assistée de mise en route s'effectue dans la fenêtre **Dirigez votre entreprise dans Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e689c-107">In [!INCLUDE[d365fin](includes/d365fin_md.md)], one of the steps in the Getting Started assisted setup is the **Run your business within Office 365** window.</span></span> <span data-ttu-id="e689c-108">Dans cette fenêtre, lorsque vous cliquez sur le bouton **Configurer dans Outlook**, vous devez spécifier votre nom utilisateur et mot de passe Office 365.</span><span class="sxs-lookup"><span data-stu-id="e689c-108">In that window, when you choose the **Set up in Outlook** button, you must specify your Office 365 user name and password.</span></span> <span data-ttu-id="e689c-109">Le complément [!INCLUDE[d365fin](includes/d365fin_md.md)] est alors automatiquement ajouté à votre Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-109">The [!INCLUDE[d365fin](includes/d365fin_md.md)] add-ins are then automatically added to your Outlook.</span></span>  

<span data-ttu-id="e689c-110">Ensuite, lorsque vous ouvrez Outlook, vous voyez un courriel dans Business Central Admin. Le nouveau complément est ajouté au ruban Outlook, et dans Outlook Web Access, il apparaît dans le ruban des compléments, situé juste au-dessus du corps du message.</span><span class="sxs-lookup"><span data-stu-id="e689c-110">Then, when you open Outlook, you will see an email message from Business Central Admin. The new add-in is added to the Outlook ribbon, and in Outlook Web Access, you can see it in the add-in ribbon, immediately above the body of the email message.</span></span> <span data-ttu-id="e689c-111">Le complément lui-même est mis à jour régulièrement, et vous êtes informé qu'une nouvelle version est prête dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-111">The add-in itself will be updated periodically, and you'll get notified that a new version is ready for you in Outlook.</span></span>  

<span data-ttu-id="e689c-112">Certaines compagnies utilisant Office 365 n'autorisent pas leurs utilisateurs à déployer des compléments. Ainsi vous devez vous assurer que vous disposez d'un abonnement Office 365 comprenant la messagerie et qui vous permet de déployer des compléments. Si vous souhaitez tout de même essayer le complément, vous pouvez [essayer gratuitement Office 365](https://products.office.com/try).</span><span class="sxs-lookup"><span data-stu-id="e689c-112">Some companies using Office 365 restrict users’ permissions to deploy add-ins. So you must make sure that you have an Office 365 subscription that includes email and allows you to deploy add-ins. If you want to try out the add-in anyway, you can [try Office 365 for free](https://products.office.com/try).</span></span>  

## <a name="using-the-contact-insights-add-in"></a><span data-ttu-id="e689c-113">Utilisation du complément Panorama des contacts</span><span class="sxs-lookup"><span data-stu-id="e689c-113">Using the Contact Insights Add-in</span></span>
<span data-ttu-id="e689c-114">Imaginons que vous receviez un courriel d'un client souhaitant obtenir un devis pour certains articles.</span><span class="sxs-lookup"><span data-stu-id="e689c-114">Let's say that you get an email from a customer that wants to get a quote on some items.</span></span> <span data-ttu-id="e689c-115">Directement dans Outlook, vous pouvez ouvrir le complément [!INCLUDE[d365fin](includes/d365fin_md.md)], qui identifie l'expéditeur comme un client, et ouvre la fiche client de sa compagnie.</span><span class="sxs-lookup"><span data-stu-id="e689c-115">Directly in Outlook, you can open the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-in, which recognizes the sender as a customer, and opens the customer card for his company.</span></span> <span data-ttu-id="e689c-116">À partir de ce tableau de bord, vous pouvez afficher des informations générales relatives au client, ainsi que rechercher davantage de détails sur des documents spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e689c-116">From this dashboard, you can see overview information for the customer, as well as drill down for more detail on specific documents.</span></span> <span data-ttu-id="e689c-117">Vous pouvez également effectuer des recherches approfondies dans l'historique des ventes du client.</span><span class="sxs-lookup"><span data-stu-id="e689c-117">You can also dig into the sales history for the customer.</span></span> <span data-ttu-id="e689c-118">S'il s'agit d'un nouveau client, vous pouvez le créer en tant que tel dans [!INCLUDE[d365fin](includes/d365fin_md.md)] sans quitter Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-118">If it's a new customer, you can create them as a new customer in [!INCLUDE[d365fin](includes/d365fin_md.md)] without leaving Outlook.</span></span>  

<span data-ttu-id="e689c-119">Dans le complément, vous pouvez créer un devis et l'envoyer à ce client sans quitter Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-119">In the add-in, you can create a sales quote and send it back to this customer without leaving Outlook.</span></span> <span data-ttu-id="e689c-120">Toutes les informations dont vous avez besoin pour envoyer le devis sont disponibles dans votre boîte de réception professionnelle dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-120">All of the information that you need to send the sales quote is available in your business inbox in Outlook.</span></span>  
<span data-ttu-id="e689c-121">Une fois les données saisies, vous pouvez reporter le devis.</span><span class="sxs-lookup"><span data-stu-id="e689c-121">Once you have the data entered, you can post the quote.</span></span> <span data-ttu-id="e689c-122">Vous pouvez ensuite l'envoyer par courriel.</span><span class="sxs-lookup"><span data-stu-id="e689c-122">You can then send it by email.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="e689c-123"> génère un fichier .PDF avec le devis et le joint au message électronique que vous rédigez dans le complément.</span><span class="sxs-lookup"><span data-stu-id="e689c-123"> generates a .PDF file with the sales quote and attaches it to the email message that you draft in the add-in.</span></span>  

<span data-ttu-id="e689c-124">De même, si vous recevez un courriel d'un fournisseur, vous pouvez utiliser le complément pour travailler avec les fournisseurs et les factures achat.</span><span class="sxs-lookup"><span data-stu-id="e689c-124">Similarly, if you get an email from a vendor, you can use the add-in to work with vendors and purchase invoices.</span></span>  

<span data-ttu-id="e689c-125">Il arrive parfois que vous souhaitiez visualiser davantage de champs que ceux qui s'affichent dans le complément, par exemple si vous souhaitez renseigner des lignes dans une facture.</span><span class="sxs-lookup"><span data-stu-id="e689c-125">Sometimes you want to see more fields than you can see in the add-in, such as when you want to fill in lines in an invoice.</span></span> <span data-ttu-id="e689c-126">Afin de vous bénéficier d'un espace de travail plus important, vous pouvez ouvrir le complément dans une fenêtre distincte.</span><span class="sxs-lookup"><span data-stu-id="e689c-126">To give you a bit more space to work with, you can pop out the add-in to a separate window.</span></span> <span data-ttu-id="e689c-127">Il s'agit toujours d'Outlook, mais vous disposez de davantage d'espace.</span><span class="sxs-lookup"><span data-stu-id="e689c-127">It's still part of Outlook, but you have more space.</span></span> <span data-ttu-id="e689c-128">Au fur et à mesure que vous saisissez des données pour le document dans l'affichage contextuel, les modifications sont automatiquement enregistrées.</span><span class="sxs-lookup"><span data-stu-id="e689c-128">As you enter data for the document in the pop-out view, the changes are automatically saved.</span></span> <span data-ttu-id="e689c-129">Lorsque vous avez terminé de saisir les données pour le document, vous pouvez cliquer sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="e689c-129">When you are done entering data for the document, you can choose the **OK** button.</span></span> <span data-ttu-id="e689c-130">Sélectionner le cadre du complément dans Outlook actualise automatiquement le document avec les modifications que vous avez effectuées dans l'affichage contextuel.</span><span class="sxs-lookup"><span data-stu-id="e689c-130">Choosing the add-in frame in Outlook automatically refreshes the document with the changes you made in the pop-out view.</span></span>  

## <a name="creating-invoices-from-your-meeting-appointments"></a><span data-ttu-id="e689c-131">Création de factures à partir de vos rendez-vous de réunion</span><span class="sxs-lookup"><span data-stu-id="e689c-131">Creating Invoices from Your Meeting Appointments</span></span>
<span data-ttu-id="e689c-132">Certaines sociétés enregistrent tous les rendez-vous facturables dans le calendrier Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-132">Some businesses record all billable appointments in the Outlook calendar.</span></span> <span data-ttu-id="e689c-133">Avec [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez créer la facture du client directement à partir de l'article calendrier : ouvrez le rendez-vous, puis vous pouvez ouvrir le complément [!INCLUDE[d365fin](includes/d365fin_md.md)], rechercher des informations existantes ou créer une facture ou un autre document vente directement ici.</span><span class="sxs-lookup"><span data-stu-id="e689c-133">With [!INCLUDE[d365fin](includes/d365fin_md.md)], you can create the invoice for the customer right from the calendar item: Open the appointment, and then you can open the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-in, look up existing information or create an invoice or another sales document right there.</span></span>  

## <a name="doing-quick-document-lookup"></a><span data-ttu-id="e689c-134">Recherche rapide de document</span><span class="sxs-lookup"><span data-stu-id="e689c-134">Doing Quick Document Lookup</span></span>
<span data-ttu-id="e689c-135">Le complément Liens de document de [!INCLUDE[d365fin](includes/d365fin_md.md)] vous permet d'accéder rapidement aux documents mentionnés dans les e-mails.</span><span class="sxs-lookup"><span data-stu-id="e689c-135">The [!INCLUDE[d365fin](includes/d365fin_md.md)] Document Links add-in gives you quick access to documents mentioned in email messages.</span></span> <span data-ttu-id="e689c-136">Le complément est disponible pour un courriel si un numéro de document est identifié dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="e689c-136">The add-in is available for an email message if a document number is recognized in the body of the message.</span></span> <span data-ttu-id="e689c-137">Ouvrir le complément vous permet d'accéder rapidement à ce document.</span><span class="sxs-lookup"><span data-stu-id="e689c-137">Opening the add-in provides quick access to the document.</span></span>  

<span data-ttu-id="e689c-138">Par exemple, si vous recevez un e-mail qui mentionne le texte *S-QUO100*, [!INCLUDE[d365fin](includes/d365fin_md.md)] l'identifie comme un devis et vous pouvez donc ouvrir ce document dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-138">For example, if you receive an email message that mentions the text *S-QUO100*, [!INCLUDE[d365fin](includes/d365fin_md.md)] identifies that as a sales quote, and so you can open this document in Outlook.</span></span> <span data-ttu-id="e689c-139">Dans Outlook, cliquez sur le bouton **Liens de document** situé juste au-dessus du corps du message.</span><span class="sxs-lookup"><span data-stu-id="e689c-139">In Outlook, choose the **Document Links** button immediately above the body of the email message.</span></span> <span data-ttu-id="e689c-140">Dans Outlook Web App, sélectionnez le texte *S-QUO1001* dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="e689c-140">In the Outlook Web App, choose the *S-QUO1001* text in the body of the email message.</span></span>  

<span data-ttu-id="e689c-141">Dans le complément Liens de document, vous pouvez modifier le document et effectuer des opérations sur celui-ci, comme dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e689c-141">In the Document Links add-in, you can modify and take actions with the document, just like you can in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>

## <a name="adding-the-add-ins-manually"></a><span data-ttu-id="e689c-142">Ajout de compléments manuellement</span><span class="sxs-lookup"><span data-stu-id="e689c-142">Adding the Add-ins Manually</span></span>
<span data-ttu-id="e689c-143">Dans certains cas, les compléments ne sont pas ajoutés automatiquement dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-143">In some cases, the add-ins do not get added automatically to Outlook.</span></span> <span data-ttu-id="e689c-144">Même si vous (ou l'un de vos collègues) avez exécuté le guide de configuration assistée pour le compte de la société, [!INCLUDE[d365fin](includes/d365fin_md.md)] ne s'affiche pas forcément dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-144">Even if you or a colleague ran the assisted setup guide on behalf of the company, [!INCLUDE[d365fin](includes/d365fin_md.md)] might not show up in Outlook.</span></span> <span data-ttu-id="e689c-145">Si vous rencontrez ce problème, vous pouvez ajouter le complément [!INCLUDE[d365fin](includes/d365fin_md.md)] manuellement.</span><span class="sxs-lookup"><span data-stu-id="e689c-145">If you experience this issue, you can add the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-ins manually.</span></span>  

<span data-ttu-id="e689c-146">Premièrement, vous devez vérifier que vous avez accès aux compléments dans votre compte Office 365.</span><span class="sxs-lookup"><span data-stu-id="e689c-146">First, you must verify that you have access to the add-ins in your Office 365 account.</span></span> <span data-ttu-id="e689c-147">Il vous suffit d'ouvrir Outlook Web Access dans un navigateur, puis d'ajouter `/owa/#path=/options/manageapps` à l'URL dans la barre d'adresse.</span><span class="sxs-lookup"><span data-stu-id="e689c-147">Quite simply open your Outlook Web Access in a browser, and then add `/owa/#path=/options/manageapps` to the URL in the address bar.</span></span> <span data-ttu-id="e689c-148">La page **Gérer les compléments** s'ouvre alors et vous pouvez activer [!INCLUDE[d365fin](includes/d365fin_md.md)] pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="e689c-148">This opens the **Manage add-ins** page, where you can enable [!INCLUDE[d365fin](includes/d365fin_md.md)] for your Outlook.</span></span> <span data-ttu-id="e689c-149">Ensuite, lorsque vous revenez dans Outlook, [!INCLUDE[d365fin](includes/d365fin_md.md)] devrait être disponible.</span><span class="sxs-lookup"><span data-stu-id="e689c-149">Then, when you navigate back to Outlook, [!INCLUDE[d365fin](includes/d365fin_md.md)] should be available.</span></span>  

<span data-ttu-id="e689c-150">De même dans le client de bureau Outlook, vous pouvez vérifier si [!INCLUDE[d365fin](includes/d365fin_md.md)] est répertorié dans la fenêtre **Gérer les compléments**.</span><span class="sxs-lookup"><span data-stu-id="e689c-150">Similarly in the Outlook desktop client, you can verify that [!INCLUDE[d365fin](includes/d365fin_md.md)] is listed in the **Manage Add-ins** window.</span></span>  

<span data-ttu-id="e689c-151">Dans les deux cas, si [!INCLUDE[d365fin](includes/d365fin_md.md)] n'est toujours pas disponible, vous devez vous procurer les fichiers de manifeste macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="e689c-151">In both cases, if [!INCLUDE[d365fin](includes/d365fin_md.md)] is still not available, you have to get the add-in manifest files.</span></span> <span data-ttu-id="e689c-152">Pour plus d'informations, contactez votre administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="e689c-152">For more information, please contact your Office 365 administrator.</span></span>

## <a name="see-also"></a><span data-ttu-id="e689c-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e689c-153">See Also</span></span>
[<span data-ttu-id="e689c-154">Mise en route</span><span class="sxs-lookup"><span data-stu-id="e689c-154">Getting Started</span></span>](product-get-started.md)  
[<span data-ttu-id="e689c-155">Finance</span><span class="sxs-lookup"><span data-stu-id="e689c-155">Finance</span></span>](finance.md)  
[<span data-ttu-id="e689c-156">Ventes</span><span class="sxs-lookup"><span data-stu-id="e689c-156">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="e689c-157">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="e689c-157">Purchasing</span></span>](purchasing-manage-purchasing.md)  
