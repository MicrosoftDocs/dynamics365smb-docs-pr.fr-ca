---
title: Planifier de nouvelles demandes commande par commande
description: 'Cette tâche de planification peut être effectuée sur la page Planification commande, qui affiche toute nouvelle demande ainsi que les informations de disponibilité et les suggestions d’approvisionnement, notamment la substitution d’article.'
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '5522, 5524, 5526'
ms.date: 07/29/2021
ms.author: edupont
---
# <a name="plan-for-new-demand-order-by-order"></a>Planifier de nouvelles demandes commande par commande

Cette tâche de planification peut être effectuée sur la page **Planification commande**, affichant toute nouvelle demande ainsi que les informations de disponibilité et les suggestions d'approvisionnement. Elle fournit la visibilité et les outils nécessaires à la planification efficace des demandes des lignes vente et des lignes composante, puis à la création directe de différents types de commandes approvisionnement.  

Vous pouvez accéder à la page **Planification commande** de deux manières différentes, en fonction de votre objectif : à partir d'une commande que vous souhaitez planifier spécifiquement ou par lots, car vous souhaitez planifier toutes les nouvelles demandes.  


## <a name="to-plan-for-new-production-order-demand"></a>Pour planifier une nouvelle demande de bon de production

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de production planifiés**, puis sélectionnez le lien associé. (Vous pouvez exécuter cette procédure pour des bons de production planifiés, planifiés fermes ou libérés).
2. Ouvrez le bon de production pour lequel vous souhaitez effectuer une planification, puis choisissez l'action **Planification**.  
3. Sur la page **Planification commande**, choisissez l'action **Calculer planification**.  

La page affiche les lignes planification filtrées par la vue de filtre **Demande de production**, c'est-à-dire toutes les lignes composante insatisfaites de tous les bons de production existants. La demande du bon de production n'est pas affichée car il est nécessaire d'effectuer la planification d'un bon de production avec un aperçu de la demande des éventuelles lignes composante précédentes. Les lignes planification du bon de production du contexte sont développées.  

## <a name="to-plan-for-any-new-demand"></a>Pour planifier toute nouvelle demande

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Planification commande**, puis choisissez le lien associé.  
2. Sur la page **Planification commande**, choisissez l'action **Calculer planification**.
3. Choisissez le bouton **Afficher (+)** devant la date dans le champ **Date demande** pour afficher les lignes de planification sous-jacentes qui représentent les lignes de demande dont la disponibilité n'est pas suffisante.  
4. Pour chaque ligne planification développée, c'est-à-dire ligne demande, les valeurs s'affichent dans des champs d'information en bas de la page.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Qté. dans d'autres magasins**|Indique si l'article existe à un autre emplacement. Vous pouvez le rechercher et le sélectionner.|  
    |**Article de substitution**|Affiche si un article de substitution est créé pour l'article. Vous pouvez le rechercher et le sélectionner. Cette fonction s'applique uniquement aux composants, c'est-à-dire aux lignes demande de type **Production**.|  
    |**Quantité disponible**|Affiche la disponibilité globale de l'article, c'est-à-dire le stock prévisionnel.|  
    |**Date disponibilité au plus tôt**|Indique la date d'arrivée d'une commande approvisionnement entrante pouvant couvrir la quantité nécessaire à une date ultérieure par rapport à la date de la demande.|  

5. Dans le champ **Système réappro.**, sélectionnez le type de commande approvisionnement à créer.  

    La valeur par défaut est celle indiquée sur la fiche article, ou fiche unité de stock, mais vous pouvez la modifier et lui attribuer l'une des trois options suivantes :  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Achat**|Crée un bon de commande.|  
    |**Virement**|Crée un ordre de transfert.|  
    |**Ordre de fabrication**|Crée un bon de production.|  

    Dans le champ **Origine approvisionnement**, vous devez sélectionner une valeur en fonction du système de réapprovisionnement sélectionné.  

    > [!NOTE]  
    >  Si le champ est vide, le système affichera un message d'erreur lorsque vous utiliserez la fonction **Créer des commandes approvisionnement** et aucune commande approvisionnement ne sera créée pour la ligne planning en question. Cependant, ce n'est pas le cas si le système de réapprovisionnement est **O.F.**  

6. Dans le champ **Origine approvisionnement**, vous pouvez rechercher dans la liste appropriée et sélectionner l'origine de l'approvisionnement :  

    - Si le système de réapprovisionnement est **Achat**, le bouton de recherche du champ utilise la page **Catalogue fournisseur articles**.  
    - Si le système de réapprovisionnement est **Transfert**, le bouton de recherche du champ utilise la page **Liste des emplacements**.  

    Dans le cas où l'article existe dans un autre magasin, le champ **Quantité - Autres magasins** situé au bas de la fenêtre indique une valeur et vous pouvez rechercher et sélectionner le magasin à partir duquel l'article doit être approvisionné durant l'ordre de transfert.  

    Si un article de substitution existe pour l'article demandé, le champ **Article de substitution** est défini sur **Oui**, et vous pouvez accéder à la page **Écritures art. substitution** et sélectionner l'article de substitution.  

    > [!NOTE]  
    > Sachez que les substitutions d'articles n’entraîneront pas automatiquement le remplacement d’un article par un autre, par exemple lors de la création d’un document de vente ou dans une nomenclature. Au lieu de cela, vous serez alerté du fait qu’un substitut est disponible pour vous.

7. Cochez la case **Réserver** si vous voulez créer une réservation entre la commande approvisionnement que vous créez et la ligne demande pour laquelle cette commande est créée. Par défaut, ce champ est vide.  

    > [!NOTE]  
    >  Vous ne pouvez activer cette case que si l'article possède le champ **Manuel** ou **Toujours** dans le champ **Réserver** de la fiche article de l'article concerné.  

8. Dans le champ **Quantité à commander**, vous pouvez entrer la quantité qui sera affichée sur la commande approvisionnement que vous créez.   
    La valeur par défaut est la même quantité que celle du champ **Quantité nécessaire**. Mais vous pouvez décider de commander une quantité supérieure ou inférieure en fonction de la situation de la demande. Si, par exemple, vous voyez sur la page **Planification commande** que plusieurs lignes de demandes non liées sont destinées au même article acheté, et que leur date d'échéance tombe plus ou moins en même temps, vous pouvez les consolider en entrant la quantité totale nécessaire dans le champ **Quantité à commander** d'une ligne et supprimer les autres lignes de planification obsolètes de cet article.  

9. Dans les champs **Date échéance** et **Date commande**, vous pouvez entrer les dates devant être appliquées aux commandes approvisionnement créées.  

    Ces deux champs sont étroitement liés, comme l'indique le champ **Délai de sécurité par défaut**, qui se trouve sur la page **Configuration de la fabrication**. Par défaut, la date d'échéance correspond à la date demande, mais vous pouvez la modifier à votre convenance.  

> [!NOTE]  
>  Si vous entrez une date ultérieure à la date demande, un message vous l'indique.  

## <a name="to-make-supply-orders"></a>Pour créer des commandes approvisionnement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de production planifiés**, puis sélectionnez le lien associé. Vous pouvez exécuter cette procédure pour un bon de production planifié, planifié ferme ou libéré.  
2. Ouvrez le bon de production pour lequel vous souhaitez effectuer une planification, puis choisissez l'action **Planification**.  
3. Positionnez le curseur sur la ligne planification souhaitée, puis choisissez l'action **Créer commandes**.  
4. Sur la page **Créer des commandes d'approvisionnement**, sur le raccourci **Planification commande**, dans le champ **Créer commandes pour**, sélectionnez l'une des options suivantes.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**La ligne active**|Créez une commande approvisionnement uniquement pour la ligne sur laquelle pointe le curseur.|  
    |**La commande active**|Créez des commandes approvisionnement pour toutes les lignes sur lesquelles pointe le curseur.|  
    |**Toutes les lignes**|Créez des commandes d'approvisionnement pour toutes les lignes de la page **Planification commande**.|  

5. Sur le raccourci **Options**, définissez le type de commandes approvisionnement ou de lignes demande achat à créer.  

    > [!NOTE]  
    >  Les derniers paramètres que vous avez entrés sur la page **Créer des commandes d'approvisionnement** seront enregistrés avec votre code utilisateur afin de les conserver lors de vos prochaines utilisations de la page.  

6. Choisissez le bouton **OK** pour créer les commandes approvisionnement ou les lignes demande achat proposées.  

Vous venez d'effectuer les planifications nécessaires pour les demandes insatisfaites en créant les commandes approvisionnement correspondantes. Les processus particuliers liés à l'utilisation de la page **Planification commande** dépendent de l'organisation interne de chaque compagnie.  

Une fois que la planification est terminée sur la page **Planification commande** et que vous avez défini, par exemple, un autre moyen de fournir la quantité nécessaire, vous pouvez créer les commandes d'approvisionnement d'une ou de plusieurs lignes planification.  

> [!NOTE]  
> Les commandes approvisionnement que vous créez peuvent introduire une demande dépendante, par exemple, pour les ordres de fabrication sous-jacents ; vous devez donc choisir à nouveau **Calculer planning** pour rechercher et résoudre ceci avant de poursuivre la liste.  

## <a name="see-also"></a>Voir aussi

<!-- [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   -->
[Planification](production-planning.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
