---
title: Traitement des opportunités de vente dans les cycles de vente
description: Cette rubrique décrit les différentes manières dont vous pouvez traiter les opportunités de vente dans les cycles de vente et déplacer une opportunité à travers les phases d’un cycle de vente.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.search.keywords: 'relationship, prospect'
ms.date: 12/28/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="process-sales-opportunities"></a>Traiter des opportunités de vente

Une fois que vous avez créé une opportunité, il existe plusieurs fonctionnalités permettant de gérer l'opportunité et de la faire avancer jusqu'à l'achèvement.

## <a name="view-opportunities"></a>Afficher les opportunités

Les opportunités de vente existantes sont disponibles sur la page **Liste des opportunités**. Le tableau suivant décrit les manières d’accéder à la page pour traiter les opportunités de vente.

| Pour afficher les opportunités pour | Alors |
| --- | --- |
| Tous les représentants et contacts |Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Liste des opportunités**, puis choisissez le lien associé. |
| Un vendeur spécifique |Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Représentants**, puis sélectionnez le lien associé. Sélectionnez le vendeur, sélectionnez l'action **Opportunités**, puis l'action **Liste**. |
| Un contact spécifique |Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Contacts**, puis sélectionnez le lien associé. Sélectionnez le contact dans la liste, puis sélectionnez l'action **Opportunités**. |

Chacune de ces tâches ouvre la page **Liste des opportunités**.

## <a name="close-opportunities"></a>Fermer les opportunités

Vous pouvez fermer des opportunités lorsque les négociations sont terminées. Quand vous fermez une opportunité, vous pouvez spécifier si elle a réussi ou échoué, et préciser les motifs de la fermeture. Pour spécifier un motif, vous devez configurer des codes opportunité fermée.

1. Sur la page **Liste des opportunités**, sélectionnez l'opportunité, puis sélectionner l'action **Fermer**. La page **Fermer opportunité** s'affiche.
2. Renseignez les champs appropriés, puis cliquez sur le bouton **OK**.

   Les champs **Code fin opportunité** et **Date clôture** sont obligatoires. Vous devez les renseigner avant de cliquer sur le bouton **OK**.

   Dans le champ **Code fin opportunité**, vous pouvez choisir l'un des codes fin opportunité existants ou en ajouter un nouveau. Pour ajouter un nouveau code, dans la liste déroulante, sélectionnez **Sélectionner dans la liste complète**, puis sélectionnez **Nouveau**. Dans la nouvelle ligne vierge, renseignez les champs **Code**, **Type** et **Description**, puis cliquez le bouton **OK**.

## <a name="create-quotes-for-opportunities"></a>Créer des devis pour les opportunités

> [!NOTE]
> Vous ne pouvez créer des devis de vente qu′à partir d′opportunités dont le type de contact est Compagnie.

1. Sur la page **Liste des opportunités**, sélectionnez l'opportunité, puis sélectionner l'action **Créer devis**. La page **Devis** s'affiche.
2. Renseignez les champs de votre choix.

## <a name="create-sales-orders-for-opportunities"></a>Créer des documents de vente pour les opportunités

Vous pouvez effectuer des commandes vente à partir des devis que vous avez créés pour vos opportunités. Pour pouvoir créer des commandes vente pour vos contacts, vous devez créer le contact en tant que client. Pour plus d'informations, reportez-vous à [Créer des contacts](marketing-create-contact-companies.md).

1. Sur la page **Liste des opportunités**, recherchez l'opportunité pour laquelle vous avez créée un devis vente.
2. Sélectionnez l'option **Créer devis**. La page **Devis** s'ouvre et affiche le devis que vous avez affecté à l'opportunité.
3. Renseignez les autres champs, puis sélectionnez l'action **Créer commande**.

Lorsque vous traitez des opportunités de vente, vous pouvez être amené à créer un devis pour le contact auquel est liée l'opportunité.

## <a name="delete-opportunities"></a>Supprimer opportunités

Vous pouvez supprimer des opportunités, par exemple après avoir conclu un marché. Toutefois, vous pouvez uniquement supprimer des opportunités fermées. Il existe deux méthodes permettant de supprimer des opportunités fermées. Vous pouvez supprimer des opportunités fermées une par une à partir de la page **Liste des opportunités**, ou vous pouvez exécuter le traitement en lot **Supprimer les opportunités** afin de supprimer plusieurs opportunités sur la base de critères spécifiés.

Pour supprimer des opportunités fermées à partir de la page **Liste des opportunités**, sélectionnez l'opportunité, puis sélectionnez l'action **Supprimer**.

Pour supprimer des opportunités fermées à l’aide du traitement par lots **Supprimer les opportunités**, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") l’icône, saisissez **Administration des données**, puis choisissez le lien associé.
2. Choisissez l’action **Supprimer l’opportunité**, configurez les filtres qui spécifient les opportunités fermées à supprimer.
3. Cliquez sur le bouton **OK**.

Une fois que supprimez une opportunité, elle ne s’affiche plus sur la page **Liste des opportunités**.

## <a name="move-an-opportunity-through-sales-cycle-stages"></a>Faire avancer une opportunité au fil des phases du cycle de vente

Si une opportunité suit un cycle de vente, vous pouvez la faire passer à la phase suivante ou précédente, et même ignorer une phase.

1. Sur la page **Liste des opportunités**, sélectionnez l'action **Mettre à jour**. La fenêtre **Mise à jour opportunité** s'affiche.
2. Utilisez le champ **Type action** pour faire avancer l'opportunité au fil des étapes du cycle de vente :
   * **Suivant** fait avancer l'opportunité d'une étape.
   * **Ignorer** fait avancer l'opportunité d'une ou de plusieurs étapes dans le cycle de vente, que vous spécifiez dans le champ **Présentation**. Vous pouvez uniquement ignorer les étapes qui ont été configurées de sorte à l'autoriser.
   * **Précédent** fait reculer l'opportunité d'une étape.
   * **Omettre** fait reculer l'opportunité d'une ou de plusieurs étapes dans le cycle de vente, que vous spécifiez dans le champ **Présentation**.
   * **Mettre à jour** vous permet de modifier les informations (par exemple pour modifier votre évaluation de leurs chances de succès et valeurs estimées) sans passer à une autre étape.
3. Renseignez autres champs selon vos besoins, puis cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi .

[Ventes](sales-manage-sales.md)  
[Création et gestion des contacts](marketing-contacts.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
