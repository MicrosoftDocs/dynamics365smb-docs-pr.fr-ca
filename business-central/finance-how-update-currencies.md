---
title: Mettre à jour les taux de change (contient une vidéo)
description: Découvrez comment utiliser Business Central pour ajuster les taux de change pour les montants dans différentes devises.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.keywords: 'multiple currencies, adjust exchange rates, FX rates'
ms.search.form: '5, 118'
ms.date: 11/13/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Mise à jour des taux de change devise

Si vous négociez dans différentes devises, vous devez suivre les variations des taux de change. [!INCLUDE [prod_short](includes/prod_short.md)] vous aide à gérer et mettre à jour les taux de change manuellement ou automatiquement et configurer un service de taux de change de devise.

## Devises

> [!TIP]  
> Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous trouverez des informations en temps réel sur les taux de devise étrangère (FX) ou les taux historiques, sous le terme Devise. Pour plus d'informations, voir [Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md).

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Spécifiez les codes devise dans la liste **Devises**, y compris les informations supplémentaires et les paramètres nécessaires pour chaque code devise. Pour plus d’informations, voir [Devises](finance-set-up-currencies.md#curr)

### Exemple de transaction en devise comptabilité

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Taux de change

Les taux de change permettent de calculer la valeur en devise locale ($) de chaque transaction en devise. La page **Taux d’échange** comprend les champs suivants :

|Champ|Désignation|  
|---------------------------------|---------------------------------------|  
|**Date début**|Date à laquelle le taux de change a été effectué.|  
|**code dev.**|Code devise lié à ce taux de change.|  
|**Code devise liée**|Si cette devise fait partie d’un calcul de devise triangulaire, configurez le code devise associé ici.|  
|**Montant du taux de change**|Le montant du taux de change est le taux pour le code devise sélectionné sur la ligne. Il s’agit normalement de 1 ou 100.|  
|**Montant taux de change lié**|Le montant du taux de change lié concerne le taux à utiliser pour le code devise liée.|  
|**Montant taux de change ajust.**|Le taux pour le code devise sélectionné sur la ligne à utiliser pour le traitement en lot **Ajuster taux de change**.|  
|**Montant taux change lié ajust.**|Le taux pour le code devise sélectionné sur la ligne à utiliser pour le traitement en lot **Ajuster taux de change**.|  
|**Fixer montant taux de change**|Spécifie si le taux de change de la devise peut être modifié sur les factures et les lignes journal.|  

En général, les valeurs des champs **Montant taux de change** et **Montant taux de change lié** sont utilisées comme taux de change par défaut sur tous les nouveaux documents client et fournisseur créés à l’avenir. Le taux de change est affecté au document en fonction de la date de travail actuelle.  

> [!Note]
> Le taux de change réel est calculé à l’aide de cette formule :
>
> `Currency Amount = Amount / Exchange Rate Amount * Relational Exch. Rate Amount`

Le montant du taux de change de l’ajustement ou le montant du taux de change de l’ajustement relationnel est utilisé pour mettre à jour toutes les transactions banque, client ou fournisseur ouvertes.  

> [!Note]
> Le taux de change réel est calculé à l’aide de cette formule :
>
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## Ajustement des taux de change

Comme les taux de change ne cessent de fluctuer, ajustez régulièrement d’autres équivalents de devise. Si vous ne le faites pas, les montants que vous avez convertis à partir de devises étrangères (ou autres) et reportés dans le grand livre en devise locale peuvent être incorrects. De plus, vous devez mettre à jour les écritures quotidiennes reportées avant de saisir un taux de change quotidien.

Vous pouvez utiliser le traitement en lot **Ajuster taux de change** pour ajuster manuellement les taux de change pour les écritures client, fournisseur et compte bancaire reportées. Le traitement en lot peut également mettre à jour d’autres montants en devise de report dans les écritures GL.  

> [!TIP]
> Vous pouvez utiliser un service pour mettre à jour automatiquement les taux de change dans le système. Pour plus d'informations, reportez vous à [Configurer un service de taux de change des devises](finance-how-update-currencies.md#set-up-a-currency-exchange-rate-service). Cependant, cela n’ajuste pas les taux de change sur les transactions déjà reportées. Pour mettre à jour les taux de change sur les écritures reportées, utilisez le traitement en lot **Ajuster les taux de change**.

Vous pouvez également spécifier comment l’ajustement traite les dimensions des reports de pertes et profits non réalisés en choisissant l’une des options suivantes dans le champ **Report de dimension** :  

* **Dimensions écriture source** : transférez les valeurs de dimension des écritures GL pour les pertes et profits non réalisés à partir de l’écriture que vous ajustez.  
* **Pas de dimensions** : ne transférez pas les valeurs de dimension pour les pertes et profits non réalisés vers les écritures GL. [!INCLUDE [prod_short](includes/prod_short.md)] utilise toujours les paramètres de dimension par défaut, par exemple, **Code obligatoire**, **Même code** ou **Pas de code**. Si les écritures de transaction sources ont des valeurs de dimension, l’ajustement crée des écritures sans valeurs de dimension.  
* **Dimensions compte du grand livre** : transférez les valeurs de dimension de l’écriture source des paramètres de dimension du compte du grand livre de pertes et profits non réalisés vers les écritures GL.

> [!NOTE]
> Pour utiliser la fonctionnalité en version préliminaire, vous devez activer la fonction **Mise à jour des fonctionnalités : activer l’utilisation du nouvel ajustement du taux de change extensible, y compris la révision du report** sur la page **[Gestion des fonctionnalités](https://businesscentral.dynamics.com/?page=2610)**.

> [!IMPORTANT]
> En raison des exigences locales en Suisse, nous vous déconseillons d’activer la fonction **Mise à jour des fonctionnalités : activer l’utilisation du nouvel ajustement du taux de change extensible, y compris la révision du report** dans la version suisse (CH).

## Prévisualiser l’effet d’un ajustement

Vous pouvez prévisualiser l’effet d’un ajustement du taux de change sur le report avant le report réel en choisissant l’action **Aperçu report** sur la page de demande du rapport **Ajustement des taux de change** (rapport 596). Sur la page de demande, vous pouvez spécifier ce qu’il faut inclure dans l’aperçu :

* Obtenir un report détaillé dans le grand livre par écriture.
* Obtenir un report récapitulatif par devise. Sélectionnez simplement le champ **Ajuster par écriture** dans le rapport **Ajustement des taux de change**.

### Effet sur les clients et les fournisseurs

Pour les comptes client et fournisseur, le traitement en lot utilise le taux de change qui était valide à la date de report spécifiée pour le traitement en lot pour ajuster la device. Le traitement en lot calcule les différences pour chaque solde en devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains non réalisés** ou **Compte pertes non réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur le compte client/fournisseur dans le grand livre.

Ce traitement en lot traite toutes les écritures client et toutes les écritures fournisseur ouvertes. S’il y a une différence de taux de change pour une écriture, le traitement en lot crée une nouvelle écriture client ou fournisseur détaillée. La nouvelle écriture reflète le montant ajusté dans l’écriture client ou fournisseur.

#### Dimensions des écritures client et fournisseur

[!INCLUDE [prod_short](includes/prod_short.md)] attribue les dimensions des écritures client ou fournisseur aux écritures ajustement et reporte les ajustements pour chaque combinaison de valeurs de dimension.

### Effet sur les comptes bancaires

Pour les comptes bancaires, le traitement en lot ajuste la devise en utilisant le taux de change qui est valide à la date de report spécifiée dans le traitement en lot. Le traitement en lot calcule les différences pour chaque compte bancaire possédant un code devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains réalisés** ou **Compte pertes réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur les comptes bancaires du grand livre spécifiés dans les groupes de report compte bancaire. Le traitement en lot calcule une écriture par devise et par groupe de report.

#### Dimensions des écritures compte bancaire

Les dimensions par défaut du compte bancaire sont affectées aux écritures ajustement pour le compte GL du compte bancaire et pour le compte gain/perte.

### Effet sur les comptes du grand livre

Si vous reportez dans une autre devise de report, le traitement en lot peut créer de nouvelles écritures GL pour les ajustements de devise entre la devise locale et l’autre devise de report. Le traitement en lot calcule les différences pour chaque écriture GL. Il ajuste l’écriture GL en fonction de la valeur du champ **Ajustement taux de change** de chaque compte GL.

#### Dimensions des écritures compte du grand livre

Les dimensions par défaut des comptes dans lesquels elles sont reportées sont affectées aux écritures ajustement.

> [!Important]
> Avant de pouvoir utiliser le traitement en lot, vous devez les taux de change ajustement qui sont utilisés pour ajuster les soldes en devises étrangères. Pour ce faire sur la page **Taux de change devise**.<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Q24s?rel=0]

## Configuration d’un service de taux de change des devises

Vous pouvez utiliser un service externe pour tenir vos taux de change des devises à jour, par exemple FloatRates. 

> [!NOTE]
> La plupart des services de taux de change fournissent des données compatibles avec le processus d’importation dans [!INCLUDE[prod_short](includes/prod_short.md)]. Cependant, les données sont parfois formatées différemment et vous devez personnaliser votre processus d’importation. Pour cela, vous pouvez utiliser l’infrastructure d’échange de données en ajoutant votre propre codeunit. Vous aurez probablement besoin de l’aide d’un développeur. Pour plus d'informations, voir [Configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Services de taux de change des devises**, puis sélectionnez le lien associé.
2. Sélectionnez l’action **Nouveau**.
3. Sur la page **Service de taux de change devise**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Activez le bouton bascule **Activé** pour activer le service.

> [!NOTE]
> La vidéo suivante montre comment vous connecter à un service de taux de change des devises, en prenant l’exemple de la Banque Centrale Européenne. Dans le segment qui décrit comment configurer les mappages de champs, le paramètre de la colonne **Source** pour **Nœud parent pour code devise** ne renvoie que la première devise trouvée. Le paramètre doit être `/gesmes:Envelope/Code/Code/Code`.

<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4A1jy?rel=0]

## Mettre à jour les taux de change des devises à partir d’un service

Suivez les étapes indiquées pour mettre à jour les taux de change via un service :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Devises**, puis sélectionnez le lien associé.
2. Sélectionner l’option **Mettre à jour les taux de change**.

## Corriger les erreurs

De temps en temps, vous devrez peut-être corriger une erreur dans une opération de paiement associée à des ajustements des gains et des pertes de change. Vous pouvez utiliser l’action **Inverser transaction** sur les **écritures bancaires**, les **écritures client** et les **écritures fournisseur** pour annuler l’affectation et inverser la transaction de paiement.

> [!NOTE]
> Lorsque vous annulez l'affectation et inversez un paiement pour une écriture à laquelle sont associés des ajustements de taux de change, l’inversion reporte les écritures d'inversion pour les ajustements. Vous devrez peut-être réexécuter l’ajustement du taux de change pour obtenir le solde actuel correct.

## Voir aussi

## Voir aussi .

[Devises dans Business Central](finance-currencies.md)  
[Configurer des devises](finance-set-up-currencies.md)  
[Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
