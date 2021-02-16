---
title: Gérer les clients à l'aide de Dynamics 365 Sales | Microsoft Docs
description: Vous pouvez utiliser Dynamics 365 Sales depuis Business Central pour mapper les données et avoir une intégration et une synchronisation parfaites dans le processus allant du prospect à l'encaissement.
documentationcenter: ''
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: integration, synchronize, map, Sales
ms.date: 10/01/2020
ms.author: bholtorf
ms.openlocfilehash: 7234536ff432140b1606ffe685bb0225f4963612
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4755327"
---
# <a name="using-dynamics-365-sales-from-business-central"></a>Utilisation de Dynamics 365 Sales depuis Business Central
Si vous utilisez Dynamics 365 Sales for Customer Engagement, bénéficiez de l'intégration parfaite dans le processus allant du prospect à l'encaissement à l'aide de [!INCLUDE[prod_short](includes/prod_short.md)] pour les activités principales, telles que le traitement des commandes, la gestion de l'inventaire et de vos finances.

Avant de pouvoir utiliser les fonctionnalités d’intégration, votre administrateur système doit configurer la connexion et définir les utilisateurs de [!INCLUDE[crm_md](includes/crm_md.md)]. Pour plus d'informations, reportez-vous à la rubrique [Intégration à Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).

> [!NOTE]
> Ces étapes décrivent le processus d'intégration des versions en ligne de [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d'informations sur la configuration sur site, voir [Préparation de l'intégration à Dynamics 365 Sales On-Premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

Intégrer les applications vous permet d'accéder aux données dans Sales depuis [!INCLUDE[prod_short](includes/prod_short.md)], et dans certains cas, inversement. Vous pouvez utiliser et synchroniser les données communes aux deux services, par exemple clients, contacts et informations de vente, et mettre à jour les données dans les deux applications.  

Par exemple, un représentant dans [!INCLUDE[crm_md](includes/crm_md.md)] peut utiliser les tarifs dans [!INCLUDE[prod_short](includes/prod_short.md)] lorsqu'il crée un document de vente. Lorsqu'il ajoute l'article à la ligne document de vente dans [!INCLUDE[crm_md](includes/crm_md.md)], il peut également visualiser le niveau d'inventaire (disponibilité) de l'article dans [!INCLUDE[prod_short](includes/prod_short.md)].

Inversement, les préparateurs de commandes dans [!INCLUDE[prod_short](includes/prod_short.md)] peuvent gérer les documents de vente qui sont automatiquement ou manuellement transférés depuis [!INCLUDE[crm_md](includes/crm_md.md)]. Par exemple, ils peuvent créer et reporter des lignes de document de vente pour les articles ou les ressources saisies dans [!INCLUDE[crm_md](includes/crm_md.md)] comme produits hors catalogue. Pour plus d'informations, reportez-vous à la rubrique [Gestion des données de documents de vente spéciaux](marketing-integrate-dynamicscrm.md#handling-sales-order-data).

> [!IMPORTANT]  
> [!INCLUDE[prod_short](includes/prod_short.md)] s'intègre uniquement à [!INCLUDE[crm_md](includes/crm_md.md)]. Les autres applications Dynamics 365 qui modifient le flux de travail ou le modèle de données standard dans [!INCLUDE[crm_md](includes/crm_md.md)], par exemple Project Service Automation, peuvent désactiver l'intégration entre [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[crm_md](includes/crm_md.md)].

## <a name="coupling-records"></a>Enregistrements couplage
Le guide de configuration assistée vous permet de choisir les données à synchroniser. Ultérieurement, vous pouvez également configurer la synchronisation pour les enregistrements spécifiques. C'est ce qu'on appelle le *couplage*. Par exemple, vous pouvez coupler un compte spécifique dans [!INCLUDE[crm_md](includes/crm_md.md)] avec un client spécifique dans [!INCLUDE[prod_short](includes/prod_short.md)]. Cette rubrique décrit ce qu'il convient de prendre en compte lorsque vous couplez des enregistrements.

Par exemple, si vous souhaitez afficher les comptes [!INCLUDE[crm_md](includes/crm_md.md)] en tant que clients dans [!INCLUDE[prod_short](includes/prod_short.md)], vous devez coupler les deux types d'enregistrements. Pour ce faire, sur la page de la liste **Clients** dans [!INCLUDE[prod_short](includes/prod_short.md)], utilisez l'action **Configurer le couplage**. Puis vous devez spécifier quels clients [!INCLUDE[prod_short](includes/prod_short.md)] correspondent à quels comptes dans [!INCLUDE[crm_md](includes/crm_md.md)].

Vous pouvez également créer (et coupler) un compte dans [!INCLUDE[crm_md](includes/crm_md.md)] selon, par exemple, un enregistrement client dans [!INCLUDE[prod_short](includes/prod_short.md)] à l'aide de l'option **Créer un compte dans Dynamics 365 Sales** ou vice-versa, à l'aide de l'option **Créer un client dans [!INCLUDE[prod_short](includes/prod_short.md)]**.

Lorsque vous configurez un couplage entre deux enregistrements, vous pouvez également demander manuellement que l'enregistrement actuel, par exemple un client, soit remplacé immédiatement par les données de compte depuis Sales (ou depuis [!INCLUDE[prod_short](includes/prod_short.md)]) à l'aide de l'action **Synchroniser maintenant**. L'action **Synchroniser maintenant** vous demandera de remplacer les données dans Sales ou les données d'enregistrement [!INCLUDE[prod_short](includes/prod_short.md)].

Dans certains cas, vous devez coupler certains ensembles de données avant d'autres ensembles de données, comme l'indique le tableau suivant.

|Données|Ce qu'il convient de coupler tout d'abord|
|-----|----|
|Clients et comptes|Coupler des représentants avec des utilisateurs [!INCLUDE[crm_md](includes/crm_md.md)]|
|Articles et ressources|Coupler des unités de mesure avec des groupes d'unités de mesure [!INCLUDE[crm_md](includes/crm_md.md)]|
|Prix des articles et des ressources|Coupler des groupes tarifs client avec des prix [!INCLUDE[crm_md](includes/crm_md.md)]|

> [!NOTE]  
> Si vos prix ou clients utilisent des devises étrangères, assurez-vous de coupler des devises avec des devises de transaction Sales.

Dans [!INCLUDE[crm_md](includes/crm_md.md)], les documents de vente dépendent d'informations comme les clients, les unités de mesure, les devis, les groupes tarifs client, les articles et/ou les ressources. Pour assurer une intégration avec les documents de vente, vous devez coupler des clients, des unités de mesure, des devises, des groupes tarifs client, des articles et/ou des ressources.

## <a name="fully-synchronizing-records"></a>Synchronisation complète des enregistrements
À la fin du guide de configuration assistée, vous pouvez sélectionner l'action **Exécuter une synchronisation complète** pour démarrer la synchronisation de tous les enregistrements [!INCLUDE[prod_short](includes/prod_short.md)] avec tous les enregistrements associés dans [!INCLUDE[crm_md](includes/crm_md.md)]. Sur la page **Révision synchronisation complète Dynamics 365 Sales**, sélectionnez l'action **Démarrer**. La synchronisation complète peut prendre un certain temps, mais vous pouvez continuer à travailler dans [!INCLUDE[prod_short](includes/prod_short.md)] pendant son exécution en arrière-plan.

Pour vérifier la progression de divers projets dans le cadre d'une synchronisation complète, sur la page **Révision synchronisation complète Dynamics 365 Sales**, choisissez un enregistrement pour afficher les détails. Pour mettre à jour l'état pendant la synchronisation, actualisez la page.

Sur la page **Configuration de la connexion Microsoft Dynamics 365**, vous pouvez obtenir des détails sur la synchronisation complète à tout moment. À partir de cette page, vous pouvez aussi ouvrir la page **Correspondances table intégration** pour afficher les détails des tables dans [!INCLUDE[prod_short](includes/prod_short.md)] et dans Sales à synchroniser.

## <a name="handling-sales-order-data"></a>Gestion des données de documents de vente
Les documents de vente que les utilisateurs envoient dans [!INCLUDE[crm_md](includes/crm_md.md)] seront transférés automatiquement vers [!INCLUDE[prod_short](includes/prod_short.md)] si vous sélectionnez la case à cocher **Créer automatiquement des documents de vente** sur la page **Configuration de la connexion à Microsoft Dynamics 365**.
Sinon, vous pouvez convertir manuellement les documents de vente envoyés depuis [!INCLUDE[crm_md](includes/crm_md.md)] à l'aide de l'action **Créer dans [!INCLUDE[prod_short](includes/prod_short.md)]** disponible sur la page **Documents de vente - Dynamics 365 for Sales**.
Pour ces documents de vente, le champ **Nom** de la commande d'origine est transféré et associé au champ **Numéro de document externe** du document de vente dans [!INCLUDE[prod_short](includes/prod_short.md)].

Ceci peut également fonctionner si le document de vente d'origine indique les biens hors catalogue, c'est-à-dire les articles ou les ressources qui ne sont enregistrés dans aucune application. Dans ce cas, vous devez renseigner les champs **Type produit hors catalogue** et **N° produit hors catalogue** sur la page **Configuration ventes**, de sorte que ces ventes de produits non enregistrés soient mappées à un nombre donné d’articles ou de ressources.

> [!NOTE]
> Vous ne pouvez pas mapper une écriture à un élément ou une ressource dans [!INCLUDE[prod_short](includes/prod_short.md)] qui est couplé à un produit dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour autoriser les écritures, nous vous recommandons de créer un article ou une ressource spécifiquement à cette fin et de ne pas le coupler avec un produit dans [!INCLUDE[crm_md](includes/crm_md.md)]. 

Si la description de l'article sur le document de vente d'origine est longue, alors une ligne document de vente supplémentaire de type **Commentaire** est créée pour stocker le texte intégral du document de vente dans [!INCLUDE[prod_short](includes/prod_short.md)].

Les mises à jour vers les champs d’en-tête document de vente, tels que Date dernière livraison ou Date livraison demandée, qui sont mappés dans le mappage de tables d’intégration **DOCUMENTDEVENTE-COMMANDE**, sont synchronisées régulièrement avec [!INCLUDE[crm_md](includes/crm_md.md)]. Les processus tels que lancer une document de vente et expédier ou facturer une document de vente sont reportés vers la chronologie de document de vente dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour en savoir plus, voir [Introduction aux flux d'activité](/dynamics365/sales-enterprise/manage-activities). <!--The /dynamics365/sales-enterprise/developer/introduction-activity-feeds link was broken. Should this actually point to /dynamics365/sales-enterprise/manage-activities-->

> [!NOTE]  
> La synchronisation périodique basée sur le mappage de tables d’intégration **DOCUMENTDEVENTE-COMMANDE** fonctionne uniquement lorsque l’intégration du document de vente est activée. Pour en savoir plus, consultez [Configuration de connexion sur la page Configuration de connexion Sales](admin-prepare-dynamics-365-for-sales-for-integration.md). Seuls les documents de vente créés à partir de documents de vente envoyés dans [!INCLUDE[crm_md](includes/crm_md.md)] sont synchronisés. Pour plus d'informations, voir [Activer l'intégration du traitement des documents de vente](/dynamics365/sales-enterprise/developer/enable-sales-order-processing-integration).

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098170]

## <a name="handling-sales-quotes-data"></a>Gestion des données de devis
Les devis vente activés dans [!INCLUDE[crm_md](includes/crm_md.md)] seront transférés vers [!INCLUDE[prod_short](includes/prod_short.md)] si vous sélectionnez la case à cocher **Traiter automatiquement les devis** sur la page **Configuration de la connexion Microsoft Dynamics 365**.
Sinon, vous pouvez convertir manuellement les devis envoyés depuis [!INCLUDE[crm_md](includes/crm_md.md)] à l'aide de l'action **Traiter dans [!INCLUDE[prod_short](includes/prod_short.md)]** disponible sur la page **Devis - Dynamics 365 Sales**.
Pour ces devis, le champ **Nom** du devis d'origine est transféré et associé au champ **Numéro de document externe** du document de vente dans [!INCLUDE[prod_short](includes/prod_short.md)]. En outre, le champ **Applicable jusqu'à** du devis est transféré et mappé vers le champ **Devis valide jusqu'à** du devis dans [!INCLUDE[prod_short](includes/prod_short.md)].  

Les devis subissent de nombreuses révisions avant d'être finalisés. Le traitement automatique et manuel des devis dans [!INCLUDE[prod_short](includes/prod_short.md)] garantit que les versions précédentes des devis sont archivées avant traitement des nouvelles révisions de devis depuis [!INCLUDE[crm_md](includes/crm_md.md)].

Quand vous choisissez **Traitement** dans [!INCLUDE[prod_short](includes/prod_short.md)] pour un devis dans un état **Conclu**, un document de vente est créé dans [!INCLUDE[prod_short](includes/prod_short.md)] uniquement si un document de vente correspondant est soumis dans [!INCLUDE[crm_md](includes/crm_md.md)]. Sinon, le devis n’est publié que dans [!INCLUDE[prod_short](includes/prod_short.md)]. Si un document de vente correspondant est envoyé dans [!INCLUDE[crm_md](includes/crm_md.md)] plus tard, et qu’un document de vente en est créé, le **N° devis** est mis à jour sur le document de vente et le devis est archivé.

## <a name="handling-posted-sales-invoices-customer-payments-and-statistics"></a>Gestion des factures vente reportées, des paiements client et des statistiques
Après l'exécution d'un document de vente, les factures associées seront créées. Lorsque vous facturez un document de vente, vous pouvez transférer la facture vente reportée dans [!INCLUDE[crm_md](includes/crm_md.md)] si vous cochez la case **Créer une facture dans [!INCLUDE[crm_md](includes/crm_md.md)]** sur la page **Facture vente reportée**. Les factures reportées sont transférées dans [!INCLUDE[crm_md](includes/crm_md.md)] avec l'état **Facturé**.

Une fois que le paiement client est reçu pour la facture vente dans [!INCLUDE[prod_short](includes/prod_short.md)], l'état de la facture vente sera modifié en **Payé** avec la **raison de l'état** définie sur **Partielle** si elle est partiellement payée, ou **Totale** si elle est totalement payée, lorsque vous exécutez **Mettre à jour les statistiques compte** sur la page du client dans [!INCLUDE[prod_short](includes/prod_short.md)]. La fonction **Mettre à jour les statistiques compte** actualisera également des valeurs telles que le **solde** et les **ventes totales** dans le **récapitulatif Statistiques compte [!INCLUDE[prod_short](includes/prod_short.md)]** dans [!INCLUDE[crm_md](includes/crm_md.md)]. Sinon, les projets programmés (statistiques client et POSTEDSALESINV-INV) peuvent exécuter automatiquement ces deux processus en arrière-plan.

## <a name="see-also"></a>Voir aussi
[Intégration à Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Gestion des relations](marketing-relationship-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md)    
[Vue d'ensemble de Sales et du centre des ventes](/dynamics365/customer-engagement/sales-enterprise/overview)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  
