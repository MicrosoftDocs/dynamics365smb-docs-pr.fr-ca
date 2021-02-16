---
author: edupont04
ms.service: dynamics365-business-central
ms.topic: include
ms.date: 01/20/2021
ms.author: edupont
ms.openlocfilehash: 718845561c1a18701d20b93ebdc8339308ce7ac8
ms.sourcegitcommit: adf1a87a677b8197c68bb28c44b7a58250d6fc51
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035805"
---
Lorsque tous les articles ont été entrés sur les lignes document de vente, vous pouvez calculer l'escompte sur facture pour l’ensemble du document vente en choisissant l’action **Calculer escompte facture**.

Si le champ **Calculer escompte facture** est sélectionné dans la fenêtre **Configuration des ventes**, l'escompte facture est calculé automatiquement lorsque vous effectuez l’une des actions suivantes sur un document vente :

* Afficher les statistiques
* Afficher un rapport de test
* Imprimer
* Report

L'escompte est réparti sur toutes les lignes du document vente pour les articles et les ressources pour lesquels le champ **Escompte facture autorisé** de la ligne document de vente indique **Oui**. C’est la configuration par défaut pour les articles.

Les conditions d'escompte facture sont définies sur la page **Escomptes facture client** pour calculer l'escompte facture. Le code devise du document vente est utilisé pour trouver les conditions escompte facture dans la devise correspondante.

Si vous n’avez pas défini d'escompte facture pour les devises, les conditions d'escompte facture définies sur la page **Escomptes facture client** avec des montants dans votre devise locale et le taux de change à la date de report du document vente sont utilisés pour calculer l'escompte facture en devise étrangère.
