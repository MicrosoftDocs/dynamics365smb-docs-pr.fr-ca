---
title: "Procédure : créer des commandes permanentes ventes | Microsoft Docs"
description: "Utilisez des commandes ouvertes quand un client a accepté d'acheter de grandes quantités à livrer en plusieurs expéditions de petite taille au cours d'une période déterminée."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 8e0668e39891f6e0924afd8d9ec3ee39af95e587
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="work-with-blanket-sales-orders"></a>Utiliser des commandes permanentes ventes
Une commande permanente ventes représente le cadre d'une entente à long terme entre votre client et vous.

Une commande permanente est généralement établie quand un client s'est engagé à acheter de grandes quantités à livrer en plusieurs livraisons de plus petite taille au cours d'une période déterminée. Souvent, les commandes ouvertes ne couvrent qu'un article avec des dates de livraison prédéfinies. La principale raison d'utiliser une commande ouverte plutôt qu'une document de vente est que les quantités entrées dans une commande ouverte n'affectent pas la disponibilité de l'article et peuvent donc être utilisées comme une journal à des fins de surveillance, de précision et de planification.

Sur la commande permanente, vous pouvez configurer chaque livraison comme une ligne commande distincte qui peut ensuite être convertie en document de vente au moment de la livraison.

Vous pouvez utiliser une commande permanente ventes, par exemple, lorsqu'un client appelle pour passer une commande de 1 000 unités d'un article et souhaite des livraisons par lot de 250 unités chaque semaine du mois suivant.

> [!NOTE]
> Les commandes permanentes achats fonctionnent de la même manière que les commandes permanentes ventes. Cette documentation ne couvre pas les commandes permanentes achats.

## <a name="to-create-a-blanket-sales-order"></a>Pour créer une commande permanente ventes  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Commandes permanentes ventes**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  Laissez vide le champ **Date commande**. Lors de la création de documents de vente séparés depuis la commande permanente, la date commande du document de vente est définie comme étant égale à la date du jour.
5. Dans le raccourci **Lignes**, créez des lignes distinctes pour chaque expédition. Par exemple, si le client souhaite 1 000 unités réparties de façon uniforme sur quatre semaines, entrez quatre lignes distinctes de 250 unités chacune.   

## <a name="to-create-a-sales-order-from-a-blanket-sales-order"></a>Pour créer un document de vente à partir d'une commande permanente ventes  

1.  Pour créer une commande pour l'une des lignes de l'ordre d'assemblage ouvert, effacez la quantité du champ **Qté à expédier** de toutes les lignes que vous ne voulez PAS expédier actuellement.  
2.  Lorsque vous êtes prêt à créer les commandes, sélectionnez **Créer commande**, puis **Oui**. Un message s'affiche, vous informant que la commande ouverte a été associée à un numéro de commande. Remarquez que la commande ouverte n'a pas été supprimée.  
3.  Cliquez sur le bouton **OK**.  
4.  Pour afficher les résultats des étapes précédentes, sélectionnez l'action **Ligne**, l'action **Lignes non reportées**, puis l'action **Commandes**.  
5.  Dans la fenêtre **Lignes vente**, sélectionnez le document de vente approprié, sélectionnez l'action **Ligne**, sélectionnez Ligne, puis sélectionnez l'action **Afficher document**.  

Ce qui suit affecte les documents de vente après leur création à partir de documents de vente ouverts :  

- Une fois la commande permanente convertie en document de vente, celui-ci contient toutes les lignes de la commande permanente. Les lignes où la quantité figurant dans le champ **Qté à expédier** a été supprimée s'affichent mais avec les champs **Quantité** vides. Vous pouvez décider de laisser, de modifier ou de supprimer les lignes.  
- N'oubliez pas que la quantité de la ligne document de vente ne peut pas dépasser celle de la ligne commande permanente associée. Sinon, le report du document de vente est impossible.  
- Lorsque le document de vente est reporté comme livré et/ou facturé, les champs **Qté livrée** et **Quantité facturée** sont mis à jour sur la commande ouverte concernée.  
- Le numéro de commande ouverte et un numéro de ligne sont enregistrés comme propriétés des lignes vente en cas de création à partir d'une commande ouverte.  
- Si les commandes vente ne sont pas créées directement depuis la commande ouverte mais ont trait à celle\-ci, il est possible de créer un lien entre une commande vente et une commande ouverte en entrant le numéro de commande ouverte associé dans le champ **N° commande ouverte** sur la ligne de document de vente.  
- Une fois le document de vente créé pour la quantité totale d'une ligne commande permanente, aucun autre document de vente ne peut être créé pour la même ligne. Les utilisateurs ne peuvent plus entrer de quantité dans le champ **Qté à expédier**. Toutefois, si des quantités supplémentaires doivent être ajoutées à une commande ouverte, il est possible d'augmenter la valeur du champ **Quantité** et de créer des commandes supplémentaires.  
- La commande ouverte vente facturée reste dans le système jusqu'à ce qu'elle soit supprimée, soit en supprimant les commandes ouvertes individuelles, soit en exécutant le traitement par lots **Suppr. cdes vente ouv. fact.**.  
- Si un client est également enregistré comme contact dans le module Marketing et si vous avez spécifié un code modèle interaction pour les commandes vente ouvertes dans la fenêtre **Paramètres Marketing**, lorsque vous sélectionnez **Imprimer** pour imprimer la commande vente ouverte, une interaction est enregistrée automatiquement dans la table Écriture journal interaction.

## <a name="to-view-the-status-of-a-blanket-purchase-order"></a>Pour visualiser l'état d'une commande permanente achats  
Vous pouvez visualiser l'état d'une commande permanente ventes dans la fenêtre **Statistiques Commande permanente achats**. Ceci peut s'avérer utile lorsque vous commencez à facturer une commande créée à partir de la commande permanente achats.  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Commandes permanentes achats**, puis sélectionnez le lien associé.  
2.  Sélectionnez une commande permanente achats, puis choisissez l'action **Statistiques**.  
3.  Dans la fenêtre **Statistiques Commande ouverte achat**, sur le raccourci **Général**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la commande. Elles se basent sur la quantité totale des **champs Quantité** sur les lignes commande ouverte achat.  

    - Sur le raccourci **Facturation**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la quantité dans les champs **Qté à facturer** des lignes commande ouverte achat.  
    - Sur le raccourci **Expédition**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la quantité dans les champs **Qté à recevoir** des lignes commande ouverte achat.  
    - Sur le raccourci **Paiement anticipé**, vous pouvez visualiser des informations récapitulatives concernant les éventuels montants déjà payés.  
    - Sur le raccourci **Fournisseur**, vous pouvez visualiser certaines informations de base concernant le fournisseur.    

## <a name="to-view-unposted-and-posted-blanket-sales-order-lines"></a>Pour afficher des lignes commande permanente ventes reportées et non reportées   
Le lien entre la commande permanente ventes et le document de vente d'origine, et n'importe quel autre document vente, est conservé après report en tant que liste des lignes facture reportées et non reportées de document de vente.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Commandes permanentes ventes**, puis sélectionnez le lien associé.
2. Ouvrez la commande permanente ventes que vous souhaitez afficher.
3. Pour visualiser les écritures non reportées, sélectionnez la ligne en question, sélectionnez l'action **Ligne**, puis l'action **Lignes non reportées**. Choisissez l'une des options suivantes.  

    <table>
    <tr>
    <th>Option</th>
    <th>Description</th>
    </tr>
    <tr>
    <td>**Commandes**</td>
    <td>Spécifie les commandes ouvertes associées à la ligne sélectionnée.</td>
    </tr>
    <tr>
    <td>**Factures**</td>
    <td>Spécifie les factures ouvertes associées à la ligne sélectionnée. Ouvrez les factures associées manuellement à une commande ouverte en entrant le numéro de commande ouverte dans la ligne facture vente.</td>
    </tr>
    <tr>
    <td>**Retours**</td>
    <td>Spécifie les commandes retour ouvertes associées à la ligne sélectionnée.</td>
    </tr>
    <tr>
    <td>**Avoirs**</td>
    <td>Spécifie les avoirs ouverts associés à la ligne sélectionnée.</td>
    </tr>
    </table>
4. Pour visualiser les écritures reportées, sélectionnez la ligne en question, choisissez l'action **Ligne**, puis l'action **Lignes reportées**. Choisissez l'une des options suivantes.  

    <table>
    <tr>
    <th>Option</th>
    <th>Description</th>
    </tr>
    <tr>
    <td>**Livraisons**</td>
    <td>Livraisons reportées associées à la ligne sélectionnée.</td>
    </tr>
    <tr>
    <td>**Factures**</td>
    <td>Factures reportées associées à la ligne sélectionnée.</td>
    </tr>
    <tr>
    <td>**Réceptions retour**</td>
    <td>Réceptions retour reportées associées à la ligne sélectionnée.</td>
    </tr>
    <tr>
    <td>**Avoirs**</td>
    <td>Notes de crédit reportées associées à la ligne sélectionnée.</td>
    </tr>
    </table>
5. Dans la fenêtre **Lignes vente**, sélectionnez l'action **Afficher document** pour afficher l'écriture.

## <a name="see-also"></a>Voir aussi
[Vente](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

