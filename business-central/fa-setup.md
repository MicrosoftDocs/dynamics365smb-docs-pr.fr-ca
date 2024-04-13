---
title: Configurer des immobilisations
description: 'En savoir plus sur la série de tâches que vous devez effectuer pour configurer les immobilisations, telles que les machines ou les bâtiments.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.keywords: 'machinery, buildings'
ms.search.form: '5607,'
ms.date: 03/25/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Paramétrage d’immobilisations

Avant de pouvoir utiliser les immobilisations, vous devez définir les éléments suivants :  

* Amortir des immobilisations.  
* La manière dont vous enregistrez les coûts acquisition, amortissements et d’autres valeurs dans le grand livre.  
* En option, comment enregistrer l’assurance et l’entretien des immobilisations.

Les sections de cet article renvoient à des informations supplémentaires sur la configuration des immobilisations. Une fois la configuration terminée, vous pouvez commencer à travailler avec des immobilisations. Pour en savoir plus, voir [Utiliser des immobilisations](fa-manage.md).  

> [!NOTE]  
> Vous pouvez enregistrer les transactions immobilisation sur les pages **Journal GL immobilisation** ou **Journal immobilisation**, selon que les transactions sont destinées à des rapports financiers ou pour la gestion interne. Les articles d’aide pour les immobilisations décrivent uniquement la procédure d’utilisation de la page **Journal GL immo.**.  

Lorsque vous activez une activité immobilisation dans la section **Intégration GL** sur la page **Fiche registre amortissement**, la page **Journal GL immo.** sera utilisée pour reporter les transactions pour l’activité.

## Tâches de configuration obligatoire

Le tableau suivant contient une séquence de tâches pour configurer les immobilisations et des liens vers des articles connexes.

| À | Voir |
|---|---|
| Configurez les comptes du grand livre par défaut, les clés d’affectation, les modèles journal et les lots pour le report des immobilisations et configurez les catégories et sous-catégories d’immobilisation, telles que Corporelles et Incorporelles. |[Configurer des informations générales pour les immobilisations](fa-how-setup-general.md) |
| Créer des registres amortissement, définir différentes méthodes d'amortissement, procéder à l'intégration dans le grand livre et activer la duplication d'écritures dans plusieurs registres amortissement. |[Configuration des amortissements](fa-how-setup-depreciation.md) |

## Tâches de configuration facultatives (assurance, entretien et méthodes d’amortissement définies par l’utilisateur)

Le tableau suivant contient une séquence de tâches facultatives pour configurer les immobilisations, notamment les assurances, l’entretien et les méthodes amortissement, ainsi que des liens vers des articles connexes. 

| À | Voir |
|---|---|
| Activer l'assurance des immobilisations, configurer les informations générales d'assurance, une fiche assurance par police et préparer les journaux pour reporter les coûts d'assurance. |[Configurer une assurance immobilisation](fa-how-setup-insurance.md) |
| Activer l'entretien des immobilisations, configurer les informations générales propres à l'entretien, configurer les comptes de report de l'entretien et définir les types de travaux d'entretien. |[Configurer l’entretien des immobilisations](fa-how-setup-maintenance.md) |
| Découvrez comment appliquer des méthodes d’amortissement. |[Configuration des méthodes d’amortissement définies par l’utilisateur](fa-how-setup-user-defined-depreciation-method.md) |

## Voir aussi .

[Vue d’ensemble des immobilisations](fa-manage.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
