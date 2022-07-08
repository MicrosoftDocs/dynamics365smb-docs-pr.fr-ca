---
title: Configurer les modalités de frais financiers
description: Découvrez comment configurer Business Central afin de pouvoir informer les clients des frais supplémentaires en envoyant des notes de frais financiers.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge
ms.search.form: 6, 494
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 565654d8f7a4dd38aceccbcc39e722bad89bf67e
ms.sourcegitcommit: 00a8acc82cdc90e0d0db9d1a4f98a908944fd50a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9077616"
---
# <a name="set-up-finance-charge-terms"></a>Configurer les modalités de frais financiers

Lorsqu'un client n'effectue pas son paiement à la date d'échéance, des frais financiers peuvent être calculés automatiquement et ajoutés aux montants échus sur le compte du client. Vous pouvez informer le client des frais ajoutés en lui envoyant une facture d'intérêts. Mais tout d’abord, vous devez configurer un code qui représente chaque calcul de frais financiers. Vous pouvez ensuite entrer ce code dans le champ Code condition intérêts des fiches client.  

## <a name="finance-charge-terms"></a>Modalités de frais financiers

Vous devez configurer des modalités de frais financiers pour chaque calcul de frais financiers, puis affecter les modalités au client dans le champ **Code modalités de frais financiers** sur la page **Client**.

Les intérêts de retard peuvent être calculés en utilisant les méthodes du solde journalier moyen ou celles du solde échu.

* Solde journalier moyen  
  
  Le ombre de jours pendant lequel le paiement est en retard est pris en compte :  
  *Méthode Solde journalier moyen* - *Frais financiers* = *Montant échu* x *(Jours échus/ Période d'intérêts)* x *(Taux d'intérêt/100)*

* Solde dû  
  
  Les frais financiers représentent un pourcentage du montant échu :  
  *Méthode du solde échu* - *Frais financiers* = *Montant échu* x *(Taux d'intérêt / 100)*

En outre, chaque modalité de la table Modalités de frais financiers est lié à une autre sous-table, la table Texte frais financiers. Pour chaque ensemble de modalités de frais financiers vous pouvez définir un texte début et/ou un texte fin à inclure dans la note de frais financiers.

### <a name="to-set-up-finance-charge-terms"></a>Pour configurer des modalités de frais financiers

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de frais financiers**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.
3. Pour utiliser plusieurs combinaisons de modalités de frais financiers, créez un code pour chacun d'eux.

    Pour chaque modalité de frais financiers, vous pouvez spécifier des conditions particulières, qui peuvent inclure des frais supplémentaires en $ et en devise étrangère. Vous pouvez définir des frais supplémentaires en devise étrangère pour chaque condition sur la page **Modalités de frais financiers**.
4. Sélectionnez l'action **Devises**.
5. Sur la page **Devises condition intérêts**, définissez pour chaque condition un code devise et des frais supplémentaires.

    > [!NOTE]  
    > Lorsque vous créez des frais financiers en devise, les conditions devise définies ici serviront à créer des notes de frais financiers. Si aucune modalités de frais financiers en devise étrangère n’est définie, les modalités de frais financiers en $ définies sur la page **Modalités de frais financiers** seront utilisées, puis converties dans la devise souhaitée.

    Pour chaque condition intérêts, vous pouvez spécifier le texte à imprimer avant (**Texte début**) ou après (**Texte fin**) les écritures de la facture d'intérêts.  
6. Choisissez les actions **Texte de début** ou **Texte de fin** respectivement, puis renseignez la page **Texte frais financiers**.
7. Pour insérer automatiquement des valeurs correspondantes dans le texte frais financiers résultant, entrez les espaces réservés suivants dans le champ **Texte**.

|Paramètre substituable|Valeur|  
|-----------------|-----------|  
|%1|Contenu du champ **Date du document** de l'en-tête de note de frais financiers|  
|%2|Contenu du champ **Date d'échéance** de l'en-tête de note de frais financiers|  
|%3|Contenu du champ **Taux d'intérêt** dans les modalités de frais financiers associées|  
|%4|Contenu du champ **Montant restant** de l'en-tête de note de frais financiers|  
|%5|Contenu du champ **Montant intérêts** de l'en-tête de note de frais financiers|  
|%6|Contenu du champ **Frais supplémentaires** de l'en-tête de note de frais financiers|  
|%7|Montant total du rappel|  
|%8|Contenu du champ **Code devise** de l'en-tête de note de frais financiers|  
|%9|Contenu du champ **Date comptabilisation** de l'en-tête de facture d'intérêts|  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/send-memos-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi .

[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Configurer les niveaux et modalités de rappel](finance-setup-reminders.md)  
[Configuration de Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]