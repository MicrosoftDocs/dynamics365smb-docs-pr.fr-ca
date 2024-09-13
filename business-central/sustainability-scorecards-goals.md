---
title: Fiches et objectifs de durabilité
description: Apprenez à configurer et à utiliser des tableaux de bord et des objectifs de durabilité.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, scorecard, goal, forecast, budget'
ms.search.form: null
ms.date: 08/19/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Aperçu des tableaux de bord et des objectifs de durabilité

Cet article fournit des conseils sur la manière de créer des tableaux de bord et des objectifs, et sur la manière de mettre à jour le statut des objectifs. Les tableaux de bord et les objectifs permettent aux organisations d’organiser les mesures de durabilité et de les suivre par rapport aux principaux objectifs commerciaux. Des objectifs peuvent être créés en fonction des valeurs actuelles et cibles, afin que les utilisateurs puissent suivre la progression des émissions actuelles par rapport aux périodes précédentes.  

## Créer une fiche d’évaluation  

Pour créer une nouvelle *fiche d’évaluation du développement durable*, suivre suivez les étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Fiches de pointage de durabilité**, puis Sélectionner le lien associé. 
2. Sur la page **Fiches d’évaluation de la durabilité**, cliquez sur Sélectionner **Nouveau** pour créer une nouvelle fiche d’évaluation.  
3. Spécifiez le **No.** Et les champs  **Nom** sur le raccourci **Général**, puis ajoutez le **Propriétaire**. 

> [REMARQUE !] Dans le champ **Propriétaire**, vous ne pouvez choisir que les utilisateurs qui ont sélectionné le champ **Responsable du développement durable** dans le tableau **Configuration utilisateur** . 

## Créer des objectifs  

Pour créer un nouvel *objectif de développement durable*, suivre suivez les étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Fiches de pointage de durabilité**, puis Sélectionner le lien associé.
2. Choisissez l’action **Objectifs** pour créer un nouvel **objectif de développement durable** pour la fiche d’évaluation sélectionnée.  
3. Sélectionner **Nouveau** pour commencer à créer un nouvel objectif.
4. Le tableau de bord n° **·** Est automatiquement ajouté en fonction de la valeur du  **Sustainability Scorecard** connecté, et l’utilisateur ne pourra pas modifier ce champ. Le système configure également le champ **Unité de mesure** en fonction du **Code d’unité de mesure d’émission** sur la page **Configuration de la durabilité** .  
5. Vous devez renseigner **Non.** et **Nom** du nouvel **Objectif de développement durable**. Le champ **Propriétaire** est automatiquement renseigné en fonction de la valeur de la **fiche d’évaluation de durabilité** connectée.   
6. Les utilisateurs peuvent décider de créer un *objectif de développement durable* pour l’ensemble de l’entreprise, un pays/une région spécifique ou une installation. Si les utilisateurs souhaitent créer un objectif spécifique, ils doivent choisir le pays ou la région dans le champ **Code pays/région** ou l’établissement dans le champ **Centre de responsabilité** .  
7. Sélectionner les champs **Date de début** et **Date de fin** pour configurer une période dédiée au suivi des valeurs actuelles. Cette configuration détermine les valeurs dans les champs suivants : **Valeur actuelle pour CO2**, **Valeur actuelle pour CH4** et **Valeur actuelle pour N2O**. 
8. Sélectionner les champs **Date de début de référence** et **Date de fin de référence** pour configurer une période de référence dédiée à la comparaison des valeurs actuelles. Cette configuration détermine les valeurs dans les champs suivants : **Ligne de base pour CO2**, **Ligne de base pour CH4** et **Ligne de base pour N2O**.
9. Les utilisateurs peuvent également ajouter des valeurs cibles dans le champ  **Unité de mesure** sélectionné pour la période en cours à l’aide des champs suivants : **Valeur cible pour le CO2**, **Valeur cible pour le CH4** et **Valeur cible pour le N2O**.   
10. L’un de ces objectifs peut être sélectionné comme **objectif principal**. Les valeurs de l’objectif principal sont utilisées dans le centre de rôles  **Sustainability Manager** .  

Si vous avez de nombreux objectifs sur la page, vous pouvez utiliser l’action  **Afficher mes objectifs** pour afficher uniquement vos objectifs, et si vous souhaitez tous les afficher, vous devez exécuter l’action  **Afficher tous les objectifs** .  

> [!NOTE]
> *Les objectifs de développement durable* ne peuvent être créés que pour une *fiche de score de développement durable* spécifique, et vous ne pouvez pas créer d’objectifs qui ne sont pas liés à la fiche de score, mais vous pouvez créer plusieurs objectifs pour une seule fiche de score. Vous ne pouvez avoir qu’un seul **objectif de développement durable** marqué comme **objectif principal**.

> [!NOTE]
> Les utilisateurs peuvent configurer différentes combinaisons d’objectifs pour l’ensemble de l’entreprise, des pays ou des régions spécifiques et un centre de responsabilité pour un tableau de bord de durabilité *.* Les utilisateurs peuvent également utiliser des périodes différentes pour le même modèle de suivi. 

## Voir aussi .

[Configuration de durabilité](finance-sustainability-setup.md)    
[Plan comptable et comptabilité de durabilité](finance-sustainability-accounts-ledger.md)    
[Comment enregistrer les entrées de durabilité](finance-sustainability-journal.md)    
[Analyse ad hoc des données de durabilité](ad-hoc-analysis-sustainability.md)    
[Rapports de durabilité et analyses dans Business Central](sustainability-reports.md)   
[API de durabilité](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Finances](finance.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
