---
title: Supprimer et affecter à nouveau des écritures article
description: Vous pouvez visualiser et modifier manuellement certaines écritures d'affectation article qui sont créées automatiquement lors des transactions d'inventaire.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: '506, 521, 9125'
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="remove-and-reapply-item-ledger-entries"></a>Supprimer et affecter à nouveau des écritures article
Sur la page **Feuille affectation**, vous pouvez visualiser et modifier manuellement certaines écritures affectation article qui sont créées automatiquement lors des transactions d'inventaire.  

Lorsque vous reportez une transaction dans laquelle des articles entrent ou sortent de l'inventaire, une affectation article est créée entre chaque augmentation et diminution d'inventaire. Ces affectations déterminent le flux des coûts des marchandises entrant dans l'inventaire vers les coûts des marchandises sortant de l'inventaire. En raison du mode de calcul du coût unitaire, une affectation article incorrecte peut engendrer une erreur au niveau du coût moyen ou du coût unitaire. Pour plus d'informations, voir Détails de conception : traçabilité.

Vous pouvez être amené à annuler une affectation ou à affecter à nouveau des écritures article dans les scénarios suivants :

- Vous avez oublié d'effectuer une affectation fixe.
- Vous avez effectué une affectation fixe incorrecte.
- Vous devez retourner un article sur lequel une vente a déjà été affectée.

Si possible, utilisez un document pour affecter à nouveau une écriture article. Par exemple, si vous devez procéder à un retour achat d'un article auquel une vente a déjà été affectée, vous pouvez procéder à une nouvelle affectation en créant et en reportant le document de retour achat à l'aide de l'affectation correcte dans le champ **Écr. article à affecter** dans la ligne retour achat. Vous pouvez utiliser la fonction **Affichage de lignes document reportées à inverser** ou **Copier à partir du document** dans le document de retour achat pour faciliter cette opération. Lorsque vous reportez le document, l'écriture article est automatiquement affectée à nouveau. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md).

Si vous ne pouvez pas utiliser un document pour une nouvelle affectation, par exemple si vous devez corriger une affectation fixe, utilisez la page **Feuille affectation** pour corriger une affectation.

> [!Warning]  
> Il est important de tenir compte des considérations suivantes lorsque vous travaillez sur la feuille de travail affectation :
    - Vous ne devez pas laisser des écritures affectation non affectées pendant de longues périodes, car d’autres utilisateurs ne peuvent pas traiter les articles tant que vous n’affectez pas à nouveau les écritures affectation ou que vous ne fermez pas la page **Feuille affectation**. Les utilisateurs qui essaient d'exécuter des actions qui impliquent une écriture affectation dont l'affectation a été annulée manuellement reçoivent le message d'erreur suivant : « Il est impossible d'effectuer cette opération car l'affectation des écritures pour l'article XXX est annulée dans la feuille de travail affectation par l'utilisateur XXX. »
    - Vous devez affecter à nouveau uniquement les écritures article en dehors des heures de travail afin d'éviter les conflits avec d'autres utilisateurs qui reportent des transactions portant sur les mêmes articles.
    - Lorsque vous fermez la feuille de travail affectation, [!INCLUDE[prod_short](includes/prod_short.md)] effectue un contrôle pour s'assurer que toutes les écritures sont affectées. Par exemple, si vous supprimez une affectation quantité sans créer une nouvelle affectation et si vous fermez ensuite la feuille de travail affectation, une nouvelle affectation est créée. Cela permet de ne pas toucher au coût. Cependant, si vous supprimez une affectation fixe, une nouvelle affectation fixe n'est pas créée automatiquement lorsque vous fermez la feuille de travail. Vous devez le faire manuellement en créant une nouvelle affectation dans la feuille de travail.
    - Vous pouvez supprimer des affectations à partir de plusieurs écritures en même temps dans la feuille de travail affectation. Toutefois, comme l'affectation d'écritures affecte l'ensemble des écritures qui sont disponibles pour l'affectation, vous ne pouvez pas créer une affectation pour plusieurs écritures à la fois.
    - La feuille de travail affectation ne peut pas effectuer une affectation dans le cas suivant : si la quantité en stock est insuffisante pour l'affectation, la feuille de travail affectation ne peut pas effectuer une affectation lorsque vous tentez d'affecter une écriture diminution d'inventaire sans informations de traçabilité sur une écriture augmentation d'inventaire avec informations de traçabilité.

## <a name="to-remove-an-item-application-by-using-the-application-worksheet"></a>Pour supprimer une affectation article en utilisant le journal affectation

1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille affectation**, puis sélectionnez le lien associé.  
2.  La page **Feuille affectation** s'ouvre en affichant les écritures article existantes de tous les articles.  
3.  Définissez les filtres du raccourci **Général** pour faciliter la recherche de l'écriture comptable article pour laquelle vous souhaitez modifier le lettrage.  
4.  Sélectionnez l'écriture article, puis sélectionnez l'action **Écritures affectées**. La page **Voir écritures affectées - Écritures affectées** s'ouvre et affiche la ou les écritures article actuellement affectées pour l'écriture sélectionnée.  
5.  Sélectionnez l'écriture article dont vous souhaitez supprimer l'affectation.  
6.  Sélectionnez l'action **Supprimer affectation**. Cette action supprime l'écriture affectation article qui lie les deux écritures article et la déplace vers la page **Afficher les écritures affectées - Écritures dont l'affectation a été annulée**.  
7.  Fermez la page **Afficher les écritures affectées – Écritures affectées**.  

 Le champ **Quantité restante** des deux écritures comptables article sont augmentés de la quantité délettrée. L'écriture article supprimée peut à présent être à nouveau affectée sur la page **Afficher les écritures affectées – Écritures non affectées**.  

> [!IMPORTANT]  
>  Vous ne devez pas laisser des écritures affectation non affectées pendant de longues périodes, car d’autres utilisateurs ne peuvent pas traiter les articles concernés tant que vous n’affectez pas à nouveau les écritures affectation ou que vous ne fermez pas la page **Feuille affectation**. Le message d'erreur suivant s'affiche si vous essayez d'exécuter des tâches qui concernent une écriture d'affectation dont l'affectation a été supprimée manuellement :  
>   
>  **Il est impossible d'effectuer cette action car l'affectation des écritures pour l'article \<item\> est annulée dans la feuille de travail affectation par l'utilisateur \<user\>.**  

## <a name="to-reapply-an-item-application-by-using-the-application-worksheet"></a>Pour affecter à nouveau une affectation article en utilisant le journal affectation

1.  Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille affectation**, puis sélectionnez le lien associé.  
2.  La page **Feuille affectation** s'ouvre en affichant les écritures article existantes de tous les articles.  
3.  Pour affecter à nouveau des écritures supprimées depuis l'ouverture de la feuille, sélectionnez l'écriture article que vous souhaitez affecter à nouveau et choisissez l'action **Affecter à nouveau**.  

    > [!NOTE]  
    >  Cette nouvelle affectation vers le solde de départ se produit aussi automatiquement lorsque vous fermez la page **Feuille affectation**.  
4.  Pour affecter une écriture du grand livre d'articles en cours disponible dans une autre écriture, sélectionnez l'écriture article à affecter. Sélectionnez l'action **Écritures non lettrées**. La page **Afficher les écritures affectées – Écritures non affectées** s'ouvre.  
5.  Sélectionnez une ou plusieurs écritures article que vous voulez affecter à l'écriture sélectionnée sur la page **Feuille affectation**, puis choisissez le bouton **OK**.  

     Une écriture d'affectation article est créée entre les deux écritures article. Les champs **Quantité restante** des deux écritures sont réduits de la quantité lettrée.  

    > [!NOTE]  
    >  Si vous avez choisi d'effectuer une affectation qui créerait une boucle infinie dans le processus d'ajustement des coûts, l'affectation que vous avez proposée n'est pas appliquée. Cela peut se produire lorsque les écritures originales ont créé un stock négatif. L'affectation n'est pas effectuée. Par conséquent, vous devez sélectionner une autre écriture pour l'affectation.  
6.  Si, dans les **Paramètres stock**, le champ **Ajustement automatique des coûts** est défini sur **Toujours**, le traitement par lots d'ajustement des coûts est exécuté automatiquement après que vous avez effectué un relettrage. Sinon, exécutez le traitement en lot **Ajuster coûts - Écr. article** pour être sûr que tous les coûts sont actualisés.  

## <a name="see-also"></a>Voir aussi

[Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)  
 [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md)  
 [Gestion des coûts inventaire](finance-manage-inventory-costs.md)   
 [Détails de conception : Affectation article](design-details-item-application.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
