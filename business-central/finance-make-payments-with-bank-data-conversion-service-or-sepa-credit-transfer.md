---
title: Effectuer des paiements avec les services bancaires AMC (États-Unis) ou par virement SEPA (UE)
description: Traitez les paiements à vos fournisseurs en exportant un fichier (TEF) avec les informations de paiement provenant des lignes journal.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.search.form: '256, 1205, 1206, 1209, 10810, 10811'
ms.date: 08/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Effectuez des paiements avec l’extension AMC banking 365 fundamentals ou le virement SEPA

Sur la page **Journaux de paiement**, vous pouvez traiter les paiements de vos fournisseurs en exportant un fichier avec les informations de paiement des lignes de journal. Vous pouvez ensuite télécharger le fichier vers votre banque électronique, où sont traités les transferts d'argent associés. [!INCLUDE[prod_short](includes/prod_short.md)] prend en charge le format de virement SEPA, mais dans votre pays/région, d’autres formats de paiements électroniques peuvent être disponibles.

> [!NOTE]
> Dans la version générique de [!INCLUDE[prod_short](includes/prod_short.md)], un fournisseur global de services pour convertir les données bancaires dans n'importe quel format de fichier que votre banque requiert est paramétré et connecté. Dans les versions nord-américaines, le même service peut être utilisé pour envoyer des fichiers de paiement sous forme de transfert de fonds électronique (EFT), par exemple le réseau ACH (Automated Clearing House), mais avec un processus légèrement différent. Voir l'étape 6 de [Pour exporter des paiements vers un fichier bancaire](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).  

 Pour activer les virements SEPA, vous devez d'abord créer un compte bancaire, un fournisseur et le lot journal général sur lequel le journal de paiements est basé. Vous préparez ensuite les paiements aux fournisseurs en remplissant automatiquement la page  **Journaux de paiement** avec les paiements dus avec les dates de comptabilisation spécifiées.  

Après avoir vérifié que la banque a traité les paiements, vous pouvez publier les lignes du journal des paiements.  

## Configuration de l’extension AMC Banking 365 Fundamentals 

Activez l’extension AMC Banking 365 Fundamentals pour :

* Convertissez les fichiers de relevés bancaires dans un format que vous pouvez importer.
* Convertissez vos fichiers de paiement exportés au format requis par votre banque.

Pour plus d’informations, voir [Utiliser l’extension AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md).

## Mise en place du virement SEPA

À partir de la page **Journaux de paiement**, vous pouvez exporter les paiements vers un fichier à télécharger sur votre banque électronique pour le traitement des transferts d’argent associés. [!INCLUDE[prod_short](includes/prod_short.md)] prend en charge le format de virement SEPA, mais dans votre pays/région, d’autres formats de paiements électroniques peuvent être disponibles.  

Pour pouvoir exporter un format de fichier bancaire qui n’est pas pris en charge par défaut dans [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez configurer une définition d’échange de données. Pour plus d'informations, voir [Configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).  

Avant de pouvoir traiter le paiement par voie électronique lorsque vous exportez des fichiers paiement au format de virement SEPA, vous devez exécuter les étapes de configuration suivantes :  

* Paramétrer le compte bancaire concerné pour traiter le format de virement SEPA  
* Configurer des fiches fournisseur pour traiter les paiements en exportant les fichiers au format de virement SEPA  
* Configurez le lot de journaux généraux associé pour activer l’exportation des paiements à partir de la page **Journaux de paiement**   
* Lier la définition d'échange de données pour un ou plusieurs types de règlement au(x) mode(s) de règlement approprié(s)  

> [!NOTE]
> Business Central prend en charge les formats SEPA CT pain.001.001.03 et CT pain.001.001.09. Vous pouvez choisir n’importe quel format sur la page **Compte bancaire carte** .  

> [!TIP]
> Cet article s'applique à la version générique de [!INCLUDE [prod_short](includes/prod_short.md)]. Dans votre pays ou région, des champs obligatoires supplémentaires peuvent avoir été ajoutés aux différentes pages. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### Pour configurer un compte bancaire pour SEPA Credit Transfer

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Comptes bancaires**, puis sélectionnez le lien associé.  
2. Choisissez le compte bancaire à partir duquel vous exportez les fichiers de paiement au format Virement SEPA.
3. Sur le raccourci **Général**, dans le champ **N° msg. virement**, sélectionnez une série de numéros à partir de laquelle des numéros sont attribués aux entrées de virement SEPA.
4. Dans l’onglet rapide  **Communication**, saisissez l’adresse et les coordonnées de la banque. 

   > [!NOTE]
   > Vous devez remplir le champ  **Code Pays/Région** . Si le champ est vide, vous ne pouvez pas exporter les paiements pour le compte. De plus, le pays/la région doit avoir un code ISO valide.

5. Dans l’onglet rapide  **Publication**, dans le champ  **Code de devise**, spécifiez la devise du compte bancaire.  

   > [!NOTE]  
   > Le champ **Code devise** doit avoir la valeur **EUR**, car les virements SEPA ne peuvent être effectués que dans la devise EURO.  

6. Dans l’organisateur **Transfert**, dans le champ **Format d’exportation de paiement**, choisissez le format SEPA que vous souhaitez utiliser.  
7. Dans le champ **IBAN**, indiquez le numéro de compte bancaire international du compte.  

### Pour configurer une fiche fournisseur pour SEPA Credit Transfer

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Fournisseurs**, puis choisissez le lien associé.  
2. Ouvrez le carte du fournisseur que vous payez par voie électronique à l’aide de fichiers de paiement d’exportation au format de virement SEPA.  
3. Dans l’organisateur **Paiements**, dans le champ **Code du mode de paiement**, choisissez **BANQUE**.  
4. Dans le champ **Compte bancaire préféré**, choisissez la banque vers laquelle l’argent sera transféré lorsqu’il sera traité par votre banque électronique.  

    Si vous n’avez pas de compte bancaire Sélectionner pour ce fournisseur, vous pouvez le faire maintenant. Pour plus d'informations, consultez [Configurer les comptes bancaires des fournisseurs pour l'exportation des fichiers bancaires](bank-how-setup-bank-accounts.md#to-set-up-vendor-bank-accounts-for-export-of-bank-files). La valeur du champ **Compte bancaire préféré** est copiée dans le champ **Cpte bancaire destinataire** de la page **Journal paiement**.  

### Pour définir le journal de paiement jusqu'aux fichiers de paiement d'exportation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.  
2. Dans le champ **Nom de la feuille**, choisissez le bouton déroulant.  
3. Sur la page **Lots journal général**, sélectionnez l'action **Modifier la liste**.  
4. Sur la ligne du journal des paiements que vous utilisez pour exporter les paiements, cochez la case  **Autoriser l’exportation des paiements** .  

### Pour lier la définition d'échange de données pour un ou plusieurs types de règlement au(x) mode(s) de règlement approprié(s)

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modes de paiement**, puis sélectionnez le lien associé.  
2. Sur la page **Modes de règlement**, sélectionnez le mode de paiement qui est utilisé pour exporter des paiements, puis cliquez sur le champ **Définition ligne exportation paiem.**  
3. Sur la page **Définitions ligne exportation paiem.**, sélectionnez le code spécifié dans le champ **Code** du raccourci **Définitions ligne** à l'étape 4 de la section « Pour décrire le formatage des lignes et des colonnes dans le fichier » dans [Configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).  

## Préparation du journal des paiements

Remplissez le journal paiement avec des lignes pour les paiements dus aux fournisseurs, avec la possibilité d'insérer des dates report sur la base de la date d'échéance des documents achat associés. Pour plus d'informations, reportez-vous à [Gestion des comptes fournisseur](payables-manage-payables.md).

## Exporter les paiements vers un fichier bancaire

Lorsque vous êtes prêt à effectuer des paiements à vos fournisseurs ou des remboursements à vos employés, vous pouvez exporter un fichier contenant les informations de paiement sur les lignes de la page **Journaux de paiement** . Vous pouvez ensuite transférer le fichier à votre banque afin qu'elle traite les transferts d'argent concernés.

Dans la version générique de [!INCLUDE[prod_short](includes/prod_short.md)], l'extension AMC Banking 365 Fundamentals est disponible. Dans les versions nord-américaines, la même extension peut être utilisée pour envoyer des fichiers de paiement comme transfert de fonds électronique (EFT), toutefois avec un processus légèrement différent. Voir l'étape 6 de [Pour exporter des paiements vers un fichier bancaire](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).

> [!NOTE]  
> Pour pouvoir exporter des fichiers de paiement à partir du journal paiement, vous devez spécifier le format électronique du compte bancaire concerné, et vous devez activer l'extension AMC Banking 365 Fundamentals. Pour plus d’informations, voir [Configurer des comptes bancaires](bank-how-setup-bank-accounts.md) et [Utiliser l’extension AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md). Vous devez aussi cocher la case **Autoriser exportation paiement** sur la page **Lots journal général**. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

Utilisez la page  **Registres de virements** pour afficher les fichiers de paiement exportés à partir du journal des paiements. Depuis cette page, vous pouvez également réexporter des fichiers de paiement s’il y a eu des erreurs techniques ou des modifications de fichiers. Notez cependant que les fichiers EFT exportés ne sont pas affichés sur cette page et ne peuvent pas être réexportés.  

### Pour exporter des paiements vers un fichier bancaire

Les étapes suivantes décrivent comment payer un fournisseur par chèque. La procédure est la même pour rembourser un client par chèque.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.
2. Renseignez les lignes journal paiement. Pour plus d'informations, voir [Enregistrer des paiements et des remboursements](payables-how-post-payments-refunds.md).

    > [!NOTE]
    > Si vous utilisez EFT, vous devez sélectionner **Paiement électronique** ou **Paiement électronique-IAT** dans le champ **Mode émission paiement**. Différents services d'exportation de fichiers et leurs formats nécessitent des valeurs de configuration différentes sur les pages **Fiche compte bancaire archivé** et **Fiche compte bancaire fourn.**. Vous serez informé si des valeurs de configuration sont manquantes ou fausses alors que vous essayez d'exporter le fichier.
    >
    > La fonction EFT ne peut être utilisée que pour les comptes bancaires dans la devise locale. Elle ne peut pas être utilisée avec une devise étrangère, indiquée par une valeur dans le champ **Code de devise**. (La valeur du champ vide signifie la devise locale.)

3. Après avoir rempli toutes les lignes du journal des paiements, choisissez l’action  **Exporter** .
4. Sur la page **Exporter paiements électroniques**, renseignez les champs selon vos besoins.

    Les messages d’erreur s’affichent dans la zone d’informations **Erreurs du fichier de paiement**, où vous pouvez également choisir un message d’erreur pour accéder à plus de détails. Vous devez résoudre toutes les erreurs avant de pouvoir exporter le fichier de paiement.

    > [!TIP]  
    > Lorsque vous utilisez l'extension AMC Banking 365 Fundamentals, un message d'erreur courant stipule que le numéro de compte bancaire n'a pas la longueur requise par votre banque. Pour éviter ou résoudre l'erreur, vous devez supprimer la valeur du champ **IBAN** sur la page **Fiche compte bancaire** puis, dans le champ **N° compte bancaire**, saisissez le numéro du compte bancaire dans le format requis par votre banque.

5. Sur la page **Enregistrer sous**, spécifiez l'emplacement où le fichier est exporté, puis choisissez **Enregistrer**.

    > [!NOTE]  
    > Si vous utilisez EFT, enregistrez le formulaire de remise fournisseur qui en résulte en tant que document Word ou sélectionnez de l'envoyer directement au fournisseur par courriel. Les paiements sont à présent ajoutés sur la page **Générer fichier EFT** d'où vous pouvez générer plusieurs ordres de paiement ensemble pour économiser le coût de transmission. Pour plus d'informations, reportez-vous aux étapes suivantes.
6. Sur la page **Journaux de paiement**, choisissez l’action **Générer un fichier EFT** .

    Sur la page **Générer un fichier EFT**, l’onglet rapide **Lignes** affiche tous les paiements EFT que vous avez exportés à partir du journal des paiements pour un compte bancaire mais qui ne sont pas encore générés.
7. Choisissez **Générer fichier EFT** pour exporter un fichier pour tous les paiements EFT.
8. Sur la page **Enregistrer sous**, spécifiez l'emplacement où le fichier est exporté, puis choisissez **Enregistrer**.

Le fichier de paiement bancaire est exporté vers l’emplacement que vous avez spécifié. Vous pouvez le télécharger sur votre compte bancaire électronique et effectuer les paiements réels. Vous pouvez ensuite reporter les lignes journal paiement exportées.

### Pour planifier le report des paiements exportés

Si vous ne souhaitez pas publier une ligne de journal de paiement pour un paiement exporté, vous pouvez simplement supprimer la ligne de journal. Par exemple, parce que vous attendez la confirmation que la banque a traité la transaction. Plus tard, lorsque vous créez une ligne de journal de paiement pour payer le montant restant, le champ  **Montant total exporté** indique la part du montant du paiement déjà exportée. En outre, vous pouvez rechercher des informations détaillées concernant le total exporté en cliquant sur le bouton **Écritures reg. virement** pour visualiser des détails sur les fichiers de paiement exportés.

Si vous ne souhaitez pas publier de paiements tant que la banque n’a pas confirmé qu’ils ont été traités, vous pouvez :

* Dans un journal de paiement avec des lignes de paiement suggérées, vous pouvez trier sur l’un ou l’autre **Exporté vers le fichier de paiement**  colonne ou la **Montant total exporté**  et supprimez ensuite les suggestions de paiement pour les factures ouvertes pour lesquelles des paiements ont déjà été effectués.
* Sur le **Suggérez des paiements aux fournisseurs**  page, où vous spécifiez les paiements à insérer dans le journal des paiements, vous pouvez Sélectionner le **Ignorer les paiements exportés**  case à cocher si vous ne souhaitez pas insérer de lignes de journal pour les paiements qui ont déjà été exportés.

Pour afficher des informations sur les paiements exportés, sélectionnez l'action **Historique d'exportation des paiements**.

### Pour réexporter des paiements vers un fichier bancaire

Vous pouvez réexporter des fichiers paiement à partir de la page **Registres virement**. Avant de supprimer ou de publier des lignes de journal de paiement, vous pouvez également réexporter le fichier de paiement à partir du **Journaux de paiement**  page en l’exportant à nouveau. Si vous supprimez ou publiez les lignes du journal de paiement après votre exportation, vous pouvez réexporter le même fichier de paiement à partir de **Registres de transfert de crédits**  page. Sélectionnez la ligne correspondant au lot de virements que vous souhaitez réexporter, puis, sélectionnez l'action **Réexporter les paiements dans un fichier**.

> [!NOTE]  
> Les fichiers EFT exportés ne sont pas affichés sur la page **Registres virement** et ne peuvent pas être réexportés.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Registres de virements**, puis sélectionnez le lien associé.
2. Sélectionnez une exportation de règlement que vous souhaitez réexporter, puis sélectionnez **Réexporter les paiements dans un fichier**.

## Comptabilisation des paiements

Une fois que votre banque a traité le paiement électronique, enregistrez les paiements. Pour plus d'informations, reportez-vous à [Effectuer des paiements](payables-make-payments.md).

## Voir aussi .

[Utilisation de l’extension AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
