---
title: Prédire les retards de paiement pour les documents de vente
description: Cet article explique comment utiliser notre modèle prédictif pour prédire si un client paiera une facture à temps.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'customer, payment, invoice, sales, invoice, quote'
ms.search.form: '1950, 1951,'
ms.date: 07/11/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="the-late-payment-prediction-extension"></a>Extension Prédiction de retard de paiement

Une gestion efficace des créances est importante pour la santé financière générale d'une société. Pour minimiser les créances ouvertes et ajuster votre stratégie de collectes, l’extension prédit si des retard de paiements sont à attendre. Par exemple, si un retard de paiement est prévu, vous pouvez décider d'ajuster les conditions de paiement ou le mode de règlement du client.

## <a name="get-started"></a>Mise en route

Lorsque vous ouvrez un document vente reporté, une notification s’affiche en haut de la page. Pour utiliser l’extension Prévision de retard de paiement, sélectionnez **Activer** dans la notification. Sinon, vous pouvez configurer l'extension manuellement. Par exemple, si vous regrettez d'ignorer la notification.

Pour activer manuellement l'extension, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration de prévision de paiement en retard**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

> [!NOTE]
> Si vous décidez d'activer l'extension manuellement, sachez que [!INCLUDE[prod_short](includes/prod_short.md)] ne vous permet pas de le faire si la qualité du modèle est faible. La qualité du modèle indique la probabilité de précision des prévisions du modèle. Plusieurs facteurs peuvent affecter la qualité d'un modèle. Par exemple, il n’y avait peut-être pas suffisamment de données ou les données n’avaient pas de variation suffisante. Vous pouvez afficher la qualité du modèle que vous utilisez actuellement sur la page **Configuration des prévisions de retard de paiement**. Vous pouvez également spécifier un seuil minimum pour la qualité du modèle.

## <a name="view-all-payment-predictions"></a>Afficher toutes les prévisions de paiement

Si vous activez l’extension, une vignette **Retards de paiements prévus** est disponible dans le tableau de bord **Gestionnaire d’activité**. La vignette affiche le nombre de retards de paiements prévus, et vous permet d’ouvrir la page **Écritures client** où vous pouvez examiner plus en détail les factures reportées. Il existe trois colonnes à examiner attentivement :  

* **Retard de paiement** - Indique si le paiement de la facture sera en retard.
* **Niveau de fiabilité de la prévision** - Indique la fiabilité de la prévision. **Elevée** signifie que la prévision est fiable à au moins 90 %, **Moyenne** est compris entre 80 % et 90 %, et **Faible** est inférieur à 80 %.
* **% du niveau de fiabilité de la prévision** - Affiche le pourcentage réel de du niveau de fiabilité. Par défaut, cette colonne est masquée, mais vous pouvez l’ajouter si vous le souhaitez. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

> [!TIP]
> La page Écritures client affiche un récapitulatif. Lorsque vous vérifiez les prévisions, les informations de la section **Détails client** peuvent être utile. Lorsque vous sélectionnez la facture dans la liste, la section affiche des informations sur le client. Elle vous permet également de prendre une mesure immédiate. Par exemple, si un client égare fréquemment son portefeuille, vous pouvez ouvrir la fiche client dans le récapitulatif et bloquer le client pour des ventes futures.  

## <a name="design-details"></a>Détails de conception

Microsoft déploie et exploite des services web prédictifs dans toutes les régions où [!INCLUDE[prod_short](includes/prod_short.md)] est disponible. L'accès à ces services web est inclus dans votre abonnement [!INCLUDE[prod_short](includes/prod_short.md)]. Pour en savoir plus, consultez le guide des licences Microsoft Dynamics 365 Business Central. Le guide est téléchargeable sur le site Internet [Business Central](https://dynamics.microsoft.com/business-central/overview/).

Les services web fonctionnent en trois modes :

* Former le modèle. Le service web forme le modèle sur la base de l'ensemble de données fourni.
* Évaluer le modèle. Le service web vérifie si le modèle renvoie des données fiables pour l'ensemble de données fourni.
* Prévoir. Le service web applique le modèle à l'ensemble de données fourni pour établir une prévision.

Ces services web sont sans état. Autrement dit, ils utilisent des données uniquement pour calculer des prévisions à la demande. Ils ne stockent pas de données.

> [!NOTE]  
> Vous pouvez utiliser votre propre service web prévisionnel au lieu du nôtre. Pour en savoir plus, consultez [Créer et utiliser votre propre service web prévisionnel pour des prévisions de retard de paiement](#AnchorText).

### <a name="data-required-to-train-and-evaluate-the-model"></a>Données nécessaires pour former et évaluer le modèle

Pour chaque **Écriture client** ayant une **Facture vente reportée** associée :

* Montant en devise locale, y compris la taxe
* Les modalités de paiement en jours sont calculées comme suit : **Date d’échéance** moins **Date de report**
* S’il existe une note de crédit affectée

En outre, l’enregistrement a agrégées les données provenant d’autres factures associées au même client.

- Nombre total et montants total des factures payées
- Nombre total et montants total des factures payées en retard
- Nombre total et montants total des factures en souffrance
- Nombre total et montants total des factures en souffrance déjà en retard
- Moyenne des retards en jours
- Ratio : nombre de factures payées en retard/payées
- Ratio : montant des factures payées en retard/payées
- Ratio : nombre de factures en retard en attente/en souffrance
- Ratio : montants des factures en souffrance en retard/en souffrance

> [!NOTE]
> Les informations sur le client ne sont pas incluses dans le jeu de données.

### <a name="standard-model-and-my-model"></a>Modèle standard et Mon modèle

Le modèle prédictif de l’extension Prévision de retard de paiement est formé à l’aide de données représentant un éventail de PME. Lorsque vous commencez à reporter des factures et à recevoir des paiements, [!INCLUDE[prod_short](includes/prod_short.md)] évalue si le modèle standard correspond à votre flux d’activité.

Si vos processus ne correspondent pas au modèle standard, vous pouvez utiliser l’extension, mais vous devez obtenir plus de données. Continuez simplement à utiliser [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> Nous utilisons une partie de votre temps de calcul chaque semaine lorsque nous évaluons et reformons le modèle.

[!INCLUDE[prod_short](includes/prod_short.md)] exécute automatiquement la formation et l’évaluation lorsqu’un nombre suffisant de factures payées et en retard sont disponibles. Cependant, vous pouvez l’exécuter manuellement quand vous le souhaitez.

#### <a name="to-train-and-use-your-model"></a>Pour former et utiliser votre modèle

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration de prévision de paiement en retard**, puis sélectionnez le lien associé.  
2. Dans le champ **Modèle sélectionné**, choisissez **Mon modèle**.
3. Choisissez l'action **Créer mon modèle** pour former le modèle sur vos données.  

## <a name="a-nameanchortext-acreate-and-use-your-own-predictive-web-service-for-late-payment-prediction"></a><a name="AnchorText"> </a>Créer et utiliser votre propre service web prévisionnel pour des prévisions de retard de paiement

Pour [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, le modèle est publié par Microsoft et connecté à l’abonnement Microsoft. Pour les autres options de déploiement, vous devez créer des ressources Machine Learning dans votre propre abonnement Azure. Vous pouvez trouver des exemples d’étapes dans l’[exemple de référentiel](https://github.com/microsoft/BCTech/tree/master/samples/MachineLearning). L’objectif de cette tâche est d’obtenir l’URI de l’API et la clé API.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration de prévision de paiement en retard**, puis sélectionnez le lien associé.  
2. Activez la case à cocher **Utiliser mon abonnement Azure**.
3. Dans l’onglet rapide  **Utiliser mon abonnement Azure**, saisissez l’URL de l’API et la clé API de votre modèle.  

## <a name="see-also"></a>Voir aussi .

[Personnaliser Business Central à l’aide d’extensions](ui-extensions.md)    
[Bienvenue à [!INCLUDE[prod_long](includes/prod_long.md)]](welcome.md)    
[Utiliser l’intelligence artificielle chez Microsoft Dynamics 365 Business Central](/training/paths/use-artificial-intelligence/)    
[Vue d’ensemble de l’API de prédiction](/dynamics365/business-central/dev-itpro/developer/ml-prediction-api-overview)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
