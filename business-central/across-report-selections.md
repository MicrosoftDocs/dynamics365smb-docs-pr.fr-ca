---
title: "Sélection des rapports dans Business\_Central"
description: "Découvrez comment configurer les rapports que vous utilisez pour imprimer différents types de documents dans Business\_Central."
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: 'setup, reporting'
ms.search.form: '306, 307, 347, 385, 524, 865, 5932, 7401, 7355, 99000917'
ms.date: 06/09/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="report-selection-for-documents-in-business-central"></a>Sélection de rapport pour les documents dans Business Central

Vous pouvez configurer des rapports par défaut à utiliser pour imprimer des documents de vente, d’achat et de services, tels que des commandes, des devis et des factures. Par exemple, si vous avez une présentation spécifique pour les factures vente, vous pouvez spécifier ce rapport sur la page **Sélection des rapports - Vente** afin qu’elle soit utilisée pour envoyer ou imprimer les factures vente.  

## <a name="available-report-selections"></a>Sélection des rapports disponible

Les pages **Sélection des rapports** spécifient quel rapport sera imprimé dans différentes situations. [!INCLUDE [prod_short](includes/prod_short.md)] fournit des configurations par défaut, mais vous pouvez les modifier si nécessaire. Vous pouvez également ajouter des rapports aux pages **Sélection des rapports** si vous souhaitez imprimer plus d’un rapport par type de document, par exemple. 

Le tableau suivant décrit où vous pouvez trouver des informations sur les différentes pages.  

|Zone ou tâche  |En savoir plus|
|--------------|----------|
|Exemple de fonctionnement de la sélection des rapports (ventes)|[Sélection des rapports pour les documents de vente](#example-report-selection-for-sales-documents) ci-dessous|
|Présentation par défaut des courriels avec des documents vente et achat  |[Configurer des textes et des présentations de courriel réutilisables pour des documents vente et achat](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts) |
|Définir les mises en page de chèques     |[Sélectionner une mise en page de chèque](finance-how-define-check-layouts.md) |
|Définir des rapports pour la déclaration de taxe sur la valeur ajoutée (TVA) (Allemagne)|[Configurer les rapports pour la TVA et Intrastat](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md) |

> [!TIP]
> Votre [!INCLUDE [prod_short](includes/prod_short.md)] peut inclure des pages **Sélection des rapports** en fonction de votre emplacement et de votre secteur d’activité, par exemple. Pour vérifier votre configuration, sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sélection des rapports**, puis choisissez le lien approprié.

La version par défaut de [!INCLUDE [prod_short](includes/prod_short.md)] comprend les pages **Sélection des rapports** suivantes :

* **Sélection des rapports - Ventes**  
* **Sélection des rapports - Achats**  
* **Sélection des rapports - Inventaire**  
* **Sélection des rapports - Trésorerie**  
* **Sélection des rapports - Entrepôt**  
* **Sélection des rapports - Compte bancaire**  
* **Sélection des rapports - Projet**  
* **Sélection des rapports : Services**

## <a name="example-report-selection-for-sales-documents"></a>Exemple : Sélection des rapports pour les documents de vente

La page **Sélection des rapports - Ventes** présente les rapports par défaut à utiliser dans différents scénarios pour chaque type de document associé. Choisissez un type de document dans le champ **Usage**, puis ajoutez ou examinez la sélection des rapports. Vous pouvez configurer plusieurs rapports et spécifier l’ordre de séquence dans lequel les rapports doivent être envoyés ou imprimés.  

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Vous ne pouvez pas envoyer tous les types de documents sous forme de pièces jointes à des courriels. Lorsque cela est possible, la page **Sélection des rapports** contient des champs supplémentaires.  

Par exemple, dans les pages **Sélection des rapports - Ventes** et **Sélection des rapports -Achat**, les champs suivants vous aident à configurer l’envoi de courriels :

|Nom du champ |Désignation  |
|-----------|-------------|
|**Utiliser pour le corps du courriel**| Insérez des informations résumées, telles que le numéro de facture, la date d’échéance, ou un lien vers un service de paiement, dans un courriel.        |
|**Utiliser comme pièce jointe à un courriel**| Joignez le document correspondant au courriel.|
|**Description de la présentation du corps du courriel**|Spécifiez la présentation à utiliser pour le corps du courriel. En règle générale, la présentation du rapport est personnalisée. |

## <a name="see-also"></a>Voir aussi .

[Configurer des textes et des présentations de courriel réutilisables](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts)  
[Sélectionner une mise en page de chèque](finance-how-define-check-layouts.md)  
[Configurer les déclarations de TVA et Intrastat (Allemagne)](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md)  
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Rapports et analyses financiers dans Business Central](finance-reports.md)  
[Rapports comptabilité client et analyses d’immobilisation dans Business Central](receivables-reports.md)  
[Rapports comptabilité fournisseur et analyses d’immobilisation dans Business Central](payables-reports.md)  
[Rapports et analyses d’immobilisation dans Business Central](fa-reports.md)  
[Rapports et analyses de projet dans Business Central](project-reports.md)  
[Rapports et analyses de vente dans Business Central](sales-reports.md)  
[Rapports et analyses d'achat dans Business Central](purchase-reports.md)  
[Rapports et analyses d'inventaire et d’entrepôt dans Business Central](inventory-WMS-reports.md)  
[Rapports et analyses d’assemblage dans Business Central](assembly-reports.md)  
[Rapports et analyses de production dans Business Central](production-reports.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
