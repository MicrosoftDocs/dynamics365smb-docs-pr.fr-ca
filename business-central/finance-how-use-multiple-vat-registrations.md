---
title: Plusieurs numéros d’enregistrement à la TVA
description: Découvrez la fonctionnalité permettant d’utiliser plusieurs numéros d’enregistrement de taxe sur la valeur ajoutée (TVA) (alternatifs).
author: altotovi
ms.topic: conceptual
ms.reviewer: null
ms.search.keywords: 'VAT, multiple, alternative, customer, tax, value-added tax'
ms.search.form: '212, 301,'
ms.date: 08/21/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# <a name="multiple-vat-registration-numbers"></a>Plusieurs numéros d’enregistrement à la TVA

Pour les entreprises disposant d’entrepôts dans plusieurs pays de l’UE, la gestion de la TVA (taxe sur la valeur ajoutée) peut être difficile, car chaque emplacement d’entrepôt nécessite un numéro de TVA différent pour se conformer aux réglementations spécifiques de chaque pays. Cet article fournit des informations sur cette exigence et explique la fonctionnalité permettant d’obtenir plusieurs numéros d’enregistrement de taxe sur la valeur ajoutée (TVA). Cette fonctionnalité permet aux utilisateurs de configurer des numéros d’enregistrement fiscal pour leurs clients dans différents pays/régions.  

> [!NOTE]
> La fonctionnalité *Numéros de TVA multiples pour les clients* est disponible uniquement à partir de Business Central 2024 vague de lancement 2 (version 25).

## <a name="how-to-set-up-the-alternative-vat-registration-numbers"></a>Comment configurer les numéros d’enregistrement de TVA alternatifs

Pour configurer les numéros d’enregistrement de TVA alternatifs pour différents pays/régions, suivre ces étapes : 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Enregistrement TVA du client alternatif**, puis Sélectionner le lien associé. 
2. Ajoutez le client dans le champ  **Numéro de client** et le pays/la région associé à cette inscription à la TVA dans le **Code pays/région de TVA**.  
3. Vous devez ajouter le numéro de TVA dans le champ **Numéro d’enregistrement TVA** . Vous devez respecter le format lorsque vous utilisez le  **code pays/région**. 
4. Si vous souhaitez utiliser différents groupes de comptabilisation TVA ou généraux, vous pouvez également les ajouter à la configuration dans les champs  **Groupe de comptabilisation TVA** et **Groupe de comptabilisation générale** . 
5. Fermez la page.   

Pour créer une adresse alternative pour votre client, suivre les étapes :  

1. Ouvrez le **Client** carte pour le client auquel vous souhaitez ajouter une nouvelle **adresse de livraison**. 
2. Sélectionner **Client**, puis choisissez l’action **Adresses de livraison** .   
3. La page  **Liste d’adresses de livraison** s’ouvre et sélectionnez **Nouveau**. 
4. Remplissez les informations sur la destination de livraison de votre client.  
5. Choisissez le code de pays/région approprié. **·**   
6. Si vous avez déjà configuré un nouveau **numéro d’enregistrement de TVA** sur **l’enregistrement de TVA du client alternatif** pour ce pays ou cette région, rien ne se passera. 
7. Mais si vous n’avez pas configuré le **Numéro d’enregistrement de TVA** précédemment sur **Enregistrement TVA client alternatif** pour ce pays ou cette région, la notification suivante s’affiche : **Cliquez sur Ajouter si vous souhaitez insérer l’enregistrement TVA alternatif pour ce code de pays de livraison.** 
8. Une notification apparaît comme un avertissement vous indiquant que vous devez ajouter un nouveau numéro de TVA. Pour ce faire, vous devez choisir l’action  **Ajouter** sur la notification et la page  **Enregistrement de TVA du client alternatif** s’ouvre. 
9. Cette page renseigne votre **numéro de client.** Et le **code pays/région de TVA**. Il vous suffit donc d’ajouter la configuration que vous souhaitez utiliser. 

## <a name="work-with-the-sales-documents"></a>Utiliser les documents de vente

Vous pouvez créer une nouvelle [facture de vente](sales-how-invoice-sales.md) ou [commande de vente](sales-how-sell-products.md) dans [!INCLUDE[prod_short](includes/prod_short.md)]. Si vous devez utiliser une adresse de livraison différente de l’adresse du client et située dans un autre pays, suivre les étapes :  

### <a name="alternate-shipping-address"></a>Adresse de livraison alternative

1. Développez l’onglet rapide  **Expédition et facturation** .   
2. Dans le champ Expédier à, choisissez l’option  **Adresse de livraison alternative** . 
3. La page  **Liste d’adresses de livraison** avec les adresses alternatives disponibles s’affiche. 
4. Choisissez l’une des adresses avec différents **codes de pays/région**. 
5. La page de dialogue  **Confirmer l’enregistrement alternatif de la TVA du client** apparaît avec une liste de champs que vous avez modifiés en raison du changement de configuration de l’ **enregistrement alternatif de la TVA du client** . 
6. Sélectionner **OK** pour confirmer.   

> [!NOTE]
> Si vous ne souhaitez plus confirmer un tel choix, vous pouvez Sélectionner le champ  **Ne plus afficher**  et à l’avenir vous ne verrez plus ce type de notification concernant les modifications. Mais si vous souhaitez le réactiver, vous pouvez le faire en activant le champ  **Confirmer l’enregistrement alternatif à la TVA** dans la **Configuration de la TVA**.  
   
7. Une fois que vous avez confirmé, les valeurs sont écrasées par les valeurs de la configuration de l’ **Enregistrement de TVA du client alternatif** . Vous pouvez vérifier tous les champs liés à la TVA qui se trouvent sous l’onglet rapide  **Détails de la facture** .  
8. Validez le document.  

### <a name="custom-address"></a>Adresse personnalisée

Si vous n’avez pas configuré l’adresse de livraison mais que vous souhaitez néanmoins utiliser une adresse différente pour l’expédition, vous pouvez utiliser cette option.  

1. Développez l’onglet rapide  **Expédition et facturation** .   
2. Dans le champ Expédier à, choisissez l’option  **Adresse personnalisée** .  
3. Modifiez le pays dans le champ **Pays/Région** .  
4. Une fois que vous avez modifié le code pays/région pour qu’il corresponde au **code pays/région de TVA** de l’ **enregistrement TVA du client alternatif**, la page de dialogue **Confirmer l’enregistrement TVA du client alternatif**  s’affiche avec une liste de champs qui ont été modifiés. 
5. [!INCLUDE[prod_short](includes/prod_short.md)] modifiera également tous les champs liés à la TVA qui se trouvent sous l’onglet rapide  **Détails de la facture** .  

### <a name="work-with-no-shipment"></a>Travailler sans expédition

S’il n’y a pas d’expédition en tant que processus, vous pouvez toujours tirer parti de la configuration de l’ **enregistrement alternatif de la TVA du client** .

Dans la commande client ou la facture, vous pouvez trouver le **Code pays/région de TVA** sous l’onglet rapide **Détails de la facture** et spécifier la valeur qui correspond à la configuration **Enregistrement TVA client alternatif** . Et vous devriez voir la même page de dialogue de confirmation que ci-dessus. 

Dans cette situation, vous pouvez publier une facture de vente avec le numéro d’enregistrement de TVA approprié pour votre client, même si vous n’expédiez pas d’articles avec ce document. **·**  

### <a name="work-with-the-sales-credit-memo"></a>Travailler avec la note de crédit de vente

Une fois que vous avez enregistré la facture avec une **adresse de livraison** ou **code pays/région de TVA** qui comporte des données de comptabilisation différentes, la **note de crédit de vente** corrective prend les valeurs de l’en-tête **Facture de vente enregistrée** où ces valeurs sont extraites de **l’enregistrement TVA du client alternatif**, donc aucune autre action n’est requise. 

## <a name="see-also"></a>Voir aussi .

[Présentation de la gestion de la TVA](finance-manage-vat.md)    
[Mettre en place la TVA](finance-setup-vat.md)    
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)    
[Déclarer la TVA à une autorité fiscale](finance-how-report-vat.md)    
[Fonctionnalités locales dans Business Central](about-localization.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
