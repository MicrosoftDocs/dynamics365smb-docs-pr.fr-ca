---
title: Rapports Comptabilité client et analyse
description: Découvrez les rapports et analyses disponibles dans la version standard de Business Central afin que vous puissiez suivre vos comptes client.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont
ms.openlocfilehash: 76de1625ee71b666b01d6b2fef1efe5605d9a418
ms.sourcegitcommit: a486aa1760519c380b8cdc8fdf614bed306b65ea
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/13/2021
ms.locfileid: "6543395"
---
# <a name="accounts-receivable-reports-and-analytics-in-business-central"></a>Rapports comptabilité client et analyses d’immobilisation dans Business Central

Pour vous aider à gérer votre comptabilité client dans [!INCLUDE [prod_short](includes/prod_short.md)], des rapports et des analyses standard sont intégrés. Ils vont au-delà des contraintes des rapports traditionnels pour vous aider à concevoir efficacement divers types de rapports.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports de comptabilité client.

| Rapport | Code objet | Description |
|--|--|--|
| **Comptabilités client chronologiques** | 120 | Affiche le montant impayé avec les clients répartis en intervalles de temps pour le temps de retard. Le rapport affiche également la partie du solde des clients qui n’est pas due et peut être affiché avec ou sans les détails du document pour chaque client. Ce rapport est le rapport principal pour la conciliation des grands livres clients avec le grand livre. En supposant que vous n’ayez pas autorisé le report direct sur les comptes utilisés dans le grand livre client des groupes de report, ce rapport est une spécification des montants que vous trouvez en grand livre. |
| **Relevé client** | 1316 | Génère un relevé client pour un intervalle de temps spécifié. Il est généralement envoyé aux clients pour leur donner un aperçu des montants impayés et également pour rappeler de payer les montants en souffrance. Vous pouvez choisir d’afficher les montants en souffrance dans une section distincte. Vous pouvez inclure une bande chronologique similaire à celle utilisée dans le rapport **Comptabilités chronologiques**. Pour la bande chronologique, vous définissez généralement *30D*, ce qui signifie des intervalles de 30 jours tels que 30, 60, 90 et 90+ jours de retard, à compter de la date de fin, ou *1M+CM*, qui sera le mois en cours dans un intervalle séparé, puis des intervalles mensuels pour les mois précédents. **Remarque** : dans la liste des clients, ce rapport a également une action distincte, **Relevés programmés**. Cette option ne filtre pas le client que vous avez sélectionné. C’est le même rapport, mais utilisé lorsque vous souhaitez envoyer un relevé à tous/plus de clients. |
| **Clients - Solde à ce jour** | 121 | Affiche les écritures client ouvertes jusqu’à la date de fin. Ce rapport affiche un contenu similaire à celui du relevé client, mais sans indication si l’entrée est en retard. **Remarque** : Le filtre de date est affecté aux écritures client. Autrement dit, si vous avez des paiements postérieurs à la date de fin qui ont été affectés à des factures dans la plage de dates, les factures apparaîtront dans le rapport, car elles n’ont pas été fermées à la date de fin. |
| **Clients –– Balance de vérification** | 129 | Affiche les écarts nets pour les clients pour la période spécifiée dans le filtre de date ainsi que les écarts nets depuis le début de l’exercice financier correspondant à la période sélectionnée. Le rapport est regroupé par groupes de report des clients et donne une vue du grand livre client différente du rapport **Comptabilités client chronologiques**. **Remarque** : si vous n’avez pas configuré de période comptable, le système ne saura pas quel exercice financier utiliser et affichera le cumul annuel à partir du dernier exercice financier défini ou sélectionnera simplement la période, qui peut ou non être dès le début d’une année.|
| **Client - Balance de vérification détaillée** | 104 | Affiche toutes les écritures client dans le filtre de date spécifié. Ce rapport est généralement utilisé pour vérifier que toutes les écritures pour un client spécifique sont prises en compte, ou pour d’autres contrôles internes sur les grands livres clients. |
| **Reçu paiement client** | 211 | Crée un reçu de paiement pour chaque écriture client de type **Paiement**. Si le paiement a été affecté aux factures, les factures sont précisées; à défaut, il indique simplement le montant du paiement comme non affecté. Ce rapport est utilisé pour envoyer aux clients qui souhaitent une documentation pour la réception du paiement.|
| **Concordance comptes client et fournisseur** | 33 |Affiche les écritures résultant du report des écritures client et fournisseur réparties par compte du grand livre et groupes de report. Ce rapport est utilisé pour rapprocher les soldes des livres clients et fournisseurs avec les soldes grand livre. |
| **Clients : chronologie sommaire**| 109 |Il s’agit d’une ancienne version d’un échéancier des comptes clients. Nous vous recommandons d’utiliser le rapport **Comptabilités client chronologiques** à la place. |
| **Statistiques vente** |112  |[!INCLUDE [reports-sales-statistics](includes/reports-sales-statistics.md)]<br>Ce rapport peut également être utilisé dans la comptabilité client, car il est plus facile d’effectuer une recherche rapide des paiements, escomptes et ventes reportés pour un client donné.|
|**Liste des clients**|101| Affiche diverses informations de base sur les clients, par exemple le groupe de report, le groupe escompte, les informations sur les frais financiers et le paiement, le représentant, la devise par défaut du client et la limite de crédit dans votre devise locale (en $), ainsi que le solde actuel du client (en $). Le rapport permet, par exemple, de maintenir à jour les informations de la table Client.|

## <a name="see-also"></a>Voir aussi

[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Utilisation des dimensions](finance-dimensions.md)  
[Gestion des immobilisations](fa-manage.md)  
[Vue d’ensemble des fonctionnalités locales](about-localization.md)  
[Expériences de comptable dans [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
