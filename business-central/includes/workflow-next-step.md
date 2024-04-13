---
author: brentholtorf
ms.topic: include
ms.date: 03/27/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

> [!IMPORTANT]
> Lorsque vous modifiez l’événement when pour une étape du flux de travail, les réponses then changent également. Parfois, les réponses d’autres événements lorsque se réfèrent à ces réponses comme étape suivante du flux de travail. Après avoir modifié un événement when, vérifiez que les étapes suivantes pour ses événements then sont correctes.  
>
> Par exemple, le **Flux de travail d’approbation du fournisseur** le modèle de workflow a un événement when principal **L’approbation d’un fournisseur est demandée**. Ceci lorsque l’événement a un **Envoyer une demande d’approbation pour l’enregistrement et créer une notification** puis la réponse, qui autre que les réponses fait référence. Si vous changez le primaire **L’approbation d’un fournisseur est demandée** quand un événement, par exemple, **Un enregistrement de fournisseur est modifié**, la réponse then est effacée avec les références.
>
> Les réponses ensuite pour le **Une demande d’approbation est déléguée** et **Une demande d’approbation est approuvée** (avec le **À condition** de **Approbations en attente >0**) lorsque les événements sont des exemples de cas dans lesquels la modification d’un événement principal lorsque peut causer des problèmes. Leurs réponses comportent ensuite une étape suivante qui fait référence au **Envoyer une demande d’approbation pour l’enregistrement et créer une notification** puis réponse du **L’approbation d’un fournisseur est demandée** quand événement. Parce que Alors, réponse pour En cas d’événement **L’approbation d’un fournisseur est exigée** n’est plus disponible, En cas d’événements décalés ne fonctionnera pas comme prévu.
>
> Vous devrez spécifier les étapes suivantes pour les réponses then pour les événements when faisant référence à l’événement when modifié.