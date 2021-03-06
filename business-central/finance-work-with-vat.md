---
title: Procédure d'utilisation de la TVA sur les ventes et les achats | Microsoft Docs
description: Cette rubrique décrit comment effectuer des tâches telles que la correction de la TVA reportée. Dans les pays/régions de l'UE, chaque transaction de vente et d'achat est soumise à des calculs de TVA. Elle décrit la procédure à suivre.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, sales, purchases,
ms.date: 04/01/2021
ms.author: bholtorf
ms.openlocfilehash: ec880df940816b68a9b6f8a82098985471720984
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5781566"
---
# <a name="work-with-vat-on-sales-and-purchases"></a>Utiliser la TVA sur les ventes et les achats
Si votre pays ou région vous demande de calculer la TVA sur les transactions de vente et d'achat afin de pouvoir déclarer les montants à une administration fiscale, vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour calculer automatiquement la TVA sur les documents vente et achat. Pour plus d'informations, voir [Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md).

Il existe, cependant, certaines tâches associées à la TVA que vous pouvez effectuer manuellement. Par exemple, vous devrez peut-être corriger un montant reporté si vous découvrez qu'un fournisseur utilise un mode d'arrondissement différent.  

> [!TIP]
> Vous pouvez laisser [!INCLUDE[prod_short](includes/prod_short.md)] valider les numéros d’identification intracommunautaire et d’autres informations compagnie lorsque vous créez ou mettez à jour des documents. Pour plus d’informations, consultez [Valider des numéros d’identification intracommunautaire](finance-how-validate-vat-registration-number.md).

## <a name="calculating-and-displaying-vat-amounts-in-sales-and-purchase-documents"></a>Calcul et affichage des montants de TVA dans des documents achat et vente  
Vous pouvez calculer et afficher des montants de TVA dans des documents achat et vente de façon différente, en fonction du type de client ou de fournisseur avec lequel vous traitez. Vous pouvez également remplacer le montant de TVA calculé pour qu'il corresponde au montant de TVA calculé par le fournisseur sur une transaction donnée.  

### <a name="unit-price-and-line-amount-includingexcluding-vat-on-sales-documents"></a>Prix unitaire et montant ligne incluant/excluant la TVA sur les documents vente  
Lorsque vous sélectionnez un numéro d'article dans le champ **N°** d'un document vente, [!INCLUDE[prod_short](includes/prod_short.md)] renseigne le champ **Prix unitaire**. Le prix unitaire provient de la fiche **Article** ou des prix article autorisés pour l'article et le client. [!INCLUDE[prod_short](includes/prod_short.md)] calcule le **Montant ligne** lorsque vous entrez une quantité pour la ligne.  

Si vous vendez au détail à des consommateurs, vous souhaitez peut-être que les documents vente incluent la TTC. Pour ce faire, activez la case à cocher **Prix TTC** du document.  

### <a name="including-or-excluding-vat-on-prices"></a>Inclusion ou exclusion de la TVA sur les prix
Si la case à cocher **Prix TTC** est activée sur un document vente, les champs **Prix unitaire** et **Montant ligne** incluent la TVA, ce que les noms de champ reflètent également. Par défaut, la TVA n'est pas incluse dans ces champs.  

Si le champ n'est pas sélectionné, l'application renseigne les champs **Prix unitaire** et **Montant ligne** en excluant la TVA, ce que reflètent les noms de champ.  

Vous pouvez configurer les paramètres par défaut de **Prix TTC** pour tous les documents vente relatifs à un client dans le champ **Prix TTC** sur la fiche **Client**. Vous pouvez également configurer des prix article pour inclure ou exclure la TVA. Normalement, les prix article contenus dans la fiche article sont les prix hors TVA. L'application utilise les informations du champ **Prix TTC** de la fiche **Article** pour déterminer le prix unitaire pour les documents vente.  

Le tableau suivant montre comment l'application calcule les montants de prix unitaire pour un document vente lorsque vous n'avez pas configuré de prix sur la page **Prix vente** :  

|**Le prix inclut le champ TVA sur la fiche client.**|**Prix incluant le champ TVA dans l'en-tête vente**|**Action exécutée**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|Désactivé|Désactivé|Le champ **Prix unitaire** de la fiche article est copié dans le champ **Prix unitaire HT** dans les lignes vente.|  
|Désactivé|Activé|L'application calcule le montant de TVA par unité et l'ajoute au **Prix unitaire** sur la fiche article. Ce prix unitaire total est entré dans le champ **Prix unitaire TTC** dans les lignes vente.|  
|Activé|Désactivé|L'application calcule le montant de la TVA inclus dans le **Prix unitaire** sur la fiche article à l'aide du % TVA par rapport à la combinaison Gpe report marché TVA (prix) et Groupe de report produit TVA. Le **prix unitaire** sur la fiche article, moins le montant de la TVA, est ensuite saisi dans le champ **Prix unitaire HT** dans les lignes de vente.|  
|Activé|Activé|Le champ **Prix unitaire** de la fiche article est copié dans le champ **Prix unitaire TTC** dans les lignes vente.|

## <a name="correcting-vat-amounts-manually-in-sales-and-purchase-documents"></a>Correction manuelle des montants de TVA dans des documents achat et vente  
Vous pouvez apporter des corrections à des écritures TVA reportées. Cela permet de modifier les montants de TVA vente ou achat sans modifier la base de TVA. Vous pouvez avoir besoin d'apporter des modifications, par exemple, si vous recevez une facture d'un fournisseur qui n'a pas calculé correctement la TVA.  

Même si vous avez peut-être configuré une ou plusieurs combinaisons pour traiter la TVA à l'importation, vous devez configurer au moins un groupe de report produit TVA. Par exemple, vous pouvez l'appeler **CORRECT** à des fins de correction, à moins que vous puissiez utiliser le même compte général dans le champ **Compte TVA achat** sur la ligne des paramètres de comptabilisation TVA. Pour plus d'informations, voir [Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md).

Si un escompte de paiement a été calculé sur la base d'un montant de facture TTC, vous inversez la partie escompte de paiement du montant TVA lorsque l'escompte de paiement est accordé. Remarque : vous devez activer le champ **Ajust. pour esc. paiement** à la fois dans la configuration du grand livre en général et dans la configuration du report TVA, pour des combinaisons particulières d'un groupe de report de marché TVA et d'un groupe de report de produit TVA.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-sales-documents"></a>Pour configurer le système pour la saisie manuelle de la TVA dans les documents de vente
La section suivante explique comment activer les modifications manuelles de la TVA sur les documents de vente. Les étapes sont similaires sur la page **Configuration achats et à payer**.

1. Sur la page **Configuration du grand livre**, spécifiez une **Différence TVA max. autorisée** entre le montant calculé par l'application et le montant calculé manuellement.  
2. Dans la page **Paramètres ventes**, activez le champ **Autoriser différence TVA**.  

### <a name="to-adjust-vat-for-a-sales-document"></a>Pour ajuster la TVA pour un document vente  
1. Ouvrez le document de vente approprié.  
2. Sélectionnez l'action **Statistiques**.  
3. Dans l'organisateur **Facturation**, choisissez la valeur dans le champ **Nbre de lignes fiscales**.
4. Modifiez le champ **Montant TVA**.   

> [!NOTE]  
> Le montant de TVA total de la facture et l'identificateur TVA s'affichent dans les lignes. Vous pouvez ajuster les montants manuellement dans le champ **Montant TVA** des lignes correspondant à chaque identifiant TVA. Lorsque vous modifiez la valeur du champ **Montant TVA**, l'application vérifie que vous n'avez pas modifié la TVA d'une valeur supérieure à celle du montant spécifié comme différence maximale autorisée. Si le montant se situe en dehors de la plage **Différence TVA max. autorisée**, un avertissement s'affiche, indiquant la différence maximale autorisée. Vous ne pouvez pas poursuivre tant que le montant n'est pas ajusté conformément aux paramètres acceptables. Cliquez sur **OK** , puis entrez un autre **Montant TVA** s'inscrivant dans la plage autorisée. Si la différence TVA est inférieure ou égale à la différence maximale autorisée, la TVA est répartie de façon proportionnelle entre les lignes document ayant le même identificateur TVA.  

## <a name="calculating-vat-manually-using-journals"></a>Calcul manuel de la TVA à l'aide de journaux  
Vous pouvez également ajuster les montants TVA dans les journaux généraux, vente et achat. Par exemple, vous devrez peut-être le faire lorsque vous entrez une facture fournisseur dans votre journal et qu'il y a une différence entre le montant de TVA calculé par [!INCLUDE[prod_short](includes/prod_short.md)] et le montant de TVA figurant sur la facture que vous avez reçue du fournisseur.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-a-general-journals"></a>Pour configurer le système pour la saisie manuelle de la TVA dans les journaux généraux
Vous devez suivre les étapes suivantes avant de saisir manuellement la TVA dans un journal général.  

1. Sur la page **Configuration du grand livre**, spécifiez une **Différence TVA max. autorisée** entre le montant calculé par l'application et le montant calculé manuellement.  
2. Sur la page **Modèles journal général**, cochez la case **Autoriser différence TVA** pour la journal appropriée.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-a-sales-and-purchase-journals"></a>Pour configurer le système pour la saisie manuelle de la TVA dans les journaux vente et achat
Vous devez suivre les étapes suivantes avant de saisir manuellement la TVA dans un journal vente et achat.

1. Sur la page **Configuration achats et à payer**, cochez la case **Autoriser différence TVA**.  
2. Répétez l'étape 1 pour la page **Configuration ventes & à recevoir**.
3. Après avoir effectué la configuration décrite ci-avant, vous pouvez ajuster la valeur du champ **Montant TVA** de la ligne journal général ou du champ **Montant TVA contrepartie** de la ligne journal achat ou vente. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie que la différence n'est pas supérieure à la valeur maximale spécifiée.  

    > [!NOTE]  
    > Si la différence est supérieure, un avertissement s'affiche, indiquant la différence maximale autorisée. Pour continuer, vous devez ajuster le montant. Sélectionnez **OK**, puis entrez un montant compris dans la plage autorisée. Si la différence de TVA est inférieure ou égale à la valeur maximale autorisée, [!INCLUDE[prod_short](includes/prod_short.md)] affiche la différence dans le champ **Différence TVA**.  

## <a name="posting-import-vat-with-purchase-invoices"></a>Reporter la TVA à l'importation dans les factures achat
Au lieu d'utiliser des journaux comptabilité pour reporter une facture TVA importation, vous pouvez utiliser une facture achat.  

### <a name="to-set-up-purchasing-for-posting-import-vat-invoices"></a>Pour configurer les achats pour le report des factures TVA à l'importation  
1. Paramétrer une fiche fournisseur pour l'administration d'importation qui vous envoie la facture TVA à l'importation. Les champs **Groupe compta. marché** et **Groupe compta. marché TVA** doivent être configurés de la même manière que le compte général pour la TVA à l'importation.  
2. Créez un **Groupe compta. produit** pour la TVA importation et paramétrez un **Gpe compta. produit TVA défaut** (TVA importation) pour le **Groupe compta. produit** lié.  
3. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Plan comptable**, puis sélectionnez le lien associé.  
4. Sélectionnez le compte GL de TVA à l'importation, puis choisissez l'action **Modifier**.  
5. Sur le raccourci **Validation**, sélectionnez la configuration **Groupe compta. produit** pour importer la TVA. [!INCLUDE[prod_short](includes/prod_short.md)] renseigne automatiquement le champ **Groupe compta. produit TVA**.  
6. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du report général**, puis sélectionnez le lien associé.  
7. Créez une combinaison de **Groupe de report de marché** pour l'administration fiscale et de **Groupe de report de produit** pour la TVA d'importation. Pour cette nouvelle combinaison, dans le champ **Compte achat**, sélectionnez le compte du grand livre de la TVA à l'importation.  

### <a name="to-create-a-new-invoice-for-the-import-authority-vendor-once-you-have-completed-the-setup"></a>Pour créer une facture pour le fournisseur de l'administration d'importation, une fois la configuration terminée  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Créez une facture achat.  
3. Dans le champ **N° fournisseur**, sélectionnez le fournisseur de l'administration d'importation, puis cliquez sur **OK**.  
4. Sur la ligne achat, dans le champ **Type**, sélectionnez **Compte du grand livre** et dans le champ **N°**, sélectionnez le compte du grand livre TVA à l'importation.  
5. Dans le champ **Quantité**, tapez **1**.  
6. Dans le champ **Coût unitaire direct HT**, indiquez le montant de la TVA.  
7. Reportez la facture.  

## <a name="processing-certificates-of-supply"></a>Traitement des certificats d'approvisionnement
Lorsque vous vendez des biens à un client dans un autre pays/une autre région de l'UE, vous devez envoyer au client un certificat d'approvisionnement que le client doit signer et vous renvoyer. Les procédures suivantes servent à traiter les certificats d'approvisionnement pour des livraisons vente, mais les mêmes phases s'appliquent aux livraisons service des articles, ainsi qu'aux livraisons retour aux fournisseurs.  

### <a name="to-view-certificate-of-supply-details"></a>Pour afficher les détails d'un certificat d'approvisionnement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Sélectionnez **Détails certificat d'approvisionnement**.  
4. Par défaut, si la case **Certificat d'approvisionnement requis** est cochée pour la configuration du groupe de report TVA pour le client, le champ **État** est défini sur **Requis**. Vous pouvez mettre à jour le champ pour indiquer si le client a retourné le certificat.  

    > [!Note]  
    >  Si la configuration de groupes comptabilisation TVA n'a pas la case **Certificat d'approvisionnement requis** cochée, alors un enregistrement est créé et le champ **Statut** est défini sur **Non applicable**. Vous pouvez mettre à jour le champ pour tenir compte des informations d'état correctes. Vous pouvez modifier manuellement le statut de **Non applicable** en **Requis**, et de **Requis** en **Non applicable** selon vos besoins.  

   Lorsque vous mettez à jour le champ **Statut** sur **Requis**, **Reçu** ou **Non reçu**, un certificat est créé.  

    > [!TIP]  
    >  Vous pouvez utiliser la page **Certificats d'approvisionnement** pour obtenir une vue d'état de toutes les livraisons reportées pour lesquelles un certificat d'approvisionnement a été créé.  

5. Sélectionnez **Imprimer le certificat d'approvisionnement**.  

    > [!Note]  
    >  Vous pouvez afficher un aperçu ou imprimer le document. Lorsque vous choisissez **Imprimer le certificat d'approvisionnement** et que vous imprimez le document, la case à cocher **Imprimé** est automatiquement sélectionnée. En outre, s'il n'est pas déjà renseigné, le statut du certificat est mis à jour sur **Requis**. Si nécessaire, vous incluez le certificat imprimé avec la livraison.  

### <a name="to-print-a-certificate-of-supply"></a>Pour imprimer un certificat d'approvisionnement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Sélectionnez l'action **Imprimer le certificat d'approvisionnement**.  

    > [!NOTE]  
    >  Sinon, vous pouvez imprimer un certificat à partir de la page **Certificat d'approvisionnement**.  

4. Pour inclure des informations des lignes dans le document expédition sur le certificat d'approvisionnement, sélectionnez la case à cocher **Imprimer détails de ligne**.  
5. Cochez la case **Créer des certificats d'approvisionnement s'ils n'ont pas encore été créés** pour que [!INCLUDE[prod_short](includes/prod_short.md)] crée des certificats pour les livraisons reportées qui n'en ont pas au moment de l'exécution. Lorsque vous cochez la case, de nouveaux certificats sont créés pour toutes les livraisons reportées qui n'ont pas de certificats compris dans la plage sélectionnée.  
6. Par défaut, les paramètres de filtre concernent le document livraison que vous avez sélectionné. Renseignez les informations de filtre pour sélectionner un certificat d'approvisionnement spécifique à imprimer.  
7. Dans la page **Certificat d'approvisionnement**, sélectionnez l'action **Imprimer** pour imprimer le rapport ou l'action **Aperçu** pour l'afficher à l'écran.  

    > [!Note]  
    > Le champ **État Certificat d'approvisionnement** et le champ **Imprimé** sont mis à jour pour la livraison sur la page **Certificats d'approvisionnement**.  

8. Envoyez le certificat d'approvisionnement imprimé au client pour signature.  

### <a name="to-update-the-status-of-a-certificate-of-supply-for-a-shipment"></a>Pour mettre à jour l'état d'un certificat d'approvisionnement pour une livraison  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Dans le champ **Statut**, sélectionnez l'option appropriée.  

   Si le client a retourné le certificat d'approvisionnement signé, choisissez **Reçu**. Le champ **Date de réception** est mis à jour. Par défaut, la date de réception est configurée sur la date de travail actuelle.  

   Vous pouvez modifier la date pour tenir compte de la date à laquelle vous avez reçu le certificat d'approvisionnement signé du client. Vous pouvez également ajouter un lien vers le certificat signé à l'aide des liaisons standard de [!INCLUDE[prod_short](includes/prod_short.md)].  

   Si le client ne retourne pas le certificat d'approvisionnement signé, choisissez **Non reçu**. Vous devez envoyer au client une nouvelle facture qui inclut la TVA, parce que la facture initiale ne sera pas acceptée par l'administration fiscale.  

Pour afficher un groupe de certificats, vous commencez à partir de la page **Certificats d'approvisionnement**, puis mettez à jour les informations concernant l'état des certificats en attente à mesure que vous les recevez de la part de vos clients. Ceci peut être utile si vous souhaitez rechercher tous les certificats ayant un certain statut, par exemple, **Requis**, si vous souhaitez mettre à jour leur statut en **Non reçu**.  

### <a name="to-update-the-status-of-a-group-of-certificates-of-supply"></a>Pour mettre à jour l'état d'un groupe de certificats d'approvisionnement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Certificats d'approvisionnement**, puis sélectionnez le lien associé.  
2. Filtrez le champ **Statut** sur la valeur que vous souhaitez afin de créer la liste des certificats que vous souhaitez gérer.  
3. Pour mettre les informations d'état à jour, sélectionnez **Modifier la liste**.  
4. Dans le champ **Statut**, sélectionnez l'option appropriée.  

   Si le client a retourné le certificat d'approvisionnement signé, choisissez **Reçu**. Le champ **Date de réception** est mis à jour. Par défaut, la date de réception est configurée sur la date de travail actuelle.  

   Vous pouvez modifier la date pour tenir compte de la date à laquelle vous avez reçu le certificat d'approvisionnement signé. Vous pouvez également ajouter un lien vers le certificat signé à l'aide des liaisons de document standard de [!INCLUDE[prod_short](includes/prod_short.md)].  

    > [!NOTE]  
    >  Vous ne pouvez pas créer un nouveau certificat d'approvisionnement sur la page **Certificat d'approvisionnement** lorsque vous y accédez à l'aide de cette procédure. Pour créer un certificat pour une livraison qui n'a pas été configurée pour en exiger, ouvrez la livraison vente reportée et utilisez l'une des deux procédures décrites ci-dessus :  
    >
    > * Pour créer manuellement un certificat d'approvisionnement.  
    > * Pour imprimer un certificat d'approvisionnement.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/process-vat-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi

[Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md)  
[Déclarer la TVA à une autorité fiscale](finance-how-report-vat.md)  
[Valider un numéro d'identification intracommunautaire](finance-how-validate-vat-registration-number.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
