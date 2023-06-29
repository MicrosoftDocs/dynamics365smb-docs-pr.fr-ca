---
title: "Détails de conception\_: comptes du grand livre | Microsoft Docs"
description: 'Pour rapprocher l''inventaire et les écritures du grand livre de capacité dans le grand livre, les écritures valeur associées sont reportées dans différents comptes dans le grand livre.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/08/2021
ms.author: edupont
---
# <a name="design-details-accounts-in-the-general-ledger"></a><a name="design-details-accounts-in-the-general-ledger"></a>Détails de conception : comptes du grand livre
Pour rapprocher l'inventaire et les écritures du grand livre de capacité dans le grand livre, les écritures valeur associées sont reportées dans différents comptes dans le grand livre. Pour plus d'informations, voir [Détails de conception : rapprochement de comptabilité](design-details-reconciliation-with-the-general-ledger.md).  

## <a name="from-the-inventory-ledger"></a><a name="from-the-inventory-ledger"></a>À partir de la comptabilité inventaire
Le tableau suivant montre les relations entre différents types d'écritures de valeur de l'inventaire et les comptes et les comptes de solde dans le grand livre.  

|**Type d'écriture gr. livre art.**|**Type écriture valeur**|**Type écart**|**Coût prévu**|**Compte**|**Compte de contrepartie**|  
|--------------------------------|--------------------------|-----------------------|-----------------------|-----------------|---------------------------|  
|Achat|Coût direct||Oui|Inventaire (provisoire)|Compte ajust. stock (attente)|  
|Achat|Coût direct||Non|Stocks|Coûts directs affectés|  
|Achat|Coût indirect||Non|Stocks|Coûts indirects affectés|  
|Achat|Écart|Achat|Non|Stocks|Écart achat|  
|Achat|Réévaluation||Non|Stocks|Ajustement des stocks|  
|Achat|Arrondissement||Non|Stocks|Ajustement des stocks|  
|Vente|Coût direct||Oui|Inventaire (provisoire)|CPV (intérimaire)|  
|Vente|Coût direct||Non|Stocks|COGS|  
|Vente|Réévaluation||Non|Stocks|Ajustement des stocks|  
|Vente|Arrondissement||Non|Stocks|Ajustement des stocks|  
|Ajust. positif,Ajust. négatif, Transfert|Coût direct||Non|Stocks|Ajustement des stocks|  
|Ajust. positif,Ajust. négatif, Transfert|Réévaluation||Non|Stocks|Ajustement des stocks|  
|Ajust. positif,Ajust. négatif, Transfert|Arrondissement||Non|Stocks|Ajustement des stocks|  
|(Production) Consommation|Coût direct||Non|Stocks|TEC|  
|(Production) Consommation|Réévaluation||Non|Stocks|Ajustement des stocks|  
|(Production) Consommation|Arrondissement||Non|Stocks|Ajustement des stocks|  
|Consommation d'assemblage|Coût direct||Non|Stocks|Ajustement des stocks|  
|Consommation d'assemblage|Coût direct||Non|Coûts directs affectés|Ajustement des stocks|  
|Consommation d'assemblage|Coût indirect||Non|Coûts indirects affectés|Ajustement des stocks|  
|(Production) Production|Coût direct||Oui|Inventaire (provisoire)|TEC|  
|(Production) Production|Coût direct||Non|Stocks|TEC|  
|(Production) Production|Coût indirect||Non|Stocks|Coûts indirects affectés|  
|(Production) Production|Écart|Matières|Non|Stocks|Écart sur matières|  
|(Production) Production|Écart|Capacité|Non|Stocks|Écart sur capacité|  
|(Production) Production|Écart|En sous-traitance|Non|Stocks|Écart en sous-traitance|  
|(Production) Production|Écart|Utilisation fixe de capacité|Non|Stocks|Ecarts frais généraux op.|  
|(Production) Production|Écart|Frais généraux matière|Non|Stocks|Fabric. Écart frais généraux|  
|(Production) Production|Réévaluation||Non|Stocks|Ajustement des stocks|  
|(Production) Production|Arrondissement||Non|Stocks|Ajustement des stocks|  
|Résultat d'assemblage|Coût direct||Non|Stocks|Ajustement des stocks|  
|Résultat d'assemblage|Réévaluation||Non|Stocks|Ajustement des stocks|  
|Résultat d'assemblage|Coût indirect||Non|Stocks|Coûts indirects affectés|  
|Résultat d'assemblage|Écart|Matières|Non|Stocks|Écart sur matières|  
|Résultat d'assemblage|Écart|Capacité|Non|Stocks|Écart sur capacité|  
|Résultat d'assemblage|Écart|Utilisation fixe de capacité|Non|Stocks|Ecarts frais généraux op.|  
|Résultat d'assemblage|Écart|Frais généraux matière|Non|Stocks|Fabric. Écart frais généraux|  
|Résultat d'assemblage|Arrondissement||Non|Stocks|Ajustement des stocks|  

## <a name="from-the-capacity-ledger"></a><a name="from-the-capacity-ledger"></a>À partir du grand livre de capacité
 Le tableau suivant montre les relations entre les différents types d'écritures de valeur de capacité et les comptes et les comptes de solde dans le grand livre. Les écritures du grand livre de capacité représentent le temps de travail consommé dans l'assemblage ou la charge de production.  

|**Type travail**|**Type écriture capacité**|**Type écriture valeur**|**Compte**|**Compte de contrepartie**|  
|-------------------|------------------------------------|--------------------------|-----------------|---------------------------|  
|Assemblage|Ressource|Coût direct|Coûts directs affectés|Ajustement des stocks|  
|Assemblage|Ressource|Coût indirect|Coûts indirects affectés|Ajustement des stocks|  
|Fabrication|Unité de production/Atelier|Coût direct|Compte TEC|Coûts directs affectés|  
|Fabrication|Unité de production/Atelier|Coût indirect|Compte TEC|Coûts indirects affectés|  

## <a name="assembly-costs-are-always-actual"></a><a name="assembly-costs-are-always-actual"></a>Les coûts d'assemblage sont toujours réels
 Comme indiqué dans le tableau ci-dessus, les validations d'assemblage ne sont pas représentées dans les comptes d'attente. Ceci s'explique par le fait que le concept de travail en cours (TEC) ne s'applique pas au report des résultats d'assemblage, contrairement au report des résultats de production. Les coûts d'assemblage sont uniquement reportés en tant que coûts réels, jamais en tant que coûts prévus.  

 Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-assembly-order-posting.md).  

## <a name="calculating-the-amount-to-post-to-the-general-ledger"></a><a name="calculating-the-amount-to-post-to-the-general-ledger"></a>Calcul du montant à reporter dans le grand livre
 Les champs suivants de la table **Ecritures valeur** permettent de calculer le coût total prévu qui est validé dans les écritures comptables :  

-   Coût indiqué (réel)  
-   Coût reporté dans grand livre  
-   Coût indiqué (prévu)  
-   Coût prévu reporté GL  

Le tableau suivant montre la manière dont les montants à reporter dans le grand livre sont calculés pour les deux types de coût différents.  

|Type coût|Calcul|  
|---------------|-----------------|  
|Coût réel|Coût indiqué (réel) - Coût reporté au GL.|  
|Coût prévu|Coût indiqué (prévu) - Coût prévu reporté au GL|  

## <a name="see-also"></a><a name="see-also"></a>Voir aussi
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : comptabilisation stock](design-details-inventory-posting.md)   
 [Détails de conception : validation du coût prévu](design-details-expected-cost-posting.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
