---
author: brentholtorf
ms.topic: include
ms.date: 03/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

> [!NOTE]
> Lorsque vous copiez une compagnie dans un environnement dans lequel Dataverse ou l’intégration des ventes est activée, [!INCLUDE [prod_short](prod_short.md)] efface les paramètres suivants lors de la copie vers la compagnie cible :
>
> * Dataverse et les paramètres de connexion Dynamics pour garantir que l’intégration redémarre correctement dans la compagnie cible.
> * Enregistrements d’intégration pour garantir que la compagnie cible ne pointe pas vers des enregistrements couplés dans la compagnie source.
> * Tâches de synchronisation d’intégration pour arrêter les tâches de synchronisation en arrière-plan.
> * Les erreurs de synchronisation, si elles existent, car elles pointent vers des erreurs dans la compagnie source et seraient simplement considérées comme du bruit dans l’entreprise cible.