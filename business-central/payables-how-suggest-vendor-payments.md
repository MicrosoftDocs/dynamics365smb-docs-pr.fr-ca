---
title: Traitement en lot Proposer paiements fournisseur
description: Vous pouvez spécifier les paramètres de paiement du fournisseur pour obtenir des suggestions de paiements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.keywords: 'vendor payment, creditor, debt, balance due, AP'
ms.search.form: '256,'
ms.date: 09/07/2023
ms.custom: bap-template
---
# Proposer paiements fournisseur

Sur la page **Journal paiement**, vous pouvez utiliser le traitement en lot **Proposer paiements fournisseur** pour proposer des lignes paiement. En fonction de vos paramètres, [!INCLUDE [prod_short](includes/prod_short.md)] suggère des lignes pour les paiements :

* Paiements bientôt dus
* Paiements pour lesquels un escompte de paiement est disponible

Pour bénéficier pleinement des suggestions de paiement, vous devez d'abord attribuer une priorité à vos fournisseurs. Pour en savoir plus sur la priorisation des fournisseurs, rendez-vous sur [Prioriser les fournisseurs](purchasing-how-prioritize-vendors.md).  

> [!NOTE]  
> Le traitement en lot exclut les écritures fournisseur qui sont **En attente** ou qui sont déjà affectées et ont une valeur dans le champ **Code affectation**.  

> [!IMPORTANT]  
> Si vous souhaitez profiter d'escomptes et que vous avez saisi un montant disponible, ce montant est d'abord utilisé pour :  
>
> * Les écritures fournisseur échues et prioritaires, par ordre de priorité.
> * Les écritures fournisseur échues et non prioritaires.  
> * Les écritures fournisseur ouvertes donnant lieu à un escompte. Les écritures sont classées dans l’ordre des numéros des fournisseurs.  

## Pour utiliser la fonction Proposer paiements fournisseur

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.  
2. Ouvrez le journal, puis sélectionnez l’action **Proposer paiements fournisseur**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. Cliquez sur le bouton **OK**.  

## Pour insérer la date d'échéance comme date de report sur les lignes journal paiement

Lorsque vous utilisez le traitement par lots **Proposer paiements fournisseur** pour créer des lignes de paiement pour vos fournisseurs, vous pouvez remplir deux champs spéciaux pour vous assurer que les lignes générées utilisent la date d'échéance pour calculer la date comptabilisation. Ces champs sont **Calculer la date comptabilisation à partir de la date d'échéance doc. lettrage** et **Décalage date d'échéance doc. lettrage**.  

> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le champ **Calculer la date de report à partir de la date d’échéance du doc. d'affectation** avec le champ **Trouver escompte de paiement** ou le champ **Sommaire par fournisseur**. Si la date de report est basée sur la date d'échéance, des escomptes de paiement risquent de ne pas être calculés correctement, parce que la date de report peut être postérieure à la date d'escompte de paiement.  

De plus, si la date de report calculée se trouve dans le passé, la date de report est déplacée à la date de travail, et un message d’avertissement s’affiche.  

Vous pouvez aussi créer manuellement des lignes de paiement à l’aide de la date d’échéance pour calculer la date de report. Une fois que vous avez appliqué les écritures comptables fournisseur, vous pouvez utiliser l'option **Calculer date comptabilisation** pour mettre à jour la date comptabilisation de la ligne feuille à la date d'échéance de la facture achat associée. Pour en savoir plus sur ce processus manuel, reportez-vous à [Affecter manuellement les transactions d’achat](payables-how-apply-purchase-transactions-manually.md).  

> [!NOTE]  
> Si la facture achat est en retard, la date de report est définie sur la date de travail et la police de la ligne devient rouge.  

## Voir aussi .

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Effectuer des paiements](payables-make-payments.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
