---
title: "Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base | Microsoft Docs"
description: "Dans Finance and Operations, Business edition, les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt."
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 41a23df0e19bda1262dafbfaf89df7518b2b40b6
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="walkthrough-picking-and-shipping-in-basic-warehouse-configurations"></a>Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.  

|Méthode|Processus entrant|Zones|Prélèvements|Livraisons|Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](design-details-warehouse-setup.md))|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|X|||2|  
|B|Report du prélèvement et de la livraison à partir d'un document prélèvement inventaire||X||3|  
|C|Report du prélèvement et de la livraison à partir d'un document livraison entrepôt|||X|4/5/6|  
|J|Report du prélèvement à partir d'un document prélèvement entrepôt et report de la livraison à partir d'un document livraison entrepôt||X|X|4/5/6|  

Pour plus d'informations, reportez\-vous à [Détails de conception : flux de désenlogement](design-details-outbound-warehouse-flow.md).  

La procédure pas à pas suivante illustre la méthode B dans la table précédente.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
Pour les configurations d'entrepôt de base, lorsque votre emplacement est configuré pour exiger un traitement des prélèvements mais pas un traitement des livraisons, vous utilisez la fenêtre **Prélèvement inventaire** pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents sources sortants. Le document origine sortant peut être un document de vente, un retour achat, un transfert sortant ou un bon de production avec un besoin de composantes.  

Cette procédure pas à pas présente les tâches suivantes :  

-   Configuration d'un emplacement ARGENT pour les prélèvements inventaire.  
-   Créez un document de vente pour le client 10000 pour 30 haut-parleurs.  
-   Libération du document de vente pour la gestion entrepôt.  
-   Créez un prélèvement inventaire sur la base d'un document origine libéré.  
-   Enregistrement d'un mouvement entrepôt à partir de l'entrepôt et report simultané de la livraison vente pour le document de vente d'origine.  

## <a name="roles"></a>Rôles  
Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

-   Gestionnaire d'entrepôt  
-   Préparateur de commandes  
-   Magasinier  

## <a name="prerequisites"></a>Conditions préalables  
Pour exécuter ce processus pas à pas, vous devez :  

-   avoir CRONUS International Ltd. installé.  
-   Pour devenir magasinier dans un emplacement ARGENT, procédez comme suit :  

    1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
    2.  Choisissez le champ **ID utilisateur** et sélectionnez votre propre compte utilisateur dans la fenêtre **Utilisateurs**.  
    3.  Dans le champ **Code magasin**, entrez ARGENT.  
    4.  Sélectionnez le champ **Par défaut**.  

-   Rend l'article LS-81 disponible dans l'emplacement ARGENT en suivant cette procédure :  

    1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles article**, puis sélectionnez le lien connexe.  
    2.  Ouvrez le journal par défaut, puis créez deux lignes journal article avec les informations de date de travail suivantes (23 janvier).  

        |Type écriture|Numéro d'article|Code d'emplacement|Code de zone|Quantité|  
        |----------------|-----------------|-------------------|--------------|--------------|  
        |Positif (ajust.)|LS-81|ARGENTE|S-01-0001 **Remarque** : la zone par défaut de l'article dans CRONUS|2.0|  
        |Positif (ajust.)|LS-81|ARGENTE|S-01-0002|2.0|  

    3.  Choisissez l'action **Reporter**, puis cliquez sur le bouton **Oui**.  

## <a name="story"></a>Scénario  
Ellen, la gestionnaire d'entrepôt de CRONUS, configure l'entrepôt ARGENT pour le prélèvement de base dans lequel les magasiniers traitent les commandes sortantes individuellement. Susan, préparatrice de commandes, crée un document de vente pour 30 unités de l'article LS-81 à livrer au client 10000 depuis l'entrepôt ARGENT. Jean, le magasinier, doit s'assurer que la livraison est préparée et livrée au client. Jean gère toutes les tâches impliquées dans la fenêtre **Prélèvement inventaire**, qui pointe automatiquement vers les zones où LS-81 est stocké.  

## <a name="setting-up-the-location"></a>Configuration de l'emplacement  
La configuration de la fenêtre **Fiche magasin** définit les flux d'entrepôt de la société.  

### <a name="to-set-up-the-location"></a>Pour configurer l'emplacement  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.  
2.  Ouvrez la fiche emplacement ARGENT.  
3.  Activez la case à cocher **Prélèvement requis**.  

## <a name="creating-the-sales-order"></a>Création du document de vente  
Les commandes vente sont le type de document d'origine sortant le plus répandu.  

### <a name="to-create-the-sales-order"></a>Pour créer le document de vente  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Créez une document de vente pour le client 10000 à la date de travail (23 janvier) comportant la ligne document de vente suivante.  

    |Article|Code d'emplacement|Quantité|  
    |----------|-------------------|--------------|  
    |LS_81|ARGENTE|30|  

     Informez l'entrepôt que le document de vente est prêt pour la gestion entrepôt.  

4.  Sélectionnez l'action **Lancer**.  

    Jean procède au prélèvement et à la livraison des articles vendus.  

## <a name="picking-and-shipping-items"></a>Prélèvement et livraison d'articles  
Dans la fenêtre **Prélèvement stock**, vous pouvez gérer toutes les activités entrepôt sortantes pour un document d'origine spécifique, tel qu'une commande vente.  

### <a name="to-pick-and-ship-items"></a>Pour prélever et livrer des articles  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Prélèvements inventaire**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Sélectionnez le champ **Document origine**, puis sélectionnez **Commande vente**.  
4.  Sélectionnez le champ **N° origine**, sélectionnez la ligne correspondant à la vente au client 10000, puis cliquez sur le bouton **OK**.  

    Sinon, choisissez l'action **Extraire document origine**, puis sélectionnez le document de vente.  
5.  Choisissez l'action **Remplir automatiquement la quantité à traiter**.  

    Sinon, dans le champ **Qté à traiter**, saisissez respectivement 10 et 30 sur les deux lignes prélèvement stock.  
6.  Choisissez l'action **Reporter**, sélectionnez **Livrer**, puis cliquez sur le bouton **OK**.  

    Les 30 haut-parleurs sont à présent enregistrés comme prélevés depuis les zones S-01-0001 et S-01-0002, et une écriture article négative est créée pour refléter la livraison vente reportée.  

## <a name="see-also"></a>Voir aussi  
 [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md)   
 [Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
 [Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)   
 [Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [Prélever pour la fabrication et l'assemblage](warehouse-how-to-pick-for-production.md)   
 [Déplacer des articles ad hoc dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)   
 [Détails de conception : flux de désenlogement](design-details-outbound-warehouse-flow.md)   
 [Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

