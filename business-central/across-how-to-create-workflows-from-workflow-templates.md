---
title: "Procédure\_: créer des flux de travail à partir de modèles de flux de travail"
description: 'Pour gagner du temps lors de la création de flux de travail approbation, vous pouvez créer des flux de travail à partir de modèles de flux de travail existants.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: dajoo
ms.topic: how-to
ms.search.keywords: null
ms.date: 03/27/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="create-workflows-from-workflow-templates"></a>Création de flux de travail à partir de modèles de flux de travail

Sur la page **Flux de travail**, créez un flux de travail en créant une série d'étapes de flux de travail sur les lignes. Chaque étape comprend un événement de flux de travail (En cas d'événement) modéré par des conditions d’événement (À condition), et une réponse de flux de travail (Ensuite la réponse) modérée par des options de réponse. Les champs des lignes de flux de travail fournissent des tarifs des valeurs d’événement et de réponse qui représentent les scénarios que [!INCLUDE [prod_short](includes/prod_short.md)] pris en charge. En savoir plus sur [Créer des flux de projet](across-how-to-create-workflows.md).

Pour gagner du temps à la création de flux de travail approbation, [!INCLUDE [prod_short](includes/prod_short.md)] fournit des modèles de flux de travail. Les modèles sont disponibles sur le **Modèles de flux de travail** page. Vous pouvez utiliser les modèles tels quels ou les personnaliser pour répondre à vos besoins. Les codes des modèles de flux de travail de Microsoft ont le préfixe **MS-**.

[!INCLUDE [workflow-next-step](includes/workflow-next-step.md)]

Si vous modifiez un modèle de workflow, mais que vous regrettez ultérieurement la modification, utilisez l’option **Réinitialiser les modèles Microsoft** action pour revenir au paramètre d’origine du flux de travail.

> [!CAUTION]
> Le **Réinitialiser les modèles Microsoft** L’action réinitialise tous les modèles de flux de travail Microsoft. Vous ne pouvez pas réinitialiser un seul modèle.  

Une autre façon de créer rapidement un workflow consiste à l’importer, par exemple, si vous l’avez exporté depuis une autre instance de [!INCLUDE[prod_short](includes/prod_short.md)]. En savoir plus sur [Exporter et importer des flux de travail](across-how-to-export-and-import-workflows.md).  

## <a name="to-create-a-workflow-from-a-workflow-template"></a>Pour créer un flux de travail à partir d’un modèle de flux de travail

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Flux de travail**, puis choisissez le lien associé.  
2. Choisissez l’action **Créer flux de travail à partir du modèle**. La page **Modèles flux de travail** s'ouvre.  
3. Sélectionnez un modèle de flux de travail et cliquez sur le bouton **OK**.  

   La page **Flux de travail** s'ouvre pour un nouveau flux de travail contenant toutes les informations du modèle sélectionné. La valeur du champ **Code** est étendue avec « -01 », par exemple, « -01 » pour indiquer que ce premier flux de travail est créé à partir du modèle de flux de travail.  
4. Pour Personnaliser le flux de travail, modifiant les étapes de flux de travail ou en ajoutant de nouvelles étapes. En savoir plus sur [Créer des flux de projet](across-how-to-create-workflows.md).  

## <a name="see-also"></a>Voir aussi .

[Création des flux de travail d’approbation](across-how-to-create-workflows.md)  
[Exportation et importation des flux de travail d’approbation](across-how-to-export-and-import-workflows.md)  
[Afficher des instances d'étape de workflow archivées](across-how-to-view-archived-workflow-step-instances.md)  
[Suppression des flux d’approbation](across-how-to-delete-workflows.md)  
[Procédure pas à pas : configuration et utilisation d'un flux d'approbation achat](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Configurer les flux de travail approbation](across-set-up-workflows.md)  
[Utilisation des flux d’approbation](across-use-workflows.md)  
[Flux de travail](across-workflow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
