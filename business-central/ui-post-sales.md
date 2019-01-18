---
title: Familiarisation avec le report des documents vente | Microsoft Docs
description: "En savoir plus sur les différentes fonctions de report pour reporter des documents vente."
services: project-madeira
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2018
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 7ada688f7946d7f857dc6d4a6518b8bcb4e5c707
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="posting-sales"></a>Report des ventes
Dans le groupe **Validation** sur un document vente, vous pouvez faire votre choix parmi les fonctions de validation suivantes :

* **Valider**
* **Impression test**
* **Valider et envoyer**
* **Valider et Imprimer**
* **Valider et envoyer par e-mail**
* **Valider par lot**
* **Aperçu compta.**

Lorsque vous avez renseigné toutes les lignes et entré toutes les informations du document de vente, vous pouvez le reporter. Cela crée une livraison et une facture.

Lorsqu’un document de vente est reporté, le compte du client, le grand livre et les écritures article sont mis à jour.

Pour chaque commande vente, une écriture vente est créée dans la table **Écriture comptable**. Une écriture est également créée dans le compte client de la table **Écriture comptable client** et une écriture comptable est créée dans le compte client approprié. De plus, le report de la commande peut avoir pour résultat la création d’une écriture TVA et d’une écriture pour le montant de l'escompte. Le report d’une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la page **Configuration des ventes et des comptes à recevoir**.

Pour chaque ligne commande vente, une écriture comptable article est créée dans la table **Écriture comptable article** (si les lignes vente contiennent des numéros des articles) ou une écriture comptable est créée dans la table **Écriture comptable** (si les lignes vente contiennent un compte général). En outre, les commandes vente sont toujours enregistrées dans les tables **En-tête expédition vente** et **En-tête facture vente**.

> [!IMPORTANT]  
>   Lorsque vous reportez une commande, vous pouvez créer une livraison et une facture. Ceci peut être effectué de manière simultanée ou indépendante. Vous pouvez également créer une expédition partielle et une facture partielle en renseignant les champs **Qté à expédier** et **Qté à facturer** sur chaque ligne commande vente avant la validation. Notez que vous ne pouvez pas créer de facture pour un article qui n'est pas livré. C'est-à-dire que, avant de pouvoir facturer, vous devez avoir reporté une livraison, ou vous devez choisir de livrer et de facturer en même temps.

Lorsque le report est terminé, les lignes vente reportées sont supprimées de la commande. Un message vous indique lorsque le report est terminé. Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent les écritures reportées, telles que **Écritures client**, **Écritures**, **Écritures article**, **Livraisons vente reportées** et **Factures vente reportées**.

## <a name="see-also"></a>Voir aussi
[Ventes](sales-manage-sales.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)


