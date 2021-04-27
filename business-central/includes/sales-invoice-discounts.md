---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 95121642b62f33ea1fc160c103ee845816706530
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5778657"
---
Lorsque tous les articles ont été entrés en tant que lignes, vous pouvez calculer l'escompte facture pour l’ensemble du document vente en choisissant l’action **Calculer escompte facture**.

L’escompte est calculé en fonction de toutes les lignes du document vente pour les articles et les ressources pour lesquels le champ **Escompte facture autorisée** de la ligne document de vente indique **Oui**. C’est la configuration par défaut pour les articles. Les lignes avec des frais annexes, par exemple, ne sont pas incluses dans le calcul de l’escompte facture. Si vous souhaitez affecter un escompte à ces lignes, vous devez définir le champ **% escompte ligne** sur les lignes appropriées.  

> [!TIP]
> Si le champ **Calculer escompte facture** est sélectionné dans la page **Configuration ventes**, l’escompte facture est calculé automatiquement lorsque vous effectuez l’une des actions suivantes sur un document vente :
>
> * Afficher les statistiques
> * Afficher un rapport de test
> * Imprimer
> * Report

Les conditions d’escompte facture pour un client sont définies sur la page **Escompte facture client** pour le client. Le code devise du document vente est utilisé pour trouver les conditions escompte facture dans la devise correspondante.

Si vous n’avez pas défini d'escompte facture pour les devises, les conditions d'escompte facture définies sur la page **Escomptes facture client** avec des montants dans votre devise locale et le taux de change à la date de report du document vente sont utilisés pour calculer l'escompte facture en devise étrangère.
