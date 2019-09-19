---
title: Synchronisation et intégration des données | Microsoft Docs
description: La synchronisation copie les données entre les écritures Dynamics 365 for Sales et les enregistrements de Business Central et conserve les données à jour dans les deux systèmes.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 04/01/2019
ms.author: bholtorf
ms.openlocfilehash: 9506b64229c4d936fa25d74d71a923bdf7915e45
ms.sourcegitcommit: 6ef7d2fae52feff786f2e15e2863d7f5aaa762be
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/22/2019
ms.locfileid: "1917470"
---
# <a name="synchronizing-data-in-business-central-and-dynamics-365-for-sales"></a>Synchronisation des données dans Business Central et Dynamics 365 for Sales
Lorsque vous intégrez [!INCLUDE[crm_md](includes/crm_md.md)] avec [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez décider si vous souhaitez synchroniser les données dans les champs sélectionnés des enregistrements [!INCLUDE[d365fin](includes/d365fin_md.md)] (tels que les clients, contacts et les vendeurs) avec les enregistrements équivalents dans [!INCLUDE[d365fin](includes/d365fin_md.md)] (tels que les comptes, les contacts et les utilisateurs). Selon le type d'enregistrement, vous pouvez synchroniser les données de [!INCLUDE[crm_md](includes/crm_md.md)] vers [!INCLUDE[d365fin](includes/d365fin_md.md)], ou vice versa. Pour plus d'informations, reportez-vous à la rubrique [Intégration à Dynamics 365 for Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).  

La synchronisation utilise les éléments suivants :

* Mappages de table d'intégration
* Mappages de champ d'intégration
* Règles de synchronisation
* Enregistrements couplés

Une fois la synchronisation configurée, vous pouvez coupler les enregistrements [!INCLUDE[d365fin](includes/d365fin_md.md)] et les enregistrements [!INCLUDE[crm_md](includes/crm_md.md)] pour synchroniser leurs données. Vous pouvez commencer une synchronisation manuellement, ou selon un calendrier. Le tableau suivant donne un aperçu des méthodes à disposition pour synchroniser les enregistrements.  

|  Type  |  Méthode  |  Voir  |  
|--------|----------|-------|  
|Synchronisation manuelle|Synchronisez sur une base enregistrement après enregistrement.<br /><br /> Vous pouvez synchroniser les enregistrements individuels dans [!INCLUDE[d365fin](includes/d365fin_md.md)], tel qu'un client, avec un enregistrement [!INCLUDE[crm_md](includes/crm_md.md)] correspondant, par exemple un compte. C'est généralement ainsi que les utilisateurs travailleront avec les données [!INCLUDE[crm_md](includes/crm_md.md)] dans [!INCLUDE[d365fin](includes/d365fin_md.md)].|[Coupler et synchroniser des enregistrements manuellement](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
|  |Synchronisez sur une base de mappage de table.<br /><br /> Vous pouvez synchroniser tous les enregistrements dans une table [!INCLUDE[d365fin](includes/d365fin_md.md)] avec une entité [!INCLUDE[crm_md](includes/crm_md.md)].|[Synchroniser les mappages de table individuels](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
||Synchronisez tous les enregistrements modifiés pour tous les mappages de table.<br /><br /> Vous pouvez synchroniser toutes les enregistrements qui ont été modifiés dans les tables [!INCLUDE[d365fin](includes/d365fin_md.md)] depuis la dernière synchronisation.|[Synchronisation de tous les enregistrements modifiés](admin-manual-synchronization-of-table-mappings.md#synchronizing-all-modified-records)|
||Synchronisation complète de toutes les données pour tous les mappages de table.<br /><br /> Vous pouvez synchroniser toutes les données des tables [!INCLUDE[d365fin](includes/d365fin_md.md)] et des entités [!INCLUDE[crm_md](includes/crm_md.md)] mappées et créer de nouveaux enregistrements dans la solution de destination pour les enregistrements non couplés dans la solution source.<br /><br /> La synchronisation complète permet de synchroniser toutes les données et d'ignorer le couplage. Généralement, vous effectuez une synchronisation complète lorsque vous configurez l'intégration et lorsqu'une seule des solutions contient des données. Une synchronisation complète peut être également utile dans un environnement de démonstration.|[Exécuter une synchronisation complète](admin-manual-synchronization-of-table-mappings.md#run-a-full-synchronization)|  
|Synchronisation programmée|Synchronisez tous les changements apportés aux données pour tous les mappages de table.<br /><br /> Vous pouvez synchroniser [!INCLUDE[d365fin](includes/d365fin_md.md)] avec [!INCLUDE[crm_md](includes/crm_md.md)] à des intervalles programmés en configurant des projets dans la file d'attente projets.|[Programmer une synchronisation](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)|  

## <a name="standard-sales-entity-mapping-for-synchronization"></a>Mappage d'entité Sales standard pour la synchronisation
Les entités dans [!INCLUDE[crm_md](includes/crm_md.md)], telles que des comptes, sont intégrées aux types d'entités équivalents dans [!INCLUDE[d365fin](includes/d365fin_md.md)], tels que des clients. Pour utiliser les données [!INCLUDE[crm_md](includes/crm_md.md)], vous configurez des liens, appelés couplages entre les entités dans [!INCLUDE[d365fin](includes/d365fin_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)].

Le tableau suivant répertorie le mappage standard entre les entités dans [!INCLUDE[d365fin](includes/d365fin_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] que [!INCLUDE[d365fin](includes/d365fin_md.md)] fournit.

|[!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[crm_md](includes/crm_md.md)]|Direction de synchronisation|Filtre par défaut|
|-------------------------------------------|-----|-------------------------|--------------|
|Représentant/Acheteur|Utilisateur|[!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Filtre contact Sales : l'**État** est **Non**, l'**Utilisateur sous licence** est **Oui**, le Mode utilisateur de l'intégration est **Non**|
|Client|Compte|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Filtre compte Sales : le **Type de relation** est **Client** et l'**État** est **Actif**.|
|Contact|Contact|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Filtre contact [!INCLUDE[d365fin](includes/d365fin_md.md)] : le champ **Type** est défini sur **Personne** et le contact est affecté à une compagnie. Filtre contact Sales : le contact est affecté à une compagnie et le type de client parent est **Compte**.|
|Devise|Devise de transaction|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Unité de mesure|Groupe d'unités|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Article ;|Produit|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Filtre contact Sales : le **Type de produit** est **Inventaire de vente**|
|Ressource|Produit|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Filtre contact Sales : le **Type de produit** est **Services**|
|Groupe prix client|Liste des prix|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Prix vente|Tarifs produit|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|Filtre contact [!INCLUDE[d365fin](includes/d365fin_md.md)] : le champ **Code de vente** n'est pas vide, le champ **Type de vente** est défini sur **Groupe prix client**|
|Opportunité|Opportunité|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |
|En-tête facture vente|Facturer|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Ligne facture vente|Produit facture|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|En-tête de document de vente|Document de vente|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|Filtre en-tête de vente [!INCLUDE[d365fin](includes/d365fin_md.md)] : le champ **Type de document** est défini sur Commande, le champ **État** est défini sur Libéré.|
|Remarques Document de vente|Remarques Document de vente|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |

### <a name="tip-for-admins-viewing-entity-mappings"></a>Astuce dédiée aux administrateurs : affichage des mappages d'entité
Vous pouvez afficher le mappage entre les entités dans [!INCLUDE[crm_md](includes/crm_md.md)] et les tables dans [!INCLUDE[d365fin](includes/d365fin_md.md)] sur la page **Mappages de table d'intégration**, où vous pouvez également appliquer des filtres. Vous définissez le mappage entre les champs des tables [!INCLUDE[d365fin](includes/d365fin_md.md)] et les champs des entités [!INCLUDE[crm_md](includes/crm_md.md)] de la page **Mappage de champ d'intégration**, où vous pouvez ajouter une logique de mappage supplémentaire. Par exemple, cela peut être utile si vous devez résoudre un problème de synchronisation.

### <a name="tip-for-developers-mapping-fields-in-business-central-to-the-option-sets-in-sales"></a>Astuce dédiée aux développeurs : champs de mappage dans Business Central vers les ensembles d'options dans Sales
Si vous êtes un développeur et si vous souhaitez ajouter des ensembles d'options dans [!INCLUDE[crm_md](includes/crm_md.md)], vous devez connaître ceci. Trois tables dans [!INCLUDE[d365fin](includes/d365fin_md.md)] sont mappées aux champs d'option de l'entité **Compte** dans [!INCLUDE[crm_md](includes/crm_md.md)]. Les enregistrements dans les tables qui ne sont pas couplés aux options dans [!INCLUDE[crm_md](includes/crm_md.md)] ne seront pas synchronisés. Cela signifie que le champ **Option** est vide dans [!INCLUDE[crm_md](includes/crm_md.md)].

Le tableau suivant décrit les mappages des tables [!INCLUDE[d365fin](includes/d365fin_md.md)] pour le champ **Option** de l'entité **Compte** dans [!INCLUDE[crm_md](includes/crm_md.md)].

|Table|Champ Option de l'entité Compte|
|----------------------|-------------------------------------------|
|Modalités de paiement|Modalités de paiement|
|Méthode de livraison|Adresse 1 : Conditions de transport|
|Agent de livraison|Adresse 1 : Mode de livraison|

### <a name="synchronization-rules"></a>Règles de synchronisation
Le tableau suivant décrit les règles qui contrôlent la synchronisation entre les applications.

> [!NOTE]  
> Les modifications apportées aux données dans [!INCLUDE[crm_md](includes/crm_md.md)] par le compte d'utilisateur de connexion [!INCLUDE[crm_md](includes/crm_md.md)] ne sont pas synchronisées. Par conséquent, nous vous avons recommandé de ne pas modifier les données lors de l'utilisation de ce compte. Pour en savoir plus, reportez-vous à la rubrique [Configuration des comptes d'utilisateur pour l'intégration à Dynamics 365 for Sales](admin-setting-up-integration-with-dynamics-sales.md).

|Table|Règle|
|-----|----|
|Clients|Pour qu'un client puisse être synchronisé à un compte, le représentant affecté au client doit être couplé à un utilisateur dans [!INCLUDE[crm_md](includes/crm_md.md)]. Ainsi, lorsque vous exécutez le projet de synchronisation CLIENTS - Dynamics 365 for Sales et que vous le configurez pour créer des enregistrements, assurez-vous de synchroniser les représentants avec les utilisateurs [!INCLUDE[crm_md](includes/crm_md.md)] avant de synchroniser les clients avec les comptes dans [!INCLUDE[crm_md](includes/crm_md.md)]. <br /> <br />Le projet de synchronisation Dynamics 365 for Sales - CLIENTS synchronise uniquement les comptes Sales dont le type de relation est Client.|
|Contacts|Seuls les contacts dans [!INCLUDE[crm_md](includes/crm_md.md)] qui sont associés à un compte seront créés dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. La valeur Code représentant définit le propriétaire de l'entité couplée dans [!INCLUDE[crm_md](includes/crm_md.md)].|
|Devises|Les devises sont couplées aux devises de transaction dans [!INCLUDE[crm_md](includes/crm_md.md)] conformément aux codes ISO. Seules les devises qui ont un code ISO standard seront couplées et synchronisées avec les devises de transaction.|
|Unités de mesure|Les unités de mesure sont synchronisées avec les groupes d'unités dans [!INCLUDE[crm_md](includes/crm_md.md)]. Une seule unité de mesure peut être définie dans le groupe d'unités.|
|Articles|Lors de la synchronisation d'articles avec des produits [!INCLUDE[crm_md](includes/crm_md.md)], [!INCLUDE[d365fin](includes/d365fin_md.md)] crée automatiquement une liste de prix dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour éviter les erreurs de synchronisation, vous ne devez pas modifier cette liste de prix manuellement.|
|Représentants|Les représentants sont couplés aux utilisateurs du système dans [!INCLUDE[crm_md](includes/crm_md.md)]. L'utilisateur doit être activé et sous licence et ne doit pas être l'utilisateur d'intégration. Notez qu'il s'agit de la première table qui doit être synchronisée, car elle est utilisée dans les clients, les contacts, les opportunités et les factures vente.|
|Ressources|Les ressources sont synchronisées avec les produits [!INCLUDE[crm_md](includes/crm_md.md)] dont le type de produit est Service.|
|Groupes prix client|Les groupes de prix client sont synchronisés avec les listes de prix dans Sales.|
|Prix vente|Les prix de vente dont le type vente est Groupe prix client et dont le code vente est défini sont synchronisés avec les lignes de liste de prix dans [!INCLUDE[crm_md](includes/crm_md.md)].|
|Opportunités|Les opportunités sont synchronisées avec les opportunités dans [!INCLUDE[crm_md](includes/crm_md.md)]. La valeur Code représentant définit le propriétaire de l'entité couplée dans [!INCLUDE[crm_md](includes/crm_md.md)].|
|Factures vente reportées|Les factures vente reportées sont synchronisées avec les factures vente. Pour qu'une facture puisse être synchronisée, il est préférable de synchroniser toutes les autres entités pouvant participer à la facture, depuis les représentants jusqu'aux listes de prix. La valeur Code représentant de l'en-tête de facture définit le propriétaire de l'entité couplée dans Sales.|
|Documents de vente|Lorsque l'intégration des documents de vente est activée, les documents de vente dans [!INCLUDE[d365fin](includes/d365fin_md.md)] qui sont créés à partir des documents de vente soumis dans [!INCLUDE[crm_md](includes/crm_md.md)] sont synchronisées avec les documents de vente dans INCLUDE SALES lorsqu’ils sont libérés. Avant de synchroniser les commandes, nous vous recommandons de synchroniser tout d’abord toutes les entités associées à la commande, telles que les commerciaux et les listes de prix. Le champ Code représentant de l'en-tête de commande définit le propriétaire de l'entité couplée dans [!INCLUDE[crm_md](includes/crm_md.md)].|  

## <a name="see-also"></a>Voir aussi  
[Coupler et synchroniser des enregistrements manuellement](admin-how-to-couple-and-synchronize-records-manually.md)   
[Programmer une synchronisation](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)   
[Intégration à Dynamics 365 for Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)
