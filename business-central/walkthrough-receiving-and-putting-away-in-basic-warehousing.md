---
title: "Procédure pas à pas\_: Réception et rangement dans les configurations de stockage de base"
description: Découvrez les différentes façons de gérer les processus entrants pour la réception et le rangement.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.date: 02/27/2023
ms.custom: bap-template
---
# <a name="walkthrough-receiving-and-putting-away-in-basic-warehouse-configurations"></a>Procédure pas à pas : Réception et rangement dans les configurations de stockage de base

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous recevez des articles et les rangez en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus entrant|Réceptions requises|Rangements requis|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire||Activé|De base : commande par commande.|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt|Activé||De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt|Activé|Activé|Avancé|  

Learn more at [Flux d’enlogement](design-details-inbound-warehouse-flow.md).

La procédure pas à pas suivante illustre la méthode B dans la table précédente.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas

Pour les configurations entrepôt de base, lorsqu’un emplacement est défini pour exiger un traitement des rangements mais pas un traitement des réceptions, utilisez la page **Rangement inventaire** pour enregistrer et reporter les informations de rangement et de réception pour vos documents source entrants. Les documents suivants sont des documents origine entrants :

* Bon de commande
* Retour vente
* Ordre de transfert entrant
* Bon de production avec sortie prête à être rangée

> [!NOTE]
> Bien que les paramètres soient appelés **Prélèvement requis** et **Rangement requis**, vous pouvez quand même reporter les réceptions et les livraisons directement à partir des documents commerciaux source dans les emplacements où vous cochez ces cases.  

Cette procédure pas à pas présente les tâches suivantes :  

* Configurer l’emplacement ARGENT pour le rangement inventaire.  
* Configurer l'emplacement ARGENT pour la gestion de zone.  
* Définir une zone par défaut pour l’article LS-81. (LS-75 est déjà défini dans CRONUS).  
* Créer un bon de commande de 40 haut-parleurs pour le fournisseur 10000.  
* Vérifier que les zones de rangement sont prédéfinies par la configuration.  
* Libérer le bon de commande pour l’activité entrepôt.  
* Créer un rangement inventaire sur la base d’un document source libéré.  
* Vérifier que les zones de rangement sont héritées du bon de commande.  
* Enregistrer le mouvement entrepôt dans l’entrepôt et reporter la réception achat pour le bon de commande source.  

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

## <a name="roles"></a>Rôles

Les rôles utilisateur suivants effectuent les tâches qui composent cette procédure pas à pas :  

* Gestionnaire d'entrepôt  
* Agent d'achats  
* Magasinier  

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter ce processus pas à pas, vous devez disposer de :  

* données CRONUS International Ltd.  
* être un employé d'entrepôt à l’emplacement ARGENT. Pour vous configurer, procédez comme suit :  

    1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
    2. Choisissez le champ **Code utilisateur** et sélectionnez votre compte utilisateur sur la page **Utilisateurs**.  
    3. Dans le champ **Code emplacement**, choisissez **ARGENT**.  
    4. Cochez la case **Par défaut**.  

## <a name="story"></a>Scénario

Ellen, responsable d'entrepôt chez CRONUS International Ltd., crée un bon de commande de 10 unités de l'article LS-75 et 30 unités de l'article LS-81 du fournisseur 10000, qui doivent être livrées à l'entrepôt ARGENT. Lorsque la livraison arrive à l’entrepôt, Jean, l'employé d'entrepôt, range les articles dans des zones par défaut définies pour les articles. Lorsque Jean reporte le rangement, les articles sont reportés comme étant reçus dans l'inventaire et disponibles à la vente ou pour d'autres demandes.  

## <a name="setting-up-the-location"></a>Configuration de l’emplacement

Les paramètres de la page **Fiche emplacement** définissent les flux d’entrepôt de la compagnie.  

### <a name="to-set-up-the-location"></a>Pour configurer l'emplacement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.  
2. Ouvrez la fiche emplacement ARGENT.  
3. Activez le bouton à bascule **Rangement requis**.  

    Configurez une zone par défaut pour les deux numéros d’article pour contrôler l’endroit où ils sont rangés.  

4. Choisissez l'action **Zones**.  
5. Sélectionnez la première ligne, pour la zone **S-01-0001**, puis choisissez l’action **Contenu**.  

    Remarquez sur la page **Contenu zone** que l’article **LS-75** est déjà défini comme contenu dans la zone S-01-0001.  

6. Sélectionnez l'action **Nouveau**.  
7. Sélectionnez les champs **Fixe** et **Par défaut**.  
8. Dans le champ **N° article**, saisissez **LS-81**.  

## <a name="create-the-purchase-order"></a>Créer le bon de commande

Les bons de commande sont le type de document source entrant le plus répandu.  

### <a name="to-create-the-purchase-order"></a>Pour créer le bon de commande

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de commande**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Créez un bon de commande pour le fournisseur 10 000 à la date de travail (23 janvier) comportant les lignes bon de commande suivantes.  

    |Article|Code d'emplacement|Code de zone|Quantité|  
    |----------|-------------------|--------------|--------------|  
    |LS_75|ARGENTE|S-01-0001|10|  
    |LS-81|ARGENTE|S-01-0001|30|  

    > [!NOTE]  
    > Le code de zone est renseigné automatiquement en fonction de la configuration que vous avez créée dans la section [Configuration de l’emplacement](#setting-up-the-location).  

    Ensuite, informez l’entrepôt que le bon de commande est prêt pour l’activité entrepôt lorsque la livraison arrivera.  

4. Sélectionnez l'action **Lancer**.  

    La livraison des haut-parleurs provenant du fournisseur 10000 est arrivée dans l'entrepôt ARGENT. Jean procède à leur rangement.  

## <a name="receive-and-put-the-items-away"></a>Recevoir et ranger des articles

Utilisez la page **Rangement inventaire** pour gérer toutes les activités entrepôt entrantes pour un document source spécifique, tel qu’un bon de commande.  

### <a name="to-receive-and-put-the-items-away"></a>Pour recevoir et ranger des articles

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangements inventaire**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Sélectionnez le champ **Document source**, puis sélectionnez **Bon de commande**.  
4. Sélectionnez le champ **N° origine**, sélectionnez la ligne correspondant à l'achat au fournisseur 10000, puis cliquez sur le bouton **OK**.  

    Sinon, choisissez l'action **Extraire document origine**, puis sélectionnez le bon de commande.  

5. Choisissez l'action **Remplir automatiquement la quantité à traiter**.  

    Sinon, dans le champ **Qté à traiter**, saisissez respectivement 10 et 30 sur les deux lignes rangement inventaire.  

6. Choisissez l'action **Reporter**, sélectionnez l'action **Réceptionner**, puis choisissez le bouton **OK**.  

    Les 40 haut-parleurs sont à présent enregistrés comme rangés dans la zone S-01-0001, et une écriture article positive est créée pour refléter la réception achat reportée.  

## <a name="see-also"></a>Voir aussi

[Ranger des articles avec des rangements inventaire](warehouse-how-to-put-items-away-with-inventory-put-aways.md)  
[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Prélever pour la fabrication et l'assemblage](warehouse-how-to-pick-for-production.md)  
[Déplacer des articles ad hoc dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[Détails de conception : flux d'enlogement](design-details-inbound-warehouse-flow.md)  
[Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
