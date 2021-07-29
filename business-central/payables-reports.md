---
title: Rapports Comptabilité fournisseur et analyse
description: Découvrez les rapports et analyses disponibles dans la version standard de Business Central afin que vous puissiez suivre vos comptes fournisseur.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont
ms.openlocfilehash: 774fd24bc15cb4cefb56991289d9c72c0909a319
ms.sourcegitcommit: a486aa1760519c380b8cdc8fdf614bed306b65ea
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/13/2021
ms.locfileid: "6543396"
---
# <a name="accounts-payable-reports-and-analytics-in-business-central"></a>Rapports comptabilité fournisseur et analyses d’immobilisation dans Business Central

Pour vous aider à gérer votre comptabilité fournisseur dans [!INCLUDE [prod_short](includes/prod_short.md)], des rapports et des analyses standard sont intégrés. Ils vont au-delà des contraintes des rapports traditionnels pour vous aider à concevoir efficacement divers types de rapports.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports de comptabilité fournisseur.

| Rapport | Code objet | Description |
|--|--|--|
| **Comptes fournisseurs classés chronologiquement** | 322|Affiche les soldes échus pour les fournisseurs dans les intervalles de temps en souffrance. Les montants en souffrance peuvent être affichés par date d’échéance, date de report ou par date de document selon les besoins. Vous pouvez choisir d’afficher les montants en devise locale ($) et d’imprimer les détails des documents en retard. Les intervalles de temps peuvent avoir des en-têtes avec des dates ou avec un nombre de dates échues, par rapport à l’ancienneté spécifiée par type.<br>Ce rapport est le rapport principal pour le rapprochement du grand livre de fournisseur avec la grand livre. En supposant que vous n’ayez pas autorisé le report direct sur les comptes utilisés dans le grand livre fournisseurs des groupes de report, ce rapport est une spécification des montants que vous trouvez en grand livre.|
| **Fournisseur - Solde à ce jour** | 321 | Affiche le solde du fournisseur à la date de fin de la plage de dates spécifiée. Vous pouvez choisir d’afficher le solde du fournisseur dans votre devise locale ($). Sélectionnez le champ **Inclure les écritures non affectées** pour afficher les écritures qui ont été fermées à la date de fin, mais qui ont été désaffectées (ouvertes) à une date ultérieure. Sélectionnez le champ **Afficher les écritures avec un solde nul** pour afficher les fournisseurs avec un solde nul selon la date de fin du filtre de date. Le filtre de date s’applique aux écritures fournisseur détaillées pour les écritures du rapport. Si vous avez des paiements postérieurs à la date de fin qui ont été affectés à des factures dans la plage de dates, les factures apparaîtront dans le rapport, car elles n’ont pas été fermées à la date de fin. |
| **Fournisseur - Balance de vérification** | 329 | Affiche les écarts nets pour les fournisseurs pour la période spécifiée dans le filtre de date ainsi que les écarts nets depuis le début de l’exercice financier correspondant à la période sélectionnée. Le rapport est regroupé par groupes de report des fournisseurs et donne une vue du grand livre de fournisseur différente du rapport **Comptabilités fournisseur chronologiques**. **Remarque** : si vous n’avez pas configuré de période comptable, le système ne saura pas quel exercice financier utiliser et affichera le cumul annuel à partir du dernier exercice financier défini ou sélectionnera simplement la période, qui peut ou non être dès le début d’une année.|
| **Fournisseur - Balance de vérification détaillée** | 304 | Affiche toutes les écritures fournisseur dans le filtre de date spécifié. Le rapport affiche les soldes d’ouverture du fournisseur par rapport au filtre de date. |
| **Statistiques achat** |312 |[!INCLUDE [reports-purchase-statistics](includes/reports-purchase-statistics.md)]<br>Ce rapport peut également être utilisé dans la comptabilité fournisseurs, car il est plus facile d’effectuer une recherche rapide des paiements, escomptes et autres transactions reportés pour un fournisseur donné.|
|**Fournisseur - chronologie sommaire**|305| Rapport hérité pour la comptabilité fournisseur chronologique. Nous vous recommandons d’utiliser le rapport **Comptabilités fournisseur chronologiques** à la place. Vous pouvez choisir une durée de période et une date à définir comme date *échue*.|
|**Paiements suspendus**|319|Affiche les écritures fournisseur où le champ **En attente** n’est pas vide.|
|**Journal des paiements anticipés du fournisseur**|317|Affiche le journal des paiements avec les informations d’escompte de paiement et de tolérance. Le rapport peut être utilisé pour vérifier les paiements avant de créer des fichiers de paiement et de reporter le journal. **Remarque** : Le rapport affichera les escomptes de paiement de manière incorrecte lorsque plusieurs notes de crédit ont été utilisées dans une affectation. Dans ce cas, l’escompte de paiement de paiement pour les notes de crédit supplémentaires sera affiché comme montant non affecté.|
|**Liste des fournisseurs**|301|Affiche diverses informations de base sur les fournisseurs, par exemple le groupe de report, le groupe escompte, les informations sur les escomptes et le paiement, la priorité, et la devise par défaut du fournisseur, ainsi que le solde actuel du fournisseur (en $). Le rapport peut être utilisé, par exemple, pour maintenir à jour les informations de la table Fournisseur.|

## <a name="see-also"></a>Voir aussi

[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Utilisation des dimensions](finance-dimensions.md)  
[Gestion des immobilisations](fa-manage.md)  
[Vue d’ensemble des fonctionnalités locales](about-localization.md)  
[Expériences de comptable dans [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
