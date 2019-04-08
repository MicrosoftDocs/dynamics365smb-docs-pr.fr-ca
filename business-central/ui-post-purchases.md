---
title: Familiarisation avec le report des documents achat | Microsoft Docs
description: En savoir plus sur les différentes fonctions de report pour reporter des documents achat.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2018
ms.author: solsen
ms.openlocfilehash: 5f3c709e6e2588fe7cf409e44291d331acc09432
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "812946"
---
# <a name="posting-purchases"></a>Report des achats
Dans le groupe **Validation** sur un document achat, vous pouvez faire votre choix parmi les fonctions de validation suivantes :

* **Valider**
* **Aperçu compta.**
* **Valider et Imprimer**
* **Impression test**
* **Valider par lot**

Lorsque vous avez renseigné toutes les lignes et saisi toutes les informations du bon de commande, vous pouvez le reporter, c'est-à-dire, créer une réception et une facture.

Lorsqu’un bon de commande est reporté, le compte du fournisseur, le grand livre et les écritures article sont mis à jour.

Pour chaque commande achat, une écriture achat est créée dans la table **Ecriture comptable**. Une écriture est également créée dans le compte fournisseur de la table **Ecriture fournisseur** et une autre dans le compte fournisseur approprié. De plus, le report de la commande peut avoir pour résultat la création d'une écriture TVA et d'une écriture pour le montant de l'escompte. Le report d'une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la table **Configuration des achats et des comptes à payer**.

Pour chaque ligne commande achat, une écriture comptable article est créée dans la table **Écriture comptable article** (si les lignes achat contiennent des numéros d'article) ou une écriture est créée dans la table **Écriture comptable** (si les lignes achat contiennent un compte général). En outre, les commandes achat sont toujours enregistrées dans les tables **En-tête réception achat** et **En-tête facture achat**.

Avant de commencer à reporter, vous pouvez effectuer une rapport de test qui contient toutes les informations du bon de commande et indique les erreurs afférentes. Pour imprimer l’état, sélectionnez **Validation**, puis **Impression test**.

> [!IMPORTANT]  
>   Lorsque vous reportez une commande, vous pouvez créer une réception et une facture. Celles-ci peuvent être faites simultanément ou séparément. Vous pouvez également créer une réception partielle et une facture partielle en renseignant les champs **Qté à recevoir** et **Qté à facturer** sur chaque ligne commande achat avant la validation. Remarquez que vous ne pouvez pas créer de facture pour un article qui n'a pas été reçu. C'est-à-dire que, avant de pouvoir facturer, vous devez avoir validé une réception, ou vous devez choisir de réceptionner et de facturer en même temps.

Vous pouvez soit reporter, soit reporter et imprimer. Si vous choisissez de reporter et d’imprimer, un rapport est imprimé lorsque la commande est reportée. Vous pouvez aussi choisir la fonction **Valider par lot**, qui vous permet de valider plusieurs commandes en même temps.

Lorsque le report est terminé, les lignes achat reportées sont supprimées de la commande. Un message vous indique lorsque le report est terminé. Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent les écritures reportées, comme les pages **Écritures fournisseur**, **Écritures**, **Écritures article**, **Réceptions achat** et **Factures achat reportées**.

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Valider des documents et des feuilles](ui-post-documents-journals.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

