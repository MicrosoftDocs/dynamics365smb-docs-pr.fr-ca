---
title: Allouer les coûts aux partenaires intercompagnie | Microsoft Docs
description: Découvrez comment les paramètres de TVA des clients et des fournisseurs contrôlent si et comment la TVA est calculée.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: incoming document
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="allocate-costs-to-intercompany-partners"></a>Allouer les coûts aux partenaires intercompagnie
Lorsque vous utilisez des écritures intercompagnie pour transférer des documents entre compagnies partenaires, les paramètres liés à la TVA (principalement le groupe de report marché TVA) affectés aux comptes client ou fournisseur (associés au partenaire intercompagnie) contrôlent si et comment la TVA est calculée et enregistrée. Vous pouvez également effectuer des répartitions de coûts directement à partir d’un bon de commande vers des compagnies partenaires. Par exemple, si vous enregistrez une facture achat d’un fournisseur externe et si vous souhaitez répartir tout ou partie des coûts à un ou plusieurs partenaires intercompagnie.

Vous pouvez affecter les coûts à un ou plusieurs partenaires intercompagnie en utilisant les éléments suivants :

* **Journaux généraux intersociétés** - Ces journaux sont utiles lors de l’achat d’un service. Par exemple, lorsqu’une compagnie mère engage un service pour mettre en place des systèmes informatiques dans deux filiales. La facture est envoyée à la compagnie mère, mais les coûts sont affectés aux partenaires intercompagnie. Pour plus d’informations, consultez [Utiliser les documents et les journaux intercompagnie](intercompany-how-work-documents-journals.md).
* Bons de commande et factures - L’utilisation des documents d’achat est utile lorsque les fonctions d’achat, par exemple, les dépenses d’exploitation, sont centralisées dans une compagnie, puis affectées aux partenaires intercompagnie.

## <a name="to-allocate-costs-using-an-intercompany-general-journal"></a>Pour allouer les coûts à l’aide d’un journal général intersociétés
Pour saisir une ligne dans un journal général intersociétés, procédez comme suit. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général intercompagnie**, puis sélectionnez le lien associé.
2. Si nécessaire, dans le champ **N° doc. externe**, saisissez le numéro de document sur la facture du fournisseur.
3. Dans le champ **Type document**, choisissez **Facture**.
4. Dans le champ **Type compte**, sélectionnez **Fournisseur**.
5. Dans le champ **Type compte**, sélectionnez le fournisseur.
6. Dans le champ **Montant**, saisissez un montant négatif égal au montant de la facture.
7. Dans le champ **Type compte contrepartie**, sélectionnez **Compte du grand livre**.
8. Dans le champ **N° compte de contrepartie**, sélectionnez le compte de contrepartie à utiliser.
9. Pour répartir les coûts entre les partenaires intercompagnie, procédez comme suit :
   1. Créez une ligne.
   2. Quittez le champ **Type de document**, choisissez l’option qui laisse le champ vide.
   3. Dans le champ **N° document**, entrez un nombre différent du nombre dans le champ **N° document externe**. L’affectation des coûts est considérée comme une transaction différente.
   4. Dans le champ **Type compte**, sélectionnez **Partenaire IC**.
   5. Dans le champ **N° compte**, choisissez le partenaire intercompagnie auquel allouer le coût.
   6. Dans le champ **Type compte de solde**, sélectionnez **Compte du grand livre**.
   7. Dans le champ **N° compte de solde**, choisissez le compte du grand livre sur lequel reporter le montant que vous recevez du partenaire intercompagnie.
   1. Dans le champ **Montant**, saisissez le montant de la facture à allouer au partenaire intercompagnie.
   1. Dans le champ **N° cpte du grand livre partenaire IC**, choisissez le compte du grand livre sur lequel reporter le montant que vous recevez du partenaire intercompagnie. 
   1. Renseignez les champs restants selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Répétez ces étapes pour chaque partenaire intercompagnie qui doit partager le coût.
1. Pour reporter le document et répartir les coûts, sélectionnez **Reporter**.  

## <a name="to-allocate-costs-using-a-purchase-document"></a>Pour allouer les coûts à l’aide d’un document d’achat
La procédure suivante décrit comment répartir les coûts à l’aide d’une facture achat. La procédure est identique pour des bons de commande.

> [!NOTE]
> Pour terminer ces étapes, vous devez personnaliser la page **Facture achat** en ajoutant les champs **Code du partenaire IC**, **Type de réf. du partenaire IC** et **Partenaire IC**. Pour plus d’informations, consultez [Commencer à personnaliser une page au moyen de la bannière Personnalisation](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Facture achat**, puis sélectionnez le lien associé.
2. Dans le champ **Type**, sélectionnez **Compte du grand livre**.
   
   Le compte du grand livre est la seule option que vous pouvez utiliser pour répartir les coûts.  
1. Dans le champ **N°**, sélectionnez le compte du grand livre vers lequel reporter.
1. Dans le champ **Code partenaire IC**, choisissez le partenaire intercompagnie auquel allouer le coût.
1. Dans le champ **Type de réf. du partenaire IC**, choisissez le compte du grand livre à utiliser pour l’affectation. Ce compte mappera la dépense à un compte dans le plan comptable du partenaire intersociétés.
1. Dans le champ **Quantité**, indiquez le nombre d’unités à facturer au partenaire intercompagnie.
1. Dans le champ **Coût unitaire direct HT (ou TVA incluse)**, saisissez le coût par article à facturer au partenaire intercompagnie.
1. Renseignez les champs restants selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 
1. Pour reporter le bon de commande, choisissez **Reporter**.

## <a name="to-send-the-allocated-costs-to-intercompany-partners"></a>Pour envoyer les coûts affectés aux partenaires intercompagnie
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Transactions boîte d’envoi IC**, puis choisissez le lien associé.
2. Choisissez les lignes à envoyer, puis choisissez l’action **Envoyer au partenaire IC**. 
3. Pour allouer les coûts, choisissez l’action **Terminer les actions des lignes**.

## <a name="calculating-vat-for-cost-distributions"></a>Calcul de la TVA pour les répartitions de coûts
Lorsque vous utilisez un document pour répartir les coûts entre les partenaires intercompagnie, deux paramètres de TVA doivent être pris en compte : 
* Les paramètres du compte du grand livre pour les dépenses :
   * Si les groupes de report marché général ou marché TVA sont configurés sur le compte du grand livre, le calcul dépend des groupes et des groupes de produits de la ligne de document.
   * Si les groupes de report marché général ou marché TVA ne sont pas spécifiés sur le compte du grand livre, le calcul dépend des éléments suivants :
* Les paramètres du groupe de report sur le partenaire intercompagnie
   * Indique si le partenaire intercompagnie est affecté à un numéro de client pour lequel aucun groupe de report marché général ou marché TVA n’est spécifié.
   * Il n’y a pas de numéro de client associé au partenaire intercompagnie. Ensuite, les groupes de report marché général ou marché TVA sont vides et la ligne dans la configuration de report TVA est utilisée, qui est généralement un groupe dans lequel 0 % de TVA est spécifié.

> [!NOTE]
> Il est important de valider à la fois la configuration du partenaire intercompagnie et la configuration du compte du grand livre (pour le compte de dépenses utilisé pour la répartition des coûts) avant d’allouer les coûts aux partenaires intercompagnie.

## <a name="see-also"></a>Voir aussi
[Configuration des fonctionnalités intersociétés](intercompany-how-setup.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
