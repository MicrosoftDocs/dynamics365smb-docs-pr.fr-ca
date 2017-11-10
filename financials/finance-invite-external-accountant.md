---
title: "Ajouter votre comptable externe à votre Financials | Microsoft Docs"
description: "Découvrez comment vous pouvez inviter votre comptable externe à votre Dynamics 365 for Financials."
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting
ms.date: 09/05/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: b7efbb724f322d371e9e1b725612cb4eb0b3ceb2
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="inviting-your-external-accountant-to-your-included365finincludesd365finmdmd"></a><span data-ttu-id="cc0b4-103">Invitation de votre comptable externe à votre [!INCLUDE[d365fin](includes/d365fin_md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0b4-103">Inviting Your External Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)]</span></span>
<span data-ttu-id="cc0b4-104">Si vous utilisez un comptable externe pour gérer votre comptabilité et vos états financiers, vous pouvez les inviter à votre [!INCLUDE[d365fin](includes/d365fin_md.md)] afin qu'ils puissent travailler vous et utiliser vos données fiscales.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-104">If you use an external accountant to manage your books and financial reporting, you can invite them to your [!INCLUDE[d365fin](includes/d365fin_md.md)] so they can work with you on your fiscal data.</span></span>

<span data-ttu-id="cc0b4-105">Une fois que votre comptable a accédé à votre [!INCLUDE[d365fin](includes/d365fin_md.md)], il peut utiliser le tableau de bord **Comptable** qui donne un accès facilité aux fenêtres les plus appropriées pour son travail.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-105">Once your accountant has gained access to your [!INCLUDE[d365fin](includes/d365fin_md.md)], they can use the **Accountant** Role Center that gives easy access to the most relevant windows for their work.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="cc0b4-106">Cette fonctionnalité nécessite que l'expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-106">This functionality requires that the experience is set to **Suite**.</span></span> <span data-ttu-id="cc0b4-107">Pour plus d'informations, voir [Personnalisation de votre expérience Financials](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b4-107">For more information, see [Customizing Your Financials Experience](ui-experiences.md).</span></span>  

## <a name="invite-your-accountant-to-your-included365finincludesd365finmdmd"></a><span data-ttu-id="cc0b4-108">Inviter votre comptable à votre [!INCLUDE[d365fin](includes/d365fin_md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0b4-108">Invite Your Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)]</span></span>
<span data-ttu-id="cc0b4-109">Dans la dernière version de [!INCLUDE[d365fin](includes/d365fin_md.md)], nous avons simplifié pour vous la façon d'inviter votre comptable externe.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-109">In the latest version of [!INCLUDE[d365fin](includes/d365fin_md.md)], we have made it easy for you to invite your external accountant.</span></span> <span data-ttu-id="cc0b4-110">Ouvrez simplement la fenêtre **Utilisateurs**, puis choisissez l'action **Inviter un comptable externe** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-110">Simply open the **Users** window, and then choose the **Invite External Accountant** action in the ribbon.</span></span> <span data-ttu-id="cc0b4-111">Un courriel est préparé pour vous afin de vous permettre d'ajouter le courriel professionnel de votre comptable et d'envoyer l'invitation.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-111">An email is made ready for you, just add your accountant's work email, and send the invitation.</span></span>  

![Inviter votre comptable](./media/finance-invite-accountant/invite-accountant.png)

> [!TIP]  
>  <span data-ttu-id="cc0b4-113">Pour cela, il faudrait que vous ayez configuré la messagerie SMTP.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-113">This requires that you have set up SMTP email.</span></span> <span data-ttu-id="cc0b4-114">Vous pouvez le faire manuellement ou demander à votre partenaire [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc0b4-114">You can do this yourself or ask your [!INCLUDE[d365fin](includes/d365fin_md.md)] partner.</span></span> <span data-ttu-id="cc0b4-115">En outre, vous devez être connecté à [!INCLUDE[d365fin](includes/d365fin_md.md)] en tant qu'administrateur utilisateur, pas en tant que chef d'entreprise ou autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-115">Also, you must be logged in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as a user administrator, not as the business owner or other users.</span></span>  

### <a name="separate-license"></a><span data-ttu-id="cc0b4-116">Séparer la licence</span><span class="sxs-lookup"><span data-stu-id="cc0b4-116">Separate License</span></span>
<span data-ttu-id="cc0b4-117">En arrière-plan, le comptable est ajouté à votre abonné Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-117">Behind the scenes, the accountant is added to your Active Directory tenant.</span></span> <span data-ttu-id="cc0b4-118">Votre administrateur peut vérifier que le comptable accepte l'invitation et que la licence correcte lui est attribuée.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-118">Your administrator can verify that the accountant accepts the invitation and is assigned the correct license.</span></span> <span data-ttu-id="cc0b4-119">Pour cela la procédure dépend du type de compte que vous avez utilisé pour lorsque vous vous êtes connecté à [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc0b4-119">The steps for doing this depends on the type of account that you used when you signed up for [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="cc0b4-120">Cette rubrique est basée sur l'utilisation d'un compte Office 365, qui utilise Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-120">This topic is based on the use of an Office 365 account, which uses Microsoft Azure Active Directory.</span></span>  

<span data-ttu-id="cc0b4-121">Si vous avez activé votre abonnement à [!INCLUDE[d365fin](includes/d365fin_md.md)] et que vous n'utilisez plus la société d'évaluation, vous avez un abonné Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-121">If you have activated your subscription of [!INCLUDE[d365fin](includes/d365fin_md.md)] and are no longer using the evaluation company, you have an Azure Active Directory tenant.</span></span> <span data-ttu-id="cc0b4-122">Votre administrateur ou partenaire [!INCLUDE[d365fin](includes/d365fin_md.md)] gère cet abonné dans le [Portail Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cc0b4-122">Your administrator or [!INCLUDE[d365fin](includes/d365fin_md.md)] partner manages this tenant in the [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="cc0b4-123">C'est là que de nouveaux utilisateurs sont ajoutés et que des licences sont affectées et supprimées.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-123">This is where new users are added and licenses are applied and removed.</span></span> <span data-ttu-id="cc0b4-124">Pour plus d'informations, voir [.Présentation du portail Microsoft Azure](https://docs.microsoft.com/en-us/azure/azure-portal-overview)</span><span class="sxs-lookup"><span data-stu-id="cc0b4-124">For more information, see the [Microsoft Azure portal overview](https://docs.microsoft.com/en-us/azure/azure-portal-overview).</span></span>  

<span data-ttu-id="cc0b4-125">L'un des types de licence de [!INCLUDE[d365fin](includes/d365fin_md.md)] est la licence *Comptable externe*.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-125">One of the license types for [!INCLUDE[d365fin](includes/d365fin_md.md)] is the *External Accountant* license.</span></span> <span data-ttu-id="cc0b4-126">Ce type de licence est prévu pour les utilisateurs comme les comptables externes.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-126">This license type is intended for use by users such as external accountants.</span></span> <span data-ttu-id="cc0b4-127">Cela signifie que vous ne devez pas acheter un poste supplémentaire dans votre Active Directory actuel ou utiliser l'un de vos comptes [!INCLUDE[d365fin](includes/d365fin_md.md)] utilisateur existants pour votre comptable externe.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-127">This means that you do not have to buy an extra seat in your current Active Directory or use one of your existing [!INCLUDE[d365fin](includes/d365fin_md.md)] user accounts on your external accountant.</span></span> <span data-ttu-id="cc0b4-128">Par exemple, si votre abonnement actuel à Office 365 inclut 10 utilisateurs pour [!INCLUDE[d365fin](includes/d365fin_md.md)], et que vous utilisez actuellement 10 licences *Utilisateur complet*, votre administrateur peut simplement ajouter votre comptable externe en tant qu'utilisateur invité dans le portail Azure et affecter à cet utilisateur la licence *Comptable externe* sans coût supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-128">For example, if your current Office 365 subscription includes 10 users for [!INCLUDE[d365fin](includes/d365fin_md.md)], and you are currently using 10 *Full User* licenses, your administrator can simply add your external accountant as a guest user in the Azure portal and assign this user the *External Accountant* license at no additional cost.</span></span> <span data-ttu-id="cc0b4-129">Cependant, vous ne pouvez avoir qu'un utilisateur avec la licence *Aide-comptable externe*.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-129">However, you can only have one user with the *External Accountant* license.</span></span> <span data-ttu-id="cc0b4-130">Si vous souhaitez ajouter des utilisateurs supplémentaires, vous devez mettre à jour votre abonnement à Office 365 en conséquence.</span><span class="sxs-lookup"><span data-stu-id="cc0b4-130">If you want to add more users, you must update your Office 365 subscription accordingly.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cc0b4-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc0b4-131">See Also</span></span>
[<span data-ttu-id="cc0b4-132">Finance</span><span class="sxs-lookup"><span data-stu-id="cc0b4-132">Finance</span></span>](finance.md)  
[<span data-ttu-id="cc0b4-133">Procédure : configurer l'adresse de courriel manuellement ou à l'aide de la configuration assistée</span><span class="sxs-lookup"><span data-stu-id="cc0b4-133">How to: Set Up Email Manually or Using the Assisted Setup</span></span>](madeira-how-setup-email.md)  
[<span data-ttu-id="cc0b4-134">Expériences de comptables dans Dynamics 365 for Financials</span><span class="sxs-lookup"><span data-stu-id="cc0b4-134">Accountant Experiences in Dynamics 365 for Financials</span></span>](finance-accounting.md)  
[<span data-ttu-id="cc0b4-135">Financials pour comptables sur Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc0b4-135">Financials for Accountants on Microsoft.com</span></span>](https://www.microsoft.com/en-us/dynamics365/financial-insights-for-accountants)  
