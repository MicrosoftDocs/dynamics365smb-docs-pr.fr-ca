---
title: 'Suivi des articles avec les numéros de lot, de série et de paquet'
description: 'Vous pouvez ajouter des numéros de série, de lot et de paquet à n’importe quel document sortant ou entrant, puis afficher les écritures traçabilité reportées dans les écritures article correspondantes.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.forms: '6503, 6515, 6513, 6512, 6502, 6506, 6501, 6510, 6507, 6500, 6505, 6508, 9126, 6526, 6516, 6511, 6504, 6509, 163, 6550,'
ms.date: 05/16/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="track-items-with-serial-lot-and-package-numbers"></a>Suivi des articles avec les numéros de lot, de série et de paquet

Vous pouvez attribuer des numéros de série, lot et de paquet à n’importe quel document sortant ou entrant, et ses écritures traçabilité reportées s'affichent dans les écritures article correspondantes. Vous effectuez le suivi sur la page **Lignes traçabilité**, que vous pouvez ouvrir depuis les documents entrants ou sortants.

Les champs de quantité figurant en haut de la page **Lignes traçabilité** affichent les quantités et les sommes des numéros traçabilité qui sont définis dans les lignes. Les quantités doivent correspondre à celles des lignes du document, ce qui est indiqué par *0* dans les champs **Non défini** .

[!INCLUDE [prod_short](includes/prod_short.md)] met à jour les informations de disponibilité sur la page **Lignes traçabilité** lorsque vous ouvrez la page. Elle ne met pas à jour les informations de disponibilité pendant que la page est ouverte, même si des modifications sont apportées dans l'inventaire ou sur d’autres documents à ce moment-là.

> [!NOTE]  
> Pour que les fonctionnalités décrites dans cet article fonctionnent, vous devez d’abord configurer le suivi des articles. Pour plus d’informations, voir [Configurer le suivi des articles avec les numéros lot, de série et de récépissé](inventory-how-setup-item-tracking.md).

## <a name="item-tracking-availability"></a>Disponibilité de la traçabilité

Lorsque vous travaillez avec des numéros de série, lot et paquets, [!INCLUDE[prod_short](includes/prod_short.md)] calcule les informations de disponibilité et les affiche dans les diverses pages de traçabilité. Cela vous permet de savoir l’utilisation d’un numéro lot, de série ou de paquet sur d’autres documents. Ces informations réduisent les erreurs et incertitudes liées aux doubles affectations.

Sur la page **Lignes traçabilité**, une icône d’avertissement peut s’afficher dans le champ **Disponibilité, N° de lot** ou **Disponibilité, n° de série** pour les raisons suivantes :

* Si une partie ou la totalité de la quantité que vous avez sélectionnée est déjà utilisée dans d’autres documents.
* Si le numéro de lot ou de série n’est pas disponible.

Les pages **Liste information n° de lot/n° de série**, **Disponibilité n° de lot/n° de série** et **Traçabilité - Sélectionner écritures** affichent la quantité utilisée d’un article. Le tableau suivant répertorie les champs pertinents.

|Champ|Désignation|
|-----|-----------|  
|**Quantité totale**|Nombre total d’articles actuellement en inventaire.|
|**Quantité totale demandée**|nombre total d'articles demandés pour être utilisés dans ce document et dans d'autres ;|
|**Quantité présentement en suspens**|Nombre d’articles demandés dans le document actuel, mais qui ne sont pas reportés.|
|**Quantité présentement demandée**|Nombre d'articles demandés qui seront utilisés dans le document actuel|
|**Quantité totale disponible**|Nombre total d’articles en inventaire, moins la quantité d’articles demandés dans ce document et dans d’autres (quantité totale demandée), moins la quantité demandée mais pas encore reportée dans ce document (quantité suspendue actuelle)|

Si vous travaillez sur la page  **Lignes de suivi des articles** pendant une longue période, ou s’il y a beaucoup d’activités avec l’article avec lequel vous travaillez, vous pouvez choisir l’action  **Actualiser la disponibilité** . En outre, la disponibilité de l’article est automatiquement revérifiée lorsque vous fermez la page afin de confirmer qu’il n’y a pas de problème de disponibilité.

## <a name="to-assign-serial-or-lot-numbers-during-an-inbound-transaction"></a>Pour affecter des numéros de série ou de lot lors d'une transaction entrante

Vous souhaiterez peut-être suivre les articles dès leur arrivée. Dans ce cas, le bon de commande est souvent le document central. Cependant, vous pouvez effectuer la traçabilité depuis n'importe quel document entrant, et ses écritures reportées s'affichent dans les écritures articles correspondantes.

Les numéros de suivi sont automatiquement transférés à toutes les activités de l’entrepôt de sortie.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.  
2. Ouvrez un bon de commande existant ou créez-en un.
3. Sélectionnez la ligne document et dans le récapitulatif **Lignes**, sélectionnez l’action **Ligne**, puis l’action **Lignes traçabilité** pour ouvrir la page **Modifier – Lignes traçabilité**.  

   Vous pouvez affecter des numéros de série ou de lot. Pour cela, il existe plusieurs méthodes :  
   * Automatiquement, en sélectionnant **Traiter**, puis **Affecter n° de série** ou **Affecter n° lot** pour affecter des numéros de série/lot issus de séries de numéros prédéfinies.  
   * Automatiquement, en sélectionnant **Traiter**, puis **Créer n° de série personnalisé** pour affecter des numéros de série/lot en fonction des séries de numéros définies spécifiquement pour les articles livrés.  
   * Manuellement, en entrant les numéros de série ou de lot (par exemple, les numéros fournisseur).  
   * Manuellement, en affectant un numéro spécifique à chaque article.  

4. Pour affecter automatiquement, choisissez l'action **Créer n° de série personnalisé**.  
5. Dans le champ **Numéro de série perso.**, entrez le numéro de départ d'une série de numéros de série descriptifs. Par exemple **S/N-Vend0001**.  
6. Dans le champ **Incrément**, entrez 1 afin que la valeur des numéros augmente de un en un.  

    Le champ **Quantité à créer** affiche la quantité de lignes par défaut ; elle est modifiable.  

7. Cochez la case **Créer nouv. n° lot** pour organiser les nouveaux numéros de série dans un lot distinct.  
8. Cliquez sur le bouton **OK**.  

[!INCLUDE [prod_short](includes/prod_short.md)] crée un numéro de lot avec différents numéros de série en fonction de la quantité d’articles de la ligne document. Le numéro est accompagné d’un préfixe de la valeur que vous avez saisie dans le champ **SN personnalisé**. Par exemple, commençant par **S/N-Vend0001**.  

Les champs de quantité figurant dans l’en-tête du formulaire affichent de façon dynamique les quantités et les sommes des numéros traçabilité que vous définissez sur la page. Les quantités doivent correspondre à celles des lignes document dont les champs **Non défini** sont paramétrés sur **0**.  

Lorsque vous reportez le document, les écritures traçabilité sont transférées vers les écritures article.

### <a name="to-handle-serial-and-lot-numbers-when-getting-receipt-lines-from-a-purchase-invoice"></a>Pour traiter les numéros de série et de lot lors de l'obtention des lignes réception à partir d'une facture achat

Lorsque vous obtenez des lignes réception ou livraison reportées à partir des factures ou notes de crédit associées, les lignes traçabilité sur les documents entrepôt sont transférées automatiquement. Cependant, elles sont traitées d’une manière particulière.

La fonctionnalité prend en charge les processus entrants suivants :  

* **Extraire lignes réception**, à partir d'une facture achat.  
* **Extraire lignes livraison retour**, à partir d'une note de crédit achat.  

La fonctionnalité prend en charge les processus sortants suivants :  

* **Extraire lignes livraison**, à partir d'une facture vente ou de livraisons regroupées.  
* **Extraire lignes récept. retour**, à partir d'une note de crédit vente.  

Dans ces cas, les lignes traçabilité sont transférées dans la facture ou la note de crédit, mais la page **Lignes traçabilité** ne vous permet pas de changer les numéros de série ou de lot. Vous pouvez modifier uniquement les quantités.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Ouvrez une facture achat pour les articles achetés avec des numéros de série ou de lot.  
3. À partir d'une ligne facture achat, sur le raccourci **Lignes**, sélectionnez l'action **Extraire lignes réception**.  
4. Sur la page **Extraire lignes réception**, sélectionnez la ligne réception avec des lignes traçabilité, puis cliquez sur le bouton **OK**.  

    Le document origine est copié dans la facture achat comme nouvelle ligne, et ses lignes traçabilité sont quant à elles copiées sur la page **Lignes traçabilité** sous-jacente.  

5. Sur la facture achat, sélectionnez la ligne réception transférée.  
6. Sur le raccourci **Lignes**, choisissez l’action **Ligne**, puis choisissez l’action **Lignes traçabilité** pour trouver les lignes traçabilité.  

Vous ne pouvez pas modifier les champs **N° de série** et **N° de lot**. Vous pouvez toutefois supprimer des lignes entières ou modifier les quantités pour refléter les modifications apportées à la ligne origine.  

## <a name="to-assign-a-serial-or-lot-number-during-an-outbound-transaction"></a>Pour affecter un numéro de série ou de lot lors d'une transaction sortante

Le traitement en sortie des numéros de série ou de lot est une tâche fréquente qui est réalisée au cours de différents processus entrepôt. Il existe deux méthodes pour ajouter des numéros de série et de lot aux transactions sortantes :  

- Sélectionnez parmi les numéros de série ou de lot existants. Cela s’applique lorsque des numéros traçabilité ont été affectées au cours d’une transaction entrante.
- Affectez des numéros de série ou de lot lors de transactions sortantes. Cela s’applique lorsque des numéros traçabilité ne sont pas affectés à des articles jusqu’à ce qu’ils soient vendus et prêts à être livrés.

### <a name="to-select-from-existing-serial-or-lot-numbers"></a>Pour effectuer une sélection parmi les numéros de série ou de lot existants

Lorsque vous travaillez sur des articles nécessitant une traçabilité et que vous créez des transactions sortantes, vous devez généralement sélectionner des numéros de lot ou de série qui existent déjà.

1. Dans un document sortant, sélectionnez la ligne pour laquelle vous souhaitez sélectionner des numéros de série ou de lot.  
2. Sur le raccourci **Lignes**, choisissez l’action **Ligne**, puis **Informations connexes**, puis sélectionnez **Lignes traçabilité**.  
3. Sur la page **Lignes traçabilité**, vous disposez de trois options pour spécifier un numéro de lot ou de série :  

   * Sélectionnez le champ **N° de série**, puis sélectionnez un nombre sur la page **Liste n° de série**.
   * Sélectionnez le champ **N° lot**, puis sélectionnez un nombre sur la page **Liste n° lot**. Puis, sélectionnez le champ **N° de série**, puis sélectionnez un nombre sur la page **Liste n° de série**.
   * Cliquez sur l’action **Traitement**, puis sur **Sélectionner les entrées**. La page **Sélectionner écritures** affiche tous les numéros de série et de lot en même temps que les informations de disponibilité.

4. Dans le champ **Quantité sélectionnée**, entrez la quantité de chaque numéro de lot ou de série à utiliser.
5. Cliquez sur le bouton **OK**. Les informations de traçabilité sont transférées vers la page **Lignes traçabilité**.  

Les champs de quantité figurant dans l’en-tête du formulaire affichent de façon dynamique les quantités et les sommes des numéros traçabilité que vous définissez sur la page. Les quantités doivent correspondre à celles de la ligne document dont les champs **Non défini** sont paramétrés sur **0**.  

Lorsque vous reportez la ligne document, les informations de traçabilité sont transférées vers les écritures article associées.

### <a name="to-assign-new-serial-or-lot-numbers"></a>Pour affecter les nouveaux numéros lot ou de série

Ce processus s’applique lorsque les articles n’ont pas de numéro de série ou de lot alors qu’ils sont en inventaire. Vous affectez plutôt des numéros traçabilité lorsque les articles sont vendus et prêts à être livrés. Dans ce cas, vous attribuerez généralement les numéros à partir d’une série de numéros prédéfinie.

1. Sélectionnez le document pertinent, par exemple une facture de vente ou un document de vente et, sur le raccourci **Lignes**, choisissez l’action **Ligne**, puis **Informations connexes**, puis sélectionnez l’action **Lignes traçabilité**.  

    Vous pouvez affecter des numéros traçabilité. Pour cela, il existe plusieurs procédures :  
    * Automatiquement, à partir d'une série de numéros prédéfinie : sélectionnez l’action **Affecter n° de série** ou **Affecter n° de lot**.  
    * Automatiquement, en fonction des paramètres définis spécifiquement pour les articles sortants : sélectionnez l'action **Créer n° de série personnalisé**.  
    * Manuellement, en entrant des numéros de série ou de lot sans utiliser de séries de numéros.  

2. Pour cette procédure, affectez automatiquement un numéro de série en choisissant **Affecter n° de série**  

    Le champ **Quantité à créer** affiche la quantité de lignes par défaut ; vous pouvez la modifier.  
3. Sélectionnez le champ **Créer nouv. n° lot** pour organiser les nouveaux numéros de série dans un lot distinct.  
4. Choisissez le bouton **OK** pour créer un numéro de lot et de nouveaux numéros de série en fonction de la quantité d'articles à traiter sur la ligne document correspondante.  

Les champs de quantité figurant en haut s’affichent de façon dynamique les quantités et les sommes des numéros traçabilité que vous définissez sur la page. Les quantités doivent correspondre à celles de la ligne document dont les champs **Non défini** sont paramétrés sur **0**.  

Lorsque le document est reporté, les écritures traçabilité sont transférées vers les écritures article.

### <a name="assign-tracking-numbers-on-source-documents"></a>Attribuer des numéros de suivi sur les documents sources

Certaines compagnies définissent des numéros de série ou de lot spécifiques sur le document source, tel que les documents de vente. Par exemple, si un client demande un lot spécifique. Lorsque vous créez le document prélèvement inventaire ou prélèvement entrepôt à partir d’un document source sortant sur lequel les numéros de série ou de lot sont déjà définis, vous ne pouvez pas modifier les champs de la page **Lignes traçabilité** dans le prélèvement inventaire. La seule exception est le champ **Qté à traiter**. Dans ce cas, les lignes prélèvement inventaire indiquent les numéros traçabilité sur chaque ligne prélèvement et rangement. La quantité est déjà répartie dans des combinaisons de numéros de série ou lot uniques, car le document de vente spécifie les numéros traçabilité à livrer.

## <a name="to-handle-serial-and-lot-numbers-on-transfer-orders"></a>Pour traiter les numéros de série et de lot dans les ordres de transfert

Les procédures de traitement des numéros de série et de lot transférés entre les différents emplacements sont similaires à celles qui sont affectées lorsque les articles sont achetés et vendus.  

Toutefois, les ordres de transfert sont uniques dans le sens où la livraison et la réception sont effectuées à partir de la même ligne transfert et, par conséquent, utilisent la même instance de la page **Lignes traçabilité**. Les numéros traçabilité qui ont été livrés à partir d’un emplacement doivent être reçus intacts dans l’autre emplacement.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Ordres de transfert**, puis sélectionnez le lien associé.  
2. Ouvrez l'ordre de transfert à traiter. Dans le raccourci **Lignes**, cliquez sur l’action **Ligne**, sélectionnez l’action **Lignes traçabilité**, puis sélectionnez l’action **Livraison**.  
3. Sur la page **Lignes traçabilité**, affectez ou sélectionnez des numéros de série ou de lot, comme pour toute autre transaction article sortante.  

    Lorsque vous traitez les numéros de série et de lot d’articles transfert, les numéros sont généralement déjà affectés. Par conséquent, vous choisirez souvent parmi les numéros de série ou de lot existants.  

4. Reportez l'ordre de transfert (livraison, puis réception) afin d'enregistrer que les articles sont transférés et qu'ils portent leurs écritures traçabilité.  

Au cours du transfert, vous ne pouvez pas changer les valeurs sur la page **Lignes traçabilité**.  

## <a name="to-record-additional-serial-or-lot-number-information"></a>Pour enregistrer des informations supplémentaires relatives au numéro de série ou de lot

Vous pouvez lier des informations particulières à un numéro traçabilité, par exemple pour l’assurance qualité, sur une fiche informations de numéro de série/lot.

1. Ouvrez un document qui comporte des numéros de série ou de lot affectés.
2. Ouvrez la page **Lignes traçabilité** de l’article pour lequel vous souhaitez saisir des informations.
3. Choisissez l’action **Ligne** et ensuite, par exemple, l’action **Carte d’information sur le n° de série**.  
4. Choisissez le signe plus **(+)** en haut de la liste pour créer une entrée. Les champs **N° de série** et **N° lot** sont préremplis à partir de la ligne traçabilité.
5. Entrez des informations courtes dans le champ **Description**, par exemple sur l'état de l'article.  
6. Choisissez l’action **Association**, **N° de série**, puis l’action **Commentaire** pour créer un enregistrement de commentaire séparé.  
7. Sélectionnez le champ **Bloqué** pour exclure l’ancien n° lot ou de série de toutes les transactions.  

<!--If you create serial numbers in bulk by using the **Create Customized SN** or **Assign Serial No.** actions, you can enable **Create SN Information** and an information card will be created for each tracking line.

Alternatively, you can create an information card when you post journals or documents. On the **Item Tracking Code** page, turn on the **Create SN Info. on posting** or **Create SN Info. on posting** toggles. -->

Vous pouvez modifier ultérieurement les fiches d’informations de série ou de lot créées.

## <a name="to-modify-existing-serial-or-lot-number-information"></a>Pour modifier des informations relatives au numéro de série ou de lot

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2. Sélectionnez un article qui comporte un code traçabilité et des informations de numéro de série ou de lot.
3. À partir de la page **Élément n°carte**, choisissez l’action **Associée**, choisissez l’action **Associée**, choisissez l’action **Entrées**, puis choisissez **Écritures du grand livre**.
4. Cliquez sur le champ **N° lot** ou **N° de série**. S'il existe des informations en relation avec ce numéro de traçabilité article, alors la page **Liste information n° lot** ou **Liste information n° de série** s'ouvre.  
5. Sélectionnez une fiche, puis choisissez l'action **Fiche information n° lot/série**.  
6. Modifiez le texte court de description, l'enregistrement de commentaire ou le champ **Bloqué**.  

Vous ne pouvez pas modifier les numéros de série ou de lot ni les quantités. Pour ce faire, vous devez reclasser l'écriture article. Pour en savoir plus sur le reclassement des numéros de série et de lot, consultez [Reclasser les numéros de série ou de lot](inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).

## <a name="to-reclassify-serial-or-lot-numbers"></a>Pour reclasser les numéros de lot ou de série

Le reclassement de la traçabilité pour un article consiste à remplacer un numéro de lot ou de série par un autre ou à remplacer la date de péremption par une autre. Si vous utilisez des lots, vous pouvez fusionner plusieurs lots en un seul. Utilisez un journal de reclassement des articles pour exécuter ces tâches.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] vérifie que chaque ligne possède une combinaison unique de numéros de série, de lot et/ou de colis. Si vous souhaitez fractionner un lot, un package ou un lot et un package en plusieurs lots ou packages, vous devez utiliser plusieurs lignes journal.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Journaux de reclassement d’articles**, puis choisissez le lien associé.  
2. Renseignez la ligne à l'aide des informations appropriées. Pour plus d'informations, voir [Faire l'inventaire à l'aide de documents](inventory-how-count-inventory-with-documents.md) ou [Comptabiliser, ajuster et reclasser l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md).
3. Choisissez l'action **Lignes traçabilité**.  
4. Dans le champ  **Numéros de série** ou **Numéros de lot**, Sélectionner le numéro de série ou de lot actuel.  
5. Si vous voulez entrer un nouveau numéro de traçabilité, entrez-le dans le champ **Nouveau n° de série** ou le champ **Nouveau n° lot**. Vous pouvez également fusionner un ou plusieurs lots dans un nouveau lot ou un lot existant.  

    > [!NOTE]  
    > Lorsque vous reclassez les dates d’expiration, les articles avec les dates d’expiration les plus tôt pour les transactions sortantes sont suggérés en premier. Pour en savoir plus, [Prélèvement par FEFO](warehouse-picking-by-fefo.md).  

6. Pour indiquer une nouvelle date de péremption pour le numéro de lot ou de série, entrez-la dans le champ **Nouvelle date expiration**.  

    > [!IMPORTANT]  
    > * Si vous reclassez un lot sur le même numéro de lot mais définissez une autre date d'expiration, vous devez reclasser le lot entier en utilisant une ligne de journal reclassement article.
    > * Si vous reclassez plusieurs lots sur un nouveau numéro de lot, ce qui signifie que vous fusionnez plusieurs lots en un nouveau lot, vous devez entrer la même date d'expiration pour tous les lots. 
    > * Si vous reclassez un lot existant sur un autre dont la date d'expiration diffère, vous devez utiliser la date d'expiration du second lot. 
    > * Si vous laissez le champ **Nouvelle date expiration** vide, le numéro de lot ou de série est reclassé avec une date d'expiration vide.  

7. Si des informations figurent sur l'ancien numéro de lot ou de série, vous pouvez les copier vers le nouveau numéro de lot ou de série.  

    1. Sur la page **Lignes traçabilité**, sélectionnez l'action **Informations nouveau n° série** ou l'action **Informations nouveau n° lot**.  
    2. Pour copier des informations de l'ancien numéro de lot ou de série, sélectionnez l'action sur **Copier info**.  
    3. Sur la page Liste information, sélectionnez le numéro de lot ou de série à partir duquel vous souhaitez copier, puis choisissez le bouton **OK**.  

8. Si vous voulez modifier les informations existantes du numéro de lot ou de série, vous pouvez enregistrer des informations de lot ou de série.  
9. Reportez le journal pour lier les nouveaux numéros traçabilité ou dates d'expiration à l'écriture article qui leur est associée.

## <a name="scan-barcodes-with-the-business-central-mobile-app"></a>Scanner les codes-barres avec l’application mobile Business Central

[!INCLUDE [barcode-mobile-app](includes/barcode-mobile-app.md)]

Sur la page **Lignes traçabilité** , si vous souhaitez scanner plusieurs codes-barres de série, de lot ou de colis, vous pouvez utiliser l’action **Scanner plusieurs**. Après avoir scanné un code-barres, sa valeur est saisie dans le champ de la page et le champ de saisie rapide suivant devient disponible. Vous pouvez également utiliser l’icône du lecteur de codes-barres pour remplir un champ spécifique.

Les tableaux suivants répertorient les pages qui prennent en charge la numérisation des codes-barres pour la traçabilité d’articles de l’application mobile [!INCLUDE [prod_short](includes/prod_short.md)].

|Page  |Valeurs du champ que vous pouvez scanner  |
|---------|---------|
|Lignes traçabilité     |* N° de série<br><br>* Nouveau n° de série<br><br>* N° lot<br><br>* Nouveau n° lot<br><br>* N° paquet<br><br>* Nouveau n° package|
|Lignes de suivi des articles d’entrepôt     |* N° de série<br><br>* Nouveau n° de série<br><br>* N° lot<br><br>* Nouveau n° lot<br><br>* N° paquet<br><br>* Nouveau n° package|
|Traçabilité     |* Filtre n° de série<br><br>* Filtre n° lot<br><br>* N° paquet Filtrer |
|Feu. article     |* N° de série<br><br>* N° lot<br><br>* N° paquet     |
|Ligne activité magasin     |* N° de série<br><br>* N° lot<br><br>* N° paquet<br><br>**Remarque** : Les pages suivantes utilisent la page Ligne d’activité d’entrepôt :<br><br>* page 5780 « Sous-formulaire Prélèvement entrepôt »<br><br>* page 7378 « Sous-formulaire prélèvement inventaire »<br><br>* page 5771 « Sous-formulaire Rangement entrepôt »<br><br>* page 7316 « Sous-formulaire mouvement entrepôt »<br><br>* page 7376 « Sous-formulaire rangement inventaire »<br><br>* page 7383 « Sous-formulaire mouvement inventaire »        |
|Feuilles d'inventaire Journal inventaire physique     |* N° de série<br><br>* N° lot<br><br>* N° paquet         |

## <a name="see-also"></a>Voir aussi .

[Configuration du suivi des articles avec les numéros lot, de série et de paquet](inventory-how-setup-item-tracking.md)  
[Tracer des articles - Articles suivis](inventory-how-to-trace-item-tracked-items.md)  
[Inventaire](inventory-manage-inventory.md)  
[Détails de conception : traçabilité](design-details-item-tracking.md)  
[Détails de conception : traçabilité et réservations](design-details-item-tracking-and-reservations.md)  
[Réserver des articles](inventory-how-to-reserve-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
