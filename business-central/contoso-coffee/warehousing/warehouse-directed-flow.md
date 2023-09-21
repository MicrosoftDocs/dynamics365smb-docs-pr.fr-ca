---
title: 'Réception, rangement, déplacement, prélèvement et expédition dans une configuration d’entrepôt avancée avec prélèvement et rangement dirigés'
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

# Procédure pas à pas sur les flux entrants ou sortants dans les configurations entrepôt avancées avec prélèvement et rangement suggérés

Cette procédure pas à pas montre comment effectuer des flux entrants et sortants dans la configuration avancée : Prélèvement et rangement dirigés. Pour plus d’informations, voir [Présentation des différentes options de configuration](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## Conditions préalables  
Pour exécuter cette procédure, vous devez faire de vous un employé d’entrepôt sur le site *BLANC* en procédant comme suit :  
1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2. Choisissez le champ **Code utilisateur** et sélectionnez votre propre compte utilisateur sur la page **Utilisateurs**.  
3. Dans le champ **Code d'emplacement**, entrez BLANC.  
4. Activez le bouton à bascule **Par défaut**.


## Scénario  
Ellen, la responsable de l’entrepôt, utilise la fonctionnalité de transbordement et de réapprovisionnement des zones pour accélérer les délais de réception et d’expédition.  

## Étapes

1. Créez une livraison entrepôt.  

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
    2. Sélectionnez la commande du client 10000 pour l’emplacement BLANC. Le numéro de commande externe est *W-1*. Utilisez les outils de personnalisation si le **N° de commande externe** n’est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](../../ui-personalization-user.md).
    3. Choisissez l’action **Créer livraison entrepôt** pour créer une livraison entrepôt pour le document de vente sélectionné.
    4.  Choisissez l’action **Libérer** pour informer l’entrepôt que la livraison client est prête pour l’activité entrepôt.  

2. Définir des zones pour l’article pour contrôler l’endroit où il est rangé 

    1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
    2.  Sélectionnez *WRB-1000*, puis sélectionnez l’action **Contenus zone**.  
    3.  Sélectionnez l'action **Nouveau**. Ajoutez deux lignes. Utilisez les outils de personnalisation si le champ **Code de zone** n’est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](../../ui-personalization-user.md). 
    
    |Article ;|Code d'emplacement|Code de zone|Statique|Unité de mesure|
    |----------|----------|---------|---|------|  
    |WRB-1000|BLANC|W-05-0001|Oui|SAC|  
    |WRB-1000|BLANC|W-05-0002|Oui|SAC|

3. Créez une réception entrepôt.  

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.  
    2. Sélectionnez la commande du fournisseur 10000 pour l’emplacement BLANC. Le numéro de commande fournisseur est *W-2*. Utilisez les outils de personnalisation si le **N° de commande fournisseur** n’est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](../../ui-personalization-user.md).
    3. Choisissez l’action **Créer réception entrepôt** pour créer une réception entrepôt pour le bon de commande sélectionné.


4. Vérifier si des commandes sortantes nécessitent des articles reçus et reporter la réception
    1. Choisissez l'action **Calculer transbordement**. Cela remplit une colonne **Quantité à transborder**.
    2. Entrez 0 dans le champ **Quantité à transborder** dans la ligne avec l’article *WRB-1000*, car vous ne prévoyez pas de remballer dans la zone de réception.
    3. Sélectionnez l’action **Reporter la réception**.

5. Enregistrer le rangement entrepôt
    1. Utiliser l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 5.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangement entrepôt**, puis sélectionnez le lien associé.
    2. Localiser le document de rangement entrepôt créé à partir de votre reçu d’entrepôt et l’ouvrir
    3. Sur la page **Rangement entrepôt**, consulter la section **Lignes**

    Dans cette phase, la logique de capacité de la zone est révélée. les lignes de rangement entrepôt ont trois lignes pour l’article *WRB-1000* :
    - Une ligne de prélèvement pour déplacer les quantités reçues depuis la zone de réception (W-08-0001)
    - Une ligne de placement qui déplace un SAC dans l’une des zones fixes configurées (W-05-0001)
    - Une ligne de placement qui déplace un autre SAC dans un autre emplacement fixe (W-05-0002). En effet, une zone fixe unique ne peut pas contenir la quantité totale de réception.

    Puisque ce rangement contient des lignes de transbordement, vous voyez trois lignes pour l’article *WRB-1001* :
    -  Une ligne de prélèvement pour déplacer les quantités reçues depuis la zone de réception (W-08-0001)
    -  Une ligne de placement pour les 2 dans la zone de transbordement
    -  Une ligne de placement pour la quantité restante dans la zone de stockage

    4. Choisissez l’action **Enregistrer rangement**.


6. Définir des zones de prélèvement pour l’article pour contrôler l’endroit où il est prélevé 

    1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 6.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.  
    2.  Ouvrez la fiche emplacement *BLANC*.  
    3.  Choisissez l’action **Zones** dans la **Fiche emplacement**
    4.  Sélectionnez la zone *W-02-0001*, puis sélectionnez l’action **Contenus**.  
    5.  Sélectionnez l'action **Nouveau**.  
    6.  Activez le bouton à bascule **Fixe**.  
    7.  Dans le champ **N° article**, saisissez *WRB-1000*. 
    8.  Dans le champ **Quantité min.**, saisissez *2*. 
    9.  Dans le champ **Quantité max.**, saisissez *10*. 

    Utilisez les outils de personnalisation si les champs **Quantité min.** et **Quantité max.** ne sont pas visibles. Pour plus d'informations, voir [Personnaliser votre espace de travail](../../ui-personalization-user.md). 

7. Réorganisez l’entrepôt en déplaçant les articles de la zone de stockage en vrac vers la zone de prélèvement, afin d’optimiser le temps de prélèvement.

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 7.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuilles mouvement**, puis choisissez le lien associé
    2. Choisissez l'action **Calculer réappro. zone**. 

    La feuille de calcul de l’entrepôt avec la proposition de déplacement de l’article *WRB-1000* du stockage en vrac vers la zone de prélèvement est créée.

    3. Choisissez l’action **Créer mouvement** et confirmez pour créer le document.
    4.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 8.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Mouvements entrepôt**, puis sélectionnez le lien associé
    5.  Ouvrez le mouvement d’entrepôt que vous avez créé, passez en revue la section **Lignes**

     Dans cette phase, la fonctionnalité Déconditionnement s’affiche. Il y a quatre lignes :
    - Une ligne pour sortir un SAC de la zone de stockage en vrac
    - Une ligne pour remettre les 48 pièces en stock dans la même zone. 
    - Une ligne pour sortir 10 pièces de la zone de stockage en vrac
    - Une ligne pour placer les 10 pièces dans la zone de prélèvement

    6.  Sélectionnez l’action **Enregistrer mouvement**.

8. Créer prélèvements entrepôt

    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 9.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuilles prélèvement**, puis choisissez le lien associé
    2. Choisissez l’action **Obtenir les documents d’entrepôt** , sélectionnez la ligne du document de vente pour le client 10000, puis choisissez le bouton **OK** pour remplir les lignes de la feuille de calcul en fonction du document sélectionné.

    3. Inspectez le champ **Quantité à la zone de transbordement**. 

    4. Choisissez l'action **Créer prélèvement**.
    5. Confirmez tous les paramètres de prélèvement nécessaires, par exemple, activez le bouton à bascule **Par zone de départ**. Choisissez le bouton **OK**.
    
    Vous recevrez un message de confirmation avec les numéros de prélèvement. Il y a deux prélèvements, car certains articles sont situés dans la zone de transbordement, à proximité de la zone d’expédition, et il serait logique de les traiter séparément.

9.  Enregistrer les prélèvements d’entrepôt
    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 10.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements entrepôt**, puis choisissez le lien associé.
    2. Localisez les prélèvements que vous avez créés et ouvrez-les.
    3. Choisissez l'action **Enregistrer prélèvement**.
    4. Répétez l’opération pour le deuxième prélèvement

10. Reporter la livraison entrepôt
    
    1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 11.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraison entrepôt**, puis choisissez le lien associé.
    2. Sur la page Rangement entrepôt, consulter la section **Lignes**. Une fois le prélèvement d’entrepôt enregistré, la livraison d’entrepôt est mise à jour avec le champ **Quantité à livrer** renseigné.
    3. Sélectionnez ensuite l’action **Reporter livraison**.
    4. Confirmez l’option **Livrer**.


## Résultats
- la **Réception entrepôt reportée** est créée
- le **Rangement entrepôt enreg.** est créé    
- la **Réception achat reportée** est créée    
- le **Bon de commande** a la **Quantité reçue** mise à jour pour les lignes reçues
- le **Mouvement entrepôt enreg.** est créé
- le **Prélèvement entrepôt enreg.** est créé
- la **Livraison entrepôt reportée** est créée
- la **Livraison vente reportée** est créée
- le **Document de vente** a la **Quantité livrée** mise à jour pour les lignes livrées
- l’**inventaire** d’articles est augmenté de tout reliquat non livré



## Voir aussi
[Recevoir des articles](../../warehouse-how-receive-items.md) 
[Détails de conception : Flux d’entrepôt entrant](../../design-details-inbound-warehouse-flow.md) 
[Livrer les articles](../../warehouse-how-ship-items.md) 
[Prélever les articles pour livraison entrepôt](../../warehouse-how-to-pick-items-for-warehouse-shipment.md) 
[Détails de conception : Flux d’entrepôt sortant](../../design-details-outbound-warehouse-flow.md) 
[Afficher la disponibilité des articles](../../inventory-how-availability-overview.md) 
