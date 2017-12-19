---
title: "Utiliser Invoicing et Dynamics 365 | Microsoft Docs"
description: "Solution de contournement pour accéder à Microsoft Invoicing lorsque vous vous êtes inscrit à Dynamics 365."
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 11/22/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: aa56764b5f3210229ad21eae6891fb201462209c
ms.openlocfilehash: db76c49d8f453b978e95d65afa14234cf9ccdffe
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="using-the-same-office-365-account-in-included365finincludesd365finmdmd-and-microsoft-invoicing"></a>Utilisation du même compte Office 365 dans [!INCLUDE[d365fin](includes/d365fin_md.md)] et Microsoft Invoicing
Lorsque vous êtes inscrit à une version d'évaluation avec [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez passer à une phase d'évaluation de 30 jours, démarrer un abonnement ou encore l'arrêter à l'aide de [!INCLUDE[d365fin](includes/d365fin_md.md)]. Dans tous les cas, si vous vous connectez au portail Office, vous verrez une vignette intitulée **Centre d'affaires** sur laquelle vous pouvez cliquer. Cela fait partie de l'abonnement Office 365 Business Premium, tous les utilisateurs ne verront donc pas cette vignette dans le portail Office.  

Si vous accédez au centre d'affaires, vous verrez une section intitulée **Invoicing**. Si vous accédez à cette section, vous verrez un message indiquant que vous ne pouvez pas accéder à Microsoft Invoicing car votre compte est utilisé dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Un message similaire s'affiche si vous installez l'application mobile pour Invoicing.  

## <a name="workaround"></a>Solution de contournement
Invoicing et [!INCLUDE[d365fin](includes/d365fin_md.md)] ont une plate-forme partagée. Cela signifie que vous êtes reconnu en tant qu'utilisateur existant de [!INCLUDE[d365fin](includes/d365fin_md.md)] lorsque vous cliquez sur Invoicing dans le centre d'affaires. En effet, Invoicing ne peut pas utiliser la même compagnie que [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Vous devrez donc vous connecter à [!INCLUDE[d365fin](includes/d365fin_md.md)] et renommer votre compagnie existante, puis créer une nouvelle compagnie que vous pourrez alors utiliser dans Invoicing. Aucune donnée n'est déplacée ou remplacée au cours de cette opération.

### <a name="to-rename-your-company"></a>Pour renommer votre compagnie
1.  Connectez-vous à [!INCLUDE[d365fin](includes/d365fin_md.md)].  
2.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Compagnies**, puis sélectionnez le lien associé.  
3.  Dans la fenêtre **Compagnies**, sélectionnez le bouton **Modifier la liste**.  
4.  Remplacez le nom de l'entrée *Ma compagnie* par un autre nom.  

    Patientez quelques minutes. Nous apporterons plusieurs modifications à la base de données sous-jacente, et cette opération prendra un certain temps.
5.  Lorsque le système est à nouveau prêt, sélectionnez le bouton **Créer une nouvelle compagnie**.  
6.  Dans la boîte de dialogue qui s'affiche, entrez *Ma compagnie* comme nom et sélectionnez l'option **Production Suite - Données de configuration uniquement**.  

Cette opération prend plusieurs minutes. Lorsque le processus est terminé, vous pouvez accéder à Invoicing dans le cadre de votre expérience Office 365 Business Premium.  

### <a name="what-about-my-data"></a>Qu'en est-il de mes données ?
Lorsque vous renommez la compagnie d'origine, les tables de la base de données qui stockent vos données [!INCLUDE[d365fin](includes/d365fin_md.md)] existantes sont renommées, mais les données proprement dites sont conservées.  

Si vous utilisez Invoicing et [!INCLUDE[d365fin](includes/d365fin_md.md)], les données sont stockées dans deux conteneurs différents (les deux compagnies). Aucun donnée n'est partagée, vous devrez donc gérer les clients et les articles dans les deux compagnies.  

## <a name="see-also"></a>Voir aussi
[Forum Aux Questions](across-faq.md)  
[Configuration et administration](admin-setup-and-administration.md)  

