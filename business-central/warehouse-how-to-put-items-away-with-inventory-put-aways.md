---
title: Comment ranger des articles avec le rangement stock | Microsoft Docs
description: Lorsque votre emplacement est configuré pour exiger un traitement des classements, mais qu'il ne l'est pas pour un traitement des réceptions, vous utilisez le document **Article dans l'inventaire à classer** pour enregistrer et reporter les informations de classement et de réception pour vos documents origine. Le document source entrant peut être un bon de commande, un retour vente, un ordre de transfert entrant ou un bon de production dont la production est prête à être rangée.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 439072c09555c7781632c5933ab563caf432c270
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3192853"
---
# <a name="put-items-away-with-inventory-put-aways"></a>Ranger des articles avec le rangement stock
Lorsque votre emplacement est configuré pour exiger un traitement des rangements, mais pas un traitement des réceptions, vous utilisez le document **Rangement inventaire** pour enregistrer et reporter les informations de rangement et de réception pour vos documents sources. Le document source entrant peut être un bon de commande, un retour vente, un ordre de transfert entrant ou un ordre d'assemblage/un bon de production dont la production est prête à être rangée.  

Vous pouvez créer un rangement inventaire de trois manières :  

- Créez le rangement en deux étapes en créant d'abord une demande entrepôt à partir du document origine, qui signale à l'entrepôt que le document origine est prêt pour rangement. Le rangement inventaire peut ensuite être créé à partir de la page **Rangement inventaire** sur la base du document origine.  
- Créez le rangement inventaire directement à partir du document source proprement dit.  
- Créez des rangements inventaire pour plusieurs documents sources simultanément en utilisant un traitement en lot.  

## <a name="to-request-an-inventory-put-away-by-releasing-the-source-document"></a>Pour demander un rangement inventaire en libérant le document d'source
Pour les bons de commande, les retours vente, les ordres de transfert entrants et les ordres d'assemblage, vous créez la demande entrepôt en libérant l'ordre. La section suivante décrit comment procéder à partir d'un bon de commande.  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.
2. Sélectionnez le bon de commande que vous voulez libérer, puis sélectionnez l'action **Libérer**.  

    Pour les bons de production, vous créez la demande entrepôt en créant une demande entrante à partir du bon de production libéré.  
3.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de production libérés**, puis sélectionnez le lien associé.  
4. Choisissez l'action **Créer demande d'enlogement**.  

> [!NOTE]  
>  Vous pouvez également créer la demande enlogement entrepôt en sélectionnant le champ **Créer demande d'enlogement** lors de l'actualisation de l'ordre de fabrication. Pour plus d'informations, voir [Actualiser ou replanifier des ordres de fabrication](production-how-to-replan-refresh-production-orders.md).  

Lorsque la demande entrepôt est créée, un employé d'entrepôt affecté aux rangements des articles peut voir que le document source est prêt et peut créer un document rangement inventaire.  

## <a name="to-create-an-inventory-put-away-based-on-the-source-document"></a>Pour créer un rangement inventaire sur la base du document source
Maintenant que la demande est créée, l'employé d'entrepôt peut créer un nouveau rangement inventaire sur la base du document source libéré.   
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rangement inventaire**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Document origine**, sélectionnez le type de document origine que vous rangez.  
4. Dans le champ **N° origine**, sélectionnez le document origine.  
5. Sinon, choisissez l'action **Extraire document source** pour sélectionner le document à partir de la liste des documents sources entrants prêts pour le rangement dans l'emplacement.  
6. Choisissez le bouton **OK** pour renseigner les lignes rangement en fonction du document origine sélectionné.  

## <a name="to-create-an-inventory-put-away-from-the-source-document"></a>Pour créer un rangement inventaire à partir du document source  
1.  Dans le document source, qui peut être un bon de commande, un retour vente, un ordre de transfert entrant ou un bon de production, choisissez l'action **Créer prélèvement/rangement inventaire**.  
2. Cochez la case **Créer rangement inventaire**.
3. Cliquez sur le bouton **OK**. Un nouveau rangement inventaire est créé.

## <a name="to-create-multiple-inventory-put-aways-with-a-batch-job"></a>Pour créer plusieurs rangements inventaire avec un traitement en lot  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Créer prélèv./rangement inventaire**, puis sélectionnez le lien associé.  
2.  Sur le raccourci **Demande entrepôt** de la page demande, utilisez les champs **Document origine** et **N° origine** pour opérer un filtrage sur certains types de documents ou des plages de numéros de document.  
3.  Sur le raccourci **Options**, cochez la case **Créer rangement inventaire**.
4.  Cliquez sur le bouton **OK**. Les rangements stock spécifiés sont créés.

## <a name="to-record-the-inventory-put-away"></a>Pour enregistrer les rangements inventaire  
1. Ouvrez un document rangement déjà créé en en sélectionnant un sur la page **Rangements stock**.  
2. Dans le champ **Code de zone** sur les lignes rangement, la zone où les articles doivent être rangés est proposée sur la base d'une zone par défaut de l'article. Vous pouvez modifier la zone sur cette page, si nécessaire.  
3. Exécutez le rangement et saisissez les informations pour la quantité effectivement rangée dans le champ **Quantité à traiter**.

    S'il s'avère nécessaire de placer les articles d'une ligne dans plusieurs zones, notamment parce que la zone désignée est pleine, alors utilisez la fonction **Éclater ligne** sur le raccourci **Lignes**. Pour plus d'informations sur l'éclatement des lignes, voir [Répartir des lignes activité entrepôt](warehouse-how-to-split-warehouse-activity-lines.md).  
4. Une fois le rangement exécuté, choisissez l'action **Reporter**.  

Le processus de report reporte la réception, ou la production pour les bons de production, des lignes document origine qui ont été rangées et, si l'emplacement utilise des zones, le report crée également des écritures entrepôt pour reporter les modifications apportées aux quantités zone.

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
