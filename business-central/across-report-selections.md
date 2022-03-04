---
title: Sélection des rapports dans Business Central
description: Découvrez comment configurer les rapports que vous utilisez pour imprimer différents types de documents dans Business Central.
author: edupont04
ms.topic: conceptual
ms.search.keywords: setup, reporting
ms.search.form: 306, 307, 347, 385, 524, 865, 5932, 7401, 7355, 99000917
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 16ad3480c10da544c7fdd3a6a299dc6d86cfce46
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8134066"
---
# <a name="report-selection-in-business-central"></a>Sélection des rapports dans Business Central

Vous pouvez configurer les rapports par défaut qui seront utilisés pour imprimer les divers documents vente et achat : commandes, devis, factures et notes de crédit. Par exemple, si vous avez une présentation spécifique pour les factures vente, vous pouvez spécifier ce rapport sur la page **Sélection des rapports - Vente** afin qu’elle soit utilisée pour envoyer ou imprimer les factures vente.  

Les pages **Sélection des rapports** spécifient quel rapport sera imprimé dans différentes situations. [!INCLUDE [prod_short](includes/prod_short.md)] inclut les configurations par défaut, mais vous pouvez modifier ces valeurs par défaut. Vous pouvez également ajouter des rapports aux pages **Sélection des rapports** si vous souhaitez imprimer plus d’un rapport par type de document, par exemple.  

## <a name="available-report-selections"></a>Sélection des rapports disponible

[!INCLUDE [prod_short](includes/prod_short.md)] comprend différentes pages **Sélection des rapports** pour différents domaines. Les tableaux suivants décrivent où vous pouvez trouver des informations sur les différentes pages.  

|Zone ou tâche  |En savoir plus|
|--------------|----------|
|Exemple de fonctionnement de la sélection des rapports (Sales)|[Sélection des rapports pour les documents de vente](#example-report-selection-for-sales-documents)|
|Présentation par défaut des courriels avec des documents vente et achat  |[Configurer des textes et des présentations de courriel réutilisables pour les documents vente et achat](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts-for-sales-and-purchase-documents) |
|Définir les mises en page de chèques     |[Sélectionner une mise en page de chèque](finance-how-define-check-layouts.md) |
|Définir des rapports pour la déclaration de TVA (Allemagne)|[Configurer les rapports pour la TVA et Intrastat](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md) |

> [!TIP]
> Votre [!INCLUDE [prod_short](includes/prod_short.md)] peut inclure des pages **Sélection des rapports** en fonction de votre emplacement et de votre secteur d’activité, par exemple. Vous pouvez toujours vérifier votre configuration en choisissant l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") en saisissant **Sélection des rapports**, puis choisissez le lien approprié.

La version par défaut de [!INCLUDE [prod_short](includes/prod_short.md)] comprend les pages suivantes **Section des rapports** :

* **Sélection des rapports - Ventes**  
* **Sélection des rapports - Achats**  
* **Sélection des rapports - Inventaire**  
* **Sélection des rapports - Trésorerie**  
* **Sélection des rapports - Entrepôt**  
* **Sélection des rapports - Compte bancaire**  
* **Sélection des rapports - Rappel/Frais financiers**  

## <a name="example-report-selection-for-sales-documents"></a>Exemple : Sélection des rapports pour les documents de vente

La page **Sélection des rapports - Ventes** définit les rapports par défaut à utiliser dans différents scénarios pour chaque type de document associé. Choisissez un type de document dans le champ **Utilisation**, puis ajoutez ou examinez la sélection des rapports. Vous pouvez configurer plusieurs rapports et l’ordre de séquence dans lequel les rapports doivent être envoyés ou imprimés.  

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Certains types de documents peuvent être envoyés sous forme de pièces jointes à un courriel, et d’autres non. Chaque page **Sélection des rapports** affiche des champs supplémentaires si le type de courriel de support est prêt à l’emploi.  

Par exemple, dans les pages **Sélection des rapports - Ventes** et **Sélection des rapports -Achat**, les champs suivants vous aident à configurer l’envoi de courriels :

|Nom du champ |Description  |
|-----------|-------------|
|**Utiliser pour le corps du courriel**| Spécifie que les informations résumées, telles que le numéro de facture, la date d'échéance et le lien de service de paiement, vont être insérées dans le corps du courriel que vous envoyez.        |
|**Utiliser comme pièce jointe à un courriel**| Spécifie que le document associé sera joint au courriel.|
|**Description de la présentation du corps du courriel**|Spécifie la présentation du corps du courriel utilisée, généralement une présentation de rapport personnalisée. |

## <a name="see-also"></a>Voir aussi

[Configurer des textes et des présentations de courriel réutilisables pour les documents vente et achat](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts-for-sales-and-purchase-documents)  
[Sélectionner une mise en page de chèque](finance-how-define-check-layouts.md)  
[Configurer les déclarations de TVA et Intrastat (Allemagne)](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md)  
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]