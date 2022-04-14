---
title: Transfert de fonds à la banque
description: Vous pouvez transférer des montants d'un compte bancaire à un autre, y compris dans différentes devises, en reportant la transaction dans le journal général.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account transfer, multiple currencies
ms.search.form: 39
ms.date: 04/29/2021
ms.author: edupont
ms.openlocfilehash: 632f802678de33e7c00fa95dab38530a1364ff3b
ms.sourcegitcommit: 8a12074b170a14d98ab7ffdad77d66aed64e5783
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2022
ms.locfileid: "8511737"
---
# <a name="transfer-bank-funds"></a>Transfert de fonds à la banque

Il peut vous arriver de devoir transférer un montant d'un compte bancaire dans [!INCLUDE[prod_short](includes/prod_short.md)] vers un autre. Pour ce faire, vous devez reporter la transaction sur la page **Journal général**. La tâche varie selon que les comptes bancaires utilisent la même devise ou des devises différentes.

## <a name="to-post-a-transfer-between-bank-accounts-with-the-same-currency-code"></a>Pour reporter un transfert entre comptes bancaires avec le même code devise

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général**, puis choisissez le lien associé.
2. Dans une ligne journal, renseignez les champs **Date de report** et **N° document** .
3. Cliquez sur le champ **Type compte**, sélectionnez le **Compte bancaire**.
4. Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.
5. Dans le champ **Montant**, entrez le total à transférer.

    Ensuite, vous devez spécifier le compte de contrepartie. Si vous ne visualisez pas les champs appropriés, choisissez l′action **Afficher plus de colonnes** pour afficher tous les champs disponibles.
6. Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.
7. Dans le champ **N° compte contrepartie**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.
8. Reportez le journal.

## <a name="to-post-a-transfer-between-bank-accounts-with-different-currency-codes"></a>Pour reporter des transferts entre comptes bancaires dotés de codes devise différents

Pour transférer des fonds entre des comptes bancaires qui utilisent des devises différentes, vous devez reporter deux lignes journal général.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général**, puis choisissez le lien associé.
2. Créez deux lignes journal, et renseignez les champs **Date de report** et **N° document**.
3. Sur la première ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.
4. Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.
5. Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire avec ou sans signe moins.

    > [!TIP]
    > Un montant sans signe est un débit et un montant avec un signe moins est un crédit.

    > [!NOTE]
    > Certaines compagnies préfèrent effectuer des transferts entre comptes sur des lignes journal distinctes. D′autres compagnies préfèrent tout reporter sur une seule ligne journal en utilisant un compte de contrepartie. Consultez votre expert local si vous ne savez pas quoi faire.
    >
    > Si votre compagnie préfère utiliser un compte de contrepartie, définissez le champ **Type compte de contrepartie** sur **Compte bancaire** et définissez le champ **N° compte de contrepartie** sur le compte bancaire sur lequel vous souhaitez transférer les fonds. Passez ensuite à l′étape 9 ou 10.
    >
    > Si votre compagnie préfère utiliser une ligne journal distincte, passez à l′étape suivante.
6. Sur la seconde ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.
7. Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.
8. Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire avec ou sans signe moins.

    > [!TIP]
    > Un montant sans signe est un débit et un montant avec un signe moins est un crédit.
9. Si les taux de change utilisés dans le journal sont différents des taux de change de la page **Taux de change devise**, saisissez une nouvelle ligne journal pour les pertes ou les gains sur taux de change.  

    1. Entrez **Compte général** dans le champ **Type compte**.  

    2. Entrez le numéro de compte du grand livre pour les gains ou les pertes liés au taux de change dans le champ **N° compte**.  

    3. Saisissez le gain ou la perte sur taux de change dans le champ **Montant** avec ou sans signe moins.

    > [!TIP]
    > Un montant sans signe est un débit et un montant avec un signe moins est un crédit.
10. Reportez le journal.

## <a name="see-also"></a>Voir aussi

[Rapprochement de comptes bancaires](bank-manage-bank-accounts.md)  
[Paramétrage des opérations bancaires](bank-setup-banking.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]