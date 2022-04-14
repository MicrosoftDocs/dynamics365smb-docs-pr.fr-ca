---
title: Configurer les niveaux et modalités de rappel
description: Découvrez comment configurer Business Central de telle sorte que vous puissiez envoyer un rappel à un client sur un paiement dû et ajouter des frais, ou des commissions au paiement en raison de retard.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.search.form: 431, 432, 436, 478
ms.date: 02/09/2022
ms.author: edupont
ms.openlocfilehash: 9456123c29b26c964acf974163ca31daa1e1b7c1
ms.sourcegitcommit: 8a12074b170a14d98ab7ffdad77d66aed64e5783
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523381"
---
# <a name="set-up-reminder-terms-and-levels"></a>Configurer les niveaux et modalités de rappel

Vous pouvez utiliser des relances pour rappeler aux clients les soldes échus. [!INCLUDE [reminder-terms](includes/reminder-terms.md)]

## <a name="reminder-terms"></a>Modalités de rappel

Si des clients ont des impayés, vous devez décider quand et comment leur envoyer un rappel. En outre, vous pouvez être amené à débiter leurs comptes d'intérêts ou de frais. Vous pouvez configurer autant de modalités de rappel que vous le souhaitez.  

> [!NOTE]
> Si vous souhaitez calculer les intérêts sur les paiements échus, vous pouvez le faire lorsque vous créez des rappels. Cependant, si vous souhaitez calculer les intérêts et en informer vos clients sans envoyer de rappels, utilisez les [notes de frais financiers](finance-setup-finance-charges.md). Pour plus d’informations, consultez [Rappels](receivables-collect-outstanding-balances.md#reminders) ou [Frais financiers](receivables-collect-outstanding-balances.md#finance-charges), respectivement.

### <a name="to-set-up-reminder-terms"></a>Pour configurer des modalités de rappel

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de rappel**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
3. Pour utiliser plusieurs combinaisons de modalités de rappel, créez un code pour chacun d'eux.

## <a name="reminder-levels"></a>Niveaux rappel

Vous pouvez définir un nombre illimité de niveaux rappel pour chaque code modalités de rappel. La première fois qu'un rappel est créé pour un client, la configuration utilisée est celle du niveau 1. Lorsque le rappel est émis, le numéro du niveau est enregistré dans les écritures rappel qui sont créées et associées à l'écriture client spécifique. S'il est nécessaire de rappeler le client, toutes les écritures rappel associées aux écritures client ouvertes sont vérifiées afin de localiser le numéro de niveau le plus élevé. Les conditions du niveau suivant seront alors utilisées pour le nouveau rappel.

Si vous créez plus de relances qu'il n'y a de niveaux relance, les conditions utilisées seront celles du niveau le plus élevé. Vous pouvez utiliser autant de relances que le champ **Nombre max. de relances** des conditions relance le permet.

### <a name="to-set-up-reminder-levels"></a>Pour configurer des niveaux rappel

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de rappel**, puis sélectionnez le lien associé.  
2. Sur la page **Modalités de rappel**, cliquez sur la ligne comportant les conditions pour lesquelles configurer des niveaux, puis cliquez sur l'action **Niveaux**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > Le paramétrage du champ **Calculer l’intérêt** détermine si l’intérêt apparaîtra sur le rappel lorsque le rappel est émis. Cependant, le champ **Reporter intérêts** sur la page **Modalités de rappel** détermine si les intérêts calculés doivent être reportés au GL et sur les comptes clients.
    >
    > Pour indiquer que les intérêts doivent être calculés, choisissez le champ **Calculer les intérêts**.

    En option, pour chaque niveau de rappel, spécifiez des frais supplémentaires en $ et en devise étrangère. Vous pouvez créer plusieurs frais supplémentaires en devise pour chaque code de la page **Niveaux rappel**.  

    Les frais supplémentaires peuvent être calculés de trois manières différentes qui sont définies par la valeur du champ **Type calcul frais supplémentaires**.  

    - **Statique**

        Les frais sont calculés en fonction des valeurs des champs **Frais supplémentaires** sur la ligne pour le niveau de rappel lui-même.  
    - **Dynamique unique**

        Les frais sont calculés en fonction des valeurs des champs **Configuration frais supplémentaires** sur les lignes pertinentes pour le niveau de rappel lui-même.
    - **Dynamique cumulé**

        Les frais sont calculés en fonction des valeurs des champs **Configuration frais supplémentaires** sur les lignes combinées pour le niveau de rappel lui-même.

4. Sélectionnez l'action **Devises**.
5. Sur la page **Devises niveau rappel**, définissez un code de niveau pour chaque rappel et le numéro du niveau de rappel correspondant, une devise et des frais supplémentaires.

    > [!NOTE]  
    > Lorsque vous créez une relance en devise, les conditions devise définies ici permettront de créer des relances. Si aucune condition rappel devise étrangère n'a été définie, les conditions devise $ configurées sur la page **Niveaux rappel** seront utilisées et converties dans la devise appropriée.

    Pour chaque niveau relance, vous pouvez indiquer le texte à imprimer avant (**Texte début**) ou après (**Texte fin**) les écritures de la relance.

6. Choisissez les actions **Texte de début** ou **Texte de fin** respectivement, puis renseignez la page **Texte rappel**.
7. Pour insérer automatiquement des valeurs correspondantes dans le texte de rappel résultant, entrez les espaces réservés suivants dans le champ **Texte**.  

    |Paramètre substituable|Valeur|  
    |-----------------|-----------|  
    |%1|Contenu du champ **Date du document** de l'en-tête de rappel|  
    |%2|Contenu du champ **Date d'échéance** de l'en-tête de rappel|  
    |%3|Contenu du champ **Taux d'intérêt** dans les modalités de frais financiers associées|  
    |%4|Contenu du champ **Montant ouvert** de l'en-tête de rappel|  
    |%5|Contenu du champ **Montant intérêts** de l'en-tête de rappel|  
    |%6|Contenu du champ **Frais supplémentaires** de l'en-tête de rappel|  
    |%7|Montant total du rappel|  
    |%8|Contenu du champ **Niveau rappel** de l'en-tête de rappel|  
    |%9|Contenu du champ **Code devise** de l'en-tête de rappel|  
    |%10|Contenu du champ **Date de report** de l'en-tête de rappel|  
    |%11|Nom de la compagnie|  
    |%12|Contenu du champ **Frais supplémentaires par ligne** de l'en-tête de rappel|  

    Par exemple, si vous saisissez **Vous devez %9 %7 dus au %2.**, le rappel résultant contiendra le texte suivant : Vous devez **1 200,50 USD dus au 02/02/2014.**.

    > [!NOTE]
    > La date d'échéance est calculée selon la formule de date que vous saisissez. Pour plus d’informations, voir [Utiliser des formules date](ui-enter-date-ranges.md#use-date-formulas).

Si vous avez configuré les modalités de rappel (avec des niveaux et du texte supplémentaires), saisissez l'un des codes sur chaque fiche client. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  

## <a name="see-also"></a>Voir aussi

[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Envoyer des rappels de soldes impayés](receivables-send-reminders.md)  
[Configurer les modalités de frais financiers](finance-setup-finance-charges.md)  
[Configuration de Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]