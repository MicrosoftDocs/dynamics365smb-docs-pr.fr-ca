---
title: Configuration du groupe de report| Microsoft Docs
description: "Offre un aperçu des groupes comptabilisation"
services: project-madeira
documentationcenter: 
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting setup, initialize
ms.date: 03/24/2017
ms.author: bholtorf
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 79018546484ff3bb8965089a3554d69bec219304
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="posting-group-setups"></a>Configuration du groupe de report
Les groupes comptabilisation mappent des entités telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat dans des comptes généraux. Ils vous font gagner du temps et permettent d'éviter des erreurs lorsque vous reportez des transactions. Les valeurs de transaction vont dans les comptes spécifiés dans le groupe de report pour cette entité particulière. Il vous suffit seulement d'avoir un plan comptable. Pour plus d'informations, reportez-vous à [Configuration du plan comptable](finance-setup-chart-accounts.md).  

Les groupes comptabilisation sont traités dans trois catégories :  

* Général - définit à qui vous vendez et à qui vous achetez, et ce que vous vendez et ce que vous achetez. Vous pouvez aussi combiner des groupes pour spécifier des éléments comme les comptes états des résultats sur lesquels reporter ou utiliser des groupes pour filtrer les rapports.  
* Spécifique - permet d'utiliser des documents vente au lieu de reporter directement dans le grand livre. Lors de la création d'écritures dans le grand livre client, les écritures correspondantes sont passées dans le grand livre.  
* Taxe - définit les pourcentages de taxes et les types de calcul qui s'appliquent à l'acheteur et au vendeur, et à ce que vous vendez et ce que vous achetez.

Les tables suivantes décrivent les groupes comptabilisation dans chaque catégorie.  

| Groupes comptabilisation généraux | Description |
| --- | --- |
| Groupes comptabilisation marché |Affectez ce groupe aux clients et aux fournisseurs pour spécifier à qui vous vendez, et à qui vous achetez. Définissez cela dans la fenêtre **Groupes compta. marché**. Lorsque vous effectuez cette opération, vous devez prendre en compte le nombre de groupes nécessaires pour répartir les ventes et les achats. Par exemple, les groupes clients et fournisseurs peuvent être répartis par zone géographique ou par type d'activité. |
| Groupes comptabilisation produit |Affectez ce groupe à des articles et des ressources pour spécifier les éléments que vous vendez, et que vous achetez. Définissez cela dans la fenêtre **Groupes compta. produit**. Lorsque vous effectuez cette opération, vous devez considérer le nombre de groupes nécessaires pour répartir les ventes par article et ressource, et pour répartir les achats par article. Par exemple, divisez ces groupes par Matières premières, Vte détail, Ressources, Capacités, etc. |
| Config. paramètres report |Combinez les groupes de report marché et produit, puis choisissez les comptes à reporter. Pour chaque combinaison de groupes comptabilisation marché et produit, vous pouvez affecter un ensemble de comptes généraux. Par exemple, vous pouvez reporter la vente d'un même article dans différents comptes vente du grand livre car différents groupes de report marché sont affectés aux clients. Définissez cela dans la fenêtre **Paramètres comptabilisation**. |

| Groupes comptabilisation spécifiques | Description |
| --- | --- |
| Groupes de report du client |Définissez les comptes à utiliser lorsque vous reportez des transactions Comptabilité client. Si vous utilisez un inventaire conjointement avec des clients, le groupe de report marché affecté au client et le groupe de report produit affecté à l'article dans l'inventaire déterminent les comptes sur lesquels les écritures lignes document de vente effectuent le report. Définissez cela dans la fenêtre **Groupes compta. client**. |
| Groupes de report du fournisseur |Définissez où reporter les transactions des comptes fournisseur, des comptes frais forfaitaires, et des comptes d'escompte de paiement. Cela est similaire aux groupes comptabilisation client. Définissez cela dans la fenêtre **Groupes compta. fournisseur**. |
| Groupes de report d'inventaire |Définissez les comptes inventaire de bilan. Ils offrent également un bon moyen d'organiser votre inventaire, vous pouvez ainsi séparer des articles par groupe de report lors de la génération de rapports. Définissez cela dans la fenêtre **Groupes compta. stock**. |
| Groupes de report compte bancaire |Définissez des comptes bancaires. Par exemple, cela peut simplifier les processus de traçabilité des transactions et des rapprochements bancaires. Définissez cela dans la fenêtre **Groupes compta. banque**. |
| Groupes comptabilisation immobilisations |Définissez des comptes pour les différents types de dépenses et frais, tels que les coûts d'acquisition, les montants d'amortissement cumulés, les coûts d'acquisition sur cession, l'amortissement cumulé sur cession, les gains sur cession, les pertes sur cession, les frais d'entretien et les frais d'amortissement. Définissez cela dans la fenêtre **Groupes compta. immo.**. |

| Groupe de report TVA | Description |
| --- | --- |
| Paramètres report marché fiscal |Déterminez la manière de calculer et de reporter la taxe de vente pour les clients et les fournisseurs. Définissez cela dans la fenêtre **Groupes compta. marché TVA**. Lorsque vous le faites, pensez au nombre de groupes dont vous avez besoin. De nombreux facteurs peuvent entrer en jeu, notamment la législation locale, et le fait de travailler sur le marché national et international. |
| Paramètres report produit fiscal |Indiquez les calculs TVA nécessaires pour les types d'articles ou de ressources que vous achetez ou vendez. |
| Configuration de report de taxe |Combinez des groupes compta. marché et des groupes compta. produit TVA. Lorsque vous renseignez une ligne dans un journal général, une ligne achat, ou une ligne vente, nous allons consulter la combinaison pour identifier les comptes à utiliser. |

## <a name="example-of-linking-posting-groups"></a>Exemple de liaison de groupes comptabilisation
Voici un scénario.  

Ces groupes comptabilisation sont choisis dans la fiche client :  

* Groupe de report marché
* Groupe de report client  

Ces groupes comptabilisation sont choisis dans la fiche article :  

* Groupe de report produit  
* Groupe de report inventaire  

Lors de la création d'un document vente, l'en-tête vente utilise les informations de la fiche client et les lignes ventes utilisent les informations de la fiche article.  

* Le report revenus (état des résultats) est déterminée par la combinaison du groupe de report marché et du groupe de report produit.  
* Le report des ventes (bilan) est déterminé par le groupe de report client.  
* Le report de l'inventaire (bilan) est déterminé par le groupe de report inventaire.  
* Le report coût des biens vendus (état des résultats) est déterminé par la combinaison du groupe de report marché et du groupe de report produit.  

Votre configuration détermine quand le report a lieu. Par exemple, la synchronisation est affectée au moment où vous exécutez des activités périodiques, par exemple : reporter des coûts inventaire ou ajuster des écritures coût article.

## <a name="copying-posting-setup-lines"></a>Copie de lignes configuration report
Plus il y a de groupes de report produit et marché, plus la fenêtre Config. paramètres report contient de lignes. Cela peut entraîner la nécessité d'entrer un grand nombre de données pour configurer les paramètres de report pour la compagnie. S'il peut y avoir un grand nombre de combinaisons différentes de groupes de report marché et produit, différentes combinaisons peuvent encore reporter dans les mêmes comptes du grand livre. Pour limiter le nombre de saisies manuelles, copiez les comptes généraux à partir d'une ligne existante dans la fenêtre **Paramètres comptabilisation**.

## <a name="see-also"></a>Voir aussi .
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

