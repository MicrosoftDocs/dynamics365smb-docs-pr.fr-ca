---
title: Configurer et utiliser un flux d’approbation achat
description: "Cette procédure pas à pas vous présente l’ensemble des phases impliquées dans la configuration et l’utilisation d’un flux de travail d’approbation d’achat dans Business\_Central."
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 03/11/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Procédure pas à pas : configuration et utilisation d’un flux de travail approbation achat

Vous pouvez automatiser le processus d'approbation d'enregistrements nouveaux ou modifiés, par exemple de documents, de lignes journal et de fiches client, en créant des flux de travail avec des étapes pour les approbations en question.

Avant de créer des flux d'approbation, vous devez configurer un approbateur et un approbateur remplaçant pour chaque utilisateur approbation. Vous pouvez également définir les montants maximaux que les approbateurs sont qualifiés à approuver pour les enregistrements de vente et d’achat. Les demandes d’approbation et autres notifications peuvent être envoyées par courriel ou note interne. Pour chaque configuration d'utilisateur d'approbation, vous pouvez également définir à quel moment ils reçoivent les notifications.

> [!NOTE]
> Outre la fonctionnalité de flux de travail dans [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez utiliser Power Automate pour définir des flux de travail des événements dans [!INCLUDE[prod_short](includes/prod_short.md)]. Remarquez que bien qu’ils soient deux systèmes de flux de travail distincts, tous les modèles Flow que vous créez dans Power Automate est ajouté à la liste des modèles de flux de travail dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d’informations, voir [Utiliser Business Central dans un flux automatisé](across-how-use-financials-data-source-flow.md).  

Vous pouvez configurer et utiliser des workflows qui connectent des tâches de processus entreprise exécutées par différents utilisateurs. Les tâches système, telles que le report automatique, peuvent être incluses comme étapes du flux de travail, précédées ou suivies des tâches de l'utilisateur. Demander et accorder une approbation pour créer des enregistrements sont des étapes classiques du workflow. En savoir plus sur [Flux de travail](across-workflow.md).  

## À propos de cette procédure pas à pas

Cette procédure est un scénario illustrant les tâches suivantes :  

- Configuration des utilisateurs approbation  
- Configuration des notification pour les utilisateurs approbation  
- Modification et activation d’un flux d’approbation  
- Demande d’approbation d’un bon de commande (Alicia)  
- Réception d’une notification, puis acceptation de la demande (Sean)  

## Scénario

Sean est un super utilisateur de CRONUS  et crée deux utilisateurs d’approbation. Le premier est Alicia, qui représente un agent d'achats. L’autre, c’est Sean lui-même, soit l’approbateur d’Alicia. Ensuite, Sean s’octroie des droits d’approbation pour un montant d’achat illimité et spécifie qu’ils recevront les notifications par note interne dès qu’un événement approprié se produira. Enfin, Sean crée le flux d’approbation requis en tant que copie du modèle *Flux de travail approbation bon de commande* existant, laisse toutes les conditions d’événement et options de réponse existantes inchangées, puis active le workflow.  

Pour tester le flux de travail approbation, Sean se connecte d’abord à [!INCLUDE[prod_short](includes/prod_short.md)] sous l’identité d’Alicia, puis demande l’approbation d’un bon de commande. Ensuite, Sean se connecte en tant que lui-même, voit la note dans son Tableau de bord, suit le lien vers la demande d’approbation du bon de commande, et approuve la demande.  

## Utilisateurs

Pour pouvoir configurer des utilisateurs d’approbation et leur méthode de notification, vous devez vous assurer que deux utilisateurs existent dans [!INCLUDE[prod_short](includes/prod_short.md)] : Un utilisateur représente Alicia. L'autre utilisateur, vous-même, représente Sean. En savoir plus sur [Créer des utilisateurs en fonction des licences](ui-how-users-permissions.md).

### Configuration des utilisateurs des approbations

Une fois connecté comme vous-même, définissez Alicia en tant qu’utilisateur d’approbation dont l’approbateur est vous-même. Configurez vos droits d’approbation et spécifiez comment et quand être averti des demandes d’approbation.  

#### Pour configurer votre propre profil et celui d'Alicia en tant qu'utilisateurs approbation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration utilisateur approbation**, puis choisissez le lien associé.  
2. Sur la page **Configuration d'utilisateur d'approbation**, sélectionnez l'action **Nouveau**.  

    > [!NOTE]  
    >  Vous devez configurer un approbateur avant de pouvoir configurer des utilisateurs qui ont besoin de l'approbation de l'approbateur. Par conséquent, vous devez configurer votre propre profil avant de configurer celui d’Alicia.  

3. Configurez les deux utilisateurs approbation en renseignant les champs comme indiqué dans le tableau suivant.  

    |Code utilisateur|Code approbateur|Montant illimité d'achat autorisé|  
    |-------|-----------|---------------------------|  
    |VOUS||Sélection|
    |ALICIA|VOUS||

### Configurer les notifications

Dans cette procédure, l’utilisateur est averti par une note interne concernant les demandes d’approbation. Les notifications d’approbation peuvent également être envoyées par courriel et vous pouvez ajouter une étape de réponse de flux de travail qui avertit l’expéditeur lorsqu’une demande est approuvée ou rejetée. En savoir plus sur [Spécifier quand et comment recevoir les notifications de flux de travail](across-how-to-specify-when-and-how-to-receive-notifications.md).

#### Pour spécifier comment et quand recevoir les notifications

1. Sur la page **Configuration d'utilisateur d'approbation**, sélectionnez la ligne pour vous-même, puis sélectionnez l'action **Configuration de notification**.  
2. Sur la page **Configuration de la notification**, dans le champ **Type de notification**, entrez **Approbation**.  
3. Dans le champ **Mode de notification**, choisissez **Note**.  
4. Sur la page **Configuration de la notification**, cliquez sur l'action **Calendrier de notification**.  
5. Sur la page **Calendrier de notification**, dans le champ **Répétition**, sélectionnez **Immédiatement**.  

## Créer un flux de travail approbation

Créez le flux de travail approbation bon de commande en copiant les étapes du modèle de **Flux de travail approbation bon de commande**. Laissez les étapes existantes du flux inchangées, puis activez le flux.  

> [!TIP]
> Éventuellement, ajoutez une étape de réponse de flux de travail pour informer l’expéditeur lorsque la demande a été approuvée ou rejetée. En savoir plus sur [Spécifier quand et comment recevoir les notifications de flux de travail](across-how-to-specify-when-and-how-to-receive-notifications.md).

### Pour créer et activer un flux de travail d'approbation des bons de commande

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Flux de travail**, puis choisissez le lien associé.  
2. Sur la page **Flux de travail**, sélectionnez **Actions**, puis sélectionnez **Nouveau**, puis choisissez l’action **Créer flux de travail à partir du modèle**.  
3. Sur la page **Modèles de flux de travail**, sélectionnez le modèle de flux de travail nommé **Flux de travail approbation bon de commande**.  

   La page **Flux de travail** s'ouvre pour un nouveau flux de travail contenant toutes les informations du modèle sélectionné. La valeur du champ **Code** est étendue avec *-01* pour indiquer que ce premier flux de travail est créé à partir du modèle **Flux de travail approbation bon de commande**.  
4. Dans l’en-tête de la page **Flux de travail**, activez le bouton bascule **Activé**.  

## Utiliser le flux de travail approbation

Utilisez le nouveau Flux de travail approbation bon de commande en vous connectant à [!INCLUDE[prod_short](includes/prod_short.md)] en tant qu’Alicia pour demander l’approbation d’un bon de commande. Ensuite, connectez-vous en tant que vous-même, affichez la note dans le Tableau de bord, suivez le lien vers la demande d’approbation, puis approuvez la demande.  

### Pour demander l'approbation d'un bon de commande en tant qu'Alicia

1. Connectez-vous en tant qu'Alicia.
2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de commande**, puis choisissez le lien associé.  
3. Sélectionnez la ligne pour ouvrir le *Bon de commande 106001*.  
4. Sur la page **Bon de commande**, choisissez **Actions**, puis **Demander l’approbation**, puis choisissez l’action **Envoyer demande d’approbation**.  

Notez que la valeur du champ **État** est passée à **Approbation en attente**.  

### Pour approuver le bon de commande en tant que Sean

1. Connectez-vous en tant que Sean.
2. Dans le Tableau de bord, dans la zone **Libre-service**, choisissez **Demandes à approuver**.
3. Sur la page **Demandes à approuver**, sélectionnez la ligne à propos du bon de commande d’Alicia, puis choisissez l’action **Approuver**.  

La valeur du champ **État** du bon de commande d’Alicia passe à **Libéré**.  

Vous venez de configurer et tester un flux de travail d’approbation simple incluant les deux premières étapes du **Flux de travail approbation bon de commande**. Vous pouvez facilement étendre ce flux pour reporter automatiquement le bon de commande d’Alicia lorsque c’est Sean qui l’approuve. Pour ce faire, vous devez activer le **Flux de travail facture achat**, pour que la réponse à une facture d’achat libérée soit de la reporter. Vous devez d'abord modifier la condition d'événement de la première étape du flux (achat) en remplaçant **Facturer** par **Commander**.  

La version générique de [!INCLUDE[prod_short](includes/prod_short.md)] inclut plusieurs modèles de flux de travail pour les scénarios pris en charge par le code d’application. La plupart de ce modèles concernent des flux d’approbation.  

Définissez les variations des flux de travail en renseignant les champs des lignes de flux de travail à l'aide de listes fixes de valeurs d’événement et de réponse qui représentent les scénarios pris en charge par le code de l’application. En savoir plus sur [Créer des flux de projet](across-how-to-create-workflows.md).  

[!INCLUDE[workflow](includes/workflow.md)]

## Voir aussi .

[Configuration des utilisateurs des approbations](across-how-to-set-up-approval-users.md)  
[Configuration de notifications de workflow](across-setting-up-workflow-notifications.md)  
[Créer des flux de travail approbation](across-how-to-create-workflows.md)  
[Utilisation des flux d'approbation](across-how-use-approval-workflows.md)  
[Flux de travail](across-workflow.md)  
[Utiliser Business Central dans un flux automatisé](across-how-use-financials-data-source-flow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
