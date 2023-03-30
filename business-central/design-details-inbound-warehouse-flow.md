---
title: "Détails de conception\_: flux d’enlogement"
description: 'Le flux d’entrepôt entrant commence lorsque les articles arrivent à l’entrepôt de l’entreprise et sont enregistrés, puis mis en correspondance avec les documents sources entrants.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 11/14/2022
ms.author: bholtorf
---
# Détails de conception : flux d'enlogement

Le flux entrant dans un entrepôt commence à l'arrivée des articles dans l'entrepôt de l'emplacement de la compagnie, qu'ils proviennent de sources externes ou d'un autre emplacement de la compagnie. En principe, le processus de réception des commandes entrantes se compose de deux activités :

* La réception des articles au quai de réception de l’entrepôt, où vous identifiez les articles, les mettez en correspondance avec un document origine, et enregistrez la quantité reçue. 
* Le rangement des articles dans le stock, et l’enregistrement de l’endroit où vous les avez rangés.

Les documents origine pour le flux d’entrepôt entrant sont :

* Bons de commande  
* Ordres de transfert entrants  
* Retours vente  

> [!NOTE]
> Les sorties de la production et de l’assemblage représentent également des documents origine entrants. Pour en savoir plus sur la gestion des sorties de la production et de l’assemblage pour les processus internes, consultez [Détails de conception : Flux d’entrepôt internes](design-details-internal-warehouse-flows.md).  

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous recevez des articles et les rangez en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus entrant|Réceptions requises|Rangements requis|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire||Activé|De base : commande par commande.|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt|Activé||De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt|Activé|Activé|Avancé|  

La sélection d'une approche dépend des pratiques de votre compagnie et de la complexité de votre organisation. Voici quelques exemples qui peuvent vous aider à décider.

* Dans un environnement d’entrepôt commande par commande, où la plupart du personnel de l’entrepôt travaille directement avec les documents de commande, vous pouvez décider d’utiliser la méthode A. 
* Un entrepôt commande par commande qui a un processus de rangement plus complexe, ou dans lequel le personnel de l’entrepôt sépare ses activités de rangement du document de commande, peut utiliser la méthode B.
* Les compagnies qui doivent planifier le traitement de plusieurs commandes peuvent trouver utile d’utiliser des documents de réception entrepôt, méthodes C et D.  

Dans les méthodes A, B et C, les actions de réception et de rangement sont combinées en une étape lors du report des documents comme étant reçus. Dans la méthode D, la réception est reportée d’abord pour enregistrer l’augmentation d'inventaire et pour savoir que des articles sont disponibles pour la vente. L'employé d'entrepôt enregistre ensuite le rangement pour rendre les articles disponibles pour les commandes sortantes. 

> [!NOTE]
> Bien que les rangements entrepôt et les rangements inventaire semblent similaires, ce sont des documents différents et ils sont utilisés dans des processus différents.
> * Le rangement inventaire utilisé dans la méthode B, ainsi que l’enregistrement des informations de rangement, reporte également la réception du document source.
> * Le rangement entrepôt utilisé dans la méthode D ne peut pas être reporté et enregistre uniquement le rangement. L’enregistrement rend les articles disponibles pour un traitement ultérieur mais ne reporte pas la réception. Dans le flux entrant, le rangement entrepôt nécessite une réception entrepôt.

> [!NOTE]
> Bien que les rangements entrepôt et les rangements inventaire semblent similaires, ce sont des documents différents et ils sont utilisés dans des processus différents.
> * Le rangement inventaire utilisé dans la méthode B, ainsi que l’enregistrement des informations de rangement, reporte également la réception du document source.
> * Le rangement entrepôt utilisé dans la méthode D ne peut pas être reporté et enregistre uniquement le rangement. L’enregistrement rend les articles disponibles pour un traitement ultérieur mais ne reporte pas la réception. Dans le flux entrant, le rangement entrepôt nécessite une réception entrepôt.

## Aucune activité entrepôt dédiée

Les articles suivants fournissent des informations sur le traitement des réceptions pour les documents origine si vous n’avez pas d’activités entrepôt dédiées.

* [Enregistrer des achats](purchasing-how-record-purchases.md)
* [Ordres de transfert](inventory-how-transfer-between-locations.md)
* [Traitement des retours vente](sales-how-process-sales-returns-orders.md)

## Configurations d’entrepôt de base  

Dans une configuration d’entrepôt de base, le bouton à bascule **Rangement requis** est activé, mais le bouton à bascule **Réception requise** est désactivé sur la page Fiche emplacement de l’emplacement.

Le schéma suivant présente les flux d'enlogement par type de document dans les configurations d'entrepôt de base. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

:::image type="content" source="media/design_details_warehouse_management_inbound_basic_flow.png" alt-text="Le flux entrant de base dans un entrepôt.":::

### 1 : Libérer un document source pour créer une demande de rangement inventaire  

Lorsque vous recevez des articles, émettez le document source, tel qu’un bon de commande ou un ordre de transfert entrant. L’émission du document rend les articles disponibles pour être rangés. Vous pouvez également créer des documents de rangement inventaire pour des lignes commande individuelles, de manière « push », selon les zones spécifiées et les quantités à traiter.  

### 2 : Créer un rangement inventaire  

Sur la page **Rangement inventaire**, en mode « pull », vous pouvez extraire les lignes document source en attente en fonction des requêtes d’entrepôt entrantes. En mode « push », vous pouvez également créer des lignes rangement inventaire lorsque vous créez le document source.  

### 3 : reporter un rangement inventaire  

Sur chaque ligne pour les articles qui ont été rangés, entièrement ou partiellement, renseignez le champ **Quantité**, puis reportez le rangement inventaire. Les documents source associés au rangement inventaire sont reportés comme étant reçus.  

* Des écritures du grand livre d’articles positives sont créées
* Des écritures entrepôt sont créées pour les emplacements qui nécessitent un code de zone sur toutes les transactions d’articles.
* La requête de rangement est supprimée si elle est entièrement traitée. Par exemple, le champ **Quantité reçue** sur la ligne document origine entrant est mis à jour.
* Un document réception reporté est créé et indique le bon de commande, par exemple, ainsi que les articles reçus.  

## Configurations d'entrepôt avancées  

Dans une configuration d’entrepôt avancée, le bouton à bascule **Réception requise** est activé sur la page Fiche emplacement de l’emplacement. Le bouton à bascule **Rangement requis** est facultatif.

Le schéma suivant présente le flux d’enlogement par type de document. Les numéros dans le schéma correspondent aux étapes dans les sections suivant le schéma.  

:::image type="content" source="media/design_details_warehouse_management_inbound_advanced_flow.png" alt-text="Le flux entrant avancé dans un entrepôt.":::

### 1 : Émettre le document source  

Lorsque vous recevez des articles, émettez le document source, tel que le bon de commande ou un ordre de transfert entrant. L’émission du document rend les articles disponibles pour être rangés. Le rangement contiendra des références au type et au numéro du document origine.

### 2 : Créer une réception entrepôt  

Sur la page **Réception entrepôt**, récupérez les lignes du document origine entrant. Vous pouvez combiner plusieurs lignes document origine dans un document réception entrepôt. Renseignez le champ **Qté à traiter** et sélectionnez la zone et la zone de réception, si nécessaire.  

### 3 : reporter la réception entrepôt  

Reportez la réception entrepôt pour créer des écritures article positives. Le champ **Quantité reçue** sur la ligne document origine entrant est mis à jour.  

Si le bouton à bascule **Rangement requis** n’est pas activé sur la fiche emplacement, c’est là que le processus s’arrête. Sinon, le report du document source entrant rend les articles disponibles pour être rangés. Le rangement contient des références au type et au numéro du document origine.  

### 4 : (Facultatif) Générer des lignes feuille rangement

Récupérez les lignes de rangement entrepôt dans la **Feuille rangement** en fonction des réceptions entrepôt reportées ou des opérations qui produisent une sortie. Choisissez les lignes à ranger et spécifiez les informations suivantes :

* Les zones dans lesquelles prendre les articles.
* Les zones dans lesquelles placer les articles.
* Le nombre d’unités à traiter.

Les zones peuvent être prédéfinis par la configuration de l'emplacement d’entrepôt ou de la ressource qui a effectué l’opération.  

Lorsque tous les rangements sont planifiés et affectés aux magasiniers, générez les documents de rangement entrepôt. Les lignes rangement entièrement affectées sont supprimées de la **Feuille rangement**.  

> [!NOTE]  
> Si le bouton à bascule **Utiliser feuille rangement** n’est pas activé sur la fiche emplacement, les documents rangement entrepôt sont créés directement sur la base des réceptions entrepôt reportées. Dans ce cas, cette étape n’est pas nécessaire.  

### 5 : créer un document rangement entrepôt

Créez un document de rangement entrepôt en mode « pull », en fonction de la réception entrepôt reportée. Sinon, créez le document rangement entrepôt et affectez-le à un magasinier en mode « push ».  

### 6 : Enregistrer rangement entrepôt

Sur chaque ligne pour les articles qui ont été rangés, entièrement ou partiellement, renseignez le champ **Quantité** sur la page **Rangement entrepôt**, puis enregistrez le rangement entrepôt.  

* Des écritures entrepôt sont créées pour les emplacements qui nécessitent un code de zone sur toutes les transactions d’articles.
* Les lignes de rangement entrepôt sont supprimées si elles sont entièrement traitées.
* Le document de stockage en entrepôt reste ouvert jusqu'à ce que la quantité totale du reçu entrepôt reporté soit enregistrée.
* Le champ **Qté rangement** sur les lignes d’ordre de réception entrepôt reportées est mis à jour.

## Tâches connexes

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Enregistrez la réception des articles dans les emplacements d’entrepôt avec un récépissé d’entrepôt, en cas de traitement d’entreposage semi-automatisé ou entièrement automatisé sur l’emplacement.|[Réceptionner des articles](warehouse-how-receive-items.md)|
|Rangez les articles selon le principe commande par commande et reportez la réception en une activité dans les configurations entrepôt de base.|[Ranger des articles avec des rangements inventaire](warehouse-how-to-put-items-away-with-inventory-put-aways.md)|  
|Rangez les articles reçus à partir de plusieurs achats, retours vente ou ordres de transfert dans une configuration d’entrepôt avancée.|[Ranger des articles avec le rangement entrepôt](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)|  


## Voir aussi

[!INCLUDE[footer-include](includes/footer-banner.md)]
