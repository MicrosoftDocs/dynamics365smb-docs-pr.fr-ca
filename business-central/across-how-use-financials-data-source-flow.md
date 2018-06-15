---
title: "Connecter vos données avec Flow| Microsoft Docs"
description: "Vous pouvez publier vos données Financials sous forme de sources de données et spécifier l'URL OData de vos services Web pour générer un flux de travail automatisé."
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, Odata, Power App, SOAP
ms.date: 05/09/2018
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: a9299fc1b5478ec0592d69b34732822c2d2846e0
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---
# <a name="using-included365finincludesd365finmdmd-in-an-automated-workflow"></a>Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] dans un flux automatisé
Vous pouvez utiliser vos données [!INCLUDE[d365fin](includes/d365fin_md.md)] en tant que partie du flux de travail dans Microsoft Flow.  

> [!NOTE]  
>   Vous devez disposer d'un compte valide avec [!INCLUDE[d365fin](includes/d365fin_md.md)] et avec Flow.  

## <a name="to-add-included365finincludesd365finmdmd-as-a-data-source-in-flow"></a>Pour ajouter [!INCLUDE[d365fin](includes/d365fin_md.md)] comme source de données dans Flow
1. Dans votre navigateur, accédez à [flow.microsoft.com](https://flow.microsoft.com/en-us/), puis connectez-vous.
2. Choisissez **Mes flux** dans le ruban en haut de la page.
3. Il existe 2 façons de créer un flux ; **Créer à partir d'un modèle** et **Créer à partir de rien**. Un modèle est un flux prédéfini créé pour vous.  Pour utiliser un modèle, il suffit de le sélectionner et de créer une connexion pour chaque service qu'il utilise. Un modèle vide vous permet de créer un flux complètement nouveau.
4. Pour créer à partir de rien, dans la fenêtre **Mes flux**, cliquez sur l'option **Créer à partir de rien**.
5. Recherchez un connecteur **Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]**.
6. Dans la liste des déclencheurs disponibles, sélectionnez l'un des déclencheurs [!INCLUDE[d365fin](includes/d365fin_md.md)] disponibles :  
    *Lorsque l'approbation d'un client est exigée*,  
    *Lorsque l'approbation d'un lot journal général est exigée*,  
    *Lorsque l'approbation d'une ligne journal général est exigée*,  
    *Lorsque l'approbation d'un article est exigée*,  
    *Lorsque l'approbation d'un document achat est exigée*,  
    *Lorsque l'approbation d'un document vente est exigée*, ou  
    *Quand l'approbation d'un fournisseur est-elle exigée* ?
7. Flow vous invite à sélectionner une compagnie dans votre abonné [!INCLUDE[d365fin](includes/d365fin_md.md)], ainsi que les conditions que vous souhaitez surveiller dans vos données.

À ce stade, vous êtes connecté à vos données Business Central et vous êtes prêt à générer votre flux.

8. Pour créer à partir d'un modèle, choisissez l'option **Créer à partir d'un modèle**.
9. Recherchez des modèles **Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]**.
10. Sélectionnez l'un des modèles dans la liste des modèles disponibles :  
    *Demander l'approbation pour les documents de vente Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*,  
    *Demander l'approbation pour les devis vente [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les factures vente [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les notes de crédit vente Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*,  
    *Demander l'approbation pour les clients [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les bons de commande Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*,  
    *Demander l'approbation pour les factures achat [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les notes de crédit achat Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*,  
    *Demander l'approbation pour les articles [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les fournisseurs [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft*,  
    *Demander l'approbation pour les lots journal général Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*,  
    *Demander l'approbation pour les lignes journal général Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]*.  
11. Flow vous invite à sélectionner une compagnie dans votre abonné [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. Comme chaque étape du flux est indépendante de la suivante, vous devrez peut-être définir plusieurs fois la compagnie lorsque vous utilisez un modèle de Flux [!INCLUDE[d365fin_md](includes/d365fin_md.md)].

> [!NOTE]  
> Le modèle [!INCLUDE[d365fin_md](includes/d365fin_md.md)] Flow s'intègre avec le moteur de flux de travail principal dans [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. Cela signifie que chaque fois que vous utilisez l'un de ces modèles pour créer un flux, un flux correspondant est créé au sein de [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. Pour plus d'informations, voir [Flux de travail](across-workflow.md).

Pour plus d'informations, voir [Documentation Flow](https://docs.microsoft.com/en-us/flow/getting-started).

Pour résoudre les problèmes avec Microsoft Flow, voir [Dépannage pour l'intégration avec Microsoft Flow](across-troubleshooting-how-use-financials-data-source-flow.md).

## <a name="see-also"></a>Voir aussi
[Mise en route](product-get-started.md)  
[Flux de travail](across-workflow.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Gérer les utilisateurs et les autorisations](ui-how-users-permissions.md)   
[Gérer les flux de travail [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](across-use-workflows.md)  
[Configuration d'utilisateur d'approbation](across-how-to-set-up-approval-users.md)  
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  

