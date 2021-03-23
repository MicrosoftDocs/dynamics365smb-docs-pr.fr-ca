---
title: Détails de conception - Flux d'enlogement sortant | Microsoft Docs
description: Le flux sortant dans l'entrepôt commence par une demande provenant des documents origine libérés pour amener les articles hors de l'entrepôt, pour les livrer soit à un tiers, soit à un autre emplacement de la compagnie. Depuis la zone de stockage, des activités entrepôt sont effectuées à différents niveaux de complexité pour sortir les articles pour les amener au quai de livraison.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 13902c650606ef7a4464b367283abc9d610b9e4c
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5390859"
---
# <a name="design-details-outbound-warehouse-flow"></a>Détails de conception : flux de désenlogement

Le flux sortant dans l'entrepôt commence par une demande provenant des documents origine libérés pour amener les articles hors de l'entrepôt, pour les livrer soit à un tiers, soit à un autre emplacement de la compagnie. Depuis la zone de stockage, des activités entrepôt sont effectuées à différents niveaux de complexité pour sortir les articles pour les amener au quai de livraison.  

 Chaque article est identifié et mis en correspondance avec un document origine entrant correspondant. Les documents origine sortants suivants existent :  

- Document de vente  
- Ordre de transfert sortant  
- Retour commande achat  
- Commande service  

En outre, les documents origine internes suivants existent qui fonctionnent comme des sources sortantes :  

- Bon de production avec besoin de composante  
- Ordre d'assemblage avec besoin de composante  

 Les deux derniers documents représentent les flux sortants de l'entrepôt vers les zones d'opération internes. Pour plus d'informations sur l'activité entrepôt pour les processus enlogement et désenlogement internes, reportez\-vous à [Détails de conception : flux d'entrepôt internes](design-details-internal-warehouse-flows.md).  

 Les processus et les documents de l'interface utilisateur dans les flux de désenlogement sont différents pour les configurations d'entrepôt de base et avancées. La principale différence est que les activités sont effectuées par commande dans les configurations d'entrepôt de base, et qu'elles sont regroupées pour plusieurs commandes dans les configurations d'entrepôt avancées. Pour plus d'informations sur les différents niveaux de complexité entrepôt, consultez et [Détails de conception : vue d'ensemble d'entrepôt](design-details-warehouse-setup.md).  

 Dans [!INCLUDE[prod_short](includes/prod_short.md)], les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.  

|Méthode|Processus sortant|Zones|Prélèvements|Livraisons|Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](design-details-warehouse-setup.md))|  
|------|----------------|----|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|X|||2|  
|B|Report du prélèvement et de la livraison à partir d'un document prélèvement inventaire||X||3|  
|C|Report du prélèvement et de la livraison à partir d'un document livraison entrepôt|||X|4/5/6|  
|J|Report du prélèvement à partir d'un document prélèvement entrepôt et report de la livraison à partir d'un document livraison entrepôt||X|X|4/5/6|  

 Sélectionner une méthode dépend des pratiques recommandées de la compagnie et de la complexité de son organisation. Dans un environnement commande par commande avec des processus et une structure de zone simples, la méthode A, de prélèvement et de livraison à partir de la ligne commande, est appropriée. Dans d'autres compagnies commande par commande où les articles d'une ligne commande peuvent provenir de plusieurs zones et où les employés de l'entrepôt ne peuvent pas utiliser des documents commande, l'utilisation de différents documents prélèvement, la méthode B, est appropriée. Lorsque les processus de prélèvement et de livraison d'une compagnie impliquent plusieurs traitements de commande et donc requièrent davantage de contrôle et de supervision, la compagnie peut choisir d'utiliser un document livraison entrepôt et un document prélèvement entrepôt afin de séparer les tâches de prélèvement et de livraison, les méthodes C et D.  

 Dans les méthodes A, B et C, les tâches de prélèvement et de livraison sont combinées en une étape lors du report du document correspondant comme étant livré. Dans la méthode D, le prélèvement est d'abord enregistré, puis la livraison est reportée à une date ultérieure à partir d'un document différent.  

## <a name="basic-warehouse-configurations"></a>Configurations d'entrepôt de base

 Le schéma suivant présente les flux de désenlogement par type de document dans les configurations d'entrepôt de base. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

 ![Flux sortant dans les configurations d'entrepôt de base](media/design_details_warehouse_management_outbound_basic_flow.png "Flux sortant dans les configurations d'entrepôt de base")  

### <a name="1-release-source-document--create-inventory-pick-or-movement"></a>1 : Libérer le document source / Créer un prélèvement ou un mouvement d'inventaire

 Lorsqu'un utilisateur responsable des documents d'origine, comme un préparateur de commandes ou un gestionnaire de production, est prêt pour l'activité d'entrepôt sortante, il émet le document d'origine pour signaler aux employés d'entrepôt que les composantes ou articles vendus peuvent être prélevés et placés dans les zones spécifiées. Sinon, l'utilisateur crée des documents de prélèvement ou de mouvement d'inventaire pour les lignes de commande individuelles, par déplacement, selon les zones spécifiées et les quantités à traiter.  

> [!NOTE]  
> Des mouvements d'inventaire sont utilisés pour déplacer des articles vers des zones d'opération internes dans les configurations d'entrepôt de base, sur la base des documents sources ou sur une base ad-hoc.  

### <a name="2-create-outbound-request"></a>2 : Créer demande désenlogement

 Lorsque le document origine sortant est émis, une demande entrepôt sortante est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur.  

### <a name="3-create-inventory-pick-or-movement"></a>3 : Créer un prélèvement inventaire ou un mouvement d'inventaire

 Sur la page **Prélèvement inventaire** ou **Mouvement d'inventaire**, l'employé d'entrepôt extrait, en mode extraction, les lignes document origine en attente en fonction des demandes désenlogement. Sinon, les lignes prélèvement inventaire sont déjà créées, par déplacement, par l'utilisateur responsable du document origine.  

### <a name="4-post-inventory-pick-or-register-inventory-movement"></a>4 : reporter un prélèvement inventaire ou enregistrer un mouvement d'inventaire

 Sur chaque ligne pour les articles qui ont été prélevées ou déplacés, entièrement ou partiellement, le magasinier renseigne le champ **Quantité**, puis valide le prélèvement stock ou enregistre le mouvement de stock. Les documents origine associés au prélèvement inventaire sont reportés comme étant livrés ou consommés. Les documents origine liés aux mouvements d'inventaire ne sont pas reportés.  

 Pour les prélèvements inventaire, les écritures article négatives sont créées, les écritures entrepôt sont créées, et la demande de prélèvement est supprimée, si elle a été entièrement traitée. Par exemple, le champ **Qté expédiée** sur la ligne document origine sortant est mis à jour. Un document livraison reporté est créé et indique le document de vente, par exemple, ainsi que les articles livrés.  

## <a name="advanced-warehouse-configurations"></a>Configurations d'entrepôt avancées

 Le schéma suivant présente le flux de désenlogement par type de document dans les configurations d'entrepôt avancées. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

 ![Flux sortant dans les configurations d'entrepôt avancées](media/design_details_warehouse_management_outbound_advanced_flow.png "Flux sortant dans les configurations d'entrepôt avancées")  

### <a name="1-release-source-document"></a>1 : Libérez le document origine

 Lorsqu'un utilisateur responsable des documents origine, comme un préparateur de commandes ou un gestionnaire de production, est prêt pour l'activité entrepôt sortante, il émet le document origine pour signaler aux magasiniers que les articles ou les composantes vendus peuvent être prélevés et placés dans les zones spécifiées.  

### <a name="2-create-outbound-request-2"></a>2 : Créer demande désenlogement (2)

 Lorsque le document origine sortant est émis, une demande entrepôt sortante est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur.  

### <a name="3-create-warehouse-shipment"></a>3 : Créer livraison entrepôt

 Sur la page **Livraison entrepôt**, le responsable de la livraison extrait les lignes document origine en attente en fonction de la demande désenlogement. Plusieurs lignes document source peuvent être combinées dans un document livraison entrepôt.  

### <a name="4-release-shipment--create-warehouse-pick"></a>4 : Libérer la livraison / Créer un prélèvement entrepôt

 Le responsable de la livraison libère la livraison entrepôt, afin que les magasiniers puissent créer ou coordonner des prélèvements entrepôt pour la livraison en question.  

 Sinon, l'utilisateur crée des documents prélèvement entrepôt pour des lignes livraison individuelles, par déplacement, selon les zones spécifiées et les quantités à traiter.  

### <a name="5-release-internal-operation--create-warehouse-pick"></a>5 : Libérer une opération interne / Créer un prélèvement entrepôt

 L'utilisateur qui est responsable des opérations internes émet un document origine interne, tel qu'un bon de production et d'assemblage, afin que les magasiniers puissent créer ou coordonner des prélèvements entrepôt pour l'opération interne en question.  

 Sinon, l'utilisateur crée des documents prélèvement entrepôt pour l'ordre de fabrication ou l'ordre d'assemblage individuel, par déplacement, selon les emplacements spécifiés et les quantités à traiter.  

### <a name="6-create-pick-request"></a>6 : Créer une demande de prélèvement

 Lorsque le document origine sortant est émis, une demande de prélèvement d'entrepôt est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur. En fonction de la configuration, la consommation à parti d'un bon de production et d'un ordre d'assemblage génère également une demande de prélèvement pour prélever les composantes nécessaires dans l'inventaire.  

### <a name="7-generate-pick-worksheet-lines"></a>7 : Générer des lignes feuille prélèvement

 L'utilisateur qui est responsable de coordonner les prélèvements copie des lignes de prélèvement entrepôt dans la **Feuille prélèvement** en fonction des demandes de prélèvement des expéditions entrepôt ou des opérations internes pour la consommation des composants. L'utilisateur sélectionne les lignes à prélever et prépare les prélèvements en spécifiant à partir de quels emplacements les prendre, à quels emplacements les placer, et le nombre d'unités à traiter. Les emplacements peuvent être prédéfinis par la configuration d'un entrepôt ou d'une ressource d'opération.  

 L'utilisateur spécifie des méthodes de prélèvement pour la gestion d'entrepôt optimisée puis utilise une fonction pour créer les documents de prélèvement entrepôt correspondants, qui sont affectés aux différents magasiniers exécutant les prélèvements entrepôt. Lorsque les prélèvements entrepôt sont entièrement affectés, les lignes dans la **Feuille prélèvement** sont supprimées.  

### <a name="8-create-warehouse-pick-documents"></a>8 : Créer des documents prélèvement entrepôt

 Le magasinier qui effectue des prélèvements crée un document de prélèvement entrepôt, sur le mode de l'extraction, basé sur le document origine émis. Sinon, le document prélèvement entrepôt est créé et affecté au magasinier par déplacement.  

### <a name="9-register-warehouse-pick"></a>9 : Enregistrer un prélèvement entrepôt

 Sur chaque ligne pour les articles qui ont été prélevés, entièrement ou partiellement, l'employé d'entrepôt renseigne le champ **Quantité** sur la page **Prélèvement entrepôt**, puis enregistre le prélèvement entrepôt.  

 Les écritures d'entrepôt sont créées, et les lignes de prélèvement entrepôt sont supprimées, si entièrement traitées. Le document de prélèvement entrepôt reste ouvert jusqu'à ce que la quantité totale de la livraison entrepôt associée soit reportée. Le champ **Qté prélevée** sur les lignes expédition entrepôt est mis à jour en conséquence.  

### <a name="10-post-warehouse-shipment"></a>10 : reporter livraison entrepôt

 Lorsque tous les articles dans le document livraison entrepôt sont enregistrés comme prélevés dans les zones de livraison spécifiés, le magasinier responsable reporte la livraison entrepôt. Des écritures négatives du grand livre d'articles sont créées. Par exemple, le champ **Qté expédiée** sur la ligne document origine sortant est mis à jour.  

## <a name="see-also"></a>Voir aussi

[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]