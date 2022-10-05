---
title: Configurer des utilisateurs d'approbation
description: Avant de pouvoir créer des flux de travail qui impliquent des étapes d’approbation, vous devez configurer les utilisateurs du flux de travail qui sont impliqués dans les processus d’approbation sur la page Configuration utilisateur approbation.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 663
ms.date: 09/08/2022
ms.author: edupont
ms.openlocfilehash: 2654dcb68b579d90fe3218bcd0bba3bde4cb5036
ms.sourcegitcommit: 9049f75c86dea374e5bfe297304caa32f579f6e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/23/2022
ms.locfileid: "9585848"
---
# <a name="set-up-approval-users"></a>Configurer des utilisateurs d'approbation

Avant de pouvoir créer des workflows qui impliquent des étapes d'approbation, vous devez configurer les utilisateurs du workflow qui sont impliqués dans les processus d'approbation. Sur la page **Configuration d'utilisateur d'approbation**, vous pouvez également définir les limites pour des types spécifiques de demandes et définir des approbateurs remplaçants à qui des demandes d'approbation sont déléguées lorsque l'approbateur initial est absent.  

> [!NOTE]  
> Les utilisateurs d’approbation, à la fois demandeurs d’approbation et approbateurs, doivent d’abord être définis comme utilisateurs du flux de travail sur la page **Groupe d’utilisateurs du flux de travail**. En savoir plus sur [Configurer des utilisateurs de flux de travail](across-how-to-set-up-workflow-users.md).  

Lorsque vous configurez des utilisateurs approbation, vous pouvez créer de réponses du flux de travail pour des flux de travail approbation. En savoir plus à partir de l’étape 9 sur [Créer des flux de travail approbation](across-how-to-create-workflows.md).  

> [!NOTE]  
> Pour indiquer qu’une demande d’approbation n’est pas approuvée tant que plusieurs utilisateurs dans une chaîne d’approbation ne l’ont pas approuvée, configurez les approbateurs selon une hiérarchie. Pour le type d'approbateur **Approbateur**, configurez les approbateurs sur la page **Configuration d'utilisateur d'approbation**. Pour le type d’approbateur **Groupe d’utilisateurs de flux de travail**, configurez les approbateurs sur la page **Groupe d’utilisateurs du flux de travail** et définissez la hiérarchie en affectant des numéros incrémentiels à chaque approbateur dans le champ **N° séquence** . En savoir plus sur [Configurer des utilisateurs de flux de travail](across-how-to-set-up-workflow-users.md).  

## <a name="to-set-up-an-approval-user"></a>Configurer un utilisateur approbation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration d'utilisateur d'approbation**, puis choisissez le lien associé.  
2. Créez une ligne sur la page **Configuration d'utilisateur d’approbation**, puis renseignez les champs comme indiqué dans le tableau suivant.  

   |Champ|Désignation|
   |-----|-----------|
   |**Code utilisateur**|Sélectionnez le code de l’utilisateur impliqué dans le processus d’approbation.|
   |**Code vendeur/acheteur**|Spécifiez le code représentant ou acheteur qui s’applique à l’utilisateur.<br /><br /> En général, vous remplissez le champ **Code représentant/acheteur** si le représentant ou l’acheteur responsable pour le client ou le fournisseur est aussi la personne qui doit approuver la demande vente ou achat en question.|
   |**ID approbateur**|Sélectionnez le code utilisateur de la personne qui doit approuver les demandes faites par la personne identifiée dans le champ **Code utilisateur**.|
   |**Montant maximal vente autorisé**|Spécifiez le montant de vente maximal en devise locale ($) que la personne identifiée dans le champ **Code utilisateur** peut approuver.|
   |**Montant illimité de vente autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver toutes les demandes vente quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation du montant de vente**.|
   |**Montant maximal achat autorisé**|Spécifiez le montant d’achat maximal en $ que la personne identifiée dans le champ **Code utilisateur** peut approuver.|
   |**Montant illimité d'achat autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver toutes les demandes achat quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation de demande d’achat**.|
   |**Montant maximal demande achat autorisé**|Spécifiez le montant maximal en $ que la personne identifiée dans le champ **Code utilisateur** peut approuver pour les devis d’achat.<br /><br /> Pour utiliser ce champ, vous devez sélectionner l'option **Chaîne d'approbateurs** dans le champ **Type limite approbateur** sur la page **Réponse de flux de travail**.|
   |**Montant illimité de demande d'achat autorisé**|Spécifiez que la personne identifiée dans le champ **Code utilisateur** peut approuver tous les devis achat quel que soit leur montant.<br /><br /> Si vous cochez cette case, vous ne pouvez pas renseigner le champ **Limite d’approbation du montant demandé**.|
   |**Remplaçant**|Sélectionnez le code utilisateur de la personne qui doit approuver les demandes faites par la personne identifiée dans le champ **Code utilisateur** si l’utilisateur dans le champ **Code approbateur** n’est pas disponible. <br /><br />**Note :** le remplaçant peut être soit l'utilisateur dans le champ **Remplaçant**, l'approbateur direct, soit l'administrateur d'approbation, dans cet ordre de priorité. En savoir plus sur [Utiliser des flux de travail approbation](across-how-use-approval-workflows.md).|
   |**Adresse de messagerie**|Spécifiez l’adresse de courriel de la personne dans le champ **Code utilisateur**.|
   |**Administrateur approbation**|Spécifiez l’utilisateur qui a des autorisations de débloquer des flux de travail approbation, par exemple, en déléguant les demandes d’approbation à de nouveaux approbateurs remplaçants et en supprimant des demandes d’approbation échues.|

   > [!NOTE]
   > Une seule personne peut être l’administrateur d’approbation.

3. Pour tester la configuration utilisateur d'approbation, choisissez l'action **Test config. utilis. d'approbation**.  
4. Répétez les étapes 2 et 3 pour chaque utilisateur que vous souhaitez configurer en tant qu’utilisateur approbation.  

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/create-workflows/) associée

## <a name="see-also"></a>Voir aussi .

[Configurer des utilisateurs de flux de travail](across-how-to-set-up-workflow-users.md)  
[Configuration de notifications de workflow](across-setting-up-workflow-notifications.md)  
[Créer des flux de travail approbation](across-how-to-create-workflows.md)  
[Configurer les flux de travail approbation](across-set-up-workflows.md)  
[Procédure pas à pas : configuration et utilisation d'un flux d'approbation achat](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Flux de travail](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
