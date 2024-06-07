---
title: Configurer les processus de gestion des services
description: Apprenez comment configurer les processus qui permettent de vérifier que les clients sont satisfaits de votre services.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: 'service, number sequences, setup, warnings, fee, contracts, warranties'
ms.date: 02/27/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="configure-service-management-processes"></a>Configurer des processus de gestion des services

Voici quelques exemples des paramètres que vous pouvez appliquer aux processus de gestion des services :  
  
* Certains paramètres généraux pour différents processus, comme les avertissements, les calculs de service suivants pour les articles de service, les frais de démarrage à évaluer, le niveau de rapport panne à utiliser, etc.  
* Les types au cas où les techniciens doit saisir des informations sur les documents service. Par exemple, vous pouvez lui demander de spécifier le type de commande, les dates de début et/ou de fin du travail et le type de travail effectué.  
* Certains paramètres par défaut pour les temps de réponse et les garanties. Ceux-ci incluent un délai de réponse par défaut pour commencer le service, les pourcentages d'escompte garantie pour les pièces et le travail, et le délai de validité des garanties.  
* Les paramètres pour les contrats, tels que le nombre maximum de jours que vous pouvez utiliser pour les commandes contrat de service, si vous utilisez des codes motif lorsqu’un contrat est annulé, des textes standard pour les descriptions et les valeurs contractuelles.  
* Les souches de numéros à utiliser pour les documents et les articles relatifs au service.  

## <a name="to-enter-general-and-mandatory-settings"></a>Pour saisir les paramètres généraux et obligatoires

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration Gestion des services**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="set-up-service-invoice-posting-policies-for-users"></a>Configurer les politiques de publication des factures de service pour les utilisateurs

Les compagnies ont souvent des processus uniques pour les factures et les expéditions. Par exemple, les processus peuvent varier d’une personne reportant tout sur un ordre service à plusieurs employés, chacun dans leurs propres pages.

Vous pouvez utiliser des stratégies de report pour empêcher les utilisateurs de reporter des factures de service ou leur demander de reporter les factures avec l’expédition service associée. Pour paramétrer une politique report, sur la page **Configuration de l’utilisateur**, dans les champs **Stratégie report facture service**, choisissez l’une des options suivantes :

* **Autorisé** (Par défaut) : conservez le comportement actuel, où un utilisateur peut choisir l’option de report, comme **Expédier**, **Facturer**, et **Expédier et facturer**.
* **Interdit** : empêchez les utilisateurs de reporter des factures service. [!INCLUDE [prod_short](includes/prod_short.md)] affiche une boîte de dialogue de confirmation qui fournit uniquement l’option **Expédition**.
* **Obligatoire** : Permettez aux gens de reporter des factures avec les expéditions service. [!INCLUDE [prod_short](includes/prod_short.md)] affiche une boîte de dialogue de confirmation qui fournit uniquement l’option **Expédition et facturation**.

Ce paramètre affecte les documents suivants :

* Commandes service
* Livraisons entrepôt
* Factures service
* Notes de crédit service

Le tableau suivant décrit les différentes effets sur différents documents.

|Document  |Autoriser<br>Affiche une série d’options   |Interdit<br>Boîte de dialogue de conformation  |Obligatoire<br>Boîte de dialogue de confirmation  |
|---------|---------|---------|---------|
|Commande service     | * Expédition<br>* Facturer<br>* Expédition et facturation<br>* Expédier et consommer         |* Expédition<br>* Expédier et consommer  |Souhaitez-vous reporter la livraison et la facture?         |
|Expédition entrepôt     |* Expédition<br>* Expédition et facturation         |Souhaitez-vous reporter la livraison?         | Souhaitez-vous reporter la livraison et la facture?        |
|Facture service     | Souhaitez-vous reporter la facture?         | Erreur : vous ne pouvez pas reporter.       |Souhaitez-vous reporter la facture?         |
|Note de crédit service     | Souhaitez-vous reporter la note de crédit?         | Erreur : vous ne pouvez pas reporter.        |Souhaitez-vous reporter la note de crédit?         |

> [!NOTE]
> Lorsque vous reportez des factures service et des notes de crédit, vous ne disposez d’aucune option de report. Les documents présentent toujours les transactions physiques et financières ensemble. Vous ne pouvez pas reporter partiellement les factures et les notes de crédit service.

## <a name="see-also"></a>Voir aussi .

[Configurer le signalement des défaillances](service-how-setup-fault-reporting.md)  
[Configuration de l’affectation des ressources](service-how-setup-resource-allocation.md)  
[Configurer des codes prestations standards](service-how-setup-service-coding.md)  
[Configurer des frais supplémentaires pour les services](service-how-setup-service-costs-pricing.md)  
[Configurer le dépannage](service-how-setup-troubleshooting.md)  
[Gestion des services](service-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
