---
title: "Détails de conception\_-\_report du coût prévu"
description: 'Les coûts prévus représentent l''estimation, par exemple, du coût d''un article acheté que vous enregistrez avant la réception de la facture de cet article.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 07/20/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Détails de conception : report du coût prévu
Les coûts prévus représentent l'estimation, par exemple, du coût d'un article acheté que vous enregistrez avant la réception de la facture de cet article.  

 Vous pouvez reporter les coûts prévus dans l'inventaire et dans le grand livre. Lorsque vous reportez une quantité qui est uniquement reçue ou livrée mais pas facturée, une écriture valeur est créée avec le coût prévu. Ce coût prévu affecte la valeur de l'inventaire mais n'est pas reporté au compte du grand livre, sauf si vous avez configuré le programme à cette fin.  

> [!NOTE]  
>  Les coûts prévus sont gérés uniquement pour des transactions article. Les coûts prévus ne sont pas pour des types de transaction négligeables, tels que la capacité et les frais annexes.  

 Si seule la partie de quantité d'une augmentation d'inventaire a été reportée, la valeur d'inventaire dans le grand livre ne change pas, sauf si vous avez sélectionné la case à cocher **Report coût prévu au GL** sur la page **Configuration inventaire**. Dans ce cas, le coût prévu est reporté dans les comptes provisoires au moment de la réception. Une fois que la réception a été entièrement facturée, les comptes provisoires sont ensuite équilibrés et le coût réel est reporté dans le compte inventaire.  

 Pour prendre en charge le travail de rapprochement et de traçabilité, l'écriture valeur facturée montre que le coût indiqué prévu a été reporté pour équilibrer les comptes provisoires.  

## Conditions préalables au report des coûts prévus

Pour rendre possible le report des coûts prévus, vous devez procéder comme suit :
1. Dans la page **Configuration inventaire**, cochez la case **Report coûts automatique** et la case **Report coût prévu au GL**.
2. Configurez les comptes provisoires à utiliser pendant le processus de report des coûts prévus.  

  Dans la page **Configuration report inventaire**, vérifiez les champs **Compte inventaire** et **Compte inventaire (attente)** pour le **Code d’emplacement et Code groupe de report inventaire** de l’article que vous allez acheter. Pour en savoir plus sur ces comptes, voir [Détails de conception - Comptes du grand livre](design-details-accounts-in-the-general-ledger.md).
3. Dans la page **Configuration report**, vérifiez le champ **Compte ajust. inventaire (attente)** pour le **Groupe de report de marché** et le **Groupe de report de produit** que vous utiliserez.
4. Lorsque vous créez un bon de commande, la valeur par défaut est que le champ **N° facture fournisseur** est requis. Vous devez le désactiver dans la page **Configuration achats**, en désélectionnant le champ **N° doc. ext. obligatoire**.

## Exemple :  

> [!NOTE]  
> Les numéros de compte utilisés dans cet exemple servent uniquement de référence et seront différents dans votre système. Configurez-les comme indiqué dans les conditions préalables ci-dessus.

Vous reportez un bon de commande comme reçu. Le coût prévu est 95,00 $.  

 **Écritures de valeur**  

|Date de report|Type écriture|Coût indiqué (prévu)|Coût prévu reporté GL|Coût prévu|N° écriture article gr. livre|N° séquence |  
|------------------|----------------|------------------------------|----------------------------------|-------------------|---------------------------|---------------|  
|01/01/20|Coût direct|95.00|95.00|Oui|1|1|  

 **Liens des écritures dans le grand livre – Table liens grand livre article**  

|N° écriture comptable|N° écriture valeur|N° registre GL|  
|--------------------|---------------------|-----------------------|  
|1|1|1|  
|2|1|1|  

 **Écritures journal général**  

|Date de report|Compte général|N° compte (démonstration Fr-FR)|Montant|N° séquence |  
|------------------|------------------|---------------------------------|------------|---------------|  
|01/01/20|Compte ajustement inventaire (provisoire)|5530|-95,00|2|  
|01/01/20|Compte inventaire (attente)|2131|95.00|1|  

 Plus tard, vous reporterez le bon de commande comme facturé. Le coût facturé est 100,00 $.  

 **Écritures de valeur**  

|Date de report|Coût indiqué (réel)|Coût indiqué (prévu)|Coût reporté dans grand livre|Coût prévu|N° écriture article gr. livre|N° séquence |  
|------------------|----------------------------|------------------------------|-------------------------|-------------------|---------------------------|---------------|  
|15/01/20|100.00|-95,00|100.00|Non|1|2|  

 **Liens des écritures dans le grand livre – Table liens grand livre article**  

|N° écriture comptable|N° écriture valeur|N° registre GL|  
|--------------------|---------------------|-----------------------|  
|3|2|2|  
|4|2|2|  
|5|2|2|  
|6|2|2|  

 **Écritures journal général**  

|Date de report|Compte du grand livre|N° de compte (uniquement des exemples !)|Montant|N° séquence |  
|------------------|------------------|---------------------------------|------------|---------------|  
|15/01/20|Compte ajustement inventaire (provisoire)|5530|95.00|4|  
|15/01/20|Compte inventaire (attente)|2131|-95,00|3|  
|15/01/20|Compte coût direct affecté|7291|-100|6|  
|15/01/20|Compte inventaire|2130|100|5|  

## Voir aussi
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)   
 [Détails de conception : rapprochement de comptabilité](design-details-reconciliation-with-the-general-ledger.md)   
 [Détails de conception : comptabilisation stock](design-details-inventory-posting.md)   
 [Détails de conception : écart](design-details-variance.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
