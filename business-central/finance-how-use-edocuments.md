---
title: Utiliser des documents électroniques vente
description: Découvrez comment utiliser la fonctionnalité de documents électroniques liée aux factures de vente.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'electronic document, electronic invoice, e-document, e-invoice, sales, deliver'
ms.search.form: '42, 43, 132, 6103, 6133, 6121, 9301, 9305'
ms.date: 04/10/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Utilisation des documents électroniques dans le processus vente

Vous pouvez utiliser des documents électroniques configurés (documents électroniques) avec les documents de vente.

Vous pouvez utiliser les documents vente suivants avec la fonctionnalité des documents électroniques :  

- Factures vente
- Documents de vente
- Notes de crédit vente
- Factures service
- Notes de crédit service
- Notes de frais financiers
- Relances

## Documents électroniques vente  

Pour créer et envoyer une facture électronique à un client, vous devez créer et reporter la facture vente. Pour en savoir plus sur le processus standard, voir [Facture des ventes](sales-how-invoice-sales.md).

Après avoir reporté le document vente, ouvrez la page **Factures vente reportées** pour accéder à la page **Document électronique** associée.

### Afficher les documents électroniques   

Pour afficher les documents électroniques existants, procédez comme suit.

1. Sur la page **Factures vente reportée**, sélectionnez **Document électronique** et **Ouvrir document électronique**.
2. Sur la page **Documents électronique**, dans l’en-tête, vous pouvez afficher les informations de base sur la facture reportée.
3. Le champ **Enregistrement** affiche le numéro de document de la facture vente reportée. Sélectionnez le lien pour ouvrir le document.
4. Dans le champ **État du document électronique**, vous pouvez afficher l'état en temps réel du document et son emplacement dans le pipeline de processus. Si le document est reporté, l'état est **Traité**.

### Journaux et états des documents électroniques 

Pour plus de détails sur le niveau d’état de service de votre document électronique, consultez le récapitulatif **État du service du document électronique**. Sur les lignes, le système affiche un ou plusieurs services utilisés par le document. Dans le scénario le plus courant, chaque document utilise un seul service. Cependant, un document peut utiliser plusieurs services.

- Cochez le champ **Code service de document électronique** pour déterminer quel service a été utilisé.
- Cochez le champ **État du document électronique** pour déterminer l'état de service actuel de ce document.
- Si vous souhaitez plus de détails, sélectionnez le champ **Journaux** pour le service sur la page **Journaux de documents électroniques**. Un aperçu chronologique des différents états du document est affiché.
- Vérifiez les champs **Numéro d’entrée** et **Création le** et d’autres informations sur la page **Journaux de documents électroniques**. Dans le champ **État du document électronique**, le premier état est **Exporté**, ce qui indique que le fichier de document électronique a été créé. L'état suivant est **Envoyé**, qui indique que le document a été envoyé au fournisseur de services, s’il est configuré.

Pour plus d’informations, sélectionnez l’écriture qui possède l'état **Exporté**, puis exécutez l’une des actions suivantes :

- **Ouvrir les journaux de mappage** : obtenez un aperçu de tous les champs exportés à partir des tables sourcées dans le champ **Valeur d’origine**. Si vous avez utilisé des règles de transformation lors du processus d’exportation, vous pouvez également obtenir la valeur finale dans le champ **Nouvelle valeur**.
- **Exporter le fichier** : exportez le fichier XML pour une révision manuelle.

Pour visualiser la communication entre vous et le service auquel vous envoyez votre document, utilisez le champ **Journaux de communications**. Ouvrez la page **Journaux de communication de documents électroniques** pour afficher les détails de la demande et le message de motifs avec ce service.

S’il y a un problème avec le fournisseur de services et que le document ne peut pas être envoyé, recherchez les indicateurs suivants sur la page **Documents électronique** :

- Le champ **État du document électronique** sur l’en-tête affiche l'état **Erreur**.
- Le champ **État du document électronique** sur le récapitulatif **État du service de document électronique** affiche l'état **Erreur d’envoi**.
- Le récapitulatif **Erreur et avertissements** contient un ou plusieurs messages indiquant la cause du problème.

Une fois le problème résolu, exécutez manuellement les actions **Envoyer le document**. Si vous avez besoin de différentes actions, telles que **Document recréé**, **Annuler le document**, ou **Obtenir l’approbation**, vous pouvez les exécuter.

## Vue d’ensemble des états des documents électroniques

Pour obtenir un meilleur aperçu de tous les documents électroniques de la compagnie, vous pouvez sélectionner le centre de rôles **Comptable** où existent les états des documents électroniques. Vous y trouverez des activités de documents électroniques qui ont les états suivants :

- **Documents électroniques sortants**

    - Traité
    - En cours
    - Erreur


## Voir aussi .

[Procédure : configurer les documents électroniques dans [!INCLUDE[prod_short](includes/prod_short.md)]](finance-how-setup-edocuments.md)    
[Utilisation des documents électroniques achat](finance-how-use-edocuments-purchase.md)  
[Comment étendre des documents électroniques dans [!INCLUDE[prod_short](includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)    
[Gestion financière](finance.md)    
[Facturer des ventes](sales-how-invoice-sales.md)    
[Enregistrer les achats avec les factures achat et les commandes](purchasing-how-record-purchases.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
