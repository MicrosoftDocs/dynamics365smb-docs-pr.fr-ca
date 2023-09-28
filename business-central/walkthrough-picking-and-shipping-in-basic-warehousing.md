---
title: Prélèvement et expédition dans les configurations d’entrepôt de base
description: Cet article décrit différents niveaux de complexité dans les processus de prélèvement et d’expédition.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.form: '7335, 7337, 7339, 7340, 7341, 7362, 9008'
---
# <a name="walkthrough-picking-and-shipping-in-basic-warehouse-configurations"></a>Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous prélevez et livrez des articles en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus sortant|Prélèvement requis|Livraison requise|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report du prélèvement et de la livraison à partir d’un document prélèvement inventaire|Activé||De base : commande par commande.|  
|C|Report du prélèvement et de la livraison à partir d’un document livraison entrepôt||Activé|De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report du prélèvement à partir d’un document prélèvement entrepôt, et report de la livraison à partir d’un document livraison entrepôt|Activé|Activé|Avancé|  

Learn more at [Flux de désenlogement](design-details-outbound-warehouse-flow.md).

La procédure pas à pas suivante illustre la méthode B dans la table précédente.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas

Pour les configurations d'entrepôt de base, lorsqu'un emplacement est défini pour exiger un traitement des prélèvements mais pas un traitement des livraisons, vous utilisez la page **Prélèvement inventaire** pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents origine sortants. Le document origine sortant peut être un document de vente, un retour achat, un transfert sortant ou un bon de production avec un besoin de composantes.  

Cette procédure pas à pas présente les tâches suivantes :  

- Configuration de l'emplacement SUD pour les prélèvements inventaire.  
- Créez un document de vente pour le client 10000 pour 30 lampes Amsterdam.  
- Libération du document de vente pour la gestion entrepôt.  
- Créez un prélèvement inventaire sur la base d'un document origine libéré.  
- Enregistrement d'un mouvement entrepôt à partir de l'entrepôt et report simultané de la livraison vente pour le document de vente d'origine.  

## <a name="roles"></a>Rôles

Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

- Gestionnaire d'entrepôt  
- Préparateur de commandes  
- Magasinier  

<!-- ## Prerequisites

To complete this walkthrough, you will need:  

- For [!INCLUDE[prod_short](includes/prod_short.md)] online, a company based on the **Advanced Evaluation - Complete Sample Data** option in a sandbox environment. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, CRONUS installed.
 -->

## <a name="story"></a>Scénario

Ellen, la gestionnaire d’entrepôt de CRONUS, configure l’entrepôt SUD pour le prélèvement de base dans lequel les magasiniers traitent les commandes sortantes individuellement. Susan, préparatrice de commandes, crée un document de vente pour 30 unités de l’article 1928-S à livrer au client 10000 depuis l’entrepôt SUD. Jean, le magasinier, doit s'assurer que la livraison est préparée et livrée au client. Jean gère toutes les tâches impliquées sur la page **Prélèvement inventaire**, qui indique automatiquement les zones où 1928-S est stocké.

[!INCLUDE[set_up_location.md](includes/set_up_location.md)]

### <a name="setting-up-the-bin-codes"></a>Configuration des codes de zone

Une fois que vous avez configuré l'emplacement, vous devez ajouter deux zones.

#### <a name="to-setup-the-bin-codes"></a>Pour configurer les codes de zone

1. Sélectionnez l’action **Zones**.
2. Créez deux zones, avec les codes *S-01-0001* et *S-01-0002*.

### <a name="making-yourself-a-warehouse-employee-at-location-south"></a>Se définir comme employé d'entrepôt à l'emplacement SUD

Pour utiliser cette fonctionnalité, vous devez vous ajouter à l'emplacement en tant qu'employé d'entrepôt. 

#### <a name="to-make-yourself-a-warehouse-employee"></a>Pour vous définir comme employé d'entrepôt

  1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me pour la première fois.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
  2. Choisissez le champ **Code utilisateur** et sélectionnez votre propre compte utilisateur sur la page **Employés d'entrepôt**.
  3. Dans le champ **Code d'emplacement**, choisissez SUD.  
  4. Sélectionnez le champ **Par défaut**, puis cliquez sur le bouton **Oui**.  

### <a name="making-item-1928-s-available"></a>Rendre l’article 1928-S disponible

Pour rendre l’article 1928-S disponible dans l'emplacement SUD, suivez cette procédure :  

  1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me pour la deuxième fois.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article**, puis choisissez le lien associé.  
  2. Ouvrez le journal par défaut, puis créez deux lignes journal article avec les informations de date de travail suivantes (23 janvier).  

        |Type écriture|Numéro d'article|Code d'emplacement|Code de zone|Quantité|  
        |----------------|-----------------|-------------------|--------------|--------------|  
        |Positif (ajust.)|1928-S|SUD|S-01-0001|20|  
        |Positif (ajust.)|1928-S|SUD|S-01-0002|20|  

        Par défaut, le champ **Code de zone** des lignes vente est masqué, vous devez donc l’afficher. Pour cela, vous devez personnaliser la page. Pour plus d’informations, consultez [Commencer à personnaliser une page au moyen de la bannière Personnalisation](ui-personalization-user.md#to-start-personalizing-a-page-through-the-personalizing-banner).

  3. Choisissez **Actions**, puis **Report**, puis **Reporter**.  
  4. Sélectionnez le bouton **Oui**.  

## <a name="creating-the-sales-order"></a>Création du document de vente

Les commandes vente sont le type de document d'origine sortant le plus répandu.  

### <a name="to-create-the-sales-order"></a>Pour créer le document de vente

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me pour la troisième fois.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Créez une document de vente pour le client 10000 à la date de travail (23 janvier) comportant la ligne document de vente suivante.  

    |Article ;|Code d'emplacement|Quantité|  
    |----|-------------|--------|  
    |1928-S|SUD|30|  

     Informez l'entrepôt que le document de vente est prêt pour la gestion entrepôt.  

4. Sélectionnez l'action **Lancer**.  

    Jean procède au prélèvement et à la livraison des articles vendus.  

## <a name="picking-and-shipping-items"></a>Prélèvement et livraison d'articles

Sur la page **Prélèvement inventaire**, vous pouvez gérer toutes les activités entrepôt sortantes pour un document d'origine spécifique, tel qu'un document de vente. [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

### <a name="to-pick-and-ship-items"></a>Pour prélever et livrer des articles

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me pour la quatrième fois.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements inventaire**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  

    Assurez-vous que le champ **N°** du raccourci **Général** est rempli.
3. Sélectionnez le champ **Document origine**, puis sélectionnez **Commande vente**.  
4. Sélectionnez le champ **N° origine**, sélectionnez la ligne correspondant à la vente au client 10000, puis cliquez sur le bouton **OK**.  

    Sinon, choisissez l'action **Extraire document origine**, puis sélectionnez le document de vente.  
5. Choisissez l'action **Remplir automatiquement la quantité à traiter**.  

    Sinon, dans le champ **Qté à traiter**, saisissez respectivement 10 et 20 sur les deux lignes prélèvement stock.  
6. Choisissez l'action **Reporter**, sélectionnez **Livrer**, puis cliquez sur le bouton **OK**.  

    Les 30 lampes Amsterdam sont à présent enregistrées comme prélevées depuis les zones S-01-0001 et S-01-0002, et une écriture article négative est créée pour refléter la livraison vente reportée.  

## <a name="see-also"></a>Voir aussi .

[Prélever des articles avec les prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md)  
[Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md)  
[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Prélever pour la fabrication et l'assemblage](warehouse-how-to-pick-for-production.md)  
[Déplacer des articles ad hoc dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[Détails de conception : flux de désenlogement](design-details-outbound-warehouse-flow.md)  
[Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
