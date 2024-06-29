---
title: Extension de gestion du groupe TVA pour le Royaume-Uni
description: Vous pouvez vous engager avec d’autres entreprises pour former un groupe TVA où tous les membres déclarent la TVA dans une seule déclaration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'VAT, value added tax, report'
ms.search.form: '4700, 4701, 4703, 4704, 4705, 4706, 4707, 4708, 4709,'
ms.date: 06/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="the-vat-group-management-extension-for-the-united-kingdom"></a>Extension de gestion du groupe TVA pour le Royaume-Uni

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Vous pouvez connecter une ou plusieurs entreprises du Royaume-Uni pour combiner la déclaration de taxe sur la valeur ajoutée (TVA) sous un numéro d’enregistrement unique. Ce type d’arrangement est connu sous le nom de *Groupe TVA*. Vous pouvez vous engager avec le groupe en tant que membre ou comme société représentante du groupe.

## <a name="forming-a-vat-group"></a>Formation d’un groupe TVA

Les membres du groupe TVA et la société représentante du groupe peuvent utiliser le guide de configuration assisté **Configuration de la gestion des groupes TVA** pour définir à la fois leur engagement avec le groupe et créer une connexion entre leurs locataires [!INCLUDE[prod_short](includes/prod_short.md)]. Les membres du groupe utilisent cette connexion pour soumettre leurs déclarations de TVA à la société représentante du groupe. Le représentant du groupe utilise ensuite une seule déclaration de TVA pour soumettre la TVA du groupe aux autorités fiscales.

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge la soumission des déclarations de TVA intragroupe pour les compagnies utilisant [!INCLUDE[prod_short](includes/prod_short.md)] sur site ou en ligne, dans n'importe quelle combinaison, ce qui influence la configuration de la communication entre les entreprises. Cet article décrit diverses configurations de groupes.

### <a name="license-requirements"></a>Exigences en matière de licences

Les participants du groupe doivent être autorisés à utiliser [!INCLUDE[prod_short](includes/prod_short.md)]. Vous ne pouvez pas utiliser de comptes d’invité dans les groupes TVA.

* Pour calculer et soumettre des déclarations de TVA, un utilisateur doit être un utilisateur complet de [!INCLUDE[prod_short](includes/prod_short.md)].
* La licence Team Member [!INCLUDE[prod_long](includes/prod_long.md)] est obligatoire pour vous connecter et effectuer des tâches de base, telles que la création de comptes.

## <a name="set-up-a-vat-group"></a>Configurer un groupe TVA

Voici l'ordre recommandé des étapes qu'un administrateur utilise pour configurer un groupe TVA :

1. Créez la configuration dans [Configuration Microsoft Entra ID pour les membres du groupe](#microsoft-entra-id-setup-for-group-members).
2. Partagez les informations techniques dont les membres du groupe TVA et la compagnie représentante du groupe ont besoin pour connecter leur locataires [!INCLUDE[prod_short](includes/prod_short.md)]. Habituellement, le représentant du groupe dispose de ces informations, telles que l'[URL de l'API](#group-api-setup) et le nom de l’environnement du représentant du groupe TVA auquel les membres soumettent leurs données de TVA.
3. Créez des utilisateurs que les membres du groupe TVA utilisent pour s’authentifier lorsqu’ils se connectent au [!INCLUDE[prod_short](includes/prod_short.md)] de la société représentante du groupe TVA. Les utilisateurs doivent disposer de licences d’utilisation complètes pour [!INCLUDE[prod_short](includes/prod_short.md)].
4. Exécutez le guide de configuration assistée **Configurer la gestion des groupes TVA** pour connecter les membres du groupe TVA.

   Le représentant du groupe TVA doit fournir certaines informations aux membres du groupe pour finaliser leur configuration. (En savoir plus dans la section [Configurer des membres du groupe TVA](#set-up-vat-group-members) ci-dessous.) Notez le **Code de membre du groupe** pour chaque membre du groupe TVA. La compagnie représentante du groupe a besoin de ces codes pour ajouter les compagnies au groupe TVA.
5. Configurez l’extension de gestion du groupe TVA dans le [!INCLUDE[prod_short](includes/prod_short.md)] de la société représentante du groupe TVA en utilisant le guide de configuration assistée **Configurer la gestion des groupes TVA**.

> [!NOTE]
> Pour se connecter à la société représentante du groupe TVA, les membres du groupe doivent disposer d’un compte utilisateur pouvant accéder au [!INCLUDE[prod_short](includes/prod_short.md)] de la société représentante du groupe TVA. Le représentant du groupe TVA doit créer au moins un utilisateur pour cela. Cependant, pour des raisons de sécurité, nous leur avons recommandé de créer un utilisateur pour chaque membre du groupe TVA, qui peut être un compte d'utilisateur système non lié à une personne réelle. Assurez-vous de distribuer les informations d’identification des utilisateurs aux membres du groupe TVA de manière sécurisée.

### <a name="microsoft-entra-id-setup-for-group-members"></a>Configuration Microsoft Entra ID pour les membres du groupe

Lorsque la société représentante du groupe TVA utilise [!INCLUDE[prod_short](includes/prod_short.md)] en ligne ou sur site, les membres du groupe TVA utilisent Microsoft Entra ID pour authentifier les utilisateurs lorsqu’ils soumettent des déclarations de TVA à la société représentante du groupe TVA. Pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site, les membres doivent configurer l’authentification unique. En savoir plus dans la rubrique [Configurer l’authentification Microsoft Entra avec WS-Federation](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-active-directory?tabs=singletenant%2Cadmintool).

Si les membres du groupe TVA utilisent également [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, le membre peut s'authentifier avec les informations d'identification de l'utilisateur désigné et les informations de connexion fournies par le représentant du groupe. En savoir plus dans la section [Configurer des membres du groupe TVA](#set-up-vat-group-members) ci-dessous.

Les membres du groupe TVA qui ont [!INCLUDE[prod_short](includes/prod_short.md)] sur site doivent configurer un enregistrement d’application dans Microsoft Entra ID pour le locataire [!INCLUDE[prod_short](includes/prod_short.md)] de la société représentante du groupe TVA. L’enregistrement de l’application permet au [!INCLUDE[prod_short](includes/prod_short.md)] en ligne de la société représentante du groupe TVA d’authentifier le membre du groupe. En savoir plus dans la rubrique [Démarrage rapide : enregistrer une application avec la plateforme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app).

Lorsque l’administrateur du membre du groupe de TVA crée l’enregistrement d’application dans Microsoft Entra ID, il doit préciser les informations suivantes.

* Dans la section **Authentification**, ajoutez **Web** comme plateforme et utilisez les éléments **URL de redirection** suivants : `https://businesscentral.dynamics.com/OAuthLanding.htm`.
* Dans la section **Authentification**, dans l’option de sélection **Types de compte pris en charge**, sélectionnez **Comptes dans n’importe quel annuaire organisationnel (tout annuaire Microsoft Entra – multi-locataires)**.
* Dans la section **Certificats et secrets**, créez un secret client et notez la valeur. Les membres du groupe TVA ont besoin du secret pour configurer la connexion à la société représentante du groupe.
* Dans la section **Autorisations API**, ajoutez des autorisations à [!INCLUDE[prod_short](includes/prod_short.md)]. Activez l’accès délégué à **Finances.ReadWrite.All** et **user_impersonation**.
* Dans la section **Aperçu**, notez le **Code de l’application (client)**. Les membres du groupe TVA ont besoin du code pour configurer la connexion à la société représentante du groupe.

### <a name="group-api-setup"></a>Configuration de l'API de groupe

Le représentant du groupe TVA crée et fournit une API aux membres du groupe. Les membres utilisent cette API pour se connecter au locataire [!INCLUDE[prod_short](includes/prod_short.md)] et soumettre les déclarations de TVA. Les membres du groupe TVA utilisent souvent [!INCLUDE[prod_short](includes/prod_short.md)] dans des locataires Microsoft Entra séparés. Par conséquent, une configuration est nécessaire pour connecter le membre du groupe TVA et le [!INCLUDE[prod_short](includes/prod_short.md)] du représentant.

> [!NOTE]
> Cette configuration nécessite des informations d’identification pour un compte administrateur disposant d’une licence utilisateur complète pour [!INCLUDE[prod_short](includes/prod_short.md)].

1. Dans le centre d’administration Business Central du locataire de la société représentante, choisissez l’onglet **Environnements**.
1. Choisissez l’environnement du représentant.
1. Dans la section **Détails**, copiez l’**URL**.
1. Ouvrez le Bloc-notes et collez l’URL. Remplacez `https://businesscentral.dynamics.com` par `https://api.businesscentral.dynamics.com/v2.0`.

## <a name="set-up-vat-group-members"></a>Configurer les membres du groupe TVA

Les membres du groupe TVA se connectent à la société représentante en appelant un service web sur le locataire de la société représentante du groupe TVA. L’appelant doit être authentifié à l’aide d’OAuth2. Lors de la mise en place de l'extension de gestion du groupe TVA, les membres sont invités à s'authentifier auprès du représentant du groupe TVA, au cours de laquelle un jeton d'accès est généré et enregistré. Ce jeton d’accès est utilisé lors de la soumission des déclarations de TVA à la société représentante du groupe TVA.

> [!IMPORTANT]
> Les compagnies membres du groupe TVA n’ont pas besoin de se connecter au HMRC, car elles rendent compte par l’intermédiaire de la compagnie représentante du groupe.

Avant que les membres du groupe TVA ne débutent leur configuration (énumérée ci-dessous), ils doivent contacter le représentant du groupe TVA pour obtenir les informations suivantes concernant leur locataire [!INCLUDE[prod_short](includes/prod_short.md)] :

* L’URL de l’API
* Le nom de leur compagnie
* Les informations d’identification de connexion pour l’utilisateur dédié

1. Dans le coin supérieur droit, cliquez sur l'icône **Paramètres** ![Paramètres.](media/ui-experience/settings_icon_small.png "Icône Paramètres du tableau de bord") , puis choisissez l'action **Configuration assistée**.
2. Choisissez l’action **Configurer la gestion des groupes TVA**.
3. Dans le champ **Rôle du groupe TVA**, choisissez **Membre**, puis **Suivant**.
4. Copiez la valeur du **Code de membre du groupe**, puis partagez-la avec la société représentante du groupe TVA afin qu’elle puisse ajouter votre compagnie en tant que membre approuvé du groupe.
5. Dans le champ **Version produit de la société représentante du groupe**, spécifiez la version de [!INCLUDE[prod_short](includes/prod_short.md)] que le représentant utilise.
6. Dans le champ **URL de l’API**, saisissez l’URL de l’API fourni par le représentant du groupe TVA. En règle générale, l’URL est mise en forme comme suit : `https://api.businesscentral.dynamics.com/v2.0/[TENANT-ID]/[ENVIRONMENTNAME]`. Par exemple, `https://api.businesscentral.dynamics.com/v2.0/907869c3-b252-4aca-b9cb-17a15d25477b/UKRepresentative`.
7. Dans le champ **Compagnie représentante du groupe**, saisissez la raison sociale de la compagnie représentante du groupe TVA, par exemple, **CRONUS UK Ltd**.
8. Dans le champ **Type d’authentification**, choisissez **OAuth2**. Si la société représentante du groupe TVA utilise [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, activez le bouton bascule **La société représentante du groupe utilise Business Central Online**, puis choisissez **Suivant**.

   Ensuite, suivez les étapes de la section [La société représentante du groupe TVA utilise Business Central Online](ui-extensions-vat-group.md#vat-group-representative-uses-business-central-online) ou de la section [La société représentante du groupe TVA utilise Business Central sur site](ui-extensions-vat-group.md#vat-group-representative-uses-business-central-on-premises) ci-dessous.

### <a name="vat-group-representative-uses-business-central-online"></a>La société représentante du groupe TVA utilise Business Central Online

1. Entrez les informations d’identification de l’utilisateur fournies par la société représentante du groupe TVA et ajoutez les autorisations requises pour générer le jeton d'accès.
2. Choisissez la configuration des déclarations de TVA que vous utilisez pour soumettre les déclarations de TVA aux autorités fiscales du Royaume-Uni. 

Une fois la configuration terminée, [!INCLUDE[prod_short](includes/prod_short.md)] crée une nouvelle configuration basée sur ce choix vous permettant de soumettre les déclarations de TVA à la société représentante du groupe TVA.

### <a name="vat-group-representative-uses-business-central-on-premises"></a>La société représentante du groupe TVA utilise Business Central sur site

1. Saisissez les informations d'identification de l'utilisateur fournies par le représentant du groupe TVA et choisissez **Suivant**.
2. Dans le champ **Code client**, indiquez le code client de l’enregistrement d’application dans [Configuration de Microsoft Entra ID pour les membres du groupe](#microsoft-entra-id-setup-for-group-members).
3. Dans le champ **Secret client**, indiquez le secret client de l’enregistrement d’application dans Microsoft Entra ID.
4. Dans le champ **Point de terminaison d’autorité OAuth 2.0**, entrez `https://login.microsoftonline.com/common/oauth2`.
5. Dans le champ **URL de ressource OAuth 2.0**, entrez `https://api.businesscentral.dynamics.com/`.
6. Dans le champ **URL de redirection OAuth 2.0**, entrez `https://businesscentral.dynamics.com/OAuthLanding.htm`.
7. Lorsque vous avez spécifié les différents champs, choisissez **Suivant**, puis confirmez la connexion d'authentification pour générer le jeton d'accès.
8. Choisissez la configuration des déclarations de TVA que vous utilisez pour soumettre les déclarations de TVA aux autorités fiscales du Royaume-Uni.

## <a name="set-up-the-vat-group-representative"></a>Configurer la société représentante du groupe TVA

> [!NOTE]
> Pour la version sur site, [!INCLUDE[prod_short](includes/prod_short.md)] prend uniquement en charge une instance de locataire de la société représentante du groupe.

> [!IMPORTANT]
> La compagnie représentante doit activer la connexion du service **Configuration de la TVA HMRC** sur la page **Connexions de services**. Les sociétés représentantes doivent également télécharger les périodes de déclaration de TVA à partir du HMRC.

1. Dans le coin supérieur droit, sélectionnez l’icône **Paramètres**![Paramètres.](media/ui-experience/settings_icon_small.png "Icône Paramètres du tableau de bord"), puis choisissez l’action **Configuration assistée**.
2. Choisissez l’action **Configurer la gestion des groupes TVA**.
3. Dans le champ **Rôle du groupe TVA**, choisissez **Représentant** pour agir en tant que représentant du groupe TVA, puis choisissez **Suivant**.
4. Dans le champ **Compte de déclaration de groupe**, spécifiez le compte de déclaration utilisé pour les montants de TVA du membre du groupe. Ce compte doit avoir des **actifs** comme la **catégorie de compte**.
5. Dans le champ **Compte de déclaration de TVA**, spécifiez le compte que vous utilisez pour les déclarations de TVA. Ce compte doit avoir un **Passif** comme la **catégorie de compte**.
6. Dans le champ **N° zone TVA due**, spécifiez la zone qui représente le montant total de la TVA due à partir d’une soumission de groupe TVA.
7. Dans le champ **Modèle journal général relevé de groupe**, spécifiez le modèle journal général utilisé pour créer le document avec lequel la compagnie représentante du groupe reporte la TVA du groupe sur le compte de relevé.
8. Le champ **Membres approuvés** indique le nombre de membres du groupe configurés pour soumettre les déclarations de TVA au représentant du groupe. Pour ajouter de nouveaux membres, choisissez le nombre souhaité pour ouvrir la page **Membres approuvés du groupe TVA** et ajoutez les informations suivantes :
    1. Dans le champ **Code de membre du groupe**, saisissez un identifiant pour le membre du groupe, tel qu'il s'affiche lors de la configuration du membre du groupe (pour en savoir plus, consultez la section [Configuration des membres du groupe TVA](#set-up-vat-group-members) ci-dessus).
    2. Dans le champ **Nom du membre du groupe**, indiquez le nom du membre du groupe.
    3. Dans le champ **Compagnie**, indiquez la compagnie à partir de laquelle le membre du groupe soumet les déclarations de TVA dans [!INCLUDE[prod_short](includes/prod_short.md)], telle que **CRONUS UK Ltd**.
    4. Spécifiez les informations de contact de la compagnie.

## <a name="use-the-vat-group-management-features"></a>Utiliser des fonctionnalités de gestion du groupe TVA

Les membres du groupe TVA utilisent les processus standard pour préparer les déclarations de TVA. La seule différence est que les membres doivent choisir la version de déclaration **VATGROUP** dans la page **Retour TVA** pour soumettre la déclaration de TVA à la compagnie représentante du groupe TVA plutôt qu'aux autorités. En savoir plus dans la section [À propos de la déclaration Retour TVA](finance-how-report-vat.md#vatreturn).

> [!NOTE]
> Les membres du groupe TVA peuvent corriger les déclarations de TVA soumises tant que la société représentante du groupe n’a pas libéré la déclaration de TVA du groupe. Pour effectuer une correction, le membre du groupe TVA doit créer une déclaration de TVA pour la période de déclaration de TVA et la soumettre à la société représentante du groupe TVA. Du côté de la société représentante du groupe TVA, la dernière déclaration de TVA du membre remplace la précédente et est incluse dans la page **Retours de TVA**.

Les sections suivantes décrivent les tâches que les sociétés représentantes du groupe TVA doivent effectuer pour déposer le retour TVA du groupe.

### <a name="review-vat-member-submissions"></a>Examen des soumissions des membres de la TVA

La page **Soumissions groupe TVA** répertorie les déclarations de TVA que les membres ont soumises. La page sert d’emplacement provisoire pour les soumissions jusqu’à ce que la société représentante du groupe TVA les inclue dans une déclaration de TVA pour le groupe. Le représentant peut ouvrir les soumissions pour passer en revue les cases individuelles contenant le montant déclaré par chaque membre du groupe TVA.

> [!TIP]
> Sur la page **Périodes de retour de TVA**, le champ **Soumission des membres du groupe** indique le nombre de déclarations soumises par les membres. Pour vous assurer que ce nombre est à jour, choisissez l’action **Obtenir les déclarations de TVA**.

### <a name="create-a-group-vat-return"></a>Créer une déclaration de TVA de groupe

Pour déclarer la TVA pour le groupe, sur la page **Déclarations TVA**, créez une déclaration TVA pour votre compagnie uniquement. Ensuite, incluez les dernières soumissions de TVA des membres du groupe TVA en choisissant l’action **Inclure la TVA du groupe**.  

Lorsque la compagnie représentante du groupe a soumis la déclaration de TVA du groupe aux autorités, elle exécute normalement l'action **Calculer et reporter le relevé de TVA**. Cette action ferme les écritures TVA ouvertes et transfère les montants vers le compte de relevé de TVA. Actuellement, cette action ne prend pas en compte les soumissions de groupe. Seules les écritures de TVA de la compagnie représentante du groupe TVA sont reportées. Les montants soumis par les membres du groupe TVA doivent être reportés à l’aide de l’action **Reporter le règlement de TVA du groupe**.

> [!IMPORTANT]
> La fonctionnalité de groupe TVA n’est prise en charge que sur les marchés où [!INCLUDE[prod_short](includes/prod_short.md)] utilise une infrastructure de TVA composé de déclarations de TVA et de périodes de déclaration de TVA. Vous ne pouvez pas utiliser de groupes TVA sur des marchés ayant d’autres implémentations de déclaration de TVA locale, tels que l’Autriche, l’Allemagne, l’Italie, l’Espagne et la Suisse.

## <a name="issue-with-enabling-multifactor-authentication-mfa"></a>Problème lié à l’activation de l’authentification multifacteur (MFA)

Si vous recevez un message d’erreur lié à l’autorisation lors du renouvellement du **Jeton OAuth2** sur la page **Configuration déclaration TVA** après avoir activé MFA, procédez comme suit.  

1. Connectez-vous au **Portail Azure** en tant qu’administrateur d’authentification.  
2. Accédez à **Microsoft Entra Code**.   
3. Accédez à **Utilisateurs**, puis sélectionnez l’utilisateur que vous voulez voir exécuter une action.  
4. Sélectionnez **Méthodes d’authentification**, puis en haut de la page, sélectionnez **Réenregistrement de l’authentification multifacteur obligatoire**. 
5. Revenez à Dynamics 365 Business Central, puis choisissez de renouveler le jeton à partir de l’option **Configuration déclaration TVA**.  

Il doit s’agir d’une configuration unique après avoir activé l’authentification multifacteur pour l’utilisateur sélectionné dans **Configuration déclaration TVA**.  

## <a name="see-also"></a>Voir aussi .

[Fonctionnalité locale du Royaume-Uni dans la version britannique](LocalFunctionality/unitedkingdom/united-kingdom-local-functionality.md)  
[Numériser les taxes au Royaume-Uni](LocalFunctionality/UnitedKingdom/making-tax-digital-submit-vat-return.md)  
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  
[Configuration de la TVA](finance-setup-vat.md)  
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  
[Consolidation des données financières de plusieurs compagnies](finance-consolidated-company-reporting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
