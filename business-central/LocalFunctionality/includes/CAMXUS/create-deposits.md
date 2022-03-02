---
author: edupont04
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 75205f4c9fd94cd499b1f1c017a8bfc396465ae7
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8146017"
---
Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.  

La page **Dépôt** spécifie des informations sur les dépôts bancaires. Ces informations incluent le numéro de compte bancaire, le montant de dépôt total, les lignes dépôt, la date de report, la date de document, le code de département, le code de devise et les notes de dépôt. Vous pouvez utiliser cette page pour créer des dépôts, reporter des dépôts, imprimer des dépôts, afficher des commentaires sur les dépôts ou consulter un rapport qui indique le montant du dépôt à rapprocher.

Le rapport **Dépôt** affiche les dépôts clients et fournisseurs avec le montant du dépôt initial, le montant du dépôt qui reste ouvert et le montant affecté. Le rapport indique également le montant total des dépôts reportés à rapprocher.

Les lignes dépôt contiennent des informations sur les différents éléments faisant l'objet de dépôts, tels que les chèques des clients. Ces informations comprennent la date et le numéro du document, le type et le numéro du compte et le montant. Le total des montants sur les lignes doit s'additionner pour correspondre au montant total du dépôt inscrit dans l'en-tête du dépôt.

Après avoir renseigné les informations de dépôt et les lignes dépôt associées, vous devez les reporter afin de mettre à jour le grand livre bancaire, le grand livre général, le grand livre client et tout autre grand livre pertinent. Les dépôts reportés sont stockés pour référence ultérieure et peuvent être consultés sur la page **Dépôts reportés**.

## <a name="to-create-a-deposit"></a>Pour créer un dépôt  
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Dépôts**, puis sélectionnez le lien associé.  
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

5.  Éventuellement, choisissez l'action **Dimensions**, puis ajoutez les dimensions correspondantes sur la page **Écritures de l'ensemble de dimensions**.  
6. Sélectionnez l'action **Reporter**.  

    > [!NOTE]  
    >  Vous pouvez reporter un dépôt uniquement si le montant affiché dans le champ **Lignes de dépôt total** est égal au montant figurant dans le champ **Montant total de dépôt**.  

Ensuite, vous pouvez utiliser les rapports **Test des dépôts** et **Dépôt** pour rapprocher vos dépôts reportés avec vos notes de crédit et factures en attente.  
