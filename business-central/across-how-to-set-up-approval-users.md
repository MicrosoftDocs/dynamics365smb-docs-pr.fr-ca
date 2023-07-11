---
title: Configurer des utilisateurs d'approbation
description: 'Avant de pouvoir créer des workflows qui impliquent des étapes d’approbation, vous devez configurer les utilisateurs du workflow impliqués dans les processus d’approbation.'
author: brentholtorf
ms.topic: how-to
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '663,'
ms.date: 05/31/2023
ms.author: bholtorf
---
# Configuration des utilisateurs des approbations

Avant de pouvoir créer des flux de travail qui impliquent des étapes d’approbation, vous devez configurer les utilisateurs du flux de travail impliqués dans les processus d’approbation sur la page **Configuration utilisateur approbation**. Vous pouvez également définir des limites de montant pour différents types de demandes, définir des approbateurs de remplacement et configurer des notifications.  

Lorsque vous configurez des utilisateurs approbation, vous pouvez créer de réponses du flux de travail pour des flux de travail approbation. En savoir plus sur [Créer des flux de travail approbation](across-how-to-create-workflows.md).  

> [!TIP]
> Vous pouvez exiger que plusieurs approbateurs réagissent à une demande d’approbation en créant un groupe d’approbateurs sur la page **Groupe d’utilisateurs de workflow**. En savoir plus sur [Configurer des groupes d’utilisateurs de flux de travail](across-how-to-set-up-workflow-users.md).  

## Configurer un utilisateur approbation

[!INCLUDE [workflow-requestor-approver](includes/workflow-requestor-approver.md)]

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration d'utilisateur d'approbation**, puis choisissez le lien associé.  
2. Créez une ligne sur la page **Configuration d'utilisateur d'approbation**, puis renseignez les champs comme indiqué dans le tableau suivant.  

   |Champ|Désignation|
   |-----|-----------|
   |**Code utilisateur**|Sélectionnez le code de l’utilisateur impliqué dans le processus d’approbation.|
   |**Code vendeur/acheteur**|Spécifiez le code représentant ou acheteur qui s’applique à l’utilisateur.<br /><br /> En général, vous remplissez le champ **Code représentant/acheteur** si le représentant ou l’acheteur responsable pour le client ou le fournisseur, est aussi la personne qui doit approuver la demande vente ou achat.|
   |**ID approbateur**|Sélectionnez le code d’utilisateur qui doit approuver des demandes effectuées par l’utilisateur dans le champ **Code utilisateur**.|
   |**Montant maximal vente autorisé**|Spécifiez le montant de vente maximal en devise locale ($) qui peut être approuvé par l’utilisateur dans le champ **Code utilisateur**.|
   |**Montant illimité de vente autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver toutes les demandes vente quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation de montant de vente**.|
   |**Montant maximal achat autorisé**|Spécifiez le montant d’achat maximal en $ que la personne identifiée dans le champ **Code utilisateur** peut approuver.|
   |**Montant illimité d'achat autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver toutes les demandes achat quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation de demande d’achat**.|
   |**Montant maximal demande achat autorisé**|Spécifiez le montant maximal en $ que la personne identifiée dans le champ **Code utilisateur** peut approuver pour les devis d’achat.<br /><br /> Pour utiliser ce champ, vous devez sélectionner l'option **Chaîne d'approbateurs** dans le champ **Type limite approbateur** sur la page **Réponse de flux de travail**.|
   |**Montant illimité de demande d'achat autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver tous les devis achat quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation de demande d’achat**.|
   |**Remplaçant**|Sélectionnez le code d’utilisateur qui doit approuver des demandes effectuées par l’utilisateur dans le champ **Code utilisateur** si l’utilisateur dans le champ **Code approbateur** n’est pas disponible. <br /><br />**Note :** le remplaçant peut être soit l'utilisateur dans le champ **Remplaçant**, l'approbateur direct, soit l'administrateur d'approbation, dans cet ordre de priorité. En savoir plus sur [Utiliser des flux de travail approbation](across-how-use-approval-workflows.md).|
   |**Adresse de messagerie**|Spécifiez l’adresse de courriel de la personne dans le champ **Code utilisateur**.|
   |**Administrateur approbation**|Spécifiez l’utilisateur qui a des autorisations de débloquer des flux de travail approbation, par exemple, en déléguant les demandes d’approbation à de nouveaux approbateurs remplaçants et en supprimant des demandes d’approbation échues.<br /><br />**Remarque** Une seule personne peut être l’administrateur d’approbation.|

3. Pour tester la configuration utilisateur d'approbation, choisissez l'action **Test config. utilis. d'approbation**.  
4. Répétez les étapes 2 et 3 pour chaque utilisateur que vous souhaitez configurer en tant qu’utilisateur approbation.  

L’étape suivante consiste à spécifier comment vous souhaitez [!INCLUDE [prod_short](includes/prod_short.md)] informer les personnes qu’une demande est en attente de leur attention. En savoir plus dans la rubrique [Configuration de notifications de flux de travail approbation](across-setting-up-workflow-notifications.md).

## Voir la [formation Microsoft](/training/modules/create-workflows/) associée

## Voir aussi .

[Configuration des utilisateurs des flux de travail](across-how-to-set-up-workflow-users.md)  
[Configuration de notifications de workflow](across-setting-up-workflow-notifications.md)  
[Créer des flux de travail approbation](across-how-to-create-workflows.md)  
[Configurer les flux de travail approbation](across-set-up-workflows.md)  
[Procédure pas à pas : configuration et utilisation d'un flux d'approbation achat](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Flux de travail](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
