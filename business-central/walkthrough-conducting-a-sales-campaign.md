---
title: "Procédure pas à pas\_: Mise en place d’une promotion de vente"
description: "Cette procédure pas à pas donne un aperçu détaillé de toutes les tâches impliquées dans la conduite d’une promotion de vente dans Business\_Central."
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/24/2021
ms.author: bholtorf
---
# Procédure pas à pas : Mise en place d’une promotion de vente

Une promotion désigne tout type d'utilisation impliquant plusieurs contacts. La sélection du public cible de votre promotion représente une étape importante de la configuration. Pour ce faire, dans [!INCLUDE[prod_short](includes/prod_short.md)], créez un segment ou un groupe de contacts à l'aide de filtres.  

 Les fonctionnalités du module Ventes & marketing permet de planifier soigneusement vos activités de marketing et de gérer les interactions avec les contacts et clients. Vous pouvez créer des campagnes et configurer des segments de contacts pour le publipostage et d'autres types d'interactions avec vos contacts et prospects.  

 Les fonctionnalités Promotion et Segment et les processus automatisés associés vous permettent de planifier, d'organiser et de suivre vos activités de marketing. Ainsi, vos chances de gagner de nouveaux clients et de fidéliser les clients existants augmentent.  

## À propos de cette procédure pas à pas

 Cette procédure pas à pas répertorie les phases de suivi d'un salon commercial, ainsi que les phases de ciblage des clients potentiels (contacts) dans le cadre d'une promotion de suivi.  

 Elle présente la fonctionnalité de gestion des campagnes et segments pour le département Ventes & marketing. Cette procédure pas à pas présente les tâches suivantes :  

- préparation des données ;
- configuration d'une promotion ;  
- sélection du public cible ;  
- exploration de données ;  
- envoi de lettres aux contacts ;  
- enregistrement des réponses de promotion.  

## Rôles

 Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

- Directeur marketing ou directeur des ventes  
- Membre de l'équipe marketing  

## Conditions préalables

 Avant d'exécuter cette procédure pas à pas, veuillez installer [!INCLUDE[prod_short](includes/prod_short.md)].  

## Scénario

 Le directeur marketing du département Ventes de CRONUS est responsable de la planification et de l'exécution des campagnes. Le responsable marketing prend les décisions relatives à la participation ou non de la société à des salons commerciaux et évalue l’évolution des promotions.  

 Les membres de l'équipe marketing du département Marketing gèrent la production, la distribution, et le placement des supports marketing.  

 La compagnie vient de lancer un nouveau produit appelé Rome Guest Chair. Ce dernier a récemment été exposé au salon Office Futurus. De nombreux clients ont montré un grand intérêt pour le produit et, dans le cadre d’un effort promotionnel, les clients qui ont acheté Rome Guest Chair pendant la période de promotion se sont vus proposer un prix spécial promotion.  

 Après le salon commercial, l'une des tâches des membres de l'équipe marketing consiste à entrer toutes les informations de contact des clients potentiels.  

 Le directeur marketing configure une promotion, crée un segment contenant les nouveaux contacts, puis explore les données de contact pour sélectionner le public cible de la promotion.  

 Les membres de l'équipe marketing aident à l'envoi de lettres de remerciement à tous les contacts qui ont laissé leur carte de visite sur le stand. Le directeur marketing enregistre toutes les réponses reçues de la part des prospects.  

## Configuration d'une promotion

 Dès que les membres de l'équipe ont entré les cartes de visite reçues lors du salon commercial, le directeur marketing configure une fiche promotion visant à gérer les activités associées.  

### Pour configurer une promotion  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Promotions**, puis choisissez le lien associé.  
2. Choisissez l'action **Nouveau** pour créer une promotion. Dans la fiche promotion, sélectionnez <kbd>Entrée</kbd> pour qu’un numéro de promotion soit automatiquement inséré.  
3. Dans le champ **Description**, entrez la description de la promotion, par exemple, **Salon Office Futurus**.  
4. Choisissez le champ **Code état** et sélectionnez le code état « 1-PLAN ». 
5. Renseignez les champs **Date début** et **Date fin** de la campagne en fonction des besoins.  

## Sélection du public cible

 Le directeur marketing crée un segment pour sélectionner les contacts avec lesquels il souhaite interagir.  
 
 Lorsque vous créez un segment, vous pouvez utiliser divers critères pour sélectionner les contacts qui doivent être des cibles pour le segment. Par exemple, vous pouvez sélectionner des personnes travaillant sur le site ou des prospects responsables des achats pour leur compagnie. Utilisez des filtres pour ajouter des contacts en fonction des critères correspondant le mieux à vos besoins. Par exemple, vous pouvez choisir de filtrer la responsabilité du contact, les relations d'affaires ou le secteur d'utilisation de la compagnie. Pour cette procédure pas à pas, nous choisissons le filtre **Responsabilité** pour sélectionner les contacts.

### Pour créer un segment avec les contacts appropriés  

1. Choisissez l’action **Naviguer**, puis choisissez **Segments**.  
2. Choisissez l'action **Nouveau** pour créer un segment. Dans la fiche segment, sélectionnez **Entrée** pour qu’un numéro de segment soit automatiquement inséré.  
3. Sur le raccourci **Général**, dans le champ **Description**, entrez par exemple *Visiteurs du salon Office Futurus*.
4. Choisissez l’action **Ajouter contacts** pour ouvrir le filtre **Ajouter contacts**.  
5. Faites défiler vers le raccourci **Responsabilité contact**, sélectionnez le filtre **Achat** comme **Code responsabilité**, puis choisissez le bouton **OK**.  

La page **Segment** inclut désormais une liste de contacts basée sur le filtre entré. Sur le raccourci **Général**, dans le champ **Nbre de lignes**, vous pouvez visualiser en un clin d'œil le nombre de contacts répondant à ces critères.  

> [!NOTE]  
> Vous pouvez enregistrer vos critères de segmentation pour qu'ils soient réutilisés ultérieurement.

### Pour enregistrer vos critères de segmentation

1. Sur la page **Segment**, sélectionnez **Actions**.
2. Choisissez **Fonctions**, puis **Segment**, puis choisissez l’action **Enregistrer critères**.  
3. Sur la page **Critères segment enregistrés**, entrez un code pour le segment. Dans le champ **Description**, entrez la description des critères segment.
4. Cliquez sur le bouton **OK**.  

## Exploration de données

 Le directeur marketing observe attentivement la liste segmentée des contacts et réalise que la liste est bien trop longue. Il décide de la réduire en se basant sur de véritables prospects afin d’être certain de se concentrer sur le bon groupe cible. Ce processus de réduction et de redéfinition des données porte également le nom d'exploration de données.  

### Pour supprimer des contacts du segment  

1. Sur la page **Segment**, sélectionnez **Actions**.
2. Dans la barre de menus ci-dessous, choisissez **Fonctions**, **Contacts**, puis **Réduire les contacts**.  

  Vous ouvrez ainsi la boîte de dialogue **Supprimer contacts – Réduire**.  
4. Sur le raccourci **Relation d’affaires contact**, sélectionnez le filtre **CUST** comme **Code relation d’affaires**, puis choisissez le bouton **OK**.

 La page **Segment** inclut désormais une liste réduite de contacts. Dans le champ **Nbre de lignes**, vous pouvez visualiser le nombre de contacts répondant à ces critères.  

 > [!NOTE]  
 > Si vous devez annuler la suppression d'un groupe de contacts, utilisez la fonction **Annuler dernière action**. En d'autres termes, vous pouvez annuler la dernière segmentation.  

### Pour rétablir les contacts supprimés

1. Sur la page **Segment**, sélectionnez l’action **Segment**.
2. Sélectionnez l’action **Annuler dernière action**.

Les contacts que vous venez de supprimer sont rajoutés à la liste des contacts.

## Association d'un segment à une promotion

Le directeur marketing décide que la liste réduite fera office de liste finale et servira pour la promotion. Pour cela, il associe le segment à la promotion Salon FUTURUS.  

### Pour associer un segment à une promotion  

1. Sur la page **Segment**, dans le raccourci **Promotion**, sélectionnez le champ **N° promotion** pour sélectionner la campagne à laquelle vous souhaitez lier le segment, par exemple, **CP0001**.
2. Sélectionnez **Oui**.  
3. Puisque ce segment représente la cible de la promotion, cochez la case **Cible promotion** et choisissez **Oui**.  

## Envoi de lettres et de courriels à des contacts

 Les membres de l’équipe marketing aident le directeur marketing à envoyer une correspondance aux prospects, dans laquelle il les remercie de leur visite au salon.

### Pour utiliser un segment afin d’envoyer une lettre à un contact :  

> [!NOTE]  
> Dans cette procédure, vous devez joindre un document Word. Vous pouvez ajouter des pièces jointes dans n’importe quelle langue.

> [!NOTE]  
> Si besoin, cliquez sur l’icône de crayon **Modifier** pour ouvrir la page en mode édition.

1. Ouvrez la fiche **Segment** correspondant aux **Visiteurs du salon commercial FUTURUS**.  
2. Sur le raccourci **Interaction**, dans le champ **Code modèle interaction**, sélectionnez un modèle de lettre commerciale, code **BUS** et sélectionnez **Oui**.
3. Choisissez le champ **Code langue (par défaut)** pour ouvrir la page **Langues interaction segment**. Sélectionnez un **Code langue** et cliquez sur le bouton **OK**.
4. Assurez-vous que **Type correspondance (par défaut)** est défini sur **Impression**.
5. Dans le champ **Pièce jointe**, cochez la case **Ellipse**. Cela ouvre la boîte de dialogue Importer pièce jointe.
    1. Sélectionnez le bouton **Choisir** pour choisir votre fichier.
    1. Recherchez le fichier et sélectionnez le bouton **Ouvrir** pour le joindre.
6. Dans le champ **Sujet (par défaut)**, entrez le texte exemple suivant : **Merci de votre visite au salon**. Sélectionnez la touche <kbd>Tab</kbd> pour quitter le champ et sélectionnez le bouton **Oui**.
7. Faites glisser **Envoyer doc Word attachés** sur Activé et sélectionnez le bouton **Oui**.
8. Sélectionnez l’action **Journaliser**. Dans la fenêtre contextuelle Journaliser segment, activez **Créer suivi segment**
9. Cliquez sur le bouton **OK** pour commencer le **traitement en lot Journaliser segment**.  

Les pièces jointes sont envoyées. Lorsque le processus est terminé, cliquez sur le bouton **OK** associé au message qui indique que le segment a été journalisé.  

 Les lettres sont automatiquement imprimées et le segment journalisé. Comme le segment a été journalisé, il ne figure plus dans la liste des segments, mais est déplacé dans la liste des segments journalisés. Pour voir cette liste, sélectionnez l’icône ![Ampoule qui ouvre la fonction Fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Segments journalisés**, puis sélectionnez le lien associé.  

Une fois le segment enregistré, chaque lettre envoyée est enregistrée en tant qu’interaction, que vous pouvez afficher dans le journal.  

Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures journal interaction**, puis choisissez le lien associé. Chaque lettre envoyée est associée à une entrée.  

### Pour envoyer un message électronique à un contact  

1. Sur le raccourci **Interaction**, dans le champ **Code modèle interaction**, sélectionnez un modèle de lettre commerciale, code **BUS**.  
2. Dans le champ **Sujet (par défaut)**, entrez le texte exemple suivant : **Merci de votre visite au salon**.  
3. Dans le champ **Type correspondance**, sélectionnez **Courriel**.  
4. Spécifiez les paramètres de langue et joignez un document Word, comme dans la procédure précédente.  
5. Sélectionnez l'action **Journal**. La page **Journaliser segment** s’affiche.  
6. Cochez la case **Envoyer les pièces jointes** pour envoyer les pièces jointes par courriel.  
7. Cochez la case **Créer suivi segment**.  
8. Cliquez sur le bouton **OK**.  

 Les lettres sont automatiquement envoyées par courriel et le segment journalisé. Comme le segment a été journalisé, il ne figure plus dans la liste des segments, mais est enregistré dans la liste des segments journalisés. Pour voir cette liste, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Segments journalisés**, puis sélectionnez le lien associé.  

## Enregistrement des réponses de promotion

 Au cours des semaines suivantes, les prospects répondent à la lettre. Le directeur marketing souhaite assurer le suivi des réponses et enregistre ces interactions.  

 Pour cela, configurez un segment pour les contacts ayant répondu à la lettre.  

### Pour enregistrer les réponses de la promotion  

1. Sur la page **Segment**, sur le raccourci **Interaction**, choisissez le champ **Code modèle interaction**.  

 Aucun modèle d'interaction n'existe pour l'enregistrement des réponses à la campagne. Par conséquent, créez un nouveau modèle.  

2. Dans la liste déroulante **Modèles interaction**, cliquez sur l’action **Nouveau**.  
3. Dans le champ **Code**, entrez **RESP**. Dans le champ **Description**, entrez **Réponses à la campagne**.  
4. Choisissez le bouton **OK**.
5. Choisissez **Oui** pour confirmer que vous souhaitez appliquer ce code de modèle interaction à toutes les lignes segment.
6. Sur le raccourci **Promotion**, activez le champ **Réponse promotion**. Choisissez **Oui** pour confirmer le message *Vous avez modifié la réponse de promotion*.  
7. Sur la page **Segment**, sélectionnez l'action **journal**.  
8. Sur la page **Journaliser segment**, décochez la case **Envoyer les pièces jointes**. Choisissez ensuite le bouton **OK** pour confirmer le message indiquant que le segment a été journalisé.  
  
## Voir aussi  
[Gestion des relations](marketing-relationship-management.md)  
 [Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
