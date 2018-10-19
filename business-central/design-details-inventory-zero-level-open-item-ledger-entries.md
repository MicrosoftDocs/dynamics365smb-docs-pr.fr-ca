---
title: "écritures article ouvertes"
description: "Découvrez pourquoi le niveau d'inventaire est nul alors qu'il existe des écritures article ouvertes."
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: e114142be1708447931fb475074245b57564f6b3
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="design-details-known-item-application-issue"></a>Détails de conception : problème connu lié à l'affectation d'articles
Cet article traite du problème de niveau d'inventaire nul alors qu'il existe des écritures article ouvertes dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

L'article commence par répertorier les symptômes courants du problème, puis décrit les notions de base de l'affectation d'articles pour justifier les raisons décrites pour ce problème. À la fin de l'article, une solution de contournement est proposée pour résoudre ce problème.  

## <a name="symptoms-of-the-issue"></a>Symptômes du problème  
 Voici les symptômes courants du problème d'inventaire nul alors qu'il existe des écritures article ouvertes :  

-   Le message suivant s'affiche lorsque vous tentez de fermer une période d'inventaire : « L'inventaire ne peut pas être fermé en raison d'un inventaire négatif pour un ou plusieurs articles ».  

-   Il existe une situation d'écriture article où une écriture article sortante et son écriture article entrante associée sont ouvertes.  

     Consultez l'exemple suivant d'une écriture article.  

     |N° séquence |Date de report|Type écriture|Type document|N° document|Nombre d'articles|Code d'emplacement|Quantité|Coût indiqué (réel)|Quantité facturée|Quantité restante|Ouvert|  
     |---------|------------|----------|-------------|------------|--------|-------------|--------|------------------------|-----------------|------------------|----|  
     |333|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|-1|-10|-1|-1|Oui|  
     |334|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|1|10|1|1|Oui|  

## <a name="basics-of-item-application"></a>Notions de base de l'affectation d'articles  
 Une écriture d'affectation article est créée pour chaque transaction inventaire afin de lier le destinataire de coût à sa source de coût afin que le coût puisse être transféré en fonction du mode d'évaluation coût. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-application.md).  

-   Pour une écriture article entrante, l'écriture d'affectation article est créée lorsque l'écriture article est créée.  

-   Pour une écriture article sortante, l'écriture d'affectation article est créée lorsque l'écriture article est reportée, à condition qu'il existe une écriture article entrante ouverte avec une quantité disponible à laquelle elle peut être affectée. S'il n'existe aucune écriture article entrante ouverte à laquelle elle peut être affectée, l'écriture article sortante reste ouverte jusqu'à ce qu'une écriture article entrante à laquelle elle peut être affectée soit reportée.  

 Il existe deux types d'affectation d'articles :  

-   Affectation de quantité  

-   Coût appliqué  

### <a name="quantity-application"></a>Affectation de quantité  
 Les affectations de quantité sont effectuées pour toutes les transactions d'inventaire et sont créées automatiquement, ou manuellement dans des processus spécifiques. Lorsqu'elles sont effectuées manuellement, les affectations de quantité sont appelées affectations fixes.  

 Le schéma suivant montre la façon dont les affectations de quantité sont effectuées.  

![Flux de l'ajustement des coûts de l'achat à la vente](media/helene/TechArticleInventoryZero2.png "Flux de l'ajustement des coûts de l'achat à la vente")

 En outre, notez que l'écriture article 1 (Achat) est le fournisseur de l'article et la source de coût de l'écriture article affectée, c'est-à-dire l'écriture article 2 (Vente).  

> [!NOTE]  
>  Si l'écriture article sortante est évaluée par coût moyen, l'écriture article entrante affectée n'est pas l'unique source de coût. Elle joue simplement un rôle dans le calcul du coût moyen de la période.  

### <a name="cost-application"></a>Coût appliqué  
Les affectations de coût sont uniquement créées pour les transactions entrantes lorsque le champ **Écriture article à affecter** est renseigné pour réaliser une affectation fixe. Cela se produit généralement dans le cadre d'une note de crédit vente ou d'un scénario d'annulation de livraison. L'affectation de coût garantit que l'article retourne dans l'inventaire avec le même coût que lorsqu'il a été livré.  

Le schéma suivant montre la façon dont les affectations de coût sont effectuées.  

|N° séquence |Date de report|Type écriture|Type document|N° document|Nombre d'articles|Code d'emplacement|Quantité|Coût indiqué (réel)|Quantité facturée|Quantité restante|Ouvert|  
|---------|------------|----------|-------------|------------|--------|-------------|--------|------------------------|-----------------|------------------|----|  
|333|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|-1|-10|-1|-1|Oui|  
|334|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|1|10|1|1|Oui|  

 En outre, notez que l'écriture article entrante 3 (Retour vente) est un destinataire de coût pour l'écriture article sortante d'origine 2 (Vente).  

## <a name="illustration-of-a-basic-cost-flow"></a>Illustration d'un flux de coûts de base  
 Imaginez un flux de coûts complet où un article est reçu, livré et facturé, retourné avec une inversion du coût exacte et relivré.  

 Le schéma suivant illustre le flux de coûts.  

![Flux de l'ajustement des coûts de la vente au retour vente](media/helene/TechArticleInventoryZero4.png "Flux de l'ajustement des coûts de la vente au retour vente")

 En outre, notez que le coût est transféré vers l'écriture article 2 (Vente), puis vers l'écriture article 3 (Retour vente) et enfin vers l'écriture article 4 (Vente 2).  

## <a name="reasons-for-the-issue"></a>Raisons du problème  
 Les scénarios suivants peuvent être à l'origine d'un problème d'inventaire nul alors qu'il existe des écritures article ouvertes :  

-   Scénario 1 : une livraison et une facture sont reportées bien que l'article ne soit pas disponible. Le report est ensuite soumis à une inversion des coûts exacte avec une note de crédit vente.  

-   Scénario 2 : une livraison est reportée bien que l'article ne soit pas disponible. Le report est ensuite annulé avec la fonction Annuler livraison.  

 Le schéma suivant illustre la façon dont les affectations d'article sont effectuées dans les deux scénarios.  

![Le flux de l'ajustement des coûts va dans les deux directions](media/helene/TechArticleInventoryZero6.png "Le flux de l'ajustement des coûts va dans les deux directions")  

 En outre, notez qu'une affectation de coût est effectuée (représentée par les flèches bleues) pour garantir que l'écriture article 2 (Retour vente) a les mêmes coûts que l'écriture article qu'elle inverse, c'est-à-dire l'écriture article 1 (Vente 1). Toutefois, une affectation de quantité (représentée par les flèches rouges) n'est pas effectuée.  

 L'écriture article 2 (Retour vente) ne peut pas être un destinataire de coût de l'écriture article d'origine et en même temps un fournisseur d'articles et leur source de coûts. Par conséquent, l'écriture article d'origine 1 (Vente 1) reste ouverte jusqu'à ce qu'une source valide s'affiche.  

## <a name="identifying-the-issue"></a>Identification du problème  
 Pour déterminer si les écritures article ouvertes sont créées, procédez comme suit pour le scénario respectif :  

 Pour le scénario 1, identifiez le problème comme suit :  

-   Dans la fenêtre **Note de crédit vente reportée** ou **Réception de retour reportée**, recherchez le champ **Écriture article à affecter** pour voir si le champ est renseigné, et dans ce cas, à quelle écriture article le coût de la réception retour est affecté.  

 Pour le scénario 2, identifiez le problème de l'une des manières suivantes :  

-   Recherchez une écriture article sortante ouverte et une écriture article entrante avec le même numéro dans le champ **N° document**, et Oui dans le champ **Correction**. Consultez l'exemple suivant d'une écriture article.  

|N° séquence |Date de report|Type écriture|Type document|N° document|Nombre d'articles|Code d'emplacement|Quantité|Coût indiqué (réel)|Quantité facturée|Quantité restante|Ouvert|Correction|  
|---------|------------|----------|-------------|------------|--------|-------------|--------|------------------------|-----------------|------------------|----|---------|
|333|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|-1|-10|-1|-1|Oui|Non|  
|334|01/28/2018|Vente|Livraison de vente|102043|TEST|BLEU|1|10|1|1|Oui|**Oui**|  

-   Dans la fenêtre **Livraison vente reportée**, recherchez le champ **Écriture article à affecter** pour voir si le champ est renseigné, et dans ce cas, à quelle écriture article le coût de la réception retour est affecté.  

> [!NOTE]  
>  Les affectations de coût ne peuvent pas être identifiées dans la fenêtre **Écritures article affectées**, car cette fenêtre affiche uniquement les affectations de quantité.  

 Pour les deux scénarios, identifiez l'affectation de coût concernée comme suit :  

1.  Ouvrez la table **Écriture d'affectation article**.  

2.  Filtrez le champ **N° écriture article** à l'aide du numéro de l'écriture article (Retour vente).  

3.  Analysez l'écriture d'affectation article, en tenant compte de ce qui suit :  

     Si le champ **N° écriture article sortant** est renseigné pour une écriture comptable article entrante (quantité positive), cela signifie que l'écriture comptable article entrante est le destinataire de coût de l'écriture comptable article sortante.  

     Consultez l'exemple suivant d'une écriture d'affectation article.  

     |N° séquence |N° écriture article gr. livre|N° écriture article entrant|N° écriture article sortant|Quantité|Date de report|Coût appliqué|  
     |---------|---------------------|----------------------|-----------------------|--------|------------|----------------|  
     |299|334|334|333|1|01/28/2018|Oui|  
<!--![Why is inventory zero 8](media/helene/TechArticleInventoryZero8.png "Whyisinventoryzero\_8")  -->

 En outre, notez que le coût de l'écriture article entrante 334 est affecté à l'écriture article sortante 333.  

## <a name="workaround-for-the-issue"></a>Solution de contournement du problème  
 Dans la fenêtre **Journal article**, reportez les lignes suivantes pour l'article concerné :  

-   Un ajustement positif pour fermer l'écriture article sortante ouverte.  

-   Un ajustement négatif avec la même quantité.  

     Cet ajustement équilibre l'augmentation d'inventaire causée par l'ajustement positif et ferme l'écriture article entrante ouverte.  

 Par conséquent, l'inventaire devient nul et toutes les écritures article sont fermées.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : affectation article](design-details-item-application.md)   
[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)  

