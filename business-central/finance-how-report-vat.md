---
title: Envoyer les rapports TVA destinés à l'administration fiscale | Microsoft Docs
description: Apprendre à préparer les rapports qui répertorient la TVA des ventes au cours d'une période, ou à partir des ventes et achats, et envoyer le rapport à l'administration fiscale.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.date: 10/01/2018
ms.author: bholtorf
ms.openlocfilehash: 729524ce2145b4e167fb49671045b298affb862b
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813546"
---
# <a name="how-to-report-vat-to-a-tax-authority"></a>Procédure : déclarer la TVA à une administration fiscale
Cette rubrique décrit les rapports dans [!INCLUDE[d365fin](includes/d365fin_md.md)] que vous pouvez utiliser pour envoyer des informations sur les montants de la taxe sur la valeur ajoutée (TVA) relatifs aux ventes et achats à l'administration fiscale de votre région.

Vous pouvez utiliser les rapports suivants :

* La déclaration de liste des ventes de l'Union européenne (EU) **Liste des ventes UE** répertorie les montants de la taxe sur la valeur ajoutée (TVA) que vous avez collectés pour les ventes aux clients enregistrés dans les pays de l'Union européenne (UE).  
* Le rapport **Retour TVA** inclut la TVA pour les ventes et les achats aux clients dans tous les pays utilisant la TVA.

Si vous souhaitez afficher un historique complet des écritures TVA, chaque report impliquant la TVA crée une écriture dans la page **Écritures TVA**. Ces écritures sont utilisées pour calculer le montant du relevé de TVA, tel que paiement et remboursement, pour une période donnée. Pour afficher les écritures TVA, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Écritures TVA**, puis sélectionnez le lien associé.

## <a name="about-the-ec-sales-list-report"></a>À propos du rapport Liste des ventes UE
Au Royaume-Uni, toutes les compagnies qui vendent des marchandises et des services aux clients enregistrés à la TVA, y compris les clients dans d'autres pays de l'Union européenne (UE), doivent envoyer une version électronique du rapport Liste des ventes de la Communauté européenne (CE) au format XML sur le site Web du service de la fiscalité et des douanes du Royaume-Uni. Le rapport de liste des ventes de l'Union européenne ne fonctionne que pour les pays de l'UE.

Le rapport comprend une ligne pour chaque type de transaction avec le client, et affiche le montant total pour chaque type de transaction. Il peut inclure trois types de transactions :  

* Marchandises B2B  
* Services B2B  
* Marchandises triangulées B2B  

Les biens et services B2B indiquent si vous avez vendu un bien ou un service, et sont contrôlés par le paramètre **Service UE** de la configuration du report TVA. Les marchandises triangulées B2B indiquent si vous vous êtes engagé dans des transactions avec un tiers, et sont contrôlées par le paramètre **Trans. tripartite UE** sur les documents vente, comme des documents de vente, des factures, des notes de crédit, etc.  

Une fois que l'administration fiscale aura examiné votre rapport, elle devra envoyer un courriel au contact de votre compagnie. Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], le contact est spécifié sur la page **Informations société**. Avant de soumettre le rapport, assurez-vous qu'un contact a été sélectionné.

## <a name="about-the-vat-return-report"></a>À propos du rapport Retour TVA
Utilisez ce rapport pour envoyer les documents relatifs à la TVA sur les ventes et les achats, tels que les commandes d'achat et de vente, les factures et les notes de crédit. Les informations de ce rapport ont le même format que dans la déclaration de l'administration fiscale et douanière.  

La TVA est calculée sur la base de la configuration du report TVA et des groupes de report TVA que vous avez définis.

Pour le retour TVA, vous pouvez spécifier les écritures pour :

* Envoyer les transactions ouvertes uniquement, ou ouvertes et fermées. Par exemple, cela est utile lorsque vous préparez votre retour TVA annuel final.
* Envoyer uniquement les écritures des périodes définies, ou inclure également les écritures des périodes précédentes. Cette fonction est utile pour mettre à jour un retour TVA déjà envoyé, par exemple, si un fournisseur vous envoie une facture échue.    

## <a name="to-connect-to-your-tax-authoritys-web-service"></a>Pour vous connecter au service Web de votre administration fiscale
[!INCLUDE[d365fin](includes/d365fin_md.md)] fournit des connexions de service à des sites Web d'administrations fiscales. Par exemple, si vous vous trouvez au Royaume-uni, vous pouvez activer la connexion de service **GovTalk** pour envoyer la liste des ventes UE et les rapports Retour TVA par voie électronique. Si vous souhaitez envoyer le rapport manuellement, par exemple en entrant vos données sur le site Web de l'administration fiscale, cela n'est pas nécessaire.   

Pour déclarer la TVA à une administration par voie électronique, vous devez connecter [!INCLUDE[d365fin](includes/d365fin_md.md)] au service Web de l'administration fiscale. Cela suppose que vous configuriez un compte avec votre administration fiscale. Lorsque vous avez un compte, vous pouvez activer une connexion de service que nous fournissons dans [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Connexions au service**, puis sélectionnez le lien approprié.
2. Renseignez les champs requis. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]  
    >   Il est judicieux de tester votre connexion. Pour cela, choisissez la case à cocher **Mode test**, puis préparez et envoyez votre rapport TVA comme décrit dans la section _Préparer et envoyer un rapport TVA_. En mode Test, le service vérifie si l'administration fiscale peut recevoir votre rapport, et l'état du rapport indiquera si l'envoi du test a réussi. Il est important de retenir que ce n'est pas un envoi réel. Pour réellement envoyer le rapport, vous devez désactiver la case à cocher **Mode test**, puis répéter le processus d'envoi.

## <a name="to-set-up-vat-reports-in-included365finincludesd365finmdmd"></a>Pour configurer les rapports TVA dans [!INCLUDE[d365fin](includes/d365fin_md.md)]
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration déclaration TVA**, puis sélectionnez le lien associé.  
2. Pour laisser des utilisateurs modifier et retourner ce rapport, sélectionnez la case à cocher **Modifier les rapports soumis**.  
3. Choisissez la série de numéros à utiliser pour chaque rapport.  

## <a name="to-prepare-and-submit-a-vat-report"></a>Pour préparer et soumettre un rapport TVA
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Liste des ventes UE** ou **Retour TVA**, et sélectionnez le lien associé.  
2. Sélectionnez **Nouveau**, puis renseignez les champs requis. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour générer le contenu de l'état, sélectionnez l'action **Proposer lignes**.  

    > [!NOTE]  
    >   Pour le rapport Liste des ventes UE, vous pouvez consulter les transactions incluses dans les lignes de rapport avant d'envoyer le rapport. Pour cela, sélectionnez la ligne, puis cliquez sur l'action **Afficher écritures TVA**.  
4. Pour valider et préparer le rapport pour l'envoi, choisissez l'action **Libérer**.  

    > [!NOTE]  
    >   [!INCLUDE[d365fin](includes/d365fin_md.md)] confirme que l'état est configuré correctement. Si la validation échoue, les erreurs sont affichées sous **Erreurs et avertissements**, de sorte que vous sachiez quoi corriger. Généralement, si le message concerne un paramètre manquant dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez cliquer sur le message pour ouvrir la page contenant les informations à corriger.  
5. Pour envoyer l'état, sélectionnez l'action **Soumettre**.  

Une fois que vous envoyez la déclaration, [!INCLUDE[d365fin](includes/d365fin_md.md)] surveille le service et conserve un enregistrement de vos communications. Le champ **Statut** indique l'état de la déclaration en cours. Par exemple, lorsque l'administration traite votre déclaration, le statut de celle-ci passe à **Réussie**. Si l'administration fiscale trouve des erreurs dans la déclaration que vous avez envoyée, le statut de celle-ci est **Échec**. Vous pouvez afficher les erreurs sous **Erreurs et avertissements**, corrigez-les, puis envoyez le rapport. Pour visualiser une liste de toutes vos déclarations de liste des ventes UE, consultez la page **États de liste des ventes UE**.  

## <a name="viewing-communications-with-your-tax-authority"></a>Affichage de l’historique des communications avec votre administration fiscale
Dans certains pays, vous échangez des messages avec l'administration fiscale lorsque vous envoyez des états. Vous pouvez afficher le premier et le dernier message que vous avez envoyés ou reçus en choisissant **Télécharger le message d’envoi** et les actions **Télécharger le message de réponse**.  

## <a name="submitting-vat-reports-manually"></a>Envoi manuel des rapports TVA
Si vous utilisez une autre méthode pour envoyer l'état, par exemple en exportant le XML et en le téléchargeant sur le site Web d'une administration fiscale, vous pouvez ensuite choisir **Marquer comme Soumis** pour clôturer la période de référence. Lorsque vous signalez le rapport comme libéré, vous ne pouvez plus le modifier. Si vous devez modifier le rapport après l'avoir signalé comme libéré, vous devez le rouvrir.

## <a name="vat-settlement"></a>Relevé de TVA
Périodiquement, vous devez régler la TVA nette aux autorités fiscales. Si vous devez effectuer des relevés de TVA fréquemment, vous pouvez exécuter le traitement en lot **Calculer et reporter le relevé de TVA** pour fermer les écritures TVA ouvertes et transférer les montants TVA achat et vente au compte de relevé de TVA.

Lors du transfert des montants TVA vers le compte de déclaration, le compte TVA achat est crédité et le compte TVA vente est débité sur la base des montants calculés pour la période spécifiée. Le montant net est crédité ou débité, si le montant TVA achat est supérieur, sur le compte du relevé de TVA. Vous pouvez reporter la déclaration immédiatement ou imprimer d'abord un rapport de test.  

> [!Note]
> Lorsque vous utilisez le traitement en lot **Calculer et reporter le relevé de TVA**, si vous ne spécifiez pas un **Groupe de report de marché TVA** et un **Groupe de report produit TVA**, les écritures contenant tous les groupes de report de marché et tous les groupes de report de produit sont incluses.

## <a name="configuring-your-own-vat-reports"></a>Configuration de vos propres états de TVA
Vous pouvez utiliser le rapport Liste des ventes UE prédéfini, cependant, vous pouvez également créer vos propres rapports. Cela nécessite de créer des codeunits. Si vous avez besoin de l'aide à cette fin, contactez un partenaire certifié Microsoft.  

Le tableau suivant décrit les codeunits que vous devez créer pour votre rapport.

| Codeunit | Ce qu'il doit effectuer |
|----|-----|
|Proposer lignes| Extraire les informations de la table Écritures TVA, et les afficher sur les lignes du rapport TVA.|
|Contenu | Contrôler le format du rapport. Par exemple, si c'est un fichier XML ou JSON. Le format à utiliser dépend des besoins du service Web de votre administration fiscale. |
|Soumission | Contrôler comment et quand vous envoyez le rapport selon les besoins de votre administration fiscale. |
|Gestionnaire de réponse | Gérer le retour de l'administration fiscale. Par exemple, elle peut envoyer un courriel au contact de votre compagnie. |
|Annuler | Envoyer une annulation d'un rapport TVA qui a été envoyé précédemment à votre administration fiscale. |  

> [!Note]
> Lorsque vous créez des codeunits pour le rapport, faites attention à la valeur du champ **Version de la déclaration TVA**. Ce champ doit refléter la version du rapport qui est ou a été requis par l'administration fiscale. Par exemple, vous pouvez saisir **2017** dans le champ pour indiquer que l'état remplit les conditions qui étaient en place cette année. Pour trouver la version en cours, contactez votre administration fiscale.
 
## <a name="see-also"></a>Voir aussi .
[Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md)  
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  
[Définition des ventes](sales-setup-sales.md)  
[Facturer des ventes](sales-how-invoice-sales.md)  
