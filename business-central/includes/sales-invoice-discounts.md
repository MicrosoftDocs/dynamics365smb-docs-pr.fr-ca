---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 01/25/2021
ms.author: edupont
ms.openlocfilehash: 539ee2eb2c9e4a71eacfb78d95320870128fb1d9
ms.sourcegitcommit: cb06aa973f5c767df774b0e1e199c6fbe0e85b88
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470297"
---
Lorsque tous les articles ont été entrés sur les lignes vente, vous pouvez calculer l’escompte sur facture pour l’ensemble du document vente en choisissant l’action **Calculer escompte facture**.

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
