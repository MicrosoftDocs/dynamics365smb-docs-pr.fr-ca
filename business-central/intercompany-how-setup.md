---
title: Configurer le report des transactions intercompagnies
description: Découvrez comment mettre en place un partenariat interentreprises.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 01/31/2023
ms.custom: bap-template
ms.search.keywords: 'IC, group, consolidation, affiliate, subsidiary'
ms.search.form: '605, 620, 602, 603, 601, 600, 652, 653, 606, 607, 609, 608, 621'
---
# Configurer les transactions intersociétés

Les partenariats intercompagnies facilitent la gestion des processus comptables lorsque deux ou plusieurs filiales d’une compagnie font fréquemment affaire entre elles. Les partenaires peuvent échanger des transactions, telles que des ventes et des achats, et les gérer manuellement ou automatiquement. Par exemple, lorsqu’un partenaire envoie une ligne de journal des ventes à un autre partenaire, une ligne de journal des achats est créée pour le partenaire destinataire.

Le plan de compte intersociété peut être, par exemple, une version simplifiée du plan de compte du partenaire de synchronisation. Chaque partenaire mappe ses comptes sur le plan comptable intersociétés. Chaque partenaire mappe également ses dimensions et valeurs de dimension aux dimensions intercompagnies.

> [!NOTE]
> Dans la 1re vague de lancement 2023, nous avons introduit une page améliorée **Configuration intercompagnie**. La nouvelle page facilite la mise en place d’un partenariat intersociétés en regroupant toutes les tâches de mise en place sur une seule page. Si vous êtes un nouveau client [!INCLUDE [prod_short](includes/prod_short.md)], vous utilisez déjà la nouvelle expérience. Si vous êtes un client existant, votre administrateur peut activer la fonctionnalité **Accepter automatiquement les transactions journal général intercompagnies** sur la page **Gestion des fonctionnalités**.
>
> Les tâches décrites dans cet article supposent que le commutateur de fonctionnalité est activé. Si vous avez déjà mis en place un partenariat intersociétés, vous pouvez continuer à l’utiliser.

## Avant de commencer

Avant de commencer à mettre en place votre partenariat intersociétés, il y a quelques décisions à prendre.

|Décision  |Désignation  |
|---------|---------|
|Quel plan comptable doit servir de base au plan comptable intersociétés ?     | Toutes les compagnies du partenariat doivent utiliser le même plan comptable intercompagnie. Vous pouvez baser votre plan comptable intercompagnie sur le plan comptable de l’une des compagnies du partenariat ou créer un plan comptable intercompagnie. Vous mappez les comptes à utiliser dans le partenariat dans les deux sens, afin que chaque partenaire envoie et reçoive des transactions dans les bons comptes. Pour en savoir plus sur la configuration du plan comptable intersociétés, consultez [Configurer les plans comptables intersociétés](#set-up-the-intercompany-charts-of-accounts).         |
|Quelles dimensions doivent être à la base des dimensions intercompagnies?     | Si vous utilisez des dimensions intercompagnies, ils doivent être les mêmes pour toutes les compagnies du partenariat. Après avoir spécifié vos dimensions intercompagnies, mappez leurs valeurs de dimension. En savoir plus sur le mappage des valeurs de dimension dans la rubrique [Configurer les dimensions intercompagnies](#set-up-intercompany-dimensions).        |
|Quels partenaires sont des clients ou des fournisseurs, ou les deux ?     |  Pour en savoir plus sur la configuration de clients et de fournisseurs dans un partenariat intercompagnie, consultez [Configurer des partenaires intercompagnies en tant que clients et fournisseurs](#set-up-intercompany-partners-as-customers-and-vendors).       |
|Voulez-vous préciser les comptes bancaires à utiliser dans le partenariat ?| Vous pouvez accélérer le processus d’enregistrement des transactions de paiement en spécifiant le compte bancaire à utiliser pour chaque compagnie partenaire. Pour en savoir plus, consultez [Spécifier les comptes bancaires à utiliser pour les partenaires intercompagnies](#specify-the-bank-accounts-to-use-for-intercompany-partners). |
|Comment souhaitez-vous identifier les compagnies du partenariat?     | Toutes les parties doivent convenir d’un code d’identification de partenaire intercompagnie unique pour chaque compagnie. Vous attribuerez le code aux fiches client et fournisseur pour identifier les transactions associées. En savoir plus sur les identificateurs sur [Créer une série de numéros](ui-create-number-series.md).        |
|Comment souhaitez-vous traiter les numéros d’article ?     | Si les lignes intersociétés contiennent des articles, vous pouvez soit utiliser vos propres numéros d’article, soit configurer ceux de votre partenaire pour chaque article concerné, dans le champ **Référence fournisseur** ou **N° article commun** de la fiche article. Vous pouvez également utiliser l’action **Référence d’article** pour faire correspondre les numéros de vos articles aux descriptions des articles de vos partenaires intercompagnies. Pour en savoir plus sur les références d’articles, accédez à [Utiliser les références d’articles](inventory-how-use-item-cross-refs.md).        |
|Des ressources sont-elles impliquées ?     | Si vous créez des transactions de vente intercompagnies incluant des ressources, vous devez renseigner le champ **N° cpte G/L partenaire ach. IC** de la fiche ressource de chaque ressource concernée. Le champ contient le numéro du compte GL intercompagnie sur lequel le montant de cette ressource va être validé dans la compagnie partenaire. Pour en savoir plus sur la configuration des ressources, consultez [Configurer des ressources](projects-how-setup-resources.md).<br><br>**REMARQUE**<br>Les transactions d’achat intersociétés qui incluent des ressources, des immobilisations et des frais annexes ne sont pas entièrement prises en charge. Dans la compagnie de votre partenaire, le champ **Type de ligne** sera vide sur les lignes du document achat qui incluent ces entités. Vous devez mettre à jour manuellement le champ.        |

## Présentation des étapes pour commencer

Utilisez la page **Configuration intercompagnie** pour configurer les composantes suivantes des transactions intercompagnies :

* Les paramètres intercompagnies de votre compagnie.
* La compagnie qui sera le partenaire de synchronisation.
* Le plan comptable inter-sociétés que tous les partenaires utilisent pour échanger des transactions.
* Les mappages entre les comptes dans le plan comptable et le plan comptable intersociétés pour les transactions entrantes et sortantes pour chaque partenaire.
* Les dimensions et valeurs de dimension à utiliser et comment elles sont mappées aux dimensions pour chaque partenaire.
* Les entreprises qui sont les partenaires intercompagnies.
* Les compagnies qui sont des fournisseurs ou des clients, ou les deux.

## Configurer un partenaire de synchronisation

Tous les partenaires doivent utiliser le même plan comptable intercompagnies et, si nécessaire, les mêmes dimensions intercompagnies. Vous pouvez gagner du temps lors de la configuration du partenariat en utilisant le plan comptable et les dimensions de l’un des partenaires comme référence pour le plan comptable et les dimensions intercompagnies. La compagnie que vous utilisez comme référence est appelée le *partenaire de synchronisation*. En règle générale, le partenaire de synchronisation est le siège social, mais ce n’est pas obligatoire.

Sur la page **Configuration intersociétés**, chaque partenaire spécifie le partenaire de synchronisation dans le champ **Partenaire de synchronisation**. Par la suite, le plan comptable intercompagnie et les dimensions intercompagnies leur sont automatiquement spécifiés, en fonction de la configuration du partenaire de synchronisation. Les partenaires utilisent ensuite les pages **Mappage de plan comptable intercompagnie** et **Mappage de la dimension intercompagnie** pour mapper leur plan comptable et dimensions au plan comptable et dimensions intercompagnies, et inversement. 

Lorsque vous êtes prêt à synchroniser les données avec votre partenaire de synchronisation, choisissez l’action **Configuration de la synchronisation**.

> [!NOTE]
> Il est important de mapper les comptes et les dimensions dans les deux sens. Autrement dit, à la fois vers le plan comptable et les dimensions intercompagnies, et de ceux-ci vers vos propres comptes et dimensions.

## Configurer les plans comptables intersociétés

Tous les partenaires doivent utiliser le même plan comptable intersociétés et y associer les comptes de leur propre plan comptable. Si le plan comptable de votre compagnie définit le plan comptable intercompagnie de vos compagnies partenaires, suivez les étapes décrites dans cette section.

Si vous utilisez un fichier XML contenant le plan comptable intersociétés, suivez les étapes décrites dans [Importer ou exporter un plan comptable intersociétés](intercompany-how-setup.md#import-or-export-an-intercompany-chart-of-accounts).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Choisissez l’action **Plan comptable IC**.
3. Pour ajouter des comptes, procédez comme suit sur la page **Plan comptable intersociétés** :
    * Choisissez **Nouveau**, puis saisissez chaque compte sur une ligne de la page.  
    * Si votre plan comptable intersociété est identique ou semblable à celui que vous utilisez habituellement, vous pouvez renseigner la page automatiquement en choisissant l'action **Copier à partir du plan comptable**. Vous pouvez modifier au besoin les nouvelles lignes.
    * Si vous avez configuré un plan comptable intersociétés pour un partenaire de synchronisation, utilisez l’action **Configuration de la synchronisation** pour copier ces comptes.

    > [!TIP]
    > Si vous copiez le plan comptable inter-sociétés d’un partenaire de synchronisation, vous pouvez utiliser l’action **Configuration de la synchronisation** pour mettre à jour vos comptes intersociétés avec toute modification apportée par le partenaire aux leurs.

La prochaine étape consiste à mapper votre plan comptable aux plans comptables intersociétés. En savoir plus [Mapper le plan comptable intercompagnie aux plans comptables de votre compagnie](#map-the-intercompany-chart-of-accounts-to-your-companys-chart-of-accounts).

### Importer ou exporter un plan comptable intersociété

La compagnie de synchronisation peut partager son plan comptable avec des partenaires en l’exportant dans un fichier. Les partenaires peuvent importer le fichier pour obtenir le plan comptable.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Choisissez l’action **Plan comptable IC**.
3. Sur la page **Plan comptable intersociétés**, choisissez l’action **Importer/Exporter**, puis choisissez **Importer** ou **Exporter**.
4. Choisissez le fichier à importer ou à exporter.  

La page **Plan comptable intercompagnie** est remplie avec les lignes nouvelles ou modifiées du compte du grand livre en fonction du plan comptable intercompagnie dans le fichier. Les lignes existantes non connexes présentes sur la page ne changent pas.

## Mapper le plan comptable intercompagnie au plan comptable de votre compagnie  

Lorsque vous avez défini ou importé le plan comptable intersociétés, mappez chaque compte intersociétés avec l’un de vos comptes. Sur la page **Plan comptable intercompagnie**, indiquez comment les comptes du grand livre intercompagnies des transactions entrantes doivent être convertis en comptes du grand livre du plan comptable de votre compagnie.

Si les comptes intersociétés et vos comptes ont les mêmes numéros, vous pouvez mapper les comptes automatiquement.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.  
2. Choisissez l’action **Plan comptable IC**.

    > [!TIP]
    > Pour accéder aux actions de la page, vous devrez peut-être développer la page en vue de mise en page large.

3. Sur la page **Plan comptable intersociétés**, choisissez l’action **Mappage des plans de compte**.
4. Vous pouvez mapper les comptes manuellement ou automatiquement.

    * Pour créer manuellement le mappage, sur les volets **Plan comptable intercompagnie** et **Plan comptable général**, choisissez un compte, puis choisissez un compte dans les champs **N° compte GL** et **N° IC** .
    * Pour mapper automatiquement les comptes qui ont les mêmes numéros, sélectionnez les lignes que vous souhaitez mapper, choisissez l’action **Faire correspondre au compte ayant le même numéro**, puis choisissez le plan comptable à mettre à jour.

    > [!TIP]
    > Si vous souhaitez mapper plusieurs ou peut-être tous les comptes, choisissez une ligne, choisissez :::image type="icon" source="media/show-more-options-icon.png" border="false":::, puis choisissez **Sélectionnez plus**.

## Configurer des dimensions intercompagnies

Si les partenaires intercompagnies échangent des transactions auxquelles des dimensions sont liées, vous devez décider ensemble des dimensions que vous allez tous utiliser. Par exemple, la compagnie de synchronisation peut créer une version simplifiée de leurs dimensions, les exporter dans un fichier XML qui est distribué à chaque partenaire. Chaque partenaire peut importer le fichier XML sur la page **Dimensions intercompagnies** , puis associez les dimensions intercompagnies à leurs dimensions. En savoir plus [Mapper les dimensions intercompagnies aux dimensions de votre compagnie](#map-intercompany-dimensions-to-your-companys-dimensions).

> [!NOTE]
> Chaque compagnie doit mettre en correspondance ses dimensions avec les dimensions intercompagnies pour les documents sortants et les documents entrants. Le mappage des comptes dans les deux sens est important et permet de maintenir la cohérence entre les compagnies.

Si les partenaires utilisent les dimensions intercompagnies du partenaire de synchronisation, suivez les étapes de cette section. Si vous souhaitez partager en utilisant un fichier XML contenant les dimensions interscompagnies, suivez les étapes décrites dans [Importer ou exporter les dimensions intercompagnies](#import-or-export-intercompany-dimensions).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.  
2. Choisissez l’action **Dimensions IC**.
3. Pour ajouter des dimensions, procédez comme suit sur la page **Dimensions intercompagnies** :
    * Choisissez **Nouveau**, puis saisissez chaque dimension sur une ligne.  
    * Si vos dimensions intercompagnies sont identiques ou semblables à celles que vous utilisez habituellement, vous pouvez renseigner la page automatiquement en choisissant l’action **Copier à partir des dimensions**. Vous pouvez modifier au besoin les nouvelles lignes.
    * Si vous avez configuré des dimensions intercompagnies spécifiées pour un partenaire de synchronisation, utilisez l’action **Configuration de la synchronisation** pour copier ces dimensions.

    > [!TIP]
    > Si vous copiez les dimensions intercompagnies d’un partenaire de synchronisation, vous pouvez utiliser l’action **Configuration de la synchronisation** pour mettre à jour vos dimensions intercompagnies avec toute modification apportée par le partenaire aux leurs.  

### Importer ou exporter les dimensions intercompagnies  

La compagnie de synchronisation peut partager ses dimensions avec des partenaires en les exportant dans un fichier. Les partenaires peuvent importer le fichier pour obtenir les dimensions.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Choisissez l’action **Dimensions IC**.  
3. Sur la page **Dimensions intercompagnies**, choisissez l’action **Importer/Exporter**, puis choisissez **Importer** ou **Exporter**.
4. Choisissez le fichier à importer ou à exporter.

La prochaine étape consiste à mapper les dimensions aux dimensions intercompagnies. En savoir plus [Mapper les dimensions intercompagnies aux dimensions de votre compagnie](#map-intercompany-dimensions-to-your-companys-dimensions).

### Mapper les dimensions intercompagnies aux dimensions de votre compagnie

Après avoir spécifié les dimensions intercompagnies à utiliser, mappez chaque dimension intercompagnie avec l’une des dimensions de votre compagnie, et vice versa. Utilisez la page **Mappage des dimensions intercompagnies** pour spécifier le mappage. Ensuite, répétez le processus pour les valeurs de dimension.

* Spécifiez comment les dimensions intercompagnies des transactions entrantes correspondent aux dimensions de la liste des dimensions de votre compagnie.
* Spécifiez comment vos dimensions doivent être converties en dimensions intercompagnies dans les *transactions sortantes*.

Si certaines dimensions intercompagnies possèdent le même code que les dimensions correspondantes de votre compagnie, vous pouvez mapper automatiquement les dimensions.  

Dans les étapes suivantes, vous devez d’abord mapper les dimensions intercompagnies aux dimensions des documents entrants sur le volet **Dimensions intercompagnies**. Ensuite, vous mappez les dimensions aux dimensions intercompagnies pour les documents sortants sur le volet **Dimensions de la compagnie actuelle**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Choisissez l’action **Dimensions IC**.
3. Sur la page **Plan comptable intercompagnie**, choisissez l’action **Mappage des dimensions**.
4. Vous pouvez mapper les dimensions manuellement ou automatiquement.

    * Pour créer manuellement le mappage, dans les volets **Dimensions intercompagnies** et **Dimensions de la compagnie actuelle**, choisissez une dimension, puis choisissez une dimension dans les champs **Code dimension** et **Code dimension IC**.
    * Pour mapper automatiquement les dimensions qui ont le même code, sélectionnez les lignes que vous souhaitez mapper, choisissez l’action **Mapper les dimensions avec le même code**, puis choisissez les dimensions à mettre à jour. 

    > [!TIP]
    > Si vous souhaitez mapper plusieurs ou peut-être toutes les dimensions, choisissez une ligne, choisissez :::image type="icon" source="media/show-more-options-icon.png" border="false":::, puis choisissez **Sélectionnez plus**.

5. Choisissez l’action **Mappage des valeurs de dimension**.
6. Sur la page **Mappage des valeurs de dimension intercompagnies** , les étapes de création du mappage sont similaires à ce que vous venez de faire pour les dimensions.

## Configurer les modèles et lots de journal intercompagnies

Vous devez configurer un modèle de journal général et un lot de journaux généraux à utiliser par défaut pour les transactions intercompagnies. Le modèle et le lot sont particulièrement importants si vous acceptez automatiquement les transactions intersociétés de vos partenaires. Pour en savoir plus sur l’acceptation automatique des transactions, accédez à [Accepter automatiquement les transactions des partenaires intercompagnies](#auto-accept-transactions-from-intercompany-partners).   

* Les journaux généraux permettent de reporter dans les comptes GL et d’autres comptes tels que les comptes bancaires, clients, fournisseurs et d’immobilisations. Le report avec un journal général crée toujours des écritures dans les comptes du grand livre.  Utilisez la page **Journal général intercompagnie** pour configurer le lot de journaux comptabilité à utiliser. Les paramètres spécifiques aux transactions intersociétés sont les comptes que vous spécifiez dans les champs **Type de compte IC** et **N° de compte IC**.
* Les modèles journal vous permettent de travailler dans une fenêtre journal conçue dans un but spécifique. En effet, les champs contenus dans chaque modèle journal sont exactement ceux qui sont nécessaires pour une partie de l’application. Utilisez la page **Modèles journal général** pour configurer un modèle à utiliser pour les transactions intercompagnies.

Pour en savoir plus sur les modèles et les lots de journaux comptabilité, accédez à [Utiliser des modèles et des lots de journal](ui-work-general-journals.md#use-journal-templates-and-batches).

## Configurer une compagnie pour les transactions intercompagnies

Les étapes suivantes supposent qu’un partenaire de synchronisation est configuré avec le plan de comptes et les dimensions sur lesquels vous allez baser le plan de comptes et les dimensions intercompagnies. Vous pouvez les configurer vous-même, mais il est généralement plus rapide de démarrer et l’entretien est plus facile si vous utilisez un partenaire de synchronisation. Pour en savoir plus sur le partenaire de synchronisation, accédez à [Configurer un partenaire de synchronisation](#set-up-a-synchronization-partner).

> [!TIP]
> Il est conseillé de remplir les champs du raccourci **Général** de la page **Configuration intersociétés** pour chaque partenaire avant vous ajoutez leurs partenaires. Lorsque vous ajoutez des compagnies partenaires qui se trouvent dans le même client, [!INCLUDE [prod_short](includes/prod_short.md)] obtient leur code IC et le nom de la compagnie à partir de leur configuration sur le raccourci général. Le champ **Nom de l’entreprise** vérifie que leur code IC est unique.

> [!NOTE]
> Si vous prévoyez d’utiliser un partenaire de synchronisation, laissez le champ **Partenaire de synchronisation** vide lorsque vous configurez cette compagnie pour le partenariat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration intersociété**, complétez les champs sur le raccourci **Général**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> Dans [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, vous ne pouvez pas utiliser les emplacements de fichiers pour transférer des transactions à vos partenaires, car [!INCLUDE[prod_short](includes/prod_short.md)] n’a pas accès à votre réseau local. Par conséquent, si vous choisissez **Emplacement du fichier** dans le champ **Type de transfert**, le champ **Chemin du dossier** n’est pas disponible. Au lieu de cela, le fichier sera téléchargé dans le dossier **Téléchargements** de votre ordinateur. Vous envoyez ensuite le fichier à une personne de la compagnie partenaire, par exemple par courriel. Pour un processus plus direct, nous vous recommandons de choisir **Courriel**.

L’étape suivante consiste à configurer les compagnies partenaires.

## Paramétrer les partenaires intercompagnies

Chaque partenaire doit ajouter toutes les autres compagnies du partenariat en tant que partenaire.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Dans le raccourci **Partenaires intercompagnies**, choisissez **Ajouter**.
3. Sur la page **Partenaire intercompagnie**, renseignez les champs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour toutes les compagnies du partenariat.

> [!NOTE]
> Pour le report intercompagnie, lorsque vous avez activé le bouton à bascule **Accepter automatiquement les transactions** sur la page **Fiche partenaire intercompagnie**[!INCLUDE[prod_short](includes/prod_short.md)] supprime les messages d’avertissement concernant les factures d’achat dupliquant le bon de commande d’origine. Il est important d’avoir un processus métier pour gérer les doublons. Par exemple, en supprimant ces bons de commande lorsque la facture d’achat est reçue du partenaire intercompagnie.

### Configurer les paramètres intercompagnies en tant que clients et fournisseurs

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration intercompagnie**, puis sélectionnez le lien associé.
2. Dans le raccourci **Partenaires intercompagnies**, ouvrez la page de carte du partenaire.
3. En fonction de ce que vous voulez faire, choisissez le client ou le partenaire dans les champs **N° client** ou **N° de fournisseur**.

    > [!NOTE]
    > Si le client ou le fournisseur n’a pas été créé, vous pouvez choisir **+Nouveau** dans le menu déroulant pour les configurer. Pour en savoir plus sur la création de clients et de fournisseurs, accédez à [Enregistrer de nouveaux clients](sales-how-register-new-customers.md) et [Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md).

    > [!TIP]
    > Vous pouvez également préciser un client ou un fournisseur en tant que partenaire intercompagnie en complétant le champ **Code partenaire IC** sur les pages **Fiche client** et **Fiche fournisseur**.

### Configurer des compte GL par défaut des partenaires intercompagnies  

Lorsque vous créez une ligne vente ou achat intercompagnie à envoyer comme transaction sortante, vous indiquez un compte du plan comptable intercompagnie en tant que compte par défaut associé au compte de la compagnie de votre partenaire dans lequel le montant est reporté. Sur la page **Fiche compte du grand livre**, pour les comptes que vous utilisez régulièrement dans des lignes vente ou achat intercompagnies sortantes, vous pouvez spécifier un compte du grand livre par défaut de partenaire intercompagnie. Par exemple, pour les comptes client, vous pouvez entrer les comptes fournisseur correspondants du plan comptable intersociété. Les comptes clients et fournisseurs sont utilisés comme compte de contrepartie pour le partenaire intercompagnie lorsque vous reportez des transactions dans les journaux généraux intercompagnies.  

Ensuite, si vous indiquez un compte GL dans le champ **N° compte de solde** d'une ligne intercompagnie avec **Partenaire intercompagnie** dans le champ **Type de compte**, le champ **Compte du grand livre Partenaire IC** est renseigné automatiquement.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Plan comptable**, puis sélectionnez le lien associé.  
2. Ouvrez la ligne d’un compte du grand livre utilisé pour les transactions intercompagnies, dans le champ **Compte du grand livre par défaut de partenaire IC**, entrez le compte du grand livre intercompagnie que votre partenaire utilisera lors du report du compte du grand livre de la ligne.
3. Répétez l'étape 2 pour chaque compte que vous entrez souvent dans le champ **N° compte de solde** sur une ligne dans un document ou journal intercompagnie.

### Accepter automatiquement les transactions des partenaires intercompagnies

Pour accélérer le traitement des transactions intercompagnies, vous pouvez spécifier si cette société crée automatiquement des lignes de journal basées sur les publications d’un partenaire intercompagnie à partir de la page **Journal général IC**. Pour créer automatiquement des transactions entrantes et sortantes, vous devez activer les boutons à bascule suivantes pour chaque partenaire :

* Pour le partenaire de synchronisation, sur la page **Configuration intersociétés**, activez le bouton à bascule **Envoyer auto. des transactions**. Spécifiez ensuite où créer les transactions de journal intercompagnie reçues en remplissant les champs **Modèle journal gén. IC par défaut** et **Nom journal gén. IC par défaut**.

    > [!TIP]
    > Si le champ **Modèle journal gén. IC par défaut** est vide, vous devez configurer un modèle journal général à utiliser pour vos journaux généraux intercompagnies. Pour en savoir plus sur les modèles et les lots de journaux comptabilité, accédez à [Configurer des modèles et des lots de journal général intercompagnies](#set-up-intercompany-general-journal-templates-and-batches)    

* Sur la page **Partenaire intercompagnie**, activez le bouton à bascule **Accepter auto. les transactions**.

Les lignes journal sont créées pour vous, mais ne sont pas reportées.

> [!NOTE]
> Si votre organisation a utilisé des fonctionnalités intercompagnies dans [!INCLUDE [prod_short](includes/prod_short.md)] avant la 1re vague de lancement 2022, pour accepter automatiquement les transactions, votre administrateur doit activer la fonctionnalité **Accepter automatiquement les transactions du journal général intercompagnie** sur la page **Gestion des fonctionnalités**.

### Spécifier les comptes bancaires à utiliser pour les partenaires intercompagnies

Pour faciliter les paiements rapides, spécifiez un ou plusieurs comptes bancaires à utiliser pour les partenaires intercompagnies. Lorsqu’un partenaire utilise un journal général intercompagnie pour effectuer un paiement, il peut spécifier le compte bancaire sur la ligne. Le compte bancaire est utilisé comme compte d’équilibre dans la compagnie réceptrice, ce qui minimise la nécessité de saisir manuellement les transactions.

* Pour spécifier le compte bancaire à utiliser, sur la page **Partenaires intercompagnies**, choisissez l’action **Comptes bancaires**. Sur la **Fiche de compte bancaire intersociétés**, entrez les informations du compte.

## Dépanner votre configuration intersociété

Sur la page **Configuration intercompagnie**, le volet **Diagnostics de configuration intercompagnie** contient des vignettes qui indiquent si vous avez configuré toutes les composantes nécessaires pour échanger des transactions intercompagnies. Les vignettes sont également disponibles sur le tableau de bord Business Manager. Choisissez les vignettes pour découvrir ce qui manque. Pour un aperçu des composantes requises, rendez-vous sur [Présentation des étapes pour commencer](#overview-of-the-steps-to-get-started).

## Voir aussi

[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]