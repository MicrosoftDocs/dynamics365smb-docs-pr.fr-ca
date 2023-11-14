---
title: Vue d’ensemble des processus sortants de l’entrepôt
description: Cet article décrit le flux de travail sortant de l’entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 11/25/2022
ms.custom: bap-template
---
# Processus sortants de l’entrepôt

Les processus sortants de l’entrepôt démarrent lorsque vous libérez un document source pour sortir des articles d’un emplacement d’entrepôt. Par exemple, soit pour livrer les articles quelque part, soit pour les déplacer vers un autre emplacement de l’entreprise. Vous pouvez livrer des articles physiques et hors inventaire. Pour en savoir plus sur la réception d’articles hors inventaire, consultez [Reporter des articles hors inventaire](#post-non-inventory-items). 

En principe, le processus d’expédition des commandes sortantes se compose de deux activités :

* Prélèvement des articles sur les tablettes.
* Expédier les articles hors de l’entrepôt.

Les documents origine pour le flux d’entrepôt sortant sont les suivants :  

* Document de vente  
* Ordre de transfert sortant  
* Retour commande achat  
* Commande service  

> [!NOTE]
> Les besoins en composantes des ordres de fabrication et d’assemblage représentent également des documents source sortants. Les ordres de fabrication et d’assemblage sont un peu différents car il s’agit généralement de processus internes qui n’impliquent pas d’expédition. Au lieu de cela, ils sont utilisés pour ranger les articles produits ou déplacer les composantes nécessaires pour assembler un article vers une zone d’assemblage. Pour en savoir plus sur ces processus, consultez [Design Details : flux d’entrepôt internes](design-details-internal-warehouse-flows.md).  

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous prélevez et livrez des articles en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus sortant|Prélèvement requis|Livraison requise|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report du prélèvement et de la livraison à partir d’un document prélèvement inventaire|Activé||De base : commande par commande.|  
|C|Report du prélèvement et de la livraison à partir d’un document livraison entrepôt||Activé|De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report du prélèvement à partir d’un document prélèvement entrepôt, et report de la livraison à partir d’un document livraison entrepôt|Activé|Activé|Avancé|  

Le choix d’une méthode dépend des pratiques de stockage de votre société et de la complexité de son organisation. Voici quelques exemples qui peuvent vous aider à décider.

* Dans un environnement par commande avec des processus et une structure de zone simples, la méthode A, de prélèvement et d’expédition à partir de la ligne commande, est appropriée.
* Si les articles d’une ligne commande proviennent de plusieurs zones, ou si les employés d'entrepôt ne peuvent pas travailler avec des documents de commande, l’utilisation de documents de prélèvement distincts est appropriée; c’est la méthode B.
* Si vos processus de prélèvement et de livraison impliquent plusieurs commandes et nécessitent un contrôle et une vue d’ensemble accrus, vous pouvez choisir d’utiliser un document de livraison entrepôt et un document de prélèvement entrepôt pour séparer les tâches de prélèvement et de livraison : méthodes C et D.  

Dans les méthodes A, B et C, les activités de prélèvement et de livraison sont combinées en une étape lors du report d’un document comme étant livré. Dans la méthode D, vous enregistrez d’abord le prélèvement, puis vous reportez la livraison à partir d’un document différent.

> [!NOTE]
> Bien que les prélèvements entrepôt et les prélèvements inventaire semblent similaires, ce sont des documents différents et ils sont utilisés dans des processus différents.
> * Le prélèvement inventaire utilisé dans la méthode B, ainsi que l’enregistrement des informations de prélèvement, reporte également la livraison du document source.
> * Le prélèvement entrepôt utilisé dans la méthode D ne peut pas être reporté et enregistre uniquement le prélèvement. L’enregistrement rend les articles disponibles pour la livraison entrepôt, mais ne reporte pas la livraison. Dans le flux sortant, le prélèvement entrepôt nécessite une livraison entrepôt.

## Aucune activité entrepôt dédiée

Les articles suivants fournissent des informations sur le traitement des réceptions pour les documents origine si vous n’avez pas d’activités entrepôt dédiées.

* [Vendre des produits](sales-how-sell-products.md)
* [Ordres de transfert](inventory-how-transfer-between-locations.md)
* [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md)
* [Créer commande service](service-how-to-create-service-orders.md)

## Configurations d’entrepôt de base

Le schéma suivant présente les processus d’entrepôt sortants pour différents types de document dans les configurations d’entrepôt de base. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

:::image type="content" source="media/design-details-warehouse-management-outbound-basic-flow.png" alt-text="Affiche les étapes d’un flux sortant de base dans un entrepôt.":::

### 1 : Libérer un document source

Lorsque vous utilisez l’action **Libérer** sur un document source, tel qu’un document de vente ou un ordre de transfert, les articles du document sont prêts à être traités dans l’entrepôt. Par exemple, prélevés et placés dans la zone spécifiée sur le document. Sinon, vous pouvez créer des documents prélèvement inventaire pour des lignes commande individuelles, en mode « push », selon les zones spécifiées et les quantités à traiter.  

### 2 : Créer un prélèvement inventaire

Sur la page **Prélèvement inventaire**, l'employé d'entrepôt récupère, en mode « pull », les lignes du document source. Sinon, les lignes prélèvement inventaire sont déjà créées, par déplacement, par l'utilisateur responsable du document origine.  

### 3 : reporter un prélèvement inventaire

Sur chaque ligne pour les articles qui ont été prélevés ou déplacés, entièrement ou partiellement, renseignez le champ **Quantité**, puis reportez le prélèvement inventaire. Les documents origine associés au prélèvement inventaire sont reportés comme étant livrés ou consommés.  

Pour les prélèvements inventaire, les écritures article négatives sont créées, les écritures entrepôt sont créées, et la demande de prélèvement est supprimée, si elle a été entièrement traitée. Par exemple, le champ **Qté expédiée** sur la ligne document origine sortant est mis à jour. Un document livraison reporté est créé et indique le document de vente, par exemple, ainsi que les articles livrés.  

## Configurations d'entrepôt avancées

Le schéma suivant présente les processus d’entrepôt sortants pour différents types de document dans les configurations d’entrepôt avancées. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

:::image type="content" source="media/design_details_warehouse_management_outbound_advanced_flow.png" alt-text="Affiche les étapes d’un flux sortant avancé dans un entrepôt.":::

### 1 : Libérer un document source

Le lancement d’un document origine dans les configurations avancées a le même effet que pour les configurations de base. Les articles deviennent disponibles pour être manipulés dans l’entrepôt. Par exemple, ils peuvent être inclus dans une livraison.  

### 2 : Créer une livraison entrepôt

Sur la page **Livraison entrepôt**, récupérez les lignes du document source libéré. Vous pouvez combiner des lignes de plusieurs documents dans une livraison entrepôt.  

### 3 : Créer un prélèvement entrepôt

Sur la page **Livraison entrepôt**, créez des activités de prélèvement entrepôt pour les livraisons entrepôt de l’une des deux manières suivantes :

- En mode « push », où vous utilisez l’action **Créer prélèvement**. Sélectionnez les lignes à prélever et préparez les prélèvements en spécifiant, par exemple, à partir de quelles zones les prendre, à quelles zones les placer, et le nombre d’unités à traiter. Les zones peuvent être prédéfinies pour l’emplacement d’entrepôt ou la ressource.
- En mode « pull », où vous utilisez l’action **Libérer**. Sur la page **Feuille prélèvement**, les magasiniers peuvent utiliser l’action **Extraire documents entrepôt** pour récupérer les prélèvements qui leur sont assignés. Lorsque les prélèvements entrepôt sont entièrement enregistrés, les lignes dans la **Feuille prélèvement** sont supprimées.

### 4 : Enregistrer un prélèvement entrepôt

Sur la page **Prélèvement entrepôt**, un employé d'entrepôt renseigne le champ **Quantité** pour chaque ligne qu’il a prélevée entièrement ou partiellement, puis enregistre le prélèvement.

Les écritures d’entrepôt sont créées, et les lignes prélèvement entrepôt sont supprimées si la quantité entière a été prélevée. Le document de prélèvement entrepôt reste ouvert jusqu’à ce que la quantité totale de la livraison entrepôt soit enregistrée. Le champ **Qté prélevée** sur les lignes expédition entrepôt est mis à jour en conséquence.  

### 5 : reporter la livraison entrepôt

Lorsque tous les articles du document de livraison entrepôt sont enregistrés comme prélevés, l'employé d'entrepôt reporte la livraison. Le report met à jour les écritures article pour refléter la réduction de l'inventaire. Par exemple, le champ **Qté expédiée** sur la ligne document origine sortant est mis à jour.  

## Reporter des articles hors inventaire

[!INCLUDE [post-non-inventory-items](includes/post-non-inventory-items.md)]

## Voir aussi

[Gestion d'entrepôt](design-details-warehouse-management.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
