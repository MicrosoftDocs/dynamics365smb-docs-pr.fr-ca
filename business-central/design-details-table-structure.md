---
title: Détails de conception- Structure de la table | Microsoft Docs
description: Pour comprendre comment le stockage et le report d'écriture de dimension sont conçus, il est important de comprendre la structure de tableau.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 1dccea4f700f8cf141e05058b54fd20d62665b7b
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3910990"
---
# <a name="design-details-table-structure"></a>Détails de conception : structure de la table
Pour comprendre comment les écritures dimension sont enregistrées et reportées, il est important de comprendre la structure de la table.  

## <a name="table-480-dimension-set-entry"></a>Table 480, Écriture ensemble de dimensions  
Vous ne pouvez pas modifier cette table. Une fois les données écrites dans la table, vous ne pouvez plus les supprimer ou les modifier.

|N° champ|Nom de champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|1|**Code**|Entier|>0,0 est réservé à l'ensemble de dimensions vide. Champ de références 3 dans la table 481.|  
|2|**Code axe analytique**|Code 20|Relation de table avec la table 348.|  
|3|**Code section**|Code 20|Relation de table avec la table 349.|  
|4|**ID section analytique**|Entier|Champ de références 12 dans la table 349. Ce champ est la clé secondaire utilisée en parcourant la table 481.|  
|5|**Nom axe analytique**|Texte 30|CalcField. Rechercher dans la table 348.|  
|6|**Nom de la valeur de dimension**|Texte 30|CalcField. Rechercher dans la table 349.|  

## <a name="table-481-dimension-set-tree-node"></a>Table 481, Nœud d'arbre ensemble de dimensions  
Vous ne pouvez pas modifier cette table. Elle est utilisée pour trouver un ensemble de dimensions. Si l'ensemble de dimensions est introuvable, un nouvel ensemble est créé.  

|N° champ|Nom du champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|1|**ID ensemble de dimensions parent**|Entier|0 pour le nœud de niveau supérieur.|  
|2|**ID section analytique**|Entier|Relation de la table avec le champ 12 de la table 349.|  
|3|**ID ensemble de dimensions**|Entier|Incrémentez automatiquement. Utilisé dans le champ 1 du tableau 480.|  
|4|**Utilisé**|Booléen|Faux si non utilisé.|  

## <a name="table-482-reclas-dimension-set-buffer"></a>Table 482, Tampon ensemble de dimensions reclass.  
Cette table est utilisée lorsque vous modifiez un code valeur de dimension, par exemple, pour une écriture article en utilisant la page **Journal reclassement article** .  

|N° champ|Nom de champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|1|**Code de dimension**|Code 20|Relation de table avec la table 348.|  
|2|**Code section**|Code 20|Relation de table avec la table 349.|  
|3|**ID section analytique**|Entier|Champ de références 12 dans la table 349.|  
|4|**Nouveau code section**|Code 20|Relation de table avec la table 349.|  
|5|**ID nouvelle section analytique**|Entier|Champ de références 12 dans la table 349.|  
|6|**Nom axe analytique**|Texte 30|CalcField. Rechercher dans la table 348.|  
|7|**Nom de la section analytique**|Texte 30|CalcField. Rechercher dans la table 349.|  
|8|**Nom nouvelle valeur de dimension**|Texte 30|CalcField. Rechercher dans la table 349.|  

## <a name="transaction-and-budget-tables"></a>Transaction et tableaux de budget  
En plus des autres champs de dimension dans la table, ce champ est important :  

|N° champ|Nom de champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|480|**Code ensemble de dimensions**|Entier|Champ de références 1 dans la table 480.|  

### <a name="table-83-item-journal-line"></a>Table 83, Ligne journal article  
En plus des autres champs de dimension dans la table, les champs suivants sont importants.  

|N° champ|Nom de champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|480|**Code ensemble de dimensions**|Entier|Champ de références 1 dans la table 480.|  
|481|**Code du nouvel ensemble de dimensions**|Entier|Champ de références 1 dans la table 480.|  

### <a name="table-349-dimension-value"></a>Table 349, Valeur de dimension  
En plus des autres champs de dimension dans la table, les champs suivants sont importants.  

|N° champ|Nom de champ|Type de données|Commentaire|  
|---------------|----------------|---------------|-------------|  
|12|**Code valeur de dimension**|Entier|Incrémentez automatiquement. Utilisé pour références dans le tableau 480 et le tableau 481.|  

### <a name="tables-that-contain-the-dimension-set-id-field"></a>Tables qui contiennent le champ Code ensemble de dimensions
 Le champ **Code ensemble de dimensions** (480) existe dans les tables suivantes. Pour les tables qui stockent des données reportées, le champ fournit seulement un affichage non modifiable des dimensions, marqué comme vue détaillée. Pour les tables qui stockent des documents de travail, le champ peut être modifié. Les tables tampon qui sont utilisées en interne n'ont pas besoin de fonctionnalités modifiables ou non modifiables.  

 Le champ 480 ne peut pas être modifié dans les tables suivantes.  

|Numéro table|Nom de la table|  
|---------------|----------------|  
|17|**Écritures comptables**|  
|21|**Écritures compte client**|  
|25|**Écriture fournisseur**|  
|32|**Écriture article**|  
|110|**En-tête expédition vente**|  
|111|**Ligne expédition vente**|  
|112|**En-tête facture vente**|  
|113|**Ligne facture vente**|  
|114|**En-tête avoir vente**|  
|115|**Ligne avoir vente**|  
|120|**En-tête réception achat**|  
|121|**Ligne réception achat**|  
|122|**En-tête facture achat**|  
|123|**Ligne facture achat**|  
|124|**En-tête avoir achat**|  
|125|**Ligne avoir achat**|  
|169|**Écriture comptable projet**|  
|203|**Écriture comptable ressource**|  
|271|**Écriture comptable compte bancaire**|  
|281|**Écriture comptable inventaire**|  
|297|**En-tête relance émise**|  
|304|**En-tête fact. d'intérêts émise**|  
|5107|**Archives en-tête vente**|  
|5108|**Archives ligne vente**|  
|5109|**Archives en-tête achat**|  
|5110|**Archives ligne achat**|  
|5601|**Écriture comptable immobilisation**|  
|5625|**Écriture comptable maintenance**|  
|5629|**Écriture comptable couverture assurance**|  
|5744|**En-tête expédition transfert**|  
|5745|**Ligne expédition transfert**|  
|5746|**En-tête réception transfert**|  
|5747|**Ligne réception transfert**|  
|5802|**Écriture valeur**|  
|5832|**Écriture comptable capacité**|  
|5907|**Écriture comptable service**|  
|5908|**En-tête service**|  
|5933|**Tampon valid. cde service**|  
|5970|**En-tête contrat serv. archivé**|  
|5990|**En-tête expédition service**|  
|5991|**Ligne expédition service**|  
|5992|**En-tête facture service**|  
|5993|**Ligne facture service**|  
|5994|**En-tête avoir service**|  
|5995|**Ligne avoir service**|  
|6650|**En-tête expédition retour**|  
|6651|**Ligne livraison retour**|  
|6 660|**En-tête réception retour**|  
|6 661|**Ligne réception retour**|  

Le champ 480 peut être modifié dans les tables suivantes.  

|Numéro table|Nom de la table|  
|---------------|----------------|  
|36|**En-tête vente**|  
|37|**Ligne vente**|  
|38|**En-tête achat**|  
|39|**Ligne achat**|  
|81|**Ligne journal général**|  
|83|**Ligne journal article**|  
|89|**Ligne feuille nomenclature**|  
|96|**Écriture budget GL**|  
|207|**Ligne journal ressource**|  
|210|**Ligne journal projets**|  
|221|**Ventilation feuille compta**|  
|246|**Ligne proposition achat**|  
|295|**En-tête relance**|  
|302|**En-tête facture d'intérêts**|  
|5405|**Ordre de fabrication**|  
|5406|**Ligne O.F.**|  
|5407|**Composant O.F.**|  
|5615|**Ventilation immo**|  
|5621|**Ligne feuille immo.**|  
|5635|**Ligne feuille assurance**|  
|5740|**En-tête transfert**|  
|5741|**Ligne transfert**|  
|5900|**En-tête service**|  
|5901|**Ligne article de service**|  
|5902|**Ligne service**|  
|5965|**En-tête contrat service**|  
|5997|**Ligne service standard**|  
|7 134|**Écriture budget article**|  
|99 000 829|**Composante planification**|  

Le champ 480 existe dans les tables suivantes.  

|Numéro table|Nom de la table|  
|---------------|----------------|  
|49|**Tampon report facture**|  
|212|**Tampon validation projet**|  
|372|**Tampon paiement**|  
|382|**Tampon écriture CF**|  
|461|**Tampon ligne fact. paiement anticipé**|  
|5637|**GL tampon report immo.**|  
|7136|**Tampon de budget d'article**|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : écritures d'ensemble de dimensions](design-details-dimension-set-entries.md)   
 [Aperçu des écritures d'ensemble de dimensions](design-details-dimension-set-entries-overview.md)   
 [Détails de conception : recherche des combinaisons de dimensions](design-details-searching-for-dimension-combinations.md)   
 


[!INCLUDE[footer-include](includes/footer-banner.md)]