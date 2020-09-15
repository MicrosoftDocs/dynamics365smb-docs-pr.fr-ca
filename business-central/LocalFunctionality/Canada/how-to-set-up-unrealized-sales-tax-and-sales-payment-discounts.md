---
title: 'Procédure : configurer les escomptes de paiement de vente et la taxe de vente non réalisée | Microsoft Docs'
description: Vous pouvez utiliser la page Configuration du grand livre pour configurer la taxe de vente non réalisée. Vous pouvez également configurer des montants de taxe de correction maximum de manière à limiter les montants de correction de taxe qui sont entrés pour les ventes et les achats. Cela vous permet de remplacer la taxe calculée lorsqu'il existe des différences d'arrondissement entre ce qui est calculé sur le bon de commande et ce qui est calculé sur la facture achat du fournisseur.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: 639e8a287b8556cab05283476a7af9769d17fc10
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3778396"
---
# <a name="set-up-unrealized-sales-tax-and-sales-payment-discounts"></a>Configurer les escomptes de paiement de vente et la taxe de vente non réalisée
Vous pouvez utiliser la page **Configuration du grand livre** pour configurer la taxe de vente non réalisée. Vous pouvez également configurer des montants de taxe de correction maximum de manière à limiter les montants de correction de taxe qui sont entrés pour les ventes et les achats. Cela vous permet de remplacer la taxe calculée lorsqu'il existe des différences d'arrondissement entre ce qui est calculé sur le bon de commande et ce qui est calculé sur la facture achat du fournisseur.  

> [!NOTE]
> Si vous travaillez avec la taxe d'accise, le système ne vous autorise pas à modifier le champ **Montant taxe** sur la page **Statistiques** pour une facture, par exemple pour ajuster l'arrondissement. Par conséquent, si vous avez configuré une taxe d'accise avec plus de deux décimales et que vous constatez une différence d'arrondissement par rapport aux factures de votre fournisseur, vous devez alors traiter la différence d'arrondissement en reportant une écriture supplémentaire afin que le total corresponde au montant du document. Ce report pourrait être effectué sur un compte dépenses dédié à l'arrondissement des montants.

## <a name="to-set-up-unrealized-sales-tax"></a>Pour configurer la taxe de vente non réalisée  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du grand livre**, puis sélectionnez le lien associé.  
2.  Sur la page **Configuration du grand livre**, dans le raccourci **Général**, renseignez les champs comme décrit dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Escompte de paiement sans taxe**|Sélectionnez cette case pour calculer l'escompte de paiement sur les montants sans la taxe de vente.|  
    |**Ajust. pour esc. paiement**|Sélectionnez cette case pour recalculer les montants de taxe lorsque vous reportez des paiements qui entraînent des escomptes de paiement.<br /><br /> Ce champ est utilisé dans le contexte de la TVA, et non de la taxe de vente.|  
    |**Taxe non réalisée**|Sélectionnez cette case si l'une de vos juridictions de taxe de vente vous permet de payer votre taxe de vente après avoir été payé. Si vous n'activez pas cette case à cocher, cette fonction sera bloquée pour toutes les juridictions de taxe de vente.|  
3.  Choisissez le bouton **OK**.  

## <a name="to-set-up-unrealized-tax-for-jurisdictions"></a>Pour configurer la taxe non réalisée pour les juridictions  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Juridictions fiscales**, puis sélectionnez le lien associé.  
2.  Sur la page **Juridictions fiscales**, sélectionnez l'action **Modifier la liste**.  
3.  Renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type de taxe non réalisée**|<Blank> – La fonction de taxe non réalisée n'est pas utilisée pour cette juridiction fiscale.<br /><br /> –ou–<br /><br /> **Pourcentage** – Chaque paiement couvre à la fois les montants de taxe et les montants de facture proportionnellement au montant de la facture restant. Le montant de taxe payé est transféré du compte de taxe non réalisée vers le compte de taxe.<br /><br /> –ou–<br /><br /> **Premier** – Les paiements couvrent la taxe d'abord, puis le montant de la facture.<br /><br /> –ou–<br /><br /> **Dernier** – Les paiements couvrent le montant de la facture d'abord, puis le montant de la taxe. Dans ce cas, rien n'est transféré du compte de taxe non réalisée vers le compte de taxe jusqu'à ce que le montant total de la facture, hors taxe, soit payé.<br /><br /> –ou–<br /><br /> **Premier (Payé entièrement)** – Les paiements couvrent la taxe d'abord, mais rien n'est transféré vers le compte de taxe jusqu'à ce que le montant total de la taxe soit payé.<br /><br /> –ou–<br /><br /> **Dernier (Payé entièrement)** – Les paiements couvrent le montant de la facture d'abord, mais rien n'est transféré vers le compte de taxe jusqu'à ce que le montant total de la taxe soit payé. **Important :**  Ce champ est disponible sur la page **Juridiction fiscale**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Compte taxes non réal. (ventes)**|Le compte GL que vous souhaitez utiliser pour reporter la taxe non réalisée calculée sur les transactions de vente. **Important :**  Ce champ est disponible sur la page **Juridiction fiscale**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Compte taxes non réal. (achats)**|Le compte GL que vous souhaitez utiliser pour reporter la taxe non réalisée calculée sur les transactions d'achat. **Important :**  Ce champ est disponible sur la page **Juridiction fiscale**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Taxe déduct. prévue (achats)**|Le compte GL que vous souhaitez utiliser pour reporter les frais inversés taxe non réalisés calculés sur les transactions d'achat. **Important :**  Ce champ est disponible sur la page **Juridiction fiscale**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
4.  Cliquez sur le bouton **OK**.  

## <a name="to-set-up-adjustments-for-payment-discounts-in-a-tax-posting-group"></a>Pour configurer des ajustements pour les escomptes de paiement dans un groupe de report de taxe  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration de report de taxe**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Modifier**.  
3.  Sur la page **Fiche de configuration de report de taxe**, sélectionnez la case à cocher **Ajust. pour escompte paiement**.  

    > [!IMPORTANT]  
    >  Ce champ est disponible sur la page **Configuration report de taxe**, mais il n'est pas affiché par défaut.
4.  Choisissez le bouton **OK**.  

## <a name="to-set-up-maximum-tax-correction-amounts"></a>Pour configurer des montants de correction de taxe maximum  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.  
2.  Sur la page **Configuration des ventes & des comptes à recevoir**, sur le raccourci **Général**, cochez la case **Autoriser différence de taxe**.  
3.  Choisissez le bouton **OK**.  
4.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration achats et à payer**, puis sélectionnez le lien associé.  
5.  Sur la page **Configuration des achats & des comptes à payer**, sur le raccourci **Général**, cochez la case **Autoriser différence de taxe**.  
6.  Choisissez le bouton **OK**.  
7.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du grand livre**, puis sélectionnez le lien associé.  
8.  Sur la page **Configuration du grand livre**, dans le champ **Différence taxe max. autorisée**, entrez le montant de correction de taxe maximum autorisé pour la devise locale.  

    > [!NOTE]  
    >  Dans ce champ, si vous entrez USD 5, vous pouvez corriger les montants de taxe de cinq dollars maximum. Pour utiliser la fonction de différence de taxe, vous devez entrer un montant dans le champ **Différence taxe max. autorisée**.  
9. Cliquez sur le bouton **OK**.  

## <a name="see-also"></a>Voir aussi  
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Déclaration de la taxe de vente au Canada](ca-sales-tax.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance.md)
