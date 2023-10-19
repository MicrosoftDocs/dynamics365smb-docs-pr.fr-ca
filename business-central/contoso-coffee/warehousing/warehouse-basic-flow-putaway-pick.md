---
title: 'Réception, rangement, prélèvement et expédition dans une configuration d’entrepôt de base'
description: "Dans Business\_Central, les processus entrants et sortants peuvent être effectués de quatre manières, à l’aide de différentes fonctionnalités en fonction du niveau de complexité de l’entrepôt."
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: null
ms.date: 04/01/2021
ms.author: bholtorf
---

# <a name="walkthrough-of-inbound-and-outbound-flow-in-basic-warehouse-configurations"></a>Procédure pas à pas sur les flux entrants ou sortants dans les configurations entrepôt de base

Cette procédure pas à pas montre comment effectuer des flux entrants et sortants dans la configuration de base : commande par commande. Pour plus d’informations, voir [Présentation des différentes options de configuration](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## <a name="prerequisites"></a>Conditions préalables
Pour exécuter cette procédure, vous devez faire de vous un employé d’entrepôt sur le site *ARGENT* en procédant comme suit :  
1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2. Choisissez le champ **Code utilisateur** et sélectionnez votre propre compte utilisateur sur la page **Utilisateurs**.  
3. Dans le champ **Code d’emplacement**, entrez *ARGENT*.  

## <a name="inbound-flow-receiving-and-putting-away-in-basic-warehouse-configurations"></a>Flux entrant : Réception et rangement dans les configurations de stockage de base

Dans [!INCLUDE[prod_short](../../includes/prod_short.md)], les processus entrants de réception et de rangement peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.  

|Méthode|Processus entrant|Zones|Reçus|Rangements|Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|X|||2|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire|||X|3|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt||X||4/5/6|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt||X|X|4/5/6|  

Pour plus d'informations, reportez\-vous à [Détails de conception : flux d'enlogement](../../design-details-inbound-warehouse-flow.md).  

La procédure pas à pas suivante illustre la méthode B dans la table précédente.  

### <a name="scenario"></a>Scénario
Alicia, l’agent achat, crée un bon de commande pour divers grains torréfiés. Lorsque la livraison arrive à l’entrepôt, John, l’employé de l’entrepôt, range les articles dans des zones adaptées. Lorsque Jean valide le rangement, les articles sont reportés comme reçus dans l’inventaire et disponibles à la vente ou à une autre demande.  

### <a name="steps"></a>Étapes
1. Configurez la page **Fiche emplacement** pour définir les flux d’entrepôt entrants de la compagnie.  

    1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.  
    2.  Ouvrez la fiche emplacement *ARGENT*.  
    3.  Activez la case à cocher **Rangement requis**.  

2. Définissez une zone par défaut pour les deux numéros d’article pour contrôler l’endroit où ils sont rangés

    1.  Choisissez l’action **Zones** dans la **Fiche emplacement**
    2.  Sélectionnez la première ligne, pour la zone *S-1-01*, puis choisissez l’action **Contenu**.  
    3.  Sélectionnez l'action **Nouveau**.  
    4.  Sélectionnez les champs **Fixe** et **Par défaut**.  
    5.  Dans le champ **N° article**, saisissez *WRB-1000*.  

3. Créez le bon de commande, qui est le type de document d’origine entrant le plus répandu.  

    1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.  
    2.  Sélectionnez l'action **Nouveau**.  
    3.  Créez un bon de commande pour le fournisseur 10000 comportant les lignes bon de commande suivantes. Utilisez les outils de personnalisation si le champ **Code de zone** n’est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](../../ui-personalization-user.md). 

    |Article ;|Code d'emplacement|Code de zone|Quantité|  
    |----------|----------|---------|--------------|  
    |WRB-1000|ARGENTE|S-1-01|2.0|  
    |WRB-1001|ARGENTE||30|

    Le code de zone dans le premier article est rempli conformément à la configuration. Le code de zone du deuxième article est vide, car il n’a pas de valeurs par défaut. Ne le modifiez pas.  

    4.  Choisissez l’action **Traiter** pour informer l’entrepôt que le bon de commande sélectionné est prêt pour l’activité entrepôt lorsque la livraison arrive.  

4. Créer **Rangement inventaire** pour recevoir et ranger les articles livrés  

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangements inventaire**, puis sélectionnez le lien associé.  
    2. Sélectionnez l'action **Nouveau**. 
    3. Sélectionnez *ARGENT*, dans le champ **Code d’emplacement**.
    4. Sélectionnez le champ **Document source**, puis sélectionnez **Bon de commande**.  
    5. Sélectionnez le champ **N° source** , sélectionnez la ligne pour l’achat auprès du fournisseur 10000, puis choisissez le bouton **OK** pour remplir les lignes de rangement en fonction du document source sélectionné.

        Sinon, choisissez l'action **Extraire document origine**, puis sélectionnez le bon de commande.  

5. Modifier le rangement inventaire en fonction du placement réel des articles et reporter le document

    Lors du rangement des articles dans les zones, John a remarqué que la zone par défaut contenait déjà certains articles, il a donc décidé d’utiliser une autre zone. John place également d’autres articles dans les zones suivantes, car la quantité reçue ne correspond pas à la capacité.

    1. Dans la première ligne, modifiez le **Code de zone** de *S-1-01*, qui a été copié à partir du bon de commande, vers *S-1-02*. 
    2.  Saisissez 20 dans le champ **Quantité à traiter** de la ligne de rangement inventaire avec l’article WBR-1000.  
    3. Sur la deuxième ligne, saisissez 20 dans le champ **Quantité à traiter** et choisissez l’action **Éclater ligne**. Une nouvelle ligne s'affiche. Il s'agit d'une copie de la ligne d'origine, à la différence près que la quantité que vous avez retirée de la ligne d'origine figure dans le champ **Quantité à traiter**. 
    4. Remplissez les codes de zone pour l’article WBR-1001 :

    |Article ;|Code de zone|Quantité|  
    |----------|-------------------|--------------|  
    |WRB-1001|S-1-03|2.0|  
    |WRB-1001|S-1-04|10|

    5.  Choisissez l'action **Reporter**, sélectionnez l'action **Réceptionner**, puis choisissez le bouton **OK**.  

### <a name="results"></a>Résultats
 - les grains torréfiés sont maintenant enregistrés comme rangés dans les zones spécifiées
 - le **Rangement inventaire reporté** est créé
 - la **Réception achat reportée** est créée
 - le bon de commande a la **Quantité reçue** mise à jour pour les lignes reçues
 - l’**inventaire** d’articles est augmenté de la quantité choisie
    

## <a name="outbound-flow-picking-and-shipping-in-basic-warehouse-configurations"></a>Flux sortant : Prélèvement et expédition dans les configurations de stockage de base

Dans [!INCLUDE[prod_short](../../includes/prod_short.md)], les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.  

|Méthode|Processus entrant|Zones|Prélèvements|Livraisons|Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|X|||2|  
|B|Report du prélèvement et de la livraison à partir d'un document prélèvement inventaire||X||3|  
|C|Report du prélèvement et de la livraison à partir d'un document livraison entrepôt|||X|4/5/6|  
|J|Report du prélèvement à partir d'un document prélèvement entrepôt et report de la livraison à partir d'un document livraison entrepôt||X|X|4/5/6|  

Pour plus d'informations, reportez\-vous à [Détails de conception : flux de désenlogement](../../design-details-outbound-warehouse-flow.md).  

La procédure pas à pas suivante illustre la méthode B dans la table précédente.

### <a name="scenario-1"></a>Scénario
Susan, préparatrice de commandes, crée un document de vente pour divers grains torréfiés et le transmet à l’entrepôt. Jean, le magasinier, doit s'assurer que la livraison est préparée et livrée au client. Jean gère toutes les tâches impliquées sur la page **Prélèvement inventaire**, qui indique automatiquement les endroits où les grains torréfiés sont stockés.

### <a name="steps-1"></a>Étapes
C’est une suite de [Flux entrant : Réception et rangement dans les configurations de stockage de base](#inbound-flow-receiving-and-putting-away-in-basic-warehouse-configurations).

1. Configurez la page **Fiche emplacement** pour définir les flux d’entrepôt entrants de la compagnie.  

    1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 5.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.  
    2.  Ouvrez la fiche emplacement *ARGENT*.  
    3.  Activez la case à cocher **Prélèvement requis**.  

2. Créez le document de vente, qui est le type de document d’origine sortant le plus répandu.  

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 6.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
    2. Sélectionnez l'action **Nouveau**.  
    3. Créez un document de vente pour le client 10000 avec la ligne de document de vente suivante.  

    |Article ;|Code d'emplacement|Quantité|  
    |----|-------------|--------|  
    |WRB-1000|ARGENTE|2.0|  
    |WRB-1001|ARGENTE|30|  

    Les codes de zone sont renseignés automatiquement avec les zones par défaut.

    4. Choisissez l’action **Créer un rangement/prélèvement inventaire**.
    5. Cochez la case **Créer prélèvement inventaire**.  
    6. Choisissez le bouton **OK**. Un nouveau prélèvement inventaire sera créé.

3. Prélever et livrer des articles

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 7.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements inventaire**, puis choisissez le lien associé.  
    2. Sélectionnez le prélèvement inventaire pour les ventes au client 10000
    
    Le prélèvement inventaire créé a ignoré la zone définie pour l’article *WRB-1000*, car elle ne contient pas d’inventaire et a utilisé une autre zone. Les deuxièmes lignes, avec l’article *WRB-1001* ont été automatiquement fractionnées pour être prélevées dans plusieurs zones.
    
4. Choisissez l'action **Remplir automatiquement la quantité à traiter**.  

5. Choisissez l'action **Reporter**, sélectionnez **Livrer**, puis cliquez sur le bouton **OK**.  

### <a name="results-1"></a>Résultats
 - les grains torréfiés sont maintenant enregistrés comme prélevés depuis des zones spécifiées
 - le **Prélèvement inventaire reporté** est créé
 - la **Livraison vente reportée** est créée
 - le document de vente a la **Quantité livrée** mise à jour pour les lignes livrées
 - l’**inventaire** d’articles est réduit de la quantité choisie


## <a name="see-also"></a>Voir aussi
[Articles rangés avec rangements inventaire](../../warehouse-how-to-put-items-away-with-inventory-put-aways.md) 
[Configurer des entrepôts de base avec les zones d’opérations](../../warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md) 
[Détails de conception : flux d’entrepôt entrant](../../design-details-inbound-warehouse-flow.md) 
[Prélever des articles avec des prélèvements d’inventaire](../../warehouse-how-to-pick-items-with-inventory-picks.md) 
[Détails de conception : flux de d’entrepôt sortant](../../design-details-outbound-warehouse-flow.md) 
[Voir la disponibilité des articles](../../inventory-how-availability-overview.md) 
