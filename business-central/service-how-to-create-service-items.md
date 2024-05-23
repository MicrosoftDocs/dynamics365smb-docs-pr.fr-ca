---
title: "Procédure\_: créer des articles de service"
description: "Découvrez les différentes manières de créer des articles de service dans Business\_Central, par exemple dans une commande de service ou lors de l’expédition d’articles."
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: null
ms.date: 03/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Créer articles service

Dans [!INCLUDE[prod_short](includes/prod_short.md)], le terme « article de service » fait référence à un équipement ou un article nécessitant une maintenance. Lorsque vous créez une commande service, vous spécifiez les articles nécessitant une maintenance. Dans la commande, vous pouvez lier un article de service à un article dans l'inventaire ou à un groupe articles de service.

Lorsque vous recevez un article nécessitant une maintenance, vous pouvez l'enregistrer en tant qu'article de service. Plusieurs méthodes sont possibles. Par exemple, vous pouvez créer un article de service sur la page **Articles de service**, ou dans le cadre d'un autre traitement, par exemple en utilisant une commande service.

## Pour créer un article de service

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles de service**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Pour créer des articles de service dans des commandes service

Lorsque vous recevez des articles que vous souhaitez enregistrer comme articles de service, vous pouvez les créer en tant que tels sur la page **Commande service** ou **Devis service**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes service**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choisissez l'action **Créer article de service**.  

    Un numéro est affecté à l'article de service et une fiche article de service est créée. Le champ **N° article de service** est rempli par le numéro du nouvel article de service.

## Pour créer un article de service lors de la livraison d'articles

Si vous livrez des articles en reportant les documents de vente ou les factures vente, ces articles sont enregistrés automatiquement en tant qu'articles de service si la condition suivante est remplie. Les articles doivent appartenir à un groupe articles de service et la case à cocher **Créer article de service** doit être activée. Si ces articles portent des numéros de série enregistrés sur la page Lignes traçabilité, cette information est copiée automatiquement dans le champ **Numéro de série** de la fiche article de service, lorsque les articles de service sont créés.  

La procédure suivante explique comment créer des articles de service lorsque vous livrez des articles de documents de vente.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez le document de vente approprié.  
3. Sélectionnez l'action **Reporter** ou **Reporter et imprimer**.  
4. Choisissez l'action **Livrer** ou **Livrer et facturer**.  
5. Les articles de service sont automatiquement créés pour les articles de la commande pour autant qu'ils appartiennent à un groupe articles de service que vous avez configuré pour créer des articles de service. Si vous avez enregistré des numéros de série précis sur la page **Lignes traçabilité**, ceux-ci sont affectés à ces articles de service.  

> [!NOTE]  
> Si un article est une nomenclature et que vous ayez éclaté cette nomenclature, les articles de la nomenclature éclatée sont traités comme des articles normaux. Des articles de service sont créés à partir des mêmes conditions (groupe articles de service et numéro de série). En outre, si le programme crée un article de service pour un article nomenclature éclatée composé d'autres composantes nomenclature, ces articles sont créés comme composantes d'article de service de l'article de service de la nomenclature éclatée.  
>
> Si un article est une nomenclature que vous n'avez pas éclatée, un article de service est créé à partir des mêmes conditions (groupe articles de service et numéro de série).  

## Pour insérer des frais forfaitaires pour un article service

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Tâches service**, puis choisissez le lien associé.
2. Sélectionnez l'action **Feuille activité article**.
3. Choisissez la ligne service, puis sélectionnez **Actions**, **Fonctions**, puis l'action **Insérer frais forfaitaires**.  

    Une ligne service de type **Coût** est insérée avec les frais forfaitaires. Les frais forfaitaires affectent l'article de service sélectionné.

## Bloquer des articles, des variantes d’articles ou des articles de service spécifiques

Vous pouvez empêcher l’utilisation d’articles, de variantes d’article ou d’articles de service dans les transactions de gestion de services, telles que les contrats de service, les ordres de service et les factures de service. Cela peut être utile si vous souhaitez restreindre la disponibilité de certains articles ou articles de service à des fins de service, par exemple en raison d’une interruption du support, d’un stock limité ou d’ententes contractuelles.

Pour empêcher l’utilisation d’un article ou d’une variante d’article dans les transactions de gestion de services, activez le bouton **Service bloqué** sur la **Fiche d’article**. , **Variantes d’articles** et **Carte de variantes d’articles** page. Vous pouvez également définir ce champ sur la page **Modèle d’élément** , et il sera copié dans les éléments créés à partir de ce modèle.

Lorsqu’un article ou une variante d’article est bloqué en service, il n’est pas disponible pour la sélection sur les pages suivantes :

- Ligne de service (sauf pour les notes de crédit de service, où vous verrez une notification indiquant que l’article ou la variante est bloquée, mais autorisée sur ce type de document)
- Article de service
- Ligne contrat service
- Ligne de service standard

Si vous saisissez manuellement un numéro d’article ou une variante bloquée, vous recevrez un message d’erreur indiquant : « Le champ contient une valeur introuvable dans la table associée ».

De plus, si vous avez des contrats de service, des devis de contrat de service ou des commandes de service qui incluent des articles de service ou des variantes d’article bloqués, vous ne pouvez pas utiliser les actions suivantes :

- **Verrouillez** ou **Passez un contrat** sur la **Devis de contrat de service** page.
- **Verrouiller le contrat**, **Signer le contrat**, **Créer des commandes de service contractuelles** ou **Créez des factures contractuelles**  sur la page **Contrat de service** .
- **Créer commande** sur page **Devis service**.
- **Libération pour expédition** ou **Publier** sur la page **Commande de service** .
- **Reporter** dans page la **Facture service**.

### Bloquer d’un article de service

Pour empêcher l’utilisation d’un article de service dans les transactions de gestion de services, sur la page **Carte d’article de service** , dans la section **Bloquée** champ, choisissez l’une des options suivantes :

- **Contrat de service** : empêche l’utilisation de l’article de service dans les contrats de service et les devis de contrat de service, mais pas dans les commandes de service ou autres documents de service.
- **Tous** : empêche l’utilisation de l’article de service dans la transaction de gestion du service, notamment les contrats de service, commandes de service et autres documents de service.

Lorsqu’un article de service est bloqué, vous ne pouvez pas le sélectionner sur les pages suivantes :

- Ligne de contrat de service (si bloquée pour le contrat de service, ou la totalité)
- Ligne d’article de service (sauf pour les notes de crédit de service, si bloqués pour tous)

Si vous saisissez manuellement un numéro d’article de service ou une d'article de service bloquée, un message d’erreur indiquant : "Le champ contient une valeur introuvable dans la table associée".

De plus, si vous avez des contrats de service, des devis de contrat de service ou des commandes de service qui incluent des articles de service bloqués, vous ne pouvez pas utiliser les actions suivantes :

- **Verrouillez** et **Passez un contrat** sur la **Devis de contrat de service** page (si bloqué pour le service contrat, ou la totalité).
- **Verrouillez contrat** **Signer contrat** ou **Changer client** sur **Contrat de service** (si bloqué pour le service contrat, ou la totalité).
- **Passez commande** sur le **Devis de service** (si bloqué pour tous).
- **Libération pour expédition** ou **Publier** sur la page **Commande de service** (si bloqué pour tous. Si les documents d’ordre de service contiennent plusieurs articles de service et que certains sont bloqués et d’autres non, vous pouvez débloquer et reporter des lignes non bloquées. Déterminez s’il convient d’activer le bouton **Une ligne/commande d’article de service** sur la page **Configuration de la gestion des services** .
- **Reporter** dans la page **Facture service** (si bloqué pour tous).

Vous pouvez également afficher les éléments de service bloqués en appliquant un filtre aux rapports suivants :

- Articles service (rapport 5935)
- Articles de service hors garantie (rapport 5937)
- Profit sur serv. (art. service) (rapport 5938)

### Mise à niveau des données

Cette fonctionnalité ne nécessite aucune configuration supplémentaire. Cependant, si vous mettez à niveau votre [!INCLUDE [prod_short](includes/prod_short.md)], soyez conscient des points suivants :

- Si vous disposez d’articles, de variantes d’articles ou de modèles d’articles dont le **Ventes bloquées** la bascule est activée, le **service bloqué** Le champ est également activé pour ces enregistrements lors de la mise à niveau. Cela garantit que la logique de blocage des ventes existante s’applique également aux transactions de gestion des services.
- Mises à niveau des données uniquement si vous disposez d’au moins un élément de service dans votre compagnie, ce qui signifie que vous utilisez la fonctionnalité de gestion des services et que vous avez besoin de la mise à niveau des données. Si vous ne disposez pas d’éléments de service, la mise à niveau des données est ignorée et le **Service bloqué** La bascule est désactivée par défaut pour tous les éléments, variantes d’élément et modèles d’élément.

## Voir aussi .

[Configurer des articles de service et des composantes article de service](service-how-setup-service-items.md)  
[Paramétrage de la gestion des services](service-setup-service.md)  
[Gestion des services](service-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
