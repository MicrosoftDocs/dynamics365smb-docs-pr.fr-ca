---
title: Calcul de la date des achats | Microsoft Docs
description: L'application calcule automatiquement la date à laquelle vous devez commander un article pour l'avoir en inventaire à une certaine date. Il s'agit de la date à laquelle des articles commandés à une date donnée devraient être disponibles pour le prélèvement.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: b65e082355623f422cfb03698f6413fdb04f0daf
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5780267"
---
# <a name="date-calculation-for-purchases"></a>Calcul de la date des achats

[!INCLUDE[prod_short](includes/prod_short.md)] calcule automatiquement la date à laquelle vous devez commander un article pour l'avoir en stock à une certaine date. Il s'agit de la date à laquelle des articles commandés à une date donnée devraient être disponibles pour le prélèvement.  

Si vous saisissez une date de réception souhaitée sur un en-tête de bon de commande, la date de commande calculée est la date à laquelle la commande doit être passée pour recevoir les articles à la date que vous avez demandée. Ensuite, la date à laquelle les articles peuvent être prélevés est calculée et saisie dans le champ **Date réception prévue**.  

Si vous n'indiquez aucune date réception demandée, le programme utilise la date commande de la ligne comme point de départ pour le calcul de la date à laquelle vous souhaitez recevoir les articles et la date disponibilité des articles pour leur prélèvement.  

## <a name="calculating-with-a-requested-receipt-date"></a>Calcul avec une date réception demandée

Si la ligne bon de commande indique une date réception demandée, le programme l'utilise comme point de départ pour les calculs suivants :  

- date réception demandée - délai réapprovisionnement = date commande  
- date réception demandée + délai enlogement + délai sécurité = date réception prévue  

Si vous indiquez une date réception demandée sur l'en-tête bon de commande, le programme la copie dans le champ correspondant sur toutes les lignes. Vous pouvez modifier ou supprimer cette date sur n'importe quelle ligne.  

> [!NOTE]
> Si votre processus est basé sur un calcul en amont, par exemple, si vous utilisez la date de réception demandée pour obtenir la date de commande, nous vous recommandons d’utiliser des formules de date ayant des durées fixes, telles que "5D" pendant cinq jours ou "1W" pour une semaine. Les formules de date sans durée fixe, telles que "CW" pour la semaine en cours ou CM pour le mois en cours, peuvent entraîner des calculs de date incorrects. Pour plus d'informations sur les formules de date, voir [Utilisation de dates civiles et des heures](ui-enter-date-ranges.md).

## <a name="calculating-without-a-requested-delivery-date"></a>Calcul sans date livraison demandée

Si vous indiquez une ligne bon de commande sans date livraison demandée, le champ **Date commande** sur la ligne est renseigné avec la date du champ **Date commande** sur l'en\-tête bon de commande. Il s'agit de la date que vous avez indiquée ou de la date de travail. Le programme calcule ensuite les dates suivantes pour la ligne bon de commande en utilisant comme point de départ la date commande.  

- date commande + délai réapprovisionnement = date livraison fourn. prévue  
- date livraison fourn. prévue + délai enlogement + délai sécurité = date réception prévue  

Si vous modifiez la date commande sur la ligne, par exemple lorsque des articles ne sont pas disponibles auprès de votre fournisseur avant une date ultérieure, le programme recalcule automatiquement les dates appropriées sur les lignes.  

Si vous modifiez la date commande sur l'en\-tête, celle\-ci est copiée dans le champ **Date commande** sur toutes les lignes et tous les champs date qui y sont liés sont recalculés.  

## <a name="default-values-for-lead-time-calculation"></a>Valeurs par défaut du délai de réapprovisionnement

[!INCLUDE[prod_short](includes/prod_short.md)] utilise la valeur du champ **Délai de réappro.** sur la ligne bon de commande pour calculer la commande et les dates réception prévues.  

Vous pouvez spécifier manuellement la valeur sur la ligne ou laisser le programme utiliser les valeurs définies sur la fiche fournisseur, la fiche article, la fiche unité de stock ou le catalogue fournisseur article.
Toutefois, la valeur du délai de réapprovisionnement sur la fiche fournisseur n'est utilisée que si un délai de réapprovisionnement n'est pas spécifié sur la fiche article, la fiche unité de stock ou le catalogue fournisseur article pour l'article. Il s'agit également de l'ordre de priorité de ces valeurs. Si elles sont toutes fournies, le délai de réapprovisionnement de la fiche fournisseur a la priorité la plus faible et le délai de réapprovisionnement du catalogue fournisseur article a la priorité la plus élevée.  

## <a name="see-also"></a>Voir aussi

[Calcul de la date des ventes](sales-date-calculation-for-sales.md)   
[Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]