---
title: "Comment paramétrer plusieurs taux d'intérêt"
description: "Vous pouvez calculer les intérêts avec plusieurs taux d'intérêts pour une période donnée. Le calcul des intérêts ressemble à tous les intérêts financiers, avec une variation uniquement du taux d'intérêt pour une période donnée."
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
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 3d4c111af62db5858b81b76f9f51a9093c01e5e6
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="set-up-multiple-interest-rates"></a>Paramétrer plusieurs taux d'intérêt
Plusieurs taux d'intérêt multiples sont utilisés pour différentes périodes pour les paiements retardés dans les transactions commerciales. Par exemple, un gouvernement définit l'intérêt maximum à prélever pour un consommateur. Ce taux d'intérêt peut être modifié deux fois par an le 1er janvier et le 1er juillet inclus. Le taux d'intérêt entre les sociétés (B2B) est accepté par les parties et il n'existe aucune limite à ce groupe de clients. Le taux annoncé est généralement quatre fois supérieur aux intérêts bancaires normaux.

Lorsque vous créez des modalités de frais financiers et des modalités de rappel, pour la pénalité de retard de paiement, vous pouvez spécifier plusieurs taux d'intérêt afin que les frais de pénalité soient calculés sur la base de plusieurs taux d'intérêt à différentes périodes. Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).

## <a name="to-set-up-multiple-interest-rates"></a>Pour paramétrer plusieurs taux d'intérêt  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modalités de frais financiers**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Modalités de frais financiers**, sélectionnez la modalité financière requise, puis sélectionnez l'action **Taux d'intérêt**.  
3.  Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  Cliquez sur le bouton **OK**.  
5.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modalités de rappel**, puis sélectionnez le lien associé.  
6.  Dans la fenêtre **Modalités de rappel**, sélectionnez la modalité de rappel, puis sélectionnez l'action **Niveaux**.  
7.  Dans la fenêtre **Niveaux rappel**, sélectionnez le champ **Calculer intérêts**.  

Lorsque vous émettez une note de frais financiers, la note affiche les frais financiers avec plusieurs taux d'intérêt pour une période spécifique. La note affiche également les informations contact du client, de la compagnie émettant la note, du montant supplémentaire, et du montant total. L'écriture ouverture sur la facture est affichée en gras. Les intérêts sont calculés avec plusieurs taux d'intérêt pour une période spécifique et sont imprimés après l'écriture ouverture de la facture.  

## <a name="see-also"></a>Voir aussi  
[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Configuration de Finance](finance-setup-finance.md)

