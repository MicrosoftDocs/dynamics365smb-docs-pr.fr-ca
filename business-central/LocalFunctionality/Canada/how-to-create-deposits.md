---
title: "Procédure : créer des dépôts | Microsoft Docs"
description: "Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 0dbb40557cb1c5c6e09dbfd6489a13fb48f9e37f
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="create-deposits"></a>Créer des dépôts
Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.  

## <a name="to-create-a-deposit"></a>Pour créer un dépôt  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Dépôts**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Sous le raccourci **Général**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**N°**|Numéro d'identification unique du dépôt.|  
    |**N° de compte bancaire**|Numéro de compte bancaire pour le dépôt.|  
    |**Montant total de dépôt**|Montant total du dépôt reporté sur le grand livre bancaire.<br /><br /> Vous pouvez reporter ce dépôt uniquement si la somme des lignes dépôt est égale à la valeur de ce champ.|  
    |**Date de report**|Date de report du dépôt.|  
    |**Date du document**|Date du document du dépôt.|  
4.  Sous le raccourci **Lignes**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type compte**|Type de compte.|  
    |**N° compte**|Numéro de compte d'identification unique associé au type de compte sélectionné, sur lequel l'écriture sera reportée.|  
    |**Description**|Description de l'écriture ligne journal.|  
    |**Date du document**|Date de document de l'écriture ligne journal.|  
    |**Type document**|Type de document de l'écriture ligne journal.|  
    |**N° du document**|Numéro de document de l'écriture ligne journal.|  
    |**Montant crédit**|Montant total du crédit sur la ligne journal.|  

5.  Éventuellement, sous l'onglet **Naviguer**, choisissez **Dimensions**, puis ajoutez les dimensions correspondantes sur la page **Écritures de l'ensemble de dimensions**.  

Après avoir créé un dépôt, vous devez le reporter.  

## <a name="to-post-a-deposit"></a>Reporter un dépôt  
1. Sélectionnez l'action **Valider**.  

    > [!NOTE]  
    >  Vous pouvez reporter un dépôt uniquement si le montant affiché dans le champ **Lignes de dépôt total** est égal au montant figurant dans le champ **Montant total de dépôt**.  

Ensuite, vous pouvez utiliser le rapport Test des dépôts et les rapports Dépôt pour rapprocher vos dépôts reportés avec vos notes de crédit et factures en attente.  

## <a name="see-also"></a>Voir aussi  
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance.md)  

