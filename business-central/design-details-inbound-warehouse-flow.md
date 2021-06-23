---
title: Détails de conception - Flux d'enlogement entrant | Microsoft Docs
description: Le flux entrant dans un entrepôt commence à l'arrivée des articles dans l'entrepôt de l'emplacement de la compagnie, qu'ils proviennent de sources externes ou d'un autre emplacement de la compagnie. Un employé enregistre les articles, généralement en numérisant un code barre. Depuis le quai de réception, des activités entrepôt sont effectuées à différents niveaux de complexité pour amener les articles dans la zone de stockage.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: c2a78d585f949922e9f05e42a6ab61dcd7adc521
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6215188"
---
# <a name="design-details-inbound-warehouse-flow"></a>Détails de conception : flux d'enlogement
Le flux entrant dans un entrepôt commence à l'arrivée des articles dans l'entrepôt de l'emplacement de la compagnie, qu'ils proviennent de sources externes ou d'un autre emplacement de la compagnie. Un employé enregistre les articles, généralement en numérisant un code barre. Depuis le quai de réception, des activités entrepôt sont effectuées à différents niveaux de complexité pour amener les articles dans la zone de stockage.  

 Chaque article est identifié et mis en correspondance avec un document origine entrant correspondant. Les documents origine entrants suivants existent :  

- Bon de commande  
- Ordre de transfert entrant  
- Retour vente  

En outre, les documents origine internes suivants existent qui fonctionnent comme des sources entrantes :  

- Bon de production avec report de production  
- Ordre d'assemblage avec report de production  

Les deux derniers représentent les flux entrants dans l'entrepôt en provenance des zones d'opération internes. Pour plus d'informations sur l'activité entrepôt pour les processus enlogement et désenlogement internes, reportez\-vous à [Détails de conception : flux d'entrepôt internes](design-details-internal-warehouse-flows.md).  

Les processus et les documents de l'interface utilisateur dans les flux d'enlogement sont différents pour les configurations d'entrepôt de base et avancées. La principale différence est que les activités sont effectuées par commande dans les configurations d'entrepôt de base, et qu'elles sont regroupées pour plusieurs commandes dans les configurations d'entrepôt avancées. Pour plus d'informations sur les différents niveaux de complexité entrepôt, consultez et [Détails de conception : vue d'ensemble d'entrepôt](design-details-warehouse-setup.md).  

Dans [!INCLUDE[prod_short](includes/prod_short.md)], les processus entrants de réception et de rangement peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.  

|Méthode|Processus entrant|Zones|Reçus|Rangements|Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|X|||2|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire|||X|3|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt||X||4/5/6|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt||X|X|4/5/6|  

Sélectionner une méthode dépend des pratiques recommandées de la compagnie et de la complexité de son organisation. Dans un environnement d'entrepôt commande par commande, où la plus grande partie du personnel de l'entrepôt travaille directement avec des documents commande, une compagnie peut choisir d'utiliser la méthode A. Un entrepôt commande par commande avec un processus de rangement plus complexe ou dans lequel une équipe est dédiée à l'exécution des fonctions de l'entrepôt peut décider de séparer ses fonctions de rangement à partir du document commande, la méthode B. En outre, les compagnies qui doivent planifier la gestion de plusieurs commandes peuvent trouver utile d'utiliser des documents réception entrepôt, méthodes C et D.  

Dans les méthodes A, B et C, les tâches de réception et de rangement sont combinées en une étape lors du report des documents correspondants comme étant reçus. Dans la méthode D, la réception est reportée d'abord pour identifier l'augmentation d'inventaire et pour savoir que les articles sont disponibles pour la vente. L'employé d'entrepôt enregistre ensuite le rangement pour rendre les articles disponibles pour le prélèvement.  

## <a name="basic-warehouse-configurations"></a>Configurations d'entrepôt de base  
Le schéma suivant présente les flux d'enlogement par type de document dans les configurations d'entrepôt de base. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

![Flux entrant dans les configurations d'entrepôt de base](media/design_details_warehouse_management_inbound_basic_flow.png "Flux entrant dans les configurations d'entrepôt de base")  

### <a name="1-release-source-document--create-inventory-put-away"></a>1 : Libérer le document source / Créer un rangement inventaire  
Lorsque les articles sont réceptionnés dans l'entrepôt, l'utilisateur qui est responsable de la réception émet le document d'origine, comme un bon de commande ou un ordre de transfert entrant, pour signaler aux magasiniers que les articles reçus peuvent être rangés dans l'inventaire. Sinon, l'utilisateur crée des documents rangement inventaire pour des lignes commande individuelles, par déplacement, selon les zones spécifiées et les quantités à traiter.  

### <a name="2-create-inbound-request"></a>2 : Créer demande d'enlogement  
Lorsque le document origine entrant est émis, une demande entrepôt entrante est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur.  

### <a name="3-create-inventory-put-away"></a>3 : Créer un rangement inventaire  
Sur la page **Rangement inventaire**, l'employé d'entrepôt extrait, en mode extraction, les lignes document origine en attente en fonction des demandes enlogement. Sinon, les lignes rangement inventaire sont déjà créées, par déplacement, par l'utilisateur responsable du document source.  

### <a name="4-post-inventory-put-away"></a>4 : Reporter rangement inventaire  
Sur chaque ligne pour les articles qui ont été rangés, entièrement ou partiellement, l'employé d'entrepôt renseigne le champ **Quantité**, puis reporte le rangement inventaire. Les documents source associés au rangement inventaire sont reportés comme étant reçus.  

Des écritures article positives sont créées, des écritures entrepôt sont créées, et la demande de rangement est supprimée, si entièrement traitée. Par exemple, le champ **Quantité reçue** sur la ligne document origine entrant est mis à jour. Un document réception reporté est créé et indique le bon de commande, par exemple, ainsi que les articles reçus.  

## <a name="advanced-warehouse-configurations"></a>Configurations d'entrepôt avancées  
Le schéma suivant présente le flux d'enlogement par type de document dans les configurations d'entrepôt avancées. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

![Flux entrant dans les configurations d'entrepôt avancées](media/design_details_warehouse_management_inbound_advanced_flow.png "Flux entrant dans les configurations d'entrepôt avancées")  

### <a name="1-release-source-document"></a>1 : Libérez le document origine  
Lorsque les articles sont réceptionnés dans l'entrepôt, l'utilisateur qui est responsable de la réception émet le document d'origine, comme un bon de commande ou un ordre de transfert entrant, pour signaler aux magasiniers que les articles reçus peuvent être rangés dans l'inventaire.  

### <a name="2-create-inbound-request"></a>2 : Créer demande d'enlogement  
Lorsque le document origine entrant est émis, une demande entrepôt entrante est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur.  

### <a name="3-create-warehouse-receipt"></a>3 : Créer une réception entrepôt  
Sur la page **Réception entrepôt**, l'utilisateur qui est responsable de recevoir des articles extrait les lignes document origine en attente en fonction de la demande enlogement. Plusieurs lignes document origine peuvent être combinées dans un document réception entrepôt.  

L'utilisateur renseigne le champ **Qté à traiter** et sélectionne la zone et à l'emplacement de réception, si nécessaire.  

### <a name="4-post-warehouse-receipt"></a>4 : Reporter une réception entrepôt  
L'utilisateur reporte la réception entrepôt. Des écritures positives du grand livre d'articles sont créées. Par exemple, le champ **Quantité reçue** sur la ligne document origine entrant est mis à jour.  

### <a name="5-create-warehouse-internal-put-away"></a>5 : Créer rangement interne entrepôt  
L'utilisateur qui est responsable du stockage à partir des opérations internes crée un stockage interne en entrepôt pour les articles à stocker dans l'entrepôt, comme un résultat de production ou d'assemblage. L'utilisateur indique la quantité, la zone, et l'emplacement d'où les articles doivent être rangés, potentiellement à l'aide de la fonction **Extraire contenu emplacement**. L'utilisateur lance le stockage interne en entrepôt, ce qui crée une demande entrepôt d'entrée afin que la tâche puisse être récupérée dans des documents de stockage en entrepôt ou sur la feuille de stockage.  

### <a name="6-create-put-away-request"></a>6 : Créer demande de rangement entrepôt  
Lorsque le document d'origine entrant est reporté, une demande de stockage en entrepôt est automatiquement créée. Elle contient des références au type et au numéro du document origine et n'est pas visible à l'utilisateur. En fonction de la configuration, la production à partir d'un bon de production crée une demande de rangement pour ranger les articles finis dans l'inventaire.  

### <a name="7-generate-put-away-worksheet-lines-optional"></a>7 : Générer des lignes feuille rangement (facultatif)  
L'utilisateur qui est responsable de coordonner les stockages copie des lignes de stockage en entrepôt dans la **Feuille rangement** en fonction des reçus entrepôt reportés ou des opérations internes avec résultat. L'utilisateur sélectionne les lignes à ranger et prépare les rangements en spécifiant à partir de quelles zones les prendre, dans quelles zones les placer, et le nombre d'unités à traiter. Les emplacements peuvent être prédéfinis par la configuration d'un entrepôt ou d'une ressource d'opération.  

Lorsque tous les stockages sont planifiés et affectés aux magasiniers, l'utilisateur génère les documents de stockage en entrepôt. Des lignes rangement entièrement affectées sont supprimées de la **Feuille rangement**.  

> [!NOTE]  
>  Si le champ **Utiliser feuille rangement** n'est pas sélectionné sur la fiche emplacement, les documents rangement entrepôt sont créés directement sur la base des réceptions entrepôt reportées. Dans ce cas, l'étape 7 est omise.  

### <a name="8-create-warehouse-put-away-document"></a>8 : Créer un document rangement entrepôt  
L'employé d'entrepôt qui effectue les stockages crée un document de stockage en entrepôt, sur le mode de l'extraction, basé sur le reçu entrepôt reporté. Sinon, le document rangement entrepôt est créé et affecté à un magasinier par déplacement.  

### <a name="9-register-warehouse-put-away"></a>9 : Enregistrer rangement entrepôt  
Sur chaque ligne pour les articles qui ont été rangés, entièrement ou partiellement, l'employé d'entrepôt renseigne le champ **Quantité** sur la page **Rangement entrepôt**, puis enregistre le rangement entrepôt.  

Les écritures d'entrepôt sont créées, et les lignes de stockage en entrepôt sont supprimées, si entièrement traitées. Le document de stockage en entrepôt reste ouvert jusqu'à ce que la quantité totale du reçu entrepôt reporté soit enregistrée. Le champ **Qté rangement** sur les lignes d'ordre de réception entrepôt est mis à jour.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]