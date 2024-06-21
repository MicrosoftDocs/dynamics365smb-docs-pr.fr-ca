---
author: brentholtorf
ms.topic: include
ms.date: 11/29/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
> [!NOTE]
> De nouvelles capacités de création de dépôts bancaires sont disponibles dans la 1re vague de lancement de Business Central 2022 pour de nombreuses versions nationales/régionales. Si vous utilisiez Business Central aux États-Unis, au Canada ou au Mexique avant cette version, vous utilisiez peut-être les fonctionnalités antérieures. Vous pouvez continuer, mais les nouvelles capacités remplaceront les anciennes dans une prochaine version. Pour commencer à utiliser les nouvelles fonctionnalités immédiatement, votre administrateur peut se rendre sur la page **Gestion des fonctionnalités** et activer **Mise à jour des fonctionnalités : Rapprochement bancaire et dépôts standardisés**. Pour plus d'informations, voir [Créer des dépôts bancaires](../../../bank-create-bank-deposits.md).


Vous pouvez créer des dépôts bancaires pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être affectés aux notes de crédit et factures en attente.  

La page **Dépôts** spécifie les renseignements de dépôt bancaire comme le numéro de compte bancaire, le montant de dépôt total, les lignes dépôt, la date de report, la date de document, le code de département, le code de devise et les notes de dépôt bancaire. Vous pouvez utiliser cette page pour créer des dépôts bancaires, reporter des dépôts, imprimer des dépôts, afficher des commentaires sur les dépôts ou consulter un rapport qui indique le montant du dépôt à rapprocher.

Le rapport **Dépôt**affiche les dépôts clients et fournisseurs avec le montant du dépôt initial, le montant du dépôt qui reste ouvert et le montant affecté. Le rapport indique également le montant total des dépôts reportés à rapprocher.

Les lignes dépôt bancaire contiennent des renseignements sur les différents éléments faisant l'objet de dépôts, tels que les chèques des clients. Ces informations comprennent la date et le numéro du document, le type et le numéro du compte et le montant. Le total des montants inscrits sur les lignes doit correspondre au montant total du dépôt.

Après avoir renseigné les renseignements de dépôt et les lignes, vous devez les reporter afin de mettre à jour les grands livres correspondants, comme le grand livre bancaire, le grand livre général ou le grand livre client. Les dépôts reportés sont stockés pour référence ultérieure et peuvent être consultés sur la page **Dépôts reportés**.

## Pour créer un dépôt  
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Dépôts**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Sous le raccourci **Général**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**N°**|Numéro d'identification unique du dépôt.|  
    |**N° de compte bancaire**|Numéro de compte bancaire pour le dépôt.|  
    |**Montant total de dépôt**|Montant total du dépôt reporté sur le grand livre bancaire.<br /><br /> Vous pouvez reporter ce dépôt uniquement si la somme des lignes dépôt est égale à la valeur de ce champ.|  
    |**Date de report**|Date de report du dépôt.|  
    |**Date du document**|Date du document du dépôt.|  
4.  Sous le raccourci **Lignes**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type compte**|Type de compte.|  
    |**N° compte**|Numéro de compte d'identification unique associé au type de compte sélectionné, sur lequel l'écriture est reportée.|  
    |**Description**|Description de l'écriture ligne journal.|  
    |**Date de document**|Date de document de l'écriture ligne journal.|  
    |**Type document**|Type de document de l'écriture ligne journal.|  
    |**N° du document**|Numéro de document de l'écriture ligne journal.|  
    |**Montant crédit**|Montant total du crédit sur la ligne journal.|  

5. Éventuellement, choisissez l'action **Dimensions**, puis ajoutez les dimensions sur la page **Écritures de l'ensemble de dimensions**.  
6. Sélectionnez l'action **Reporter**.  

    > [!TIP]
    > Pour reporter un dépôt bancaire en tant qu’écriture compte bancaire unique avec la somme totale des montants dans les lignes dépôts bancaires, activez l'option **Reporter en tant que montant forfaitaire** sur le dépôt bancaire. Pour reporter en tant que montants forfaitaires pour de nouveaux dépôts bancaires par défaut, sur la page **Configuration ventes & à recevoir**, activez l'option **Reporter dépôts bancaires en tant que montant forfaitaire**.

    > [!NOTE]  
    > Vous pouvez reporter un dépôt uniquement si les montants affichés dans les champs **Lignes de dépôt total** et **Montant total de dépôt** sont égaux.  

Ensuite, vous pouvez utiliser les rapports **Test des dépôts** et **Dépôt** pour rapprocher vos dépôts reportés avec vos notes de crédit et factures en attente.  
