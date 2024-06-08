---
title: Configuration des acomptes
description: "Découvrez comment configurer Business\_Central afin de pouvoir utiliser les paiements anticipés pour facturer et collecter les paiements anticipés requis des clients ou régler des paiements anticipés aux fournisseurs."
author: brentholtorf
ms.topic: conceptual
ms.search.keyword: prepayment
ms.search.form: '314, 459, 460, 664'
ms.date: 10/27/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Configuration des acomptes

Si vous voulez que vos clients fassent des paiements avant de leur livrer une commande ou si votre fournisseur exige que vous fassiez un paiement avant de vous livrer une commande, vous pouvez utiliser la fonctionnalité Paiement anticipé. La fonctionnalité paiements anticipés vous permet de facturer et de collecter les paiements anticipés requis des clients ou de régler des paiements anticipés aux fournisseurs, et de vous assurer que tous les paiements partiels sont reportés sur une facture. Pour plus d'informations, voir [Créer des factures de paiement anticipé](finance-how-to-create-prepayment-invoices.md).

Avant de reporter des factures paiement anticipé, vous devez configurer les comptes de report dans le grand livre et configurer des séries de numéros pour les documents paiement anticipé. Vous devez spécifier un compte pour les paiements anticipés liés aux ventes et un compte pour les paiements anticipés liés aux achats. Vous pouvez spécifier les mêmes comptes report à utiliser pour tous les paiements anticipés liés à tous les groupes de report marché ou groupes report produit, ou vous pouvez spécifier des comptes spécifiques pour des groupes de report spécifiques pour les ventes et les achats, respectivement. Cela dépend des exigences de votre compagnie en matière de suivi des paiements anticipés.  

Vous pouvez définir le pourcentage du montant ligne qui sera facturé pour paiement anticipé, pour un client ou un fournisseur, pour tous les articles ou pour une sélection d'articles. Une fois la configuration terminée, vous pouvez générer des factures paiement anticipé à partir des documents de vente et des bons de commande. Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou, au besoin, modifier les montants de la facture. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

> [!NOTE]
> Nous vous recommandons de ne pas utiliser un pourcentage de paiement anticipé de 100 dans les cas suivants :
>
> * Si vous résidez en Amérique du Nord. En raison du mode de calcul des taxes, un pourcentage de paiement anticipé de 100 peut entraîner des problèmes avec les factures de paiement anticipé.
> * Dans toutes les régions, si vous déduisez manuellement un escompte de paiement de la facture. Un pourcentage de paiement anticipé de 100 ne laissera pas automatiquement un montant sur lequel déduire l'escompte.
>
> En outre, lorsque vous utilisez un pourcentage de paiement anticipé de 100, [!INCLUDE[prod_short](includes/prod_short.md)] peut avoir besoin de créer des écritures d’arrondissement décalées. Lorsque cela se produit, vous devrez choisir un compte du grand livre dans le champ **Compte d’arrondissement de facture** sur la page **Groupes de report client**. Ceci est vrai même si vous n’avez pas activé le bouton de basculement **Arrondissement facture** sur la page **Configuration des ventes**. Si vous ne spécifiez pas de compte, vous ne pourrez pas reporter de factures de paiement anticipé. 

Puisque le montant prépayé appartient à l'acheteur jusqu'à ce qu'il ait reçu les biens ou les services, vous devez configurer des comptes du grand livre pour recevoir les montants de paiement anticipé jusqu'au report de la facture finale. Les paiements anticipés vente doivent être enregistrés dans un compte passif jusqu'à la livraison des articles. Les acomptes achat doivent être enregistrés dans un compte immobilisations jusqu'à la réception des articles. En outre, vous devez configurer un compte du grand livre séparé pour chaque identificateur TVA.  

[!INCLUDE[local-func-setup-link](includes/local-func-setup-link.md)]

## Ajouter des comptes paiement anticipé à la configuration de report générale  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du report général**, puis choisissez le lien associé.
2. Sur la page **Configuration du report général**, renseignez les champs suivants pour les lignes appropriées :  

    * **Compte de paiements anticipés de vente**  
    * **Compte de paiements anticipés d'achat**  

> [!TIP]
> Si vous ne pouvez pas voir les champs de la page **Configuration du report général**, utilisez la barre de défilement horizontale au bas de la page pour faire défiler l'affichage vers la droite.  

Si vous n'avez pas encore configuré de comptes GL pour les paiements anticipés, vous pouvez ouvrir la page **Liste des comptes GL** à partir du champ du compte correspondant.  

## Configurer des séries de numéros pour des documents paiement anticipé  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes**, sur le raccourci **Séries de numéros**, remplissez les champs suivants :  

   * **N° factures pour paiement anticipé reporté**
   * **N° notes de crédit pour paiement anticipé reporté**

3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Configuration achats et à payer**, puis sélectionnez le lien associé.
4. Sur la page **Configuration achats**, sur le raccourci **Séries de numéros**, remplissez les champs suivants :

    * **N° factures pour paiement anticipé reporté**
    * **N° notes de crédit pour paiement anticipé reporté**

> [!NOTE]  
> Vous pouvez utiliser les mêmes séries de numéros pour des factures paiement anticipé et des factures normales, ou utiliser des séries de numéros différentes. Si vous utilisez des souches différentes, elles ne doivent pas se chevaucher car vous ne pouvez pas avoir des numéros identiques dans les deux souches.  

## Pour configurer des pourcentages de paiement anticipé pour des articles, des clients et des fournisseurs

Pour un article, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les clients, pour un client spécifique ou pour un groupe prix client. Si vous ne souhaitez pas appliquer le même pourcentage de paiement anticipé à tous les clients, vous devez spécifier à quels clients ou à quels groupes de prix client s’applique le pourcentage de paiement anticipé.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Sélectionnez un article, puis cliquez sur l'action **Pourcentages paiement anticipé**.  
3. Sur la page **Pourcentages paiement anticipé vente**, renseignez autant de champs que nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pour un client ou un fournisseur, vous pouvez configurer un pourcentage de paiement anticipé par défaut pour tous les articles et tous les types de lignes vente. Vous entrez cette valeur dans la fiche client ou fournisseur. La procédure suivante montre comment spécifier un pourcentage de paiement anticipé pour un client, mais des étapes similaires s’appliquent aux fournisseurs.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la fiche d'un client.
3. Remplissez le champ **% paiement anticipé**.
4. Répétez les étapes pour d'autres clients ou fournisseurs.  

> [!TIP]
> Vous pouvez également accéder à la page **Pourcentages paiement anticipé vente** à partir de la fiche client ou fournisseur.

### Pour déterminer quel pourcentage de paiement anticipé a la priorité  

Une commande peut présenter un pourcentage de paiement anticipé dans l'en-tête vente et un autre pourcentage pour les articles figurant dans les lignes. Pour déterminer quel pourcentage de paiement anticipé s'applique à chaque ligne vente, le système recherche le pourcentage de paiement anticipé dans l'ordre suivant et applique la première valeur par défaut qu'il trouve :  

1. Un pourcentage de paiement anticipé pour l'article figurant dans la ligne et le client auquel la commande est destinée ;  
2. un pourcentage de paiement anticipé pour l'article figurant dans la ligne et le groupe prix client auquel le client appartient ;  
3. un pourcentage de paiement anticipé pour l'article figurant dans la ligne pour tous les clients ;  
4. le pourcentage de paiement anticipé figurant dans l'en-tête vente ou achat.  

Autrement dit, le pourcentage de paiement anticipé figurant dans la fiche client ne s'applique que si aucun pourcentage de paiement anticipé n'est configuré pour l'article. Toutefois, si vous modifiez le contenu du champ **% acompte** dans l'en\-tête vente ou achat après avoir créé les lignes, le pourcentage d'acompte figurant dans toutes les lignes est mis à jour. Cela facilite la création d'une commande avec un pourcentage de paiement anticipé fixe, quel que soit le pourcentage configuré pour les articles.

## Pour libérer automatiquement les documents de vente lorsque des paiements anticipés sont appliqués

Vous pouvez gagner du temps en configurant une écriture file d’attente des travaux qui libérera automatiquement les documents de vente nécessitant un paiement anticipé une fois les paiements appliqués. L’automatisation du processus vous évite l’étape de validation du document de vente.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.
2. Dans le champ **Fréquence de mise à jour automatique du paiement anticipé**, spécifiez la fréquence d’exécution de l’écriture file d’attente des travaux.

> [!TIP]
> Pendant que vous y êtes, envisagez d’ajouter une protection contre l’expédition ou la facturation de documents de vente comportant des montants de paiement anticipé impayés. Si vous cochez l’option **Vérifier paiement anticipé lors du report**, [!INCLUDE[prod_short](includes/prod_short.md)] empêchera de reporter des commandes comportant des montants de paiement anticipé impayés.

3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures file d’attente des travaux**, puis sélectionnez le lien associé.
4. Configurez l’écriture file d’attente des travaux **Mise à jour Paiement anticipé en attente Ventes**, par exemple, en utilisant les paramètres du raccourci **Récurrence** pour programmer sa fréquence d'exécution. Pour plus d’informations, voir [Utiliser des files d’attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## Voir aussi .  

[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Calculer la taxe sur les biens et services pour les paiements anticipés en Australie](LocalFunctionality/Australia/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Calculer la taxe sur les biens et services pour les paiements anticipés en Nouvelle-Zélande](LocalFunctionality/NewZealand/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Familiarisation avec le grand livre et les COA](finance-general-ledger.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
