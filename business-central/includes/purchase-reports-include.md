---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: ae96e5a3fc1cc7f4b17e5ef208650248cbe0b3c2
ms.sourcegitcommit: 2c972dfc94d27245eaa99efcf638d030dedafb22
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/09/2022
ms.locfileid: "8104411"
---
Le tableau suivant décrit certains des principaux rapports dans les rapports d'achat.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Statistiques achat**|312|[!INCLUDE [reports-purchase-statistics](reports-purchase-statistics.md)]|
|**Fournisseur – Liste des 10 meilleurs**|311|Affiche des informations sur les achats aux fournisseurs pour une période déterminée. Vous pouvez choisir le nombre de fournisseurs inclus dans le rapport.<br>Les fournisseurs sont triés par montant, et vous pouvez choisir s’ils doivent être triés par montant d’achat ou par solde. Le rapport vous donne un bref aperçu des fournisseurs à qui vous achetez le plus et ceux à qui vous devez le plus d’argent.|
|**Catalogue article fournisseur** ou **Catalogue fournisseur/article**|320 ou 720|Affiche une liste des fournisseurs pour les articles sélectionnés ou des articles pour les fournisseurs sélectionnés. Pour chaque combinaison d’article et de fournisseur, l’état indique le coût unitaire direct, le délai de réapprovisionnement et la référence fournisseur.<br>Ce rapport n’est pas disponible aux États-Unis, au Canada et au Mexique. Utilisez plutôt le rapport **Catalogue Article/Fournisseur** (10164).|
|**Achats Fournisseur/Article**|313|Affiche la liste des écritures article de chaque fournisseur pendant la période choisie. Le rapport affiche des informations sur la quantité facturée, le montant et les escomptes possibles. Il peut être utilisé, par exemple, pour analyser les achats d’articles d’une compagnie et pour voir s’il existe une relation entre les escomptes et les achats d’articles.|
|**Liste coût de l'inventaire et liste de prix**|716|Affiche la liste d’informations sur les prix des articles sélectionnés ou des unités de stock : coût unitaire direct, dernier coût direct, prix unitaire, pourcentage de profit et profit.|
|**Plan de disponibilité de l'inventaire**|707|Si vous souhaitez avoir un aperçu d’articles/d'unités de stock spécifiques et de leur disponibilité. Ce rapport affichera des valeurs cumulées telles que les besoins bruts, les réceptions programmées et prévues, l'inventaire, etc. |
|**Achats fournisseur inventaire**|714|Affiche la liste des fournisseurs auxquels votre compagnie a acheté des articles pendant la période sélectionnée. Il indique la quantité facturée, le montant et l'escompte. Le rapport peut être utilisé pour analyser les achats d'article d'une compagnie.|
|**Bons de commande d'inventaire**|709|Affiche la liste des articles commandés chez les fournisseurs. Il indique aussi la date de réception prévue, la quantité et le montant des commandes en souffrance. Par exemple, utilisez le rapport pour visualiser le moment où les articles doivent être réceptionnés et si un rappel de commande en souffrance doit être émis.|
|**Disponibilité réservation achat**|409|Affiche la disponibilité des articles pour les livraisons effectuées à partir de documents achat, par exemple les retours. Vous déterminez si le rapport indique l'état de chaque document ou de chaque ligne achat. <br>Lorsque vous imprimez le rapport, vous pouvez également mettre à jour les quantités disponibles pour livraison dans le champ **Quantité à recevoir** des lignes achat. Sur les notes de crédit achat et les lignes bon de commande négatives, le champ **Quantité à recevoir** indique la quantité à livrer. Vous pouvez alors utiliser ce rapport pour déterminer les documents à livrer. **Remarque** : ce rapport n’est pas disponible pour les fonctionnalités d’entrepôt avancées.|
<!--|**Fournisseur - chronologie détaillée**|11006| Spécifique à DACH : rapport qui pourrait être utilisé par le chef d’équipe de votre département d’achat ainsi que par la comptabilité. Vous aurez ici un aperçu des factures fournisseurs impayées, y compris les dates d’échéance, les devises et les montants. La base est constituée des écritures fournisseur ouvertes.| -->

