---
title: Sélection des rapports dans Business Central
description: Découvrez comment configurer les rapports que vous utilisez pour imprimer différents types de documents dans Business Central.
author: edupont04
ms.topic: conceptual
ms.search.keywords: setup, reporting
ms.search.form: 306, 307, 347, 385, 524, 865, 5932, 7401, 7355, 99000917
ms.date: 03/11/2022
ms.author: edupont
ms.openlocfilehash: 9106b1ac3f6b179e26c8dfb01212b88e92b694fe
ms.sourcegitcommit: 7b6d70798b4da283d1d3e38a05151df2209c2b72
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/12/2022
ms.locfileid: "8950209"
---
# <a name="report-selection-in-business-central"></a>Sélection des rapports dans Business Central

Vous pouvez configurer des rapports par défaut à utiliser pour imprimer des documents de vente et d’achat, tels que des commandes, des devis et des factures. Par exemple, si vous avez une présentation spécifique pour les factures vente, vous pouvez spécifier ce rapport sur la page **Sélection des rapports - Vente** afin qu’elle soit utilisée pour envoyer ou imprimer les factures vente.  

Les pages **Sélection des rapports** spécifient quel rapport sera imprimé dans différentes situations. [!INCLUDE [prod_short](includes/prod_short.md)] fournit des configurations par défaut, mais vous pouvez les modifier si nécessaire. Vous pouvez également ajouter des rapports aux pages **Sélection des rapports** si vous souhaitez imprimer plus d’un rapport par type de document, par exemple.  

## <a name="available-report-selections"></a>Sélection des rapports disponible

[!INCLUDE [prod_short](includes/prod_short.md)] comprend différentes pages **Sélection des rapports** pour différents domaines. Le tableau suivant décrit où vous pouvez trouver des informations sur les différentes pages.  

|Zone ou tâche  |En savoir plus|
|--------------|----------|
|Exemple de fonctionnement de la sélection des rapports (Sales)|[Sélection des rapports pour les documents de vente](#example-report-selection-for-sales-documents)|
|Présentation par défaut des courriels avec des documents vente et achat  |[Configurer des textes et des présentations de courriel réutilisables pour des documents vente et achat](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts) |
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
* **Sélection des rapports - Projet**  

## <a name="example-report-selection-for-sales-documents"></a>Exemple : Sélection des rapports pour les documents de vente

La page **Sélection des rapports - Ventes** définit les rapports par défaut à utiliser dans différents scénarios pour chaque type de document associé. Choisissez un type de document dans le champ **Utilisation**, puis ajoutez ou examinez la sélection des rapports. Vous pouvez configurer plusieurs rapports et l’ordre de séquence dans lequel les rapports doivent être envoyés ou imprimés.  

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Certains types de document peuvent être envoyés sous forme de pièces jointes à un courriel, et d’autres non. Si un type de document peut être envoyé par courriel, la page **Sélection des rapports** contiendra des champs supplémentaires.  

Par exemple, dans les pages **Sélection des rapports - Ventes** et **Sélection des rapports -Achat**, les champs suivants vous aident à configurer l’envoi de courriels :

|Nom du champ |Désignation  |
|-----------|-------------|
|**Utiliser pour le corps du courriel**| Insérez des informations résumées, telles que le numéro de facture, la date d’échéance et le lien de service de paiement, dans un courriel.        |
|**Utiliser comme pièce jointe à un courriel**| Joignez le document correspondant au courriel.|
|**Description de la présentation du corps du courriel**|Spécifiez la présentation à utiliser pour le corps du courriel. En règle générale, la présentation est une présentation de rapport personnalisée. |

## <a name="see-also"></a>Voir aussi .

[Configurer des textes et des présentations de courriel réutilisables](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts)  
[Sélectionner une mise en page de chèque](finance-how-define-check-layouts.md)  
[Configurer les déclarations de TVA et Intrastat (Allemagne)](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md)  
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Rapports et analyses financiers dans Business Central](finance-reports.md)  
[Rapports et analyses de comptabilité client dans Business Central](receivables-reports.md) 
[Rapports et analyses de comptabilité fournisseur dans Business Central](payables-reports.md)  
[Rapports et analyses d’immobilisation dans Business Central](fa-reports.md)  
[Rapports et analyses de projet dans Business Central](project-reports.md)  
[Rapports et analyses de vente dans Business Central](sales-reports.md)  
[Rapports et analyses d'achat dans Business Central](purchase-reports.md)  
[Rapports et analyses d'inventaire et d’entrepôt dans Business Central](inventory-WMS-reports.md)  
[Rapports et analyses d’assemblage dans Business Central](assembly-reports.md)  
[Rapports et analyses de production dans Business Central](production-reports.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]