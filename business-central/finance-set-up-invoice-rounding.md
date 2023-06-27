---
title: Configuration de la fonction arrondissement facture
description: 'Si vous devez arrondir des montants de factures lorsque vous créez des factures, vous pouvez utiliser la fonction d’arrondissement automatique expliquée ici.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '5, 16, 118, 459, 460, 495'
ms.date: 06/16/2021
ms.author: bholtorf
---
# <a name="set-up-invoice-rounding"></a>Configuration de la fonction arrondissement facture
Si vous devez arrondir des montants de factures lorsque vous créez des factures, vous pouvez utiliser la fonction d'arrondissement automatique. Lorsqu'une facture est arrondie, une ligne supplémentaire contenant le montant de l'arrondissement est ajoutée et reportée avec les autres lignes facture.

> [!NOTE]  
>  Les réglementations ou la douane locale peuvent exiger des factures arrondies d'une certaine manière, par exemple, divisibles par 0,05.  

Pour utiliser l'arrondissement facture automatique, vous devez :  

* Spécifier les comptes du grand livre dans lesquels les différences d'arrondissement seront reportées ;  
* configurer les règles d'arrondissement des factures dans les devises locales et étrangère ;  
* activer la fonction.  

> [!NOTE]  
>  Outre les fonctions d'arrondissement facture, vous pouvez arrondir les montants des factures à l'aide des fonctions arrondissement montant unité de mesure et arrondissement montant.  

## <a name="set-up-general-ledger-accounts-for-invoice-rounding-differences"></a>Configurer des comptes GL afin d'autoriser les différences d'arrondissement dans les factures
Pour utiliser la fonction d'arrondissement automatique de facture, vous devez configurer les comptes du grand livre dans lesquels des différences d'arrondissement seront reportées. Pour cela, vous devez au préalable configurer des groupes comptabilisation produit TVA. Pour plus d'informations, reportez-vous à [Configuration TVA](finance-setup-vat.md).  

### <a name="to-set-up-general-ledger-accounts-for-invoice-rounding-differences"></a>Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement dans les factures
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
2. Sur la page **Plan comptable**, configurez le compte et nommez-le, par exemple **Arrondissement facture**. [!INCLUDE[prod_short](includes/prod_short.md)] utilise le nom de ce compte comme texte pour les factures arrondies.  
3. Selon que vous utilisez la TVA ou la taxe de vente, dans les champs **Groupe de report produit Taxe** ou **Groupe de report produit TVA**, choisissez un groupe de report pour les montants arrondis. Vous pouvez aussi configurer un nouveau code groupe à utiliser pour les arrondissements facture.
4. Laissez les champs **Type de report général** et **Groupes de report marché fiscal** ou **Groupe de report marché TVA** vides. <!-- Why do we say to leave these blank, when there are a lot of other fields we also leave blank but don't mention? -->  

À présent, vous pouvez affecter le compte arrondissement facture aux groupes de report sur la page **Groupes de report du fournisseur**.  <!-- Why only the vendor posting groups? -->

## <a name="set-up-rounding-for-foreign-and-local-currencies"></a>Configuration de règles d'arrondissement pour les devises étrangères et locales
Avant d'utiliser la fonction d'arrondissement automatique, vous devez configurer les règles d'arrondissement pour les devises étrangères et locales.

### <a name="to-set-up-rounding-for-foreign-currencies"></a>Pour configurer les règles d'arrondissement pour les devises étrangères
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Devises**, puis choisissez le lien associé.  
2. Sur la page **Devises**, choisissez la devise étrangère pour ouvrir la **Fiche devise**, puis renseignez les champs **Précision arrondissement montant**, **Précis. arrondissement montant unité de mesure**, **Précision arrondissement facture** et **Type arrondissement facture**.

### <a name="to-set-up-rounding-for-your-local-currency"></a>Pour configurer les règles d'arrondissement pour les devises locales
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.  
2. Sur la page **Configuration du grand livre**, sous le raccourci **Général**, renseignez les champs **Précis. arrondissement fact.** et **Type arrondissement facture**.  

## <a name="activate-the-invoice-rounding-function"></a>Activer la fonction d'arrondissement de factures
Vous devez activer la fonction d'arrondissement facture pour que les factures vente et achat soient automatiquement arrondies. Activez séparément la fonction d'arrondissement facture pour les factures vente et les factures achat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration ventes & à recevoir** ou **Configuration achats et à payer**, puis sélectionnez le lien associé.  
2. Sur le raccourci **Général**, sélectionnez la case **Arrondissement facture**.  

## <a name="see-also"></a>Voir aussi
[Facturer des ventes](sales-how-invoice-sales.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
