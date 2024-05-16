---
title: Configurer des niveaux et modalités de rappel
description: Configurez Business Central afin de pouvoir envoyer des rappels sur les paiements dus et ajouter des frais ou des frais en raison du retard.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'payment due, debt, overdue, fee, charge, reminder'
ms.search.form: '431, 432, 436, 478'
ms.date: 03/12/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Configurer des niveaux et modalités de rappel

Vous pouvez utiliser des rappels pour informer les clients des montants échus et leur réclamer le paiement. [!INCLUDE [reminder-terms](includes/reminder-terms.md)]

> [!TIP]
> Après avoir configuré les modalités et les niveaux de rappel, vous pouvez les inclure dans les processus automatisés de création, d’émission et d’envoi de rappels. Pour en savoir plus sur le processus automatisé, accédez à [Automatiser les rappels dans les collections](finance-automate-reminders.md).

## Modalités de rappel

Si des clients ont des impayés, vous devez décider quand et comment leur envoyer un rappel. En outre, vous pouvez être amené à débiter leurs comptes d’intérêts ou de frais. Vous pouvez configurer autant de modalités de rappel que vous le souhaitez.  

> [!NOTE]
> Si vous souhaitez calculer les intérêts sur les paiements échus, vous pouvez le faire lorsque vous créez des rappels. Cependant, si vous souhaitez calculer les intérêts et en informer vos clients sans envoyer de rappel, utilisez une [note de frais financiers](finance-setup-finance-charges.md). Pour plus d’informations, consultez [Rappels](receivables-collect-outstanding-balances.md#reminders) ou [Frais financiers](receivables-collect-outstanding-balances.md#finance-charges).

### Configurer les textes des pièces jointes et du corps des courriels pour les communications

Sur la page **Configuration des modalités de rappel**, vous pouvez configurer les textes des pièces jointes et les courriels standard soit à utiliser pour tous les niveaux de rappel, soit créer des messages spécifiques pour chaque niveau. Par exemple, le message que vous envoyez pour le premier niveau de rappel peut avoir un ton ou un contenu différent de celui du deuxième ou du troisième. Pour créer des textes de pièces jointes et de courriels pour tous les niveaux, choisissez **Communication client** en haut de la page. Pour créer des messages pour des lignes spécifiques, sur l’onglet rapide **Niveau de rappel** , choisissez une ligne, puis choisissez la **Communication client** action sur le raccourci.

Par défaut, les textes des pièces jointes et des courriels utilisent votre paramètre de langue. Toutefois, si vous envoyez des rappels à des clients dans d’autres pays, vous souhaiterez peut-être communiquer dans différentes langues. Vous pouvez créer des textes pour chaque langue [!INCLUDE [prod_short](includes/prod_short.md)] prise en charge en utilisant l’action **Ajouter du texte pour la langue** . Si vous le faites, assurez-vous que les langues sont les mêmes pour les textes des pièces jointes et les textes des courriels. S’ils ne correspondent pas et que le terme de rappel comporte plusieurs niveaux, l’automatisation risque de ne pas être en mesure de personnaliser le message pour un ou plusieurs niveaux. Pour vérifier que les langues correspondent, utilisez l’action **Aperçu des communications** et comparez les communications pour les textes.

Lorsque vous envoyez un courriel, le rappel est un rapport que vous joignez au courriel. Vous définissez le rapport qui génère le rappel sur la page **Rappel de sélection de rapport/frais financiers**, où vous sélectionnez également le rapport contenant le texte du corps du courriel dans le champ **Nom de la présentation du corps du courriel**. Lorsque vous envoyez des courriels à vos clients, les textes du raccourci **Texte du courriel** sont insérés dans le rapport sélectionné dans le champ **Nom de la disposition du corps du courriel**. Le rapport standard comporte un champ de texte pour ce texte. Si vous le souhaitez, vous pouvez modifier ce rapport, par exemple pour ajouter ou supprimer du contenu. Modifiez la mise en page de ces rapports sur la page **Mise en page des rapports** . Pour en savoir plus sur les présentations de rapport, accédez à [Commencez à créer des présentations de rapport](ui-get-started-layouts.md).

> [!NOTE]
> Pour communiquer par courriel directement depuis [!INCLUDE [prod_short](includes/prod_short.md)] , vous devez être configuré pour le faire. Pour en savoir plus sur la connexion des comptes de courriel avec [!INCLUDE [prod_short](includes/prod_short.md)], consultez [Configurer courriel](admin-how-setup-email.md).

### Configurer des modalités de rappel

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de rappel**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
3. Pour utiliser plusieurs combinaisons de modalités de rappel, créez un code pour chacun d'eux.

## Niveaux rappel

Pour chaque terme de rappel, vous pouvez définir un nombre illimité de niveaux de rappel, même si la plupart des compagnies n’utilisent que deux ou trois niveaux. La première fois qu'un rappel est créé pour un client, la configuration utilisée est celle du niveau 1. Lorsque le rappel est émis, le numéro du niveau est enregistré dans les écritures rappel qui sont créées et associées à l'écriture client spécifique. S'il est nécessaire d'envoyer un nouveau rappel au client, toutes les écritures rappel associées aux écritures client ouvertes sont vérifiées afin de localiser le numéro du niveau le plus élevé. Les conditions du niveau suivant seront alors utilisées pour le nouveau rappel.

Si vous créez plus de rappels qu'il n'y a de niveaux définis pour ceux-ci, les conditions utilisées sont celles du niveau le plus élevé. Vous pouvez utiliser autant de relances que le champ **Nombre max. de relances** des conditions relance le permet.

### Pour configurer des niveaux rappel

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de rappel**, puis sélectionnez le lien associé.  
2. Sur la page **Modalités de rappel**, sélectionnez la ligne comportant les modalités pour lesquelles configurer des niveaux, puis choisissez l’action **Niveaux**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > Le paramétrage du champ **Calculer l’intérêt** détermine si l’intérêt apparaîtra sur le rappel lorsque le rappel est émis. Cependant, le champ **Reporter intérêts** sur la page **Modalités de rappel** détermine si les intérêts calculés doivent être reportés au GL et sur les comptes clients.
    >
    > Pour indiquer que les intérêts doivent être calculés, choisissez le champ **Calculer les intérêts**.

    En option, pour chaque niveau de rappel, spécifiez des frais supplémentaires en $ et en devise étrangère. Vous pouvez définir plusieurs frais supplémentaires en devise étrangère pour chaque code sur la page **Niveaux de rappel**.  

    Les frais supplémentaires peuvent être calculés de trois manières différentes qui sont définies par la valeur du champ **Type calcul frais supplémentaires**.  

    - **Statique**

        Les frais sont calculés en fonction des valeurs des champs **Frais supplémentaires** sur la ligne pour le niveau de rappel lui-même.  
    - **Dynamique unique**

        Les frais sont calculés en fonction des valeurs des champs **Configuration frais supplémentaires** sur les lignes pertinentes pour le niveau de rappel lui-même.
    - **Dynamique cumulé**

        Les frais sont calculés en fonction des valeurs des champs **Configuration frais supplémentaires** sur les lignes combinées pour le niveau de rappel lui-même.

4. Sélectionnez l'action **Devises**.
5. Sur la page **Devises des niveaux de rappel**, définissez pour chaque code de niveau de rappel et son numéro correspondant, un code de devise et des frais supplémentaires.

    > [!NOTE]  
    > Lorsque vous créez une relance en devise, les conditions devise définies ici permettront de créer des relances. Si aucune condition rappel devise étrangère n'a été définie, les conditions devise $ configurées sur la page **Niveaux rappel** seront utilisées et converties dans la devise appropriée.

    Pour chaque niveau relance, vous pouvez indiquer le texte à imprimer avant (**Texte début**) ou après (**Texte fin**) les écritures de la relance.

6. Choisissez les actions **Texte de début** ou **Texte de fin** respectivement, puis renseignez la page **Texte rappel**.
7. Pour insérer automatiquement des valeurs correspondantes dans le texte de rappel, vous pouvez entrer les espaces réservés suivants dans le champ **Texte**.  

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
    |%12|Contenu du champ **Frais supplémentaires par ligne** de l'en\-tête de relance|  

    Par exemple, si vous saisissez **Vous devez %9%7 dus le %2.**, le rappel contient le texte suivant : **Vous devez 1 200,50 USD dus le 02/02/2024.**.

    > [!NOTE]
    > [!INCLUDE [prod_short](includes/prod_short.md)] calcule la date d’échéance selon la formule de date que vous saisissez. Pour plus d’informations, voir [Utiliser des formules date](ui-enter-date-ranges.md#use-date-formulas).

8. Pour spécifier la langue d’un courriel, choisissez l’action **Ajouter du texte pour la langue**. Le champ **Code de langue** est mis à jour pour afficher votre sélection. Sur le raccourci **Texte du courriel** , saisissez le contenu du message dans la langue sélectionnée.

Après avoir configuré les modalités de rappel, vous pouvez les affecter aux clients sur les pages Fiche client. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  

## Voir aussi .

[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Envoyer des rappels de soldes impayés](receivables-send-reminders.md)  
[Configurer les modalités de frais financiers](finance-setup-finance-charges.md)  
[Configuration de Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
