---
title: "Procédure : supprimer et affecter à nouveau des écritures article | Microsoft Docs"
description: "Vous pouvez visualiser et modifier manuellement certaines écritures d'affectation article qui sont créées automatiquement lors des transactions d'inventaire."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 5ca921ba6c8ced04899b3a8cc2cd2db91e4d69a3
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-remove-and-reapply-item-ledger-entries"></a>Procédure : supprimer et affecter à nouveau des écritures article
Dans la fenêtre **Feuille de travail Affectation**, vous pouvez visualiser et modifier manuellement certaines écritures affectation article qui sont créées automatiquement lors des transactions inventaire.  

Lorsque vous reportez une transaction dans laquelle des articles entrent ou sortent de l'inventaire, une affectation article est créée entre chaque augmentation et diminution d'inventaire. Ces affectations déterminent le flux des coûts des marchandises entrant dans l'inventaire vers les coûts des marchandises sortant de l'inventaire. En raison du mode de calcul du coût unitaire, une affectation article incorrecte peut engendrer une erreur au niveau du coût moyen ou du coût unitaire. Pour plus d'informations, voir Détails de conception : traçabilité.

Vous pouvez être amené à annuler une affectation ou à affecter à nouveau des écritures article dans les scénarios suivants :

- Vous avez oublié d'effectuer une affectation fixe.
- Vous avez effectué une affectation fixe incorrecte.
- Vous devez retourner un article sur lequel une vente a déjà été affectée.

Si possible, utilisez un document pour affecter à nouveau une écriture article. Par exemple, si vous devez procéder à un retour achat d'un article auquel une vente a déjà été affectée, vous pouvez procéder à une nouvelle affectation en créant et en reportant le document de retour achat à l'aide de l'affectation correcte dans le champ **Écr. article à affecter** dans la ligne retour achat. Vous pouvez utiliser la fonction **Extraire les lignes de document reportées à inverser** ou **Copier document** dans le document de retour achat pour faciliter cette opération. Lorsque vous reportez le document, l'écriture article est automatiquement affectée à nouveau. Pour plus d'informations, reportez-vous à [Procédure : traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md).

Si vous ne pouvez pas utiliser un document pour exécuter une nouvelle affectation, par exemple si vous devez corriger une affectation fixe, utilisez la fenêtre **Feuille de travail Affectation** pour corriger une affectation.

> [!Warning]  
> Il est important de tenir compte des considérations suivantes lorsque vous travaillez sur la feuille de travail affectation :
    - Vous ne devez pas laisser des écritures affectation non affectées pendant de longues périodes, car d'autres utilisateurs ne peuvent pas traiter les articles tant que nous n'affectez pas à nouveau les écritures affectation ou que vous fermez la fenêtre **Feuille de travail affectation**. Les utilisateurs qui essaient d'exécuter des actions qui impliquent une écriture affectation dont l'affectation a été annulée manuellement reçoivent le message d'erreur suivant : « Il est impossible d'effectuer cette opération car l'affectation des écritures pour l'article XXX est annulée dans la feuille de travail affectation par l'utilisateur XXX. »
    - Vous devez affecter à nouveau uniquement les écritures article en dehors des heures de travail afin d'éviter les conflits avec d'autres utilisateurs qui reportent des transactions portant sur les mêmes articles.
    - Lorsque vous fermez la feuille de travail affectation, [!INCLUDE[d365fin](includes/d365fin_md.md)] effectue un contrôle pour s'assurer que toutes les écritures sont affectées. Par exemple, si vous supprimez une affectation quantité sans créer une nouvelle affectation et si vous fermez ensuite la feuille de travail affectation, une nouvelle affectation est créée. Cela permet de ne pas toucher au coût. Cependant, si vous supprimez une affectation fixe, une nouvelle affectation fixe n'est pas créée automatiquement lorsque vous fermez la feuille de travail. Vous devez le faire manuellement en créant une nouvelle affectation dans la feuille de travail.
    - Vous pouvez supprimer des affectations à partir de plusieurs écritures en même temps dans la feuille de travail affectation. Toutefois, comme l'affectation d'écritures affecte l'ensemble des écritures qui sont disponibles pour l'affectation, vous ne pouvez pas créer une affectation pour plusieurs écritures à la fois.
    - La feuille de travail affectation ne peut pas effectuer une affectation dans le cas suivant : si la quantité en stock est insuffisante pour l'affectation, la feuille de travail affectation ne peut pas effectuer une affectation lorsque vous tentez d'affecter une écriture diminution d'inventaire sans informations de traçabilité sur une écriture augmentation d'inventaire avec informations de traçabilité.

## <a name="to-remove-an-item-application-by-using-the-application-worksheet"></a>Pour supprimer une affectation article en utilisant le journal affectation  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille de travail affectation**, puis sélectionnez le lien associé.  
2.  La fenêtre **Feuille lettrage** s'ouvre en affichant les écritures comptables article existantes de tous les articles.  
3.  Définissez les filtres du raccourci **Général** pour faciliter la recherche de l'écriture comptable article pour laquelle vous souhaitez modifier le lettrage.  
4.  Sélectionnez l'écriture article, puis sélectionnez l'action **Écritures affectées**. La fenêtre **Voir écritures lettrées - Ecritures lettrées** s'ouvre et affiche l'écriture ou écritures comptables article actuellement lettrées pour l'écriture sélectionnée.  
5.  Sélectionnez l'écriture article dont vous souhaitez supprimer l'affectation.  
6.  Sélectionnez l'action **Supprimer affectation**. Cette action supprime l'écriture lettrage article qui lie les deux écritures comptables article et la déplace vers la fenêtre **Voir écritures lettrées - Ecritures délettrées**.  
7.  Fermez la fenêtre **Afficher les écritures lettrées – Écritures lettrées**.  

 Le champ **Quantité restante** des deux écritures comptables article sont augmentés de la quantité délettrée. L'écriture comptable article supprimée peut à présent être relettrée dans la fenêtre **Afficher les écritures lettrées – Écritures non lettrées**.  

> [!IMPORTANT]  
>  Vous ne devez pas laisser des écritures lettrage non lettrées pendant de longues périodes, car d'autres utilisateurs ne peuvent pas traiter les articles concernés jusqu'à ce que vous relettriez les écritures lettrage ou clôturiez la fenêtre **Feuille lettrage**. Le message d'erreur suivant s'affiche si vous essayez d'exécuter des tâches qui concernent une écriture d'affectation dont l'affectation a été supprimée manuellement :  
>   
>  **Il est impossible d'effectuer cette action car l'affectation des écritures pour l'article <item> est annulée dans la feuille de travail affectation par l'utilisateur <user>.**  

## <a name="to-reapply-an-item-application-by-using-the-application-worksheet"></a>Pour appliquer à nouveau une affectation article en utilisant le journal affectation  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille de travail affectation**, puis sélectionnez le lien associé.  
2.  La fenêtre **Feuille lettrage** s'ouvre en affichant les écritures comptables article existantes de tous les articles.  
3.  Pour appliquer à nouveau des écritures qui ont été supprimées depuis l'ouverture de la feuille, sélectionnez l'écriture du grand livre d'articles que vous souhaitez appliquer à nouveau. Sur l'onglet **Actions** , dans le groupe **Fonctions**, choisissez **Relettrer**.  

    > [!NOTE]  
    >  Ce relettrage vers le solde de départ se produit aussi automatiquement lorsque vous fermez la fenêtre **Feuille lettrage**.  
4.  Pour affecter une écriture du grand livre d'articles en cours disponible dans une autre écriture, sélectionnez l'écriture article à affecter. Sélectionnez l'action **Écritures non lettrées**. La fenêtre **Afficher les écritures lettrées – Écritures non lettrées** s'ouvre.  
5.  Sélectionnez une ou plusieurs écritures comptables article que vous voulez lettrer dans l'écriture sélectionnée dans la fenêtre **Feuille lettrage**, puis choisissez le bouton **OK**.  

     Une écriture d'affectation article est créée entre les deux écritures article. Les champs **Quantité restante** des deux écritures sont réduits de la quantité lettrée.  

    > [!NOTE]  
    >  Si vous avez choisi d'effectuer une affectation qui créerait une boucle infinie dans le processus d'ajustement des coûts, l'affectation que vous avez proposée n'est pas appliquée. Cela peut se produire lorsque les écritures originales ont créé un stock négatif. L'affectation n'est pas effectuée. Par conséquent, vous devez sélectionner une autre écriture pour l'affectation.  
6.  Si, dans les **Paramètres stock**, le champ **Ajustement automatique des coûts** est défini sur **Toujours**, le traitement par lots d'ajustement des coûts est exécuté automatiquement après que vous avez effectué un relettrage. Sinon, exécutez le traitement en lot **Ajuster coûts - Écr. article** pour être sûr que tous les coûts sont actualisés.  

## <a name="see-also"></a>Voir aussi  
[Procédure : clôturer les écritures comptables article ouvertes qui résultent d'un lettrage fixe dans la feuille article](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)  
 [Procédure : traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)   
 [Détails de conception : lettrage article](design-details-item-application.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

