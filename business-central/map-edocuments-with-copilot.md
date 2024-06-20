---
title: Mappage de documents électroniques avec des lignes bon de commande avec Copilot
description: Découvrez comment utiliser Copilot pour mapper des documents électroniques aux lignes de bon de commande.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.collection:
  - get-started
  - bap-ai-copilot
ms.date: 04/10/2024
ms.custom: bap-template
---

# Mappage de documents électroniques avec des lignes bon de commande avec Copilot (version préliminaire)

À mesure que les processus d’approvisionnement deviennent de plus en plus numériques, la fonctionnalité de documents électroniques de Business Central joue un rôle clé dans l’automatisation de la réception et du traitement des factures des fournisseurs. Copilot peut vous aider dans ce processus en améliorant le mappage et la mise en correspondance des factures des fournisseurs avec les bons de commande. Cela réduit les tâches fastidieuses qui comprendraient normalement des recherches approfondies et la saisie de données. L’avantage est aggravé par le fait que les factures des fournisseurs ne correspondent souvent pas exactement aux bons de commande, auquel cas Copilot est mieux placé pour identifier les bons de commande correspondants. Les capacités de rapprochement améliorées profitent particulièrement aux petites et moyennes entreprises qui ont besoin d’un suivi efficace des documents pour les lignes bon de commande. Copilot est l’assistant de travail basé sur l’IA qui stimule la créativité et améliore la productivité des utilisateurs de Business Central.

> [!IMPORTANT]
> - Il s’agit d’une fonctionnalité en version préliminaire prêt pour la production pour les environnements de production et sandbox dans n’importe quel pays, à l’exception du Canada.
> - Les fonctionnalités en version préliminaire prêtes pour la production sont soumises à des conditions d’utilisation supplémentaires. En savoir plus : [Conditions d’utilisation supplémentaires pour la version préliminaire de Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274)
> - Le contenu généré par l’IA est peut-être incorrect.

Dans la version initiale de l’application de **document électronique**, nous avons introduit des scénarios fondamentaux pour les documents électroniques pour l’ensemble du processus de vente. Cependant, il est nécessaire d’améliorer et d’automatiser le traitement des documents reçus, notamment dans le contexte des processus d’achat. Copilot affine la façon dont vous gérez les documents électroniques dans le processus d’achat, notamment en ce qui concerne les bons de commande. Le cadre de documents électroniques vous permet de spécifier le type de document d’achat à créer pour chaque fournisseur lorsque vous recevez des factures électroniques de sa part. Auparavant, la seule option consistait à créer une facture d’achat, soit sous forme de document, soit sous forme de journal du grand livre.

Vous pouvez désormais mettre à jour un bon de commande existant dans Business Central avec les informations reçues dans la facture électronique.

<!--
> [!NOTE]
> - This feature is available as a production-ready preview for production and sandbox environments in any country localization, with the exception of Canada. Production-ready previews are subject to supplemental terms of use. For more information, see [Supplemental terms of use for Dynamics 365 preview](https://go.microsoft.com/fwlink/?linkid=2105274).
> - AI-generated content may be incorrect.-->

## Pour activer le copilote  

Si vous n’avez pas activé le copilote **Assistance de correspondance de documents électroniques**, vous devez le faire manuellement. Pour activer le copilote **Assistance de correspondance de documents électroniques**, suivez ces étapes : 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Copilote et capacités IA**, puis sélectionnez le lien associé. 
2. Dans la liste des fonctionnalités, choisissez **Assistance de mise en correspondance de documents électroniques** et modifiez l’état en **Actif**.  

Vous pouvez commencer à utiliser Copilot dès qu’il est activé. 

## Identifier des bons de commande

Tout d’abord, vous pouvez identifier les bons de commande que vous pouvez automatiquement rapprocher. Si votre **fournisseur** a configuré le champ **Recevoir le document électronique à** pour qu’il fonctionne avec **Bons de commande**, une fois le document électronique créé dans [!INCLUDE[prod_short](includes/prod_short.md)] (manuellement ou à partir d’un point de terminaison externe), [!INCLUDE[prod_short](includes/prod_short.md)] effectuera les opérations suivantes :

1. Si le **bon de commande** pour ce fournisseur particulier *existe et qu’il y a un numéro de bon de commande* dans le reçu **Fichier de document électronique** , [!INCLUDE[prod_short](includes/prod_short.md)] liera automatiquement ce **document électronique** au **spécifié**bon de commande. L’**État du document** de ce **Document électronique** sera **En cours**, et l’**État du document électronique** dans la sous-page **État du service** sera **Commande liée**.  
Ce lien sera visible dans le champ **Document** de ce **document électronique** spécifique. Si vous devez modifier automatiquement le **Bon de commande** lié, vous pouvez le faire à l’aide de l’action **Mettre à jour le lien du bon de commande** et choisissez manuellement l’un des bons de commande existants pour ce fournisseur. Vous ne pouvez le faire qu’avant de faire correspondre les lignes entre le **Document électronique** et **Bon de commande**.  
2. Si le **Bon de commande** pour ce fournisseur particulier *existe mais qu’il n’y a pas de numéro de bon de commande* dans **le document électronique** reçu, [!INCLUDE[prod_short](includes/prod_short.md)] offrira la possibilité de choisir l’un des bons de commande existants si vous avez téléchargé ce document manuellement, en ouvrant la liste **Bons de commande** des commandes reçues des fournisseurs contenant uniquement **Document électronique**, dans lequel vous devez sélectionner le **Bon de commande** souhaité, puis **OK**. Si vous n’avez pas sélectionné le **Bon de commande** approprié ou si vous avez obtenu le **document électronique** automatiquement d’un point de terminaison externe utilisant la **File d’attente des travaux**, le nouveau **document électronique** ne sera lié à aucun document d’achat et l’**État du document** sera **Erreur** et l’**État du document électronique** dans la sous-page **État du service** est **Erreur de traitement du document importé**. Pour terminer l’association avec le **Bon de commande**, choisissez l’action **Mettre à jour le lien du bon de commande** et choisissez l’un des bons de commande existants pour ce fournisseur.  

## Mapper les lignes

Copilot vous aide à faire correspondre automatiquement les lignes de facture électronique avec les lignes de bon de commande et offre des informations de correspondance supplémentaires pour améliorer les correspondances.

Une fois qu’ils ont été rapprochés et mappés, [!INCLUDE [prod_short](includes/prod_short.md)] met à jour le bon de commande rapproché avec les informations de réception pertinentes pour garantir que les bonnes quantités sont reçues sur les lignes de commande.

Vous pouvez faire correspondre vos documents électroniques reçus avec les lignes de bon de commande provenant de deux endroits différents, depuis la page **Documents électroniques** ou à partir de la page **Bon de commande**. Le moyen le plus simple de localiser les **Bons de commande** déjà liés est d’utiliser la vignette **Bons de commande liés** faisant partie de **Activités liées aux documents électroniques**. Tous les documents non liés se trouvés à l’aide de la vignette **En attente des factures électroniques d’achat** où vous avez une liste de **Documents électroniques** que vous devez revoir.  

> [!NOTE]
> Les **Activités liées aux documents électroniques** avec ces deux vignettes se trouvent dans les tableaux de bord suivants : **Évaluation du chef d’entreprise**, **Chef d’entreprise**, **Comptable**, **Gestionnaire des inventaires** et **Expédition et réception**.

Lorsque vous souhaitez exécuter un rapprochement à partir du bon de commande, choisissez l’action **Mapper les lignes de document électronique** , qui existe à la fois sur les pages de bon de commande et de liste de bons de commande. Toutefois, si vous souhaitez exécuter le rapprochement à partir de la page **E-Documents** , choisissez l’action **Rapprocher le bon de commande** de cette page. Pour terminer la correspondance, procédez comme suit :

1. Choisissez l’action **Mapper lignes documents électroniques** ou **Faire correspondre bon de commande**, pour les documents déjà liés.  
2. Vous pouvez remarquer que l’invite **Lignes de commande de correspondance de documents électroniques avec Copilot** fonctionne et vous avez la page **Rapprochement des bons de commande** en arrière-plan. Cela signifie que le même processus se produit mais avec le support automatique du **Copilote**, qui gère le processus de mise en correspondance à votre place. 
3. Après quelques secondes, le **Lignes de commande de correspondance de documents électroniques avec copilote** suggérera des lignes à faire correspondre avec détails supplémentaires : 

    1. Dans l’en-tête de l’invite, vous pouvez trouver les informations suivantes : 

    |Nom du champ |Désignation |
    |--------|-----------------|
    |Correspondance automatique | Spécifie le nombre de correspondances proposées automatiquement. Ceci est basé sur une comparaison de chaînes et s’il y a 80 % ou plus de descriptions qui se chevauchent, le système fera automatiquement correspondre ces descriptions sans utiliser les fonctionnalités GPT. |
    |Copilot mis en correspondance | Spécifie le nombre de correspondances proposées par Copilot en utilisant à la fois une comparaison de chaînes et sémantique. |
    |N° document électronique | Spécifie le numéro du document électronique lié. |
    |Montant total de la facture, hors TVA | Spécifie le montant total de la facture, hors TVA. |
    |Montant total mis en correspondance, TVA comprise | Spécifie le montant mis en correspondance, hors TVA. |
    
    2. Si toutes les lignes correspondent, vous verrez le texte vert dans le coin supérieur droit : **Toutes les lignes (100 %) correspondent. Examiner les propositions de match**.  
    3. Dans les lignes **Proposition correspondance**, vous trouver les informations suivantes :  

    |Nom du champ |Désignation |
    |--------|-----------------|
    |N° ligne document électronique | Spécifie le numéro de ligne du document électronique (provenant du fichier de document électronique d’origine). |
    |Description de la ligne document électronique | Spécifie la description de ligne du document électronique (provenant du fichier de document électronique d’origine). |
    |Quantité mise en correspondance | Spécifie la quantité qui sera affectée à la ligne bon de commande. |
    |Proposition | Spécifie l’action proposée par l’IA, et ces actions suggérées sont liées à la mise en correspondance des lignes bon de commande. |

    4. Toutes les lignes entièrement suggérées et assorties sont marquées de couleur verte. S’il y a un problème, c’est-à-dire un prix différent, mais dans la fourchette de prix autorisée, cette ligne sera marquée en jaune, et s’il y a une similitude entre les champs de description mais que la différence de prix est supérieure à celle autorisée, cette ligne sera marquée en rouge. 
    5. Si vous n’êtes pas satisfait de certaines suggestions, vous pouvez les supprimer en utilisant le **Supprimer la ligne** action.  
    6. Si vous souhaitez voir les correspondances de propositions, vous pouvez sélectionner le lien dans le **Proposition** colonne pour ouvrir la **Détails de la correspondance des documents électroniques** page. 
    7. Sur la page **Détails de la correspondance des documents électroniques**, vous pouvez comparer les détails du **Document électronique** et du **Bon de commande**, pour être sûr de la correspondance proposée avant de la confirmer. 
    8. Après révision, fermez la page.   

4. Si vous n’êtes pas satisfait de la plupart des suggestions, ou si vous ne souhaitez pas utiliser la fonctionnalité **Lignes de commande de correspondance de documents électroniques avec copilote**, sélectionnez **L'ignorer** et vous pourrez continuer [la correspondance manuelle](finance-how-use-edocuments-purchase.md) comme expliqué précédemment.  
5. Si vous souhaitez conserver les suggestions, choisissez le bouton **Conserver** et le système enregistre toutes les suggestions faites par **Copilote**.  
6. [!INCLUDE[prod_short](includes/prod_short.md)] ferme l’invite de Copilot et les lignes de la page **Rapprochement des bons de commande** seront marquées en vert, car elles sont déjà rapprochées.  
7. À partir de ce moment, vous pouvez continuer à travailler pendant que vous effectuez une correspondance manuelle, ce qui signifie que vous pouvez supprimer des correspondances, des correspondances manuelles, réinitialiser la correspondance ou si vous ne souhaitez apporter aucune modification, choisissez simplement l’action **Appliquer au bon de commande** et continuez à travailler avec le **Bon de commande**. 

> [!NOTE]
> Vous pouvez choisir l’action **Mettre en correspondance avec Copilot** dans la page **Rapprochement des bons de commande** à nouveau, mais dans ce cas, il vous est demandé si vous souhaitez écraser les correspondances existantes, car toutes les lignes sont déjà mises en correspondance.  

> [!NOTE]
> L’analyse prix/coût et le contrôle de la quantité disponible font partie de l’activité de prétraitement. 

## Voir aussi .

[Vue d’ensemble des documents électroniques](finance-edocuments-overview.md)    
[Utiliser des documents électroniques vente](finance-how-use-edocuments.md)    
[Utiliser les documents électroniques achat](finance-how-use-edocuments-purchase.md)   
[Résoudre les problèmes des fonctionnalités de Copilot et d’IA](ai-copilot-troubleshooting.md)    
[FAQ sur l’IA responsable pour l’assistance au rapprochement bancaire](faqs-bank-reconciliation.md)    
