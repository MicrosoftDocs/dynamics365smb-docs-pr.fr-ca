---
title: Intégration à Dynamics 365 Sales
description: Découvrez comment préparer Dynamics 365 Business Central pour l'intégrer à Dynamics 365 Sales.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'sales, crm, integration, integrating'
ms.date: 07/02/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="integrating-with-dynamics-365-sales"></a>Intégration à Dynamics 365 Sales

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Le rôle de vendeur est souvent considéré comme tourné vers l'extérieur dans une entreprise. Toutefois, il peut être utile pour les vendeurs d'être en mesure de regarder à l'intérieur de l'entreprise et d'observer ce qu'il s'y passe en arrière-plan. En intégrant [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[crm_md](includes/crm_md.md)], vous pouvez donner cet aperçu à vos commerciaux. L’intégration permet aux utilisateurs de visualiser des informations pendant qu’ils travaillent [!INCLUDE[prod_short](includes/prod_short.md)] . [!INCLUDE[crm_md](includes/crm_md.md)] Par exemple, dans le cadre de la préparation d'un devis, il peut s'avérer utile de savoir si vous avez suffisamment d'articles dans l'inventaire pour répondre à la commande. Pour plus d’informations, voir [Utiliser Dynamics 365 Sales depuis Business Central](marketing-integrate-dynamicscrm.md).

> [!NOTE]
> Cet article décrit le processus d’intégration des versions en ligne de [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[prod_short](includes/prod_short.md)] via [!INCLUDE[prod_short](includes/cds_long_md.md)]. Pour plus d'informations sur la configuration sur site, voir [Préparation de l'intégration à Dynamics 365 Sales On-Premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

## <a name="integrate-through-dataverse"></a>Intégration au moyen de Dataverse

Pour faciliter la connexion et la synchronisation des données avec d'autres applications Dynamics 365, [!INCLUDE[prod_short](includes/prod_short.md)] s'intègre également à [!INCLUDE[prod_short](includes/cds_long_md.md)]. Par exemple, vous pouvez vous connecter à [!INCLUDE[crm_md](includes/crm_md.md)], ou même des applications que vous générez vous-même. S’il s’agit de votre toute première intégration, vous devez l’effectuer au moyen de [!INCLUDE[prod_short](includes/cds_long_md.md)]. Pour en savoir plus, consultez [Intégration à Dataverse](admin-common-data-service.md).

Si vous êtes déjà intégré [!INCLUDE[crm_md](includes/crm_md.md)] à [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez continuer à synchroniser les données à l’aide de votre configuration. Cependant, si vous mettez à niveau ou désactivez votre intégration [!INCLUDE[crm_md](includes/crm_md.md)], vous devez vous connecter au moyen de [!INCLUDE[prod_short](includes/cds_long_md.md)] pour la réactiver. Pour en savoir plus, consultez [Mise à niveau d'une intégration à Dynamics 365 Sales](admin-upgrade-sales-to-cds.md).

> [!NOTE]
> La reconnexion au moyen de [!INCLUDE[prod_short](includes/cds_long_md.md)] affecte les paramètres de synchronisation par défaut et remplace toute configuration dont vous disposez. Par exemple, les mappages de table par défaut sont affectés.

## <a name="integration-settings-that-are-specific-to-a--integration"></a>Paramètres d’intégration dédiés à une intégration [!INCLUDE[crm_md](includes/crm_md.md)]

L’intégration à [!INCLUDE[prod_short](includes/prod_short.md)] se produit au moyen de [!INCLUDE[prod_short](includes/cds_long_md.md)], et de nombreux paramètres et tables standard sont fournis. Outre les paramètres standard, certains sont dédiés à [!INCLUDE[crm_md](includes/crm_md.md)]. Les sections suivantes répertorient ces paramètres.

## <a name="permissions-and-security-roles-for-user-accounts-in-sales"></a>Autorisations et rôles de sécurité pour les comptes d’utilisateur dans Sales

Lorsque vous installez la solution d'intégration, les autorisations pour le compte d'utilisateur d'intégration sont configurées. Si ces autorisations sont modifiées, vous devrez peut-être les réinitialiser. Vous pouvez le faire en réinstallant la solution d'intégration en choisissant **Redéployer la solution d'intégration** sur la page **Configuration de la connexion Dynamics 365**. Les rôles de sécurité suivants sont déployés :

* Administrateur d'intégration Dynamics 365 Business Central
* Utilisateur d'intégration Dynamics 365 Business Central
* Utilisateur de disponibilité produit Dynamics 365 Business Central

> [!NOTE]
> Pour utiliser l’action **Ouvrir dans Business Central** dans Sales, vous devez disposer des privilèges suivants pour les tables suivantes :
>
> * Vous devez disposer des autorisations de lecture pour la table Dynamics 365 Business Central Connexion (nav_connection).
> * Vous devez disposer des autorisations de lecture, d’écriture et de suppression pour la table Connexion par défaut Dynamics 365 Business Central (nav_defaultconnection).

### <a name="connection-settings-in-the-setup-guide"></a>Paramètres de connexion dans le guide de configuration

Vous pouvez utiliser un guide de configuration assistée pour configurer rapidement la connexion et spécifier des fonctions avancées, comme le couplage entre les enregistrements.

1. Choisissez **Configuration et extensions**, puis **Configuration assistée**.
2. Sélectionnez **Configurer la connexion Dynamics 365 Sales** pour lancer le guide de configuration assistée.
3. Renseignez les champs selon vos besoins.
4. En option, il existe des paramètres avancés qui peuvent améliorer la sécurité et activer davantage de fonctionnalités. Le tableau suivant décrit les paramètres avancés.  

| Champ | Désignation |
|--|--|
| **Importer une solution Dynamics 365 Sales** | Installez cette fonctionnalité pour installer et configurer la solution d’intégration dans [!INCLUDE[crm_md](includes/crm_md.md)]. |
|**Synchroniser automatiquement la disponibilité article**|Spécifie que la file d’attente des travaux de disponibilité de l’article doit être programmée. La file d’attente des travaux s'exécute toutes les 30 minutes et met à jour la disponibilité des éléments couplés.|
| **Activer l’intégration du document de vente hérité** | Quand les utilisateurs créent des documents de vente dans [!INCLUDE[crm_md](includes/crm_md.md)] et exécutent les commandes dans [!INCLUDE[prod_short](includes/prod_short.md)], ce paramètre intègre le processus dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour plus d'informations, voir [Activer l'intégration du traitement des documents de vente](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration).<br><br>**Remarque :** Vous ne pouvez pas utiliser cette option si vous utilisez l’option **Synchronisation bidirectionnelle des documents de vente**. Les deux paramètres s’excluent mutuellement. Pour en savoir plus sur cette option, rendez-vous sur [Synchronisation simple et bidirectionnelle des documents de vente](#single-and-bi-directional-synchronization-of-sales-orders). |
|**Activer la connexion à Dynamics 365 Sales** | Activez la connexion vers [!INCLUDE[crm_md](includes/crm_md.md)]. |
| **Version du SDK Dynamics 365** | Cela est pertinent uniquement si vous l’intégrez à une version locale de [!INCLUDE[crm_md](includes/crm_md.md)]. Il s’agit du kit de développement logiciel Dynamics 365 (SDK) (également appelé Xrm) que vous utilisez pour connecter [!INCLUDE[prod_short](includes/prod_short.md)] à [!INCLUDE[crm_md](includes/crm_md.md)]. La version doit être compatible à la version du SDK utilisée par [!INCLUDE[crm_md](includes/crm_md.md)], et identique ou plus récente que la version utilisée par [!INCLUDE[crm_md](includes/crm_md.md)]. |
|**Synchronisation bidirectionnelle des documents de vente**|Synchronisez les documents de vente dans les deux sens. Pour en savoir plus sur cette option, rendez-vous sur [Synchronisation simple et bidirectionnelle des commandes clients](#single-and-bi-directional-synchronization-of-sales-orders).<br><br>**Remarque :** Vous ne pouvez pas utiliser cette option si vous utilisez l’option **Activer l’intégration des documents de vente hérités**. Les deux paramètres s’excluent mutuellement.|

> [!TIP]
> Si vous souhaitez également intégrer Microsoft Dynamics 365 Field Service, le guide fournit un étape facultatif qui peut vous aider. Pour en savoir plus sur l’intégration avec Field Service, accédez à [Intégrer avec Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md).

### <a name="connection-settings-on-the-microsoft-dynamics-365-connection-setup-page"></a>Paramètres de connexion sur la page Configuration de la connexion Microsoft Dynamics 365

Saisissez les informations suivantes pour la connexion de [!INCLUDE[prod_short](includes/prod_short.md)] vers [!INCLUDE[crm_md](includes/crm_md.md)].

| Champ | Désignation |
|--|--|
|**URL Dynamics 365 Sales**|L'URL de votre instance de [!INCLUDE[crm_md](includes/crm_md.md)]. Ce paramètre permet aux utilisateurs d'ouvrir les enregistrements dans [!INCLUDE[prod_short](includes/prod_short.md)] qui correspondent aux enregistrements dans [!INCLUDE[crm_md](includes/crm_md.md)]. Par exemple, un compte ou un produit. Les enregistrements [!INCLUDE[prod_short](includes/prod_short.md)] s'ouvrent dans [!INCLUDE[prod_short](includes/prod_short.md)].|
|**Synchroniser automatiquement la disponibilité article**|Spécifie que la file d’attente des travaux de disponibilité de l’article doit être programmée. La file d’attente des travaux s'exécute toutes les 30 minutes et met à jour la disponibilité des éléments couplés.|
|**Version du SDK Dynamics 365**|Si vous effectuez une intégration avec une version locale de [!INCLUDE[crm_md](includes/crm_md.md)], utilisez le kit de développement logiciel Dynamics 365 (également appelé Xrm) pour Connecter [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. La version que vous sélectionnez doit être compatible avec la version du SDK utilisée par [!INCLUDE[crm_md](includes/crm_md.md)]. Cette version est égale ou plus récente que la version utilisée par [!INCLUDE[crm_md](includes/crm_md.md)].|

En plus de ces paramètres, entrez les paramètres suivants pour [!INCLUDE[crm_md](includes/crm_md.md)].

| Champ | Désignation |
|--|--|
| **L'intégration des documents de vente est activée** | Laissez les utilisateurs envoyer des documents de vente et des devis activés dans [!INCLUDE[crm_md](includes/crm_md.md)], et les visualiser et les traiter dans [!INCLUDE[prod_short](includes/prod_short.md)]. Ce paramètre intègre le processus dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour plus d'informations, voir [Activer l'intégration du traitement des documents de vente](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration). |
| **Créer automatiquement des documents de vente** | Permet de créer un document de vente dans [!INCLUDE[prod_short](includes/prod_short.md)] lorsqu'un utilisateur en crée et en envoie un dans [!INCLUDE[crm_md](includes/crm_md.md)]. |
| **Traiter automatiquement les devis** | Permet de traiter un devis dans [!INCLUDE[prod_short](includes/prod_short.md)] lorsqu'un utilisateur en crée et en active un dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour plus d’informations, reportez-vous à la rubrique [Gestion des données de devis spéciales](/dynamics365/business-central/marketing-integrate-dynamicscrm?tabs=new-experience#handling-sales-quotes-data). |
|**Synchronisation bidirectionnelle des documents de vente**|Synchronisez les documents de vente dans les deux sens. Pour en savoir plus sur cette option, rendez-vous sur [Synchronisation simple et bidirectionnelle des documents de vente](#single-and-bi-directional-synchronization-of-sales-orders).|
<!--
### <a name="user-account-settings"></a>User Account Settings
Integration with Business Central through Dataverse requires an administrator user account and an account that is used only for the connection between the apps. This account is called the "integration user." When you install the CDS Base Integration Solution, permissions for the integration user account are configured in [!INCLUDE[crm_md](includes/crm_md.md)]. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution or by manually resetting them. The following tables list the minimum permissions for the user accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  -->
### <a name="single-and-bi-directional-synchronization-of-sales-orders"></a>Synchronisation simple et bidirectionnelle des documents de vente

Lorsque vous configurez votre intégration, des options contrôlent la direction dans laquelle vous synchronisez les commandes client et la manière dont vous les soumettez.

L’option **Synchronisation bidirectionnelle des documents de vente** vous permet de synchroniser les documents de vente de Sales vers [!INCLUDE [prod_short](includes/prod_short.md)], et vice versa. Par exemple, si un client change d’avis sur le produit ou la quantité dans [!INCLUDE[crm_md](includes/crm_md.md)], vous pouvez archiver le document de vente et créer un nouveau document dans [!INCLUDE[prod_short](includes/prod_short.md)]. Il en est de même pour les modifications dans [!INCLUDE[prod_short](includes/prod_short.md)]. Par exemple, en cas de modification des prix, des montants de taxe ou des dates de livraison prévues, les modifications sont synchronisées dans [!INCLUDE[crm_md](includes/crm_md.md)]. La synchronisation bidirectionnelle permet de tenir vos vendeurs informés des dernières modifications et de l'état des documents de vente.

Pour la synchronisation bidirectionnelle, vous rendez les documents de vente disponibles pour la synchronisation lorsque vous modifiez leur état en **Soumis** dans Sales. Lorsque vous définissez cet état, vous ne pouvez plus modifier les informations sur les lignes de la commande. Lors de la synchronisation, la commande est transférée vers [!INCLUDE [prod_short](includes/prod_short.md)] avec l'état **Libéré**. En cas d’erreur, vous pouvez rétablir l’ordre sur **Ouvert** (dans [!INCLUDE [prod_short](includes/prod_short.md)]) ou **Actif** (dans Sales), puis ajoutez ou supprimez des lignes pour corriger l’erreur, puis soumettez à nouveau la commande.

> [!TIP]
> Lorsque vous activez l’option **Synchronisation bidirectionnelle des documents de vente** , [!INCLUDE [prod_short](includes/prod_short.md)] crée un enregistrement sur la page **Archives des documents de vente** lorsque vous reportez ou modifiez des informations sur une commande. Par exemple, les versions archivées peuvent être utiles pour explorer l’historique d’une commande.

L’option **Activer l’intégration des documents de vente hérités** se synchronise uniquement à partir de Sales vers [!INCLUDE [prod_short](includes/prod_short.md)]. Pour cette option, vous utilisez l’action **Soumettre** dans Sales pour rendre les commandes disponibles pour la synchronisation. Lorsque vous y parvenez, vous ne pouvez plus modifier les informations sur la commande. Lors de la synchronisation, la commande est transférée vers [!INCLUDE [prod_short](includes/prod_short.md)] avec l'état **Libéré**.

Pour utiliser cette option, vous devez fournir des informations d’identification pour un compte d’utilisateur de l’administrateur dans [!INCLUDE[crm_md](includes/crm_md.md)]. Pour en savoir plus, reportez-vous à la rubrique [Gestion des données des documents de vente](marketing-integrate-dynamicscrm.md#handling-sales-order-data).

> [!NOTE]
> Les options **Synchronisation bidirectionnelle des documents de vente** et **Activer l’intégration des documents de vente hérités** s’excluent mutuellement. Vous ne pouvez pas utiliser les deux options en même temps.

Pour les deux options, [!INCLUDE [prod_short](includes/prod_short.md)] affiche tous les documents de vente avec l'état **Soumis** sur la page **Commandes - Microsoft Dynamics 365 Sales**.

### <a name="standard-sales-entity-mapping-for-synchronization"></a>Mappage d’entité Sales standard pour la synchronisation

Les entités dans [!INCLUDE[crm_md](includes/crm_md.md)], telles que les commandes, sont intégrées aux types de tables équivalents dans [!INCLUDE[prod_short](includes/prod_short.md)], tels que des documents de vente. Pour utiliser les données [!INCLUDE[crm_md](includes/crm_md.md)], vous configurez des liens, appelés couplages entre les tables dans [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[crm_md](includes/crm_md.md)].

Le tableau suivant répertorie le mappage standard entre les tables dans [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] que [!INCLUDE[prod_short](includes/prod_short.md)] fournit.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[crm_md](includes/crm_md.md)] | Direction de synchronisation | Filtre par défaut |
|--|--|--|--|
| Unité de mesure | Groupe d'unités | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Article ; | Produit | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | Filtre contact Sales : le **Type de produit** est **Inventaire de vente** |
| Ressource | Produit | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | Filtre contact Sales : le **Type de produit** est **Services** |
| Unité de mesure article | UdM CRM |[!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
| Unité de mesure ressource | UdM CRM |[!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]||
| Groupe d'unités | CRM Uomschedule | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] ||
| Groupe prix client | Liste des prix | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Prix de vente | Tarifs produit | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] | Filtre contact [!INCLUDE[prod_short](includes/prod_short.md)] : le champ **Code de vente** n’est pas vide, le champ **Type de vente** est défini sur **Groupe prix client** |
| Opportunité | Opportunité | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] |  |
| En-tête facture vente | Facturer | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Ligne facture vente | Produit facture | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| En-tête de document de vente | Commande vente | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] <br><br> Pour synchroniser dans les deux sens, vous devez activer le bouton bascule **Synchronisation bidirectionnelle des documents de vente** sur la page **Configuration de la connexion Dynamics 365**.| [!INCLUDE[prod_short](includes/prod_short.md)] Filtre d’en-tête des ventes : **le type de document** est **commande** et **le statut** est **publié** |
| Remarques Document de vente | Remarques Document de vente | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] |  |

> [!NOTE]
> Les mappages pour les tables Unité de mesure article, Unité de mesure ressource et Groupe d’unités sont disponibles uniquement si votre administrateur a activé le bouton à bascule **Mappage de groupe d’unités** sur la page **Configuration de la connexion Microsoft Dynamics 365**. Pour en savoir plus, consultez [Synchronisation des articles et des ressources avec des produits dans différentes unités de mesure](admin-prepare-dynamics-365-for-sales-for-integration.md#synchronize-items-and-resources-with-products-with-different-units-of-measure).

## <a name="synchronize-items-and-resources-with-products-with-different-units-of-measure"></a>Synchroniser des articles et des ressources avec des produits dans différentes unités de mesure

Les entreprises produisent ou achètent souvent les articles dans une unité de mesure, puis les vendent dans une autre. Pour synchroniser des éléments qui utilisent plusieurs unités de mesure, vous devez activer le bouton à bascule  **Mappage de groupe d’unités** sur la page **Configuration de la connexion Microsoft Dynamics 365**. 

Quand vous activez la fonctionnalité, une table Groupe d’unités est créée et affectée à chaque article et ressource dans [!INCLUDE[prod_short](includes/prod_short.md)]. Les tables vous permettent de mapper les tables Groupe d’unités, Unité de mesure article et Unité de mesure ressource dans [!INCLUDE[prod_short](includes/prod_short.md)] au groupe d’unités de Dynamics 365 Sales dans [!INCLUDE[crm_md](includes/crm_md.md)]. L'image suivante montre les mappages.

:::image type="content" source="media/unit group 1.png" alt-text="Mappages de tables pour les groupes d’unités":::

Vous pouvez créer plusieurs unités de mesure pour chaque groupe d’unités et affecter les groupes aux produits dans [!INCLUDE[crm_md](includes/crm_md.md)]. Ensuite, vous pouvez synchroniser les produits avec les articles et les ressources dans [!INCLUDE[prod_short](includes/prod_short.md)]. Vous pouvez coupler manuellement des unités de mesure article ou des unités de mesure ressource à un groupe d’unités. Lorsque vous le faites, si le groupe d’unités de l’élément ou de la ressource n’est pas couplé à un groupe d’unités dans [!INCLUDE[crm_md](includes/crm_md.md)], par exemple parce que le groupe d’unités n’existait pas, [!INCLUDE[prod_short](includes/prod_short.md)] crée automatiquement le groupe d’unités dans [!INCLUDE[crm_md](includes/crm_md.md)].

### <a name="map-items-and-resources-to-products"></a>Mapper d’articles et de ressources avec des produits

Lorsque vous activez l’option **Mappage des groupes d’unités** sur la page **Microsoft Dynamics 365 Configuration de la connexion**, les événements suivants se produisent :

* Des mappages sont créés pour les articles et les ressources.
* Les mappages existants sont supprimés. <!--which mappings?-->
* Une mise à niveau des données crée des groupes d’unités pour les articles et les ressources.

Pour utiliser les nouveaux mappages, vous devez synchroniser les groupes d’unités de mesure, l’unité de mesure article et l’unité de mesure ressource. Vous devez également resynchroniser les articles et les ressources. 

> [!NOTE]
> [!INCLUDE[crm_md](includes/crm_md.md)] ne vous permet pas de modifier un groupe d’unités pour un produit. Par conséquent, vous devez supprimer vos produits et découpler les articles et les ressources, puis synchroniser en créant des produits dans [!INCLUDE[crm_md](includes/crm_md.md)]. 

Les étapes suivantes décrivent les étapes de démarrage du mappage des groupes d’unités :

1. Assurez-vous que les produits de [!INCLUDE[crm_md](includes/crm_md.md)] ne sont pas associés à des articles ou des ressources dans [!INCLUDE[prod_short](includes/prod_short.md)]. S’ils le sont, accédez aux pages **Articles** et/ou **Ressources** et utilisez les options de filtrage pour sélectionner les enregistrements associés. Ensuite, choisissez l’action **Dynamics 365 Sales** et sélectionnez **Découpler**. Cette action planifie une tâche en arrière-plan pour découpler les enregistrements. Pendant que le travail est en cours d’exécution, vous pouvez vérifier son état en utilisant l’action **Journal de synchronisation**. Pour plus d’informations, voir [Couplage et synchronisation](admin-how-to-couple-and-synchronize-records-manually.md). 
2. Étant donné que les nouveaux produits sont créés avec de nouveaux groupes d’unités, pour éviter les doublons de noms, effectuez l’une des étapes suivantes : [!INCLUDE[crm_md](includes/crm_md.md)] 

  * Renommez vos produits, puis supprimez-les de [!INCLUDE[crm_md](includes/crm_md.md)]. Pour plus d’informations, voir [Supprimer des produits (Centre des ventes)](/dynamics365/sales-enterprise/retire-product). Pour modifier en bloc vos produits dans Microsoft Excel, connectez-vous à Power Apps, choisissez votre environnement, accédez à la table **Produit** et choisissez l’onglet **Données**. Effacez tous les filtres appliqués. Dans le groupe **Données**, choisissez l’action **Modifier les données dans Excel**. Ajoutez un préfixe ou un suffixe aux produits couplés, puis supprimez-les.
    * Retirez vos produits et supprimez-les. 

3. Suivez ces étapes pour synchroniser **Groupes d’unités**, **Unité**, **Articles**, et **Ressources** :
    1. Dans [!INCLUDE[prod_short](includes/prod_short.md)], ouvrez la page **Configuration de la connexion Dynamics 365 Sales**.
    2. Utilisez l’action **Exécuter la synchronisation complète** pour ouvrir la page **Révision de synchr. complète Dataverse**.
    3. Pour les mappages **UDM ARTICLE**, **UDM RESSOURCE**, ET **GROUPE D’UNITÉS**, choisissez l’action **Recommander la synchronisation complète**.
    4. Sélectionnez l’action **Synchroniser tout**.

    > [!NOTE]
    > Pour les mappages qui n’ont pas encore été entièrement synchronisés, cette action les synchronisera entièrement. Pour empêcher ces mappages de se synchroniser, supprimez les mappages de la page. Cela les supprime uniquement de la synchronisation complète actuelle et ne supprime pas les mappages.
    
5. Choisir le mappage **ARTICLE-PRODUIT**, puis choisissez l’action **Redémarrage**. Le redémarrage crée des produits à partir des articles dans [!INCLUDE[crm_md](includes/crm_md.md)], et attribue un nouveau groupe d’unités spécifique à l’article.
6. Choisir le mappage **RESSOURCE-PRODUIT**, puis choisissez l’action **Redémarrage**. Le redémarrage crée des produits à partir des ressources dans [!INCLUDE[crm_md](includes/crm_md.md)], et attribue un nouveau groupe d’unités spécifique aux ressources.

### <a name="synchronization-rules"></a>Règles de synchronisation

Le tableau suivant répertorie les règles qui contrôlent la synchronisation entre [!INCLUDE[crm_md](includes/crm_md.md)] et [!INCLUDE[prod_short](includes/prod_short.md)]. Ces règles s’ajoutent à celles définies pour Dataverse, qui s’appliquent également. Pour en savoir plus, consultez [Mappage d'entité standard](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization).

> [!NOTE]  
> Les modifications apportées aux données par le compte d'utilisateur d'intégration ne sont pas synchronisées. Par conséquent, nous vous avons recommandé de ne pas modifier les données lors de l'utilisation de ce compte. Pour en savoir plus, reportez-vous à la rubrique [Configuration des comptes d'utilisateur pour l'intégration à Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

|Table|Règle|
|-----|----|
|Unités de mesure|Les unités de mesure sont synchronisées avec les groupes d'unités dans [!INCLUDE[crm_md](includes/crm_md.md)]. Une seule unité de mesure peut être définie dans le groupe d'unités.|
|Articles|Lorsqu’il synchronise les articles avec les produits, il crée automatiquement une liste de prix dans. [!INCLUDE[crm_md](includes/crm_md.md)]  [!INCLUDE[prod_short](includes/prod_short.md)]  [!INCLUDE[crm_md](includes/crm_md.md)] Pour éviter les erreurs de synchronisation, vous ne devez pas modifier cette liste de prix manuellement.|
|Ressources|Les ressources sont synchronisées avec les produits [!INCLUDE[crm_md](includes/crm_md.md)] dont le type de produit est Service.|
|Groupes prix client|Les groupes de prix client sont synchronisés avec les listes de prix dans Sales.|
|Prix vente|Les prix de vente dont le type vente est Groupe prix client et dont le code vente est défini sont synchronisés avec les lignes de liste de prix dans [!INCLUDE[crm_md](includes/crm_md.md)].|
|Opportunités|Les opportunités sont synchronisées avec les opportunités dans [!INCLUDE[crm_md](includes/crm_md.md)]. La valeur Code représentant définit le propriétaire de la table couplée dans [!INCLUDE[crm_md](includes/crm_md.md)].|
|Factures vente reportées|Les factures vente reportées sont synchronisées avec les factures vente. Pour qu’une facture puisse être synchronisée, il est préférable de synchroniser toutes les autres tables pouvant participer à la facture, depuis les représentants jusqu'aux listes de prix. La valeur Code représentant de l’en-tête de facture définit le propriétaire de la table couplée dans Sales.|
|Commandes vente|Lorsque vous activez l’intégration des commandes clients, lorsque vous publiez des commandes clients dans [!INCLUDE[prod_short](includes/prod_short.md)] qui ont été créées à partir de commandes clients soumises dans [!INCLUDE[crm_md](includes/crm_md.md)] elles se synchronisent avec les commandes clients dans [!INCLUDE[crm_md](includes/crm_md.md)]. Avant de synchroniser les commandes, nous vous recommandons de synchroniser d’abord toutes les tables impliquées dans la commande. Par exemple, les vendeurs et les listes de prix. Le champ Code représentant de l’en-tête de commande définit le propriétaire de la table couplée dans [!INCLUDE[crm_md](includes/crm_md.md)].|

### <a name="synchronization-jobs-for-a-sales-integration"></a>Projets de synchronisation pour une intégration de Sales

Les projets sont exécutés dans l’ordre suivant pour éviter les dépendances de couplage entre les tables. Il s’agit d’autres projets disponibles à partir de Dataverse. Pour plus d’informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](./admin-job-queues-schedule-tasks.md).

1. Projet de synchronisation Dynamics 365 Sales - UNITÉ DE MESURE  
2. Projet de synchronisation Dynamics 365 Sales - RESSOURCE-PRODUIT  
3. Projet de synchronisation Dynamics 365 Sales - ARTICLE-PRODUIT  
4. Projet de synchronisation Dynamics 365 Sales - GRPPRXCLI-PRIX.
5. Projet de synchronisation Dynamics 365 Sales - PRXVENTE-PRXPROD.
6. Projet de synchronisation Dynamics 365 Sales - FACTVENTEVALIDÉES-FACT.

### <a name="default-synchronization-job-queue-entries"></a>Écritures de file d’attente des travaux de synchronisation par défaut

Le tableau suivant décrit les projets de synchronisation par défaut pour [!INCLUDE[crm_md](includes/crm_md.md)].  

|Écriture file d'attente des travaux|Description|Sens|Correspondance table intégration|Fréquence de synchronisation par défaut (minutes)|Temps de veille pour inactivité par défaut (minutes)|  
|---------------------|---------------------------------------|---------------|-------------------------------|-----|-----|  
|Projet de synchronisation Dynamics 365 Sales - UNITÉ DE MESURE|Permet de synchroniser les groupes d'unités [!INCLUDE[crm_md](includes/crm_md.md)] avec les unités de mesure [!INCLUDE[prod_short](includes/prod_short.md)].|De [!INCLUDE[prod_short](includes/prod_short.md)] vers [!INCLUDE[crm_md](includes/crm_md.md)]|UNITÉ DE MESURE|30|720<br> (12 heures)|
|Projet de synchronisation Dynamics 365 Sales - RESSOURCE-PRODUIT|Permet de synchroniser les produits [!INCLUDE[crm_md](includes/crm_md.md)] avec les ressources [!INCLUDE[prod_short](includes/prod_short.md)].|De [!INCLUDE[prod_short](includes/prod_short.md)] vers [!INCLUDE[crm_md](includes/crm_md.md)]|RESSOURCE-PRODUIT|30|720<br> (12 heures)|
|Projet de synchronisation Dynamics 365 Sales - ARTICLE - PRODUIT|Permet de synchroniser les produits [!INCLUDE[crm_md](includes/crm_md.md)] avec les articles [!INCLUDE[prod_short](includes/prod_short.md)].|De [!INCLUDE[prod_short](includes/prod_short.md)] vers [!INCLUDE[crm_md](includes/crm_md.md)]|ARTICLE-PRODUIT|30|1440<br> (24 heures)|
|Projet de synchronisation Dynamics 365 Sales - GRPPRXCLI-PRIX|Permet de synchroniser les listes de prix de vente [!INCLUDE[crm_md](includes/crm_md.md)] avec les groupes de prix client [!INCLUDE[prod_short](includes/prod_short.md)].| |GROUPES DE PRIX CLIENT - LISTES DE PRIX DE VENTE|30|1440<br> (24 heures)|
|Projet de synchronisation Dynamics 365 Sales - PRXVENTE-PRXPRODUIT|Permet de synchroniser les prix de produit [!INCLUDE[crm_md](includes/crm_md.md)] avec les prix de vente [!INCLUDE[prod_short](includes/prod_short.md)].||PRIX DE PRODUIT - PRIX DE VENTE|30|1440<br> (24 heures)|
|Projet de synchronisation Dynamics 365 Sales - FACTVENTEVALIDEES-FACT|Permet de synchroniser les factures [!INCLUDE[crm_md](includes/crm_md.md)] avec les factures vente [!INCLUDE[prod_short](includes/prod_short.md)] reportées.|De [!INCLUDE[prod_short](includes/prod_short.md)] vers [!INCLUDE[crm_md](includes/crm_md.md)]|FACTURES - FACTURES VENTE REPORTÉES|30|1440<br> (24 heures)|
|Synchronisation Statistiques client - Dynamics 365 Sales|Permet de mettre à jour les comptes [!INCLUDE[crm_md](includes/crm_md.md)] avec les données client [!INCLUDE[prod_short](includes/prod_short.md)] les plus récentes. Dans [!INCLUDE[crm_md](includes/crm_md.md)], ces informations s'affichent dans le formulaire de vue rapide **Statistiques de compte Business Central** des comptes couplés avec les clients [!INCLUDE[prod_short](includes/prod_short.md)].<br /><br /> Ces données peuvent être également mises à jour manuellement depuis chaque enregistrement du client. Pour en savoir plus, reportez-vous à la rubrique [Coupler et synchroniser manuellement les enregistrements](admin-how-to-couple-and-synchronize-records-manually.md). </BR></BR>**Remarque :** cette file d'attente de projets est pertinente uniquement si la solution d'intégration [!INCLUDE[prod_short](includes/prod_short.md)] est installée dans [!INCLUDE[crm_md](includes/crm_md.md)]. |Non applicable|Non applicable|30|Non applicable| 

## <a name="connect-to-on-premises-versions-of-business-central-2019-release-wave-1-and-microsoft-dynamics-nav-2018"></a>Se connecter aux versions locales de la 1re vague de lancement de Business Central 2019 et Microsoft Dynamics NAV 2018

L’équipe a annoncé qu’elle abandonnait le type d’authentification. Microsoft Power Platform  [...](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse)  Office 365  Si vous utilisez une version locale antérieure à 2019 Connecter 1, vous devez utiliser le type d’authentification OAuth pour vous connecter en ligne. [!INCLUDE[prod_short](includes/prod_short.md)]  [!INCLUDE [prod_short](includes/prod_short.md)]  [!INCLUDE[crm_md](includes/crm_md.md)]  Les étapes de cette section décrivent comment établir la connexion aux versions de produit suivantes :

* 1re vague de lancement 2019 de Business Central
* Microsoft Dynamics NAV 2018

### <a name="prerequisites"></a>Conditions préalables

* Vous devez avoir un abonnement Microsoft Azure. Un compte d’essai fonctionne pour l’enregistrement de l’application.
* [!INCLUDE[crm_md](includes/crm_md.md)] est configuré pour utiliser l'un des types d'authentification suivants :

   * Office 365 (héritage)

     > [!IMPORTANT]
     > À compter d'avril 2022, Office365 (hérité) ne sera plus pris en charge. Pour plus d'informations, consultez [Modifications importantes (déconseillées) à venir dans Power Apps, Power Automate et les applications d'engagement client](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse).

   * OAuth

### <a name="connect-business-central-2019-release-wave-1-and-dynamics-nav-2018"></a>Se connecter à la 1re vague de lancement 2019 Business Central et Dynamics NAV 2018

1. Importez la solution d’intégration Microsoft Dynamics 365 Business Central dans votre environnement [!INCLUDE[crm_md](includes/crm_md.md)]. La solution d’intégration est disponible dans le dossier CrmCustomization de votre DVD d’installation [!INCLUDE[prod_short](includes/prod_short.md)] ou Dynamics NAV 2018. Selon la version de votre produit, importez l’une des solutions suivantes :

   * Pour [!INCLUDE[prod_short](includes/prod_short.md)], le dossier contient les solutions DynamicsNAVIntegrationSolution_v9 et DynamicsNAVIntegrationSolution_v91. . La solution à importer dépend de la version de [!INCLUDE[crm_md](includes/crm_md.md)] à laquelle vous êtes connecté. [!INCLUDE[crm_md](includes/crm_md.md)] en ligne nécessite la solution d’intégration DynamicsNAVIntegrationSolution_v91.
   * Pour Dynamics NAV 2018, installez la solution DynamicsNAVIntegrationSolution.

2. Créez un utilisateur d’intégration non interactif dans votre environnement [!INCLUDE[crm_md](includes/crm_md.md)] et attribuez à l’utilisateur les rôles de sécurité suivants. Pour en savoir plus, reportez-vous à la rubrique [Créer un compte d'utilisateur non interactif](/power-platform/admin/create-users-assign-online-security-roles#create-a-non-interactive-user-account).

   * Administrateur d'intégration Dynamics 365 Business Central
   * Utilisateur d'intégration Dynamics 365 Business Central

   > [!Important]
   > Cet utilisateur ne doit pas avoir le rôle de sécurité Administrateur système. De plus, vous ne pouvez pas utiliser le compte d’administrateur système en tant qu’utilisateur d’intégration.

3. Dans le portail Azure, créez une inscription d’application pour [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d’informations, consultez [Enregistrer une application dans Microsoft Entra ID](/powerapps/developer/data-platform/walkthrough-register-app-azure-active-directory). 
  
   > [!NOTE]
   > Nous vous recommandons d’enregistrer l’application dans le même locataire que votre environnement Dataverse afin que vous n’ayez pas à consentir à ce que l’application accède à l’environnement. Si vous enregistrez l’application dans un autre environnement, vous devez vous connecter à Microsoft Entra ID en utilisant le compte administrateur de votre environnement Dataverse et donner votre consentement.
   >
   > De plus, l’application que vous enregistrez ne doit pas avoir de secret. Connecter une application avec un secret à Dataverse est disponible uniquement dans la 1re vague de lancement 2020 de Business Central et versions ultérieures.
  
4. Selon la version de votre produit, faites l’une des étapes suivantes :

    * Dans [!INCLUDE[prod_short](includes/prod_short.md)], rechercher **Configuration de la connexion Microsoft Dynamics 365**, puis choisissez le lien associé. 
    * Dans Dynamics NAV 2018, recherchez **Configuration de la connexion Microsoft Dynamics 365 for Sales**, puis choisissez le lien associé.

5. Dans le champ **Type d’authentification**, choisissez l’option pour OAuth. 
6. Choisissez la version du SDK CRM qui correspond à la version de la solution que vous avez importée à l’étape 1.

   > [!NOTE]
   > Cette étape n’est pertinente que pour [!INCLUDE[prod_short](includes/prod_short.md)].

7. Saisissez l’URL de votre environnement [!INCLUDE[crm_md](includes/crm_md.md)], puis entrez le nom d’utilisateur et le mot de passe de l’utilisateur d’intégration. 

   * Dans [!INCLUDE[prod_short](includes/prod_short.md)], utilisez le champ **Adresse du serveur**.
   * Dans Dynamics NAV 2018, utilisez le champ **URL Dynamics 365 Sales**.

8. Dans le champ **Chaîne de connexion**, spécifiez le code de l’enregistrement de l’application. Ce champ a deux jetons dans lesquels le code de votre application doit être spécifié.

   |Jeton           |Description  |
   |----------------|-------------|
   |**AppId**       |Définissez le code de l’application.      |
   |**RedirectUri** |Définissez le code de l’application, mais ajoutez le préfixe **app://**.         |

    **Exemple** L’exemple suivant montre une chaîne de connexion.

    ```
    AuthType=OAuth;Username=jsmith@contoso.onmicrosoft.com;Password=****;Url=https://contosotest.crm.dynamics.com;AppId=<your AppId>;RedirectUri=app://<your AppId>;TokenCacheStorePath=;LoginPrompt=Auto
    ```
9. Activez la connexion.

> [!Note]
> Si vous souhaitez configurer une connexion à une instance [!INCLUDE[crm_md](includes/crm_md.md)] avec un type d’authentification spécifique, renseignez les champs du raccourci **Détails du type d’authentification**. Pour plus d'informations, consultez [Authentification avec les services web Microsoft Dataverse](/powerapps/developer/data-platform/authentication). Cette étape n'est pas requise lors de la connexion d'une version en ligne de [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="see-also"></a>Voir aussi .

[Configuration des comptes d'utilisateur pour intégration à [!INCLUDE[crm_md](includes/crm_md.md)]](admin-setting-up-integration-with-dynamics-sales.md)  
[Configurer une connexion vers [!INCLUDE[crm_md](includes/crm_md.md)]](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronisation de Business Central et de [!INCLUDE[crm_md](includes/crm_md.md)]](admin-synchronizing-business-central-and-sales.md)  
[Préparation de l'intégration à Dynamics 365 Sales On-Premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)


[!INCLUDE[footer-include](includes/footer-banner.md)]
