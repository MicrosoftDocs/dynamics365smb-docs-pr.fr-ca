---
title: Configuration et utilisation d'un flux d'approbation achat | Microsoft Docs
description: "Vous pouvez automatiser le processus d'approbation d'enregistrements nouveaux ou modifiés, par exemple de documents, de lignes journal et de fiches client, en créant des flux de travail avec des étapes pour les approbations en question. Avant de créer des flux d'approbation, vous devez configurer un approbateur et un approbateur remplaçant pour chaque utilisateur approbation. Vous pouvez également définir les montants maximaux que les approbateurs sont qualifiés à approuver pour les enregistrements de vente et d'achat. Les demandes d'approbation et autres notifications peuvent être envoyées par courriel ou note interne. Pour chaque configuration d'utilisateur d'approbation, vous pouvez également définir à quel moment ils reçoivent les notifications."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 825e901b4126dc1ba317527862eb459559ecb538
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="walkthrough-setting-up-and-using-a-purchase-approval-workflow"></a>Procédure pas à pas : Configuration et utilisation d'un flux d'approbation achat
Vous pouvez automatiser le processus d'approbation d'enregistrements nouveaux ou modifiés, par exemple de documents, de lignes journal et de fiches client, en créant des flux de travail avec des étapes pour les approbations en question. Avant de créer des flux d'approbation, vous devez configurer un approbateur et un approbateur remplaçant pour chaque utilisateur approbation. Vous pouvez également définir les montants maximaux que les approbateurs sont qualifiés à approuver pour les enregistrements de vente et d'achat. Les demandes d'approbation et autres notifications peuvent être envoyées par courriel ou note interne. Pour chaque configuration d'utilisateur d'approbation, vous pouvez également définir à quel moment ils reçoivent les notifications.  

 Vous pouvez configurer et utiliser des workflows qui connectent des tâches de processus entreprise exécutées par différents utilisateurs. Les tâches système, telles que le report automatique, peuvent être incluses comme étapes du flux de travail, précédées ou suivies des tâches de l'utilisateur. Demander et accorder une approbation pour créer des enregistrements sont des étapes classiques du workflow. Pour plus d'informations, voir [Flux de travail](across-workflow.md).  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
Cette procédure pas à pas présente les tâches suivantes :  

-   Configuration des utilisateurs d'approbation (y compris la configuration d'un utilisateur dans Windows et dans [!INCLUDE[d365fin](includes/d365fin_md.md)]).  
-   Configuration des notification pour les utilisateurs approbation.  
-   Modification et activation d'un flux d'approbation.  
-   Démarrage de la file d'attente des travaux qui distribue les notifications.  
-   Demande d'approbation d'un bon de commande (Alicia).  
-   Réception d'une notification, puis acceptation de la demande (Sean).  

## <a name="prerequisites"></a>Conditions préalables  
Pour effectuer cette procédure pas à pas, vous aurez besoin de la compagnie de démonstration CRONUS International Ltd.

## <a name="story"></a>Scénario  
Sean est super utilisateur chez CRONUS, sur son propre ordinateur.  

Il crée deux utilisateurs d’approbation. Le premier est Alicia, qui représente un agent d'achats. L'autre, c'est lui-même, soit l'approbateur d'Alicia. Ensuite, Sean s'octroie des droits d'approbation pour un montant d'achat illimité et spécifie qu'il recevra les notifications par note interne dès qu'un événement approprié se produira. Enfin, Sean crée le flux de travail approbation requis en tant que copie du modèle Flux de travail approbation bon de commande existant, laisse toutes les conditions d'événement et options de réponse existantes inchangées, puis active le flux de travail.  

Pour tester le flux de travail approbation, Sean se connecte d'abord à [!INCLUDE[d365fin](includes/d365fin_md.md)] sous l'identité d'Alicia, puis demande l'approbation d'un bon de commande. Ensuite, Sean se connecte avec sa propre identité, voit la note dans son Tableau de bord, suit le lien vers la demande d'approbation du bon de commande, et approuve la demande.  

## <a name="setting-up-the-sample-data"></a>Configuration des exemples de données  
Vous devez créer un nouvel utilisateur sur l'ordinateur local et dans [!INCLUDE[d365fin](includes/d365fin_md.md)] représentant Alicia, que vous sélectionnerez ultérieurement en tant qu'utilisateur d'approbation. Votre propre compte d'utilisateur représentera Sean.  

### <a name="to-add-alicia-as-a-user-on-the-local-computer"></a>Pour ajouter Alicia en tant qu'utilisateur sur l'ordinateur local  

1.  Choisissez **Démarrer**, dans la zone **Rechercher les programmes et fichiers**, saisissez **Modifier les utilisateurs et les groupes locaux**, puis sélectionnez le lien associé.  
2.  Ouvrez le dossier **Utilisateurs**.  
3.  Sous l'onglet **Actions**, choisissez **Nouvel utilisateur**.  
4.  Dans le champ **Nom utilisateur**, entrez Alicia.  
5.  Dans les champs **Mot de passe** et **Confirmer mot de passe**, entrez un mots de passe valide.  
6.  Désactivez la case à cocher **L'utilisateur doit changer le mot de passe à la prochaine ouverture de session**.  
7.  Fermez la fenêtre **Utilisateurs et groupes locaux**.  

### <a name="to-add-alicia-as-a-user-in-included365finincludesd365finmdmd"></a>Pour ajouter Alicia en tant qu'utilisateur dans [!INCLUDE[d365fin](includes/d365fin_md.md)]  
1.  Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Utilisateurs**, puis sélectionnez le lien connexe.  
2.  Dans la fenêtre **Utilisateurs Windows**, sous l'onglet **Accueil**, dans le groupe **Nouveau**, choisissez **Nouveau**.  
3.  Dans la fenêtre **Fiche utilisateur**, dans le champ **Nom utilisateur**, saisissez Alicia.  
4.  Dans le champ **Nom d'utilisateur Windows**, cliquez sur le bouton AssistEdit.  
5.  Dans la fenêtre **Sélectionner un utilisateur ou un groupe**, dans le champ **Entrer les noms d'objet à sélectionner**, entrez Alicia, puis sélectionnez le bouton **Vérifier les noms**.  
6.  Lorsque [ORDINATEUR]ALICIA s'affiche dans le champ, cliquez sur le bouton **OK**.  
7.  Dans le raccourci **Ensembles d'autorisations utilisateur**, dans le champ **Ensemble d'autorisations**, sélectionnez **SUPER**.  
8.  Dans le champ **Compagnie**, sélectionnez **CRONUS International Ltd.**  
9. Cliquez sur le bouton **OK**.  

## <a name="setting-up-approval-users"></a>Configuration des utilisateurs approbation  
À l'aide de l'utilisateur Windows que vous venez de créer, configurez Alicia en tant qu'utilisateur approbation dont vous êtes l'approbateur. Configurez vos droits d'approbation et spécifiez comment et quand être averti des demandes d'approbation.  

### <a name="to-set-up-yourself-and-alicia-as-approval-users"></a>Pour configurer votre propre profil et celui d'Alicia en tant qu'utilisateurs approbation  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration d'utilisateur d'approbation**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Configuration d'utilisateur d'approbation**, sous l'onglet **Accueil**, dans le groupe **Nouveau**, choisissez **Nouveau**.  

    > [!NOTE]  
    >  Vous devez configurer un approbateur avant de pouvoir configurer des utilisateurs qui ont besoin de l'approbation de l'approbateur. Par conséquent, vous devez configurer votre propre profil avant de configurer celui d'Alicia.  

3.  Configurez les deux utilisateurs approbation en renseignant les champs comme indiqué dans le tableau suivant.  

    |Code utilisateur|Code approbateur|Montant illimité d'achat autorisé|  
    |-------------|-----------------|---------------------------------|  
    |[ORDINATEUR][VOUS]||Sélectionné|  
    |[ORDINATEUR]ALICIA|[ORDINATEUR][VOUS]||  

## <a name="setting-up-notifications"></a>Configuration de notifications  
Spécifiez comment et quand être averti des demandes d'approbation.  

### <a name="to-set-up-how-and-when-you-are-notified"></a>Pour spécifier comment et quand recevoir les notifications  
1.  Dans la fenêtre **Configuration d'utilisateur d'approbation**, sélectionnez la ligne correspondant à vous-même, puis sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Configuration de la notification**.  
2.  Dans la fenêtre **Configuration de la notification**, dans le champ **Type de notification**, entrez **Approbation**.  
3.  Cliquez sur le champ **Code modèle de notification**, puis sélectionnez le bouton **Avancé**.  
4.  Dans la fenêtre **Modèles de notification**, sous l'onglet **Accueil**, dans le groupe **Gérer**, choisissez **Modifier la liste**.  
5.  Sur la ligne du modèle d'approbation, dans le champ **Mode de notification**, entrez **Note**.  
6.  Cliquez sur le bouton **OK**.  
7.  Dans la fenêtre **Configuration de la notification**, sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Calendrier de notification**.  
8.  Dans la fenêtre **Calendrier de notification**, dans le champ **Occurrence**, sélectionnez **Immédiatement**.  
9. Cliquez sur le bouton **OK**.  

## <a name="creating-the-approval-workflow"></a>Création d'un flux d'approbation  
 Créez le flux d'approbation du bon de commande en copiant les étapes du modèle Flux de travail approbation bon de commande. Laissez les étapes existantes du flux inchangées, puis activez le flux.  

### <a name="to-create-and-enable-a-purchase-order-approval-workflow"></a>Pour créer et activer un flux de travail d'approbation des bons de commande  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Flux de travail**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Flux de travail**, sous l'onglet **Actions**, dans le groupe **Général**, choisissez **Créer le flux de travail à partir du modèle**.  
3.  Sous l'onglet **Actions**, dans le groupe **Général**, choisissez **Créer le flux de travail à partir du modèle**. La fenêtre **Modèles flux de travail** s'ouvre.  
4.  Sélectionnez le modèle de flux de travail nommé Flux de travail approbation bon de commande, puis choisissez le bouton **OK**.  

    La fenêtre **Flux de travail** s'ouvre pour un nouveau flux de travail contenant toutes les informations du modèle sélectionné. La valeur du champ **Code** est étendue avec « -01 » pour indiquer que ce premier flux de travail est créé à partir du modèle Flux de travail approbation bon de commande.  
5.  Dans l'en-tête de la fenêtre **Flux de travail**, activez la case à cocher **Activé**.  

## <a name="starting-a-notification-job-queue"></a>Démarrage d'une file d'attente des travaux pour les notifications  
Assurez-vous qu'une file d'attente des travaux dans votre installation est configurée pour traiter les notifications du flux de travail.  

### <a name="to-start-the-notify-job-queue"></a>Pour lancer la file d'attente des travaux NOTIFY  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Files d'attente des travaux**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Files d'attente des travaux**, sélectionnez la ligne correspondant à la file d'attente des travaux NOTIFY, puis sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Démarrer la file d'attente des travaux**.  

## <a name="using-the-approval-workflow"></a>Utilisation du flux d'approbation  
Utilisez le nouveau Flux de travail approbation bon de commande en ouvrant une session dans [!INCLUDE[d365fin](includes/d365fin_md.md)] en tant qu'Alicia pour demander l'approbation d'un bon de commande. Ensuite, connectez-vous en tant que vous-même, affichez la note dans le Tableau de bord, suivez le lien vers la demande d'approbation, puis approuvez la demande.  

Pour vous connecter à [!INCLUDE[d365fin](includes/d365fin_md.md)] en tant qu'utilisateur différent, utilisez la fonction **Exécuter en tant qu'utilisateur différent**.  

### <a name="to-log-into-included365finincludesd365finmdmd-as-alicia"></a>Pour vous connecter à [!INCLUDE[d365fin](includes/d365fin_md.md)] en tant qu'Alicia  

1.  Pour le client Web [!INCLUDE[d365fin](includes/d365fin_md.md)], sur le bouton de lancement du navigateur Web, appuyez sur Maj + clic droit, puis choisissez **Exécuter en tant qu'utilisateur différent**.  

    Pour le client Windows [!INCLUDE[d365fin](includes/d365fin_md.md)], sur le bouton de lancement du programme, appuyez sur Maj + clic droit, puis choisissez **Exécuter en tant qu'utilisateur différent**.  

2.  Dans la fenêtre **Sécurité Windows**, entrez [ORDINATEUR]ALICIA et le mot de passe requis.  

### <a name="to-request-approval-of-a-purchase-order-as-alicia"></a>Pour demander l'approbation d'un bon de commande en tant qu'Alicia  

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de commande**, puis sélectionnez le lien associé.  
2.  Sélectionnez la ligne pour ouvrir le bon de commande 104001, puis sous l'onglet **Accueil**, dans le groupe **Gestion**, choisissez **Modifier**.  
3.  Dans la fenêtre **Bon de commande**, sous l'onglet **Actions**, dans le groupe **Approbation**, choisissez **Envoyer demande d'approbation**.  

    Notez que la valeur du champ **État** est passée à **Approbation en attente**.  

4.  Fermez [!INCLUDE[d365fin](includes/d365fin_md.md)].  

### <a name="to-approve-the-purchase-order-as-sean"></a>Pour approuver le bon de commande en tant que Sean  

1.  Ouvrez [!INCLUDE[d365fin](includes/d365fin_md.md)] normalement. Le programme s'ouvre avec vous-même en tant qu'utilisateur.  
2.  Dans le Tableau de bord, dans la fenêtre **Mes notifications**, recherchez une nouvelle note d'Alicia.  

    > [!NOTE]  
    >  Bien que la récurrence de notification soit définie sur **Immédiatement**, la note arrivera environ une minute après l'envoi de la demande d'approbation par Alicia. Ceci est dû à la fréquence de récurrence par défaut de la fonctionnalité File d'attente des travaux.  

3.  Lorsque la note s'affiche dans la fenêtre **Mes notifications**, sélectionnez la valeur **Écriture approbation : XX, XX** dans le champ **Page**. La fenêtre **Demandes à approuver** s'ouvre avec la demande de bon de commande d'Alicia en surbrillance.  
4.  Dans le fenêtre **Demandes à approuver**, sous l'onglet **Accueil**, dans le groupe **Traitement**, choisissez **Approuver**.  

    La valeur du champ **État** du bon de commande d'Alicia passe à **Libéré**.  

Vous venez de configurer et tester un flux de travail d'approbation simple incluant les deux premières étapes du flux de travail approbation bon de commande. Vous pouvez facilement étendre ce flux pour reporter automatiquement le bon de commande d'Alicia lorsque c'est Sean qui l'approuve. Pour cela, vous devez activer le flux de travail facture achat, dans lequel la réponse à une facture d'achat libérée est de la reporter. Vous devez d'abord modifier la condition d'événement de la première étape du flux (achat) en remplaçant **Facturer** par **Commander**.  

La version [!INCLUDE[d365fin](includes/d365fin_md.md)] générique inclut un certain nombre de modèles de flux de travail pour les scénarios pris en charge par le code de l'application. La plupart concernent des flux d'approbation. Pour plus d'informations, voir Modèles flux de travail.  

Définissez les variations des flux de travail en renseignant les champs sur les lignes flux de travail à partir de listes fixes de valeurs d'événement et de réponse qui représentent les scénarios pris en charge par le code de l'application. Pour plus d'informations, voir [Créer des flux de travail](across-how-to-create-workflows.md).  

Si un scénario d'entreprise requiert un événement ou une réponse de workflow non pris en charge, un partenaire Microsoft doit l'implémenter en personnalisant le code de l'application. Pour plus d'informations, voir [Procédure pas à pas : implémentation de nouveaux événements et réponses de flux de travail](/dynamics-nav/Walkthrough--Implementing-New-Workflow-Events-and-Responses) dans l'Aide destinée aux développeurs et aux professionnels de l'informatique.  

## <a name="see-also"></a>Voir aussi  
[Configurer des utilisateurs d'approbation](across-how-to-set-up-approval-users.md)   
[Configuration de notifications de workflow](across-setting-up-workflow-notifications.md)   
[Créer des workflows](across-how-to-create-workflows.md)   
[Utilisation des flux d'approbation](across-how-use-approval-workflows.md)   
[Flux de travail](across-workflow.md)

