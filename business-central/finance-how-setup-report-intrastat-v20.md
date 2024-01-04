---
title: Configurer et enregistrer un rapport Intrastat
description: Apprendre à configurer les fonctionnalités de rapport Intrastat et à créer un rapport sur les transactions avec des compagnies dans d'autres pays/régions de l'UE.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'electronic document, Intrastat, trade, EU, European Union'
ms.search.form: '308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 8451, 12202, 31077'
ms.date: 05/23/2022
ms.author: bholtorf
---
# Configurer et enregistrer un rapport Intrastat

Toutes les compagnies de l'Union européenne doivent déclarer leurs échanges avec les autres pays/régions de l'Union européenne. Vous devez déclarer les mouvements de marchandises aux autorités statistiques de votre pays/région mensuellement et le rapport doit être remis aux autorités fiscales. Il s'agit de la déclaration Intrastat. La page **Journal Intrastat** permet de remplir des rapports Intrastat périodiques.

[!INCLUDE[intrastat-2022w2](includes/intrastat-2022w2.md)]

## Paramètres obligatoires et facultatifs

> [!IMPORTANT]
> Les fiches client et les fiches fournisseur incluent un champ, **Type de partenaire Intrastat**, qui a les mêmes valeurs d’option que le champ **Type de partenaire** : *"" (Vide)*, *Compagnie* et *Personne*. Le champ **Type de partenaire Intrastat** a remplacé le champ **Type de partenaire** dans les rapports Intrastat. **Type de partenaire** est utilisé dans SEPA pour définir le régime des prélèvements SEPA (Base ou B2B). **Type de partenaire Intrastat** est utilisé pour la déclaration Intrastat uniquement. De cette façon, vous pouvez spécifier des valeurs différentes pour les deux champs, si nécessaire.
>
> Cependant, notez que si le champ **Type de partenaire Intrastat** est laissé vide, la valeur du champ **Type de partenaire** est utilisée pour la déclaration Intrastat.

Avant d'utiliser le journal Intrastat pour déclarer des informations Intrastat, plusieurs éléments doivent être configurés :  

* **Configuration Intrastat** : la page Configuration Intrastat permet d'activer la déclaration Intrastat et de définir des valeurs par défaut. Vous pouvez spécifier si vous devez enregistrer la déclaration Intrastat à partir des livraisons (envois), des réceptions (arrivées) ou des deux, selon les seuils définis par vos réglementations locales. Vous pouvez également définir des types de transaction par défaut pour les documents classiques et de retour, utilisés pour la nature des rapports de transaction.
* **Modèles de journal Intrastat** : Vous devez configurer les lots et les modèles de journal Intrastat que vous utiliserez. Comme la déclaration Intrastat doit être soumise mensuellement, vous devez créer 12 lots journal Intrastat basés sur le même modèle.  
* **Codes marchandise** : les autorités douanières et fiscales ont établi des codes numériques pour classer les articles et les services. Vous spécifiez ces codes sur les articles.
* **Codes nature de transaction** : les pays et les régions ont différents codes pour les types de transactions Intrastat, comme l'achat et la vente ordinaires, l'échange de marchandises retournées et l'échange de marchandises non retournées. Configurez tous les codes qui s'appliquent à votre pays/région. Utilisez ces codes sur le raccourci **Commerce étranger** pour les documents achat et vente, et lorsque vous traitez des retours.

    > [!NOTE]
    > À partir de janvier 2022, Intrastat exige un code de nature de transaction différent pour les envois aux particuliers ou aux entreprises non assujetties à la TVA et aux entreprises assujetties à la TVA. Pour se conformer à cette exigence, nous vous recommandons de revoir et/ou d’ajouter de nouveaux codes de nature de transaction dans la page **Types de transactions** selon les exigences de votre pays. Vous devriez également revoir et mettre à jour le champ **Type de partenaire Intrastat** sur *Personne* pour les clients particuliers ou les entreprises non assujetties à la TVA dans la page **Client**. Si vous n’êtes pas sûr du type de partenaire Intrastat ou du type de transaction correct à utiliser, nous vous recommandons de demander à un expert dans votre pays ou votre région.

* **Modes de transport**: Il existe sept codes à un chiffre pour les modes de transport Intrastat. **1** pour Mer, **2** pour Chemin de fer, **3** pour Route, **4** pour Air **5** pour Voie postale, **7** pour Transports fixes et **9** pour Propulsion propre (par exemple, le transport en voiture en la conduisant). [!INCLUDE[prod_short](includes/prod_short.md)] ne requiert pas ces codes, cependant, il est préférable que les descriptions offrent une signification similaire.  
* **Régimes** : Vous pouvez les utiliser pour renseigner les descriptions des types de transaction.  
* **Pays d’origine** : Utilisez les codes ISO Alpha à deux lettres pour le pays/la région où le bien a été obtenu ou produit. Si le bien a été produit dans plusieurs pays, le pays/la région d’origine est le dernier pays/la dernière région où il a été transformé de manière significative.
* **Numéro d’identification de TVA de l’opérateur partenaire dans l’État membre d’importation** : Il s’agit du numéro d’identification de TVA de l’opérateur partenaire dans l’État membre d’importation. Le numéro de TVA est également utilisé dans l’échange de données d’exportation intra-UE entre les états membres et permet aux états membres d’attribuer les données reçues à la compagnie importatrice dans leur propre pays/région. Les unités chargées des déclarations doivent déclarer le numéro de TVA de l’entreprise qui a déclaré l’acquisition intra-Union de biens dans l’État membre d’importation.

> [!NOTE]
> Le numéro de TVA du partenaire commercial à utiliser peut varier en fonction de la situation commerciale. Par exemple, le code à utiliser diffère pour les scénarios tels que les ventes en chaîne, où un fournisseur vend un produit dans un autre pays, puis cette compagnie revend l’article à une autre entreprise dans le même pays, le commerce circulaire, etc. Si vous n’êtes pas sûr du numéro de TVA correct à utiliser, nous vous recommandons de demander à un expert dans votre pays ou votre région.

Éventuellement, vous pouvez également configurer :

* **Dépts destination/provenance** : Vous pouvez les utiliser pour renseigner des informations sur les pays et les régions.  
* **Pays destination/provenance** : vous pouvez les utiliser pour spécifier les emplacements dans lesquels vous livrez ou recevez des articles vers ou à partir d’autres pays/régions. L'aéroport de Heathrow est un exemple de pays destination/provenance. Vous pouvez saisir des points d'entrée et de sortie sur les documents vente et achat sur le raccourci **Commerce étranger**. Ces informations sont également copiées à partir des écritures article lorsque vous créez le journal Intrastat.  

### Pour configurer des modèles et des lots Intrastat

Les traitements en lot Intrastat incluent uniquement des écritures articles et non des écritures GL. Si certaines écritures doivent être incluses dans la déclaration Intrastat, vous devez les saisir manuellement. Par exemple, si vous achetez un ordinateur dans un autre pays ou une autre région de l'UE, cet ordinateur n'est pas comptabilisé dans l'inventaire, mais reporté sur un compte du grand livre. Vous devez saisir manuellement ce type d'écriture dans le journal Intrastat.  

Vous pouvez exporter les écritures vers un fichier que vous pouvez envoyer à vos administrations Intrastat. Vous pouvez également imprimer un rapport, entrer manuellement les informations sur les formulaires de vos administrations, et envoyer les informations.

> [!NOTE]
> Nous vous recommandons de configurer un lot journal Intrastat pour chaque mois.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles de journaux Intrastat**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Créez un modèle pour chaque formulaire Intrastat que vous utilisez.  
3. Pour créer des lots, sélectionnez l'action **Lots**.  
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Créez un modèle pour chaque formulaire Intrastat que vous utilisez.

> [!NOTE]
> Dans le champ **Période statistique**, entrez la période statistique sous la forme d'un nombre à quatre chiffres, les deux premiers chiffres représentant l'année et les deux suivants, le mois. Par exemple, saisissez 1706 pour juin 2017.

### Pour configurer des modes de transport

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modes de transport**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Pour configurer les champs de la déclaration Intrastat obligatoires

Dans certains pays/régions, tel(le)s que l’Espagne et le R-U, les autorités exigent que les rapports Intrastat comprennent, par exemple, la méthode de livraison des achats ou d’autres valeurs lorsque les ventes sont supérieures à un certain seuil. Sur la page **Configuration Intrastat**, vous pouvez sélectionner pour que **Configuration de la liste de vérification Intrastat** définisse les champs obligatoires sur la page **Journal Intrastat**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration Intrastat**, puis choisissez le lien associé.
2. Choisissez l’action **Configuration de la liste de vérification Intrastat**.
3. Sur la page **Configuration de la liste de vérification Intrastat**, sélectionnez dans le champ **Nom de champ** pour prélever le champ de rapport Intrastat que vous souhaitez rendre obligatoire.

### Tchéquie

Notamment pour les entreprises tchèques, vous devez également paramétrer des codes marchandise et des codes nature de transaction.  

#### Pour configurer des codes marchandise

Tous les articles que vous achetez ou vendez doivent avoir un code marchandise.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Codes marchandise.**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Pour affecter un code marchandise à un article, accédez à la page **Fiche article**, développez le raccourci **Coûts et validation**, puis saisissez le code dans le champ **Code marchandise**.

### Italie

Notamment pour les entreprises italiennes, vous devez également paramétrer des codes marchandise et des codes nature de transaction.  

#### Pour configurer des codes nature de transaction

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Codes nature de transaction.**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!TIP]
> Si vous utilisez souvent un code nature de transaction spécifique, vous pouvez le définir comme valeur par défaut. Pour ce faire, accédez à la page **Configuration Intrastat** et choisissez le code.

## Pour soumettre un rapport Intrastat

Après avoir renseigné le journal Intrastat, vous pouvez exécuter l’action **Rapport : liste de vérification** pour vérifier que toutes les informations du journal sont correctes. Champs obligatoires que vous avez définis sur la page **Configuration de la liste de vérification Intrastat** qui sont des valeurs manquante, seront affichés dans le récapitulatif des erreurs et d’avertissement de la page **Journal Intrastat**. Ensuite, vous pouvez imprimer un rapport Intrastat en tant que formulaire, ou créer un fichier à envoyer à l'administration fiscale de votre pays/région.  

### Pour renseigner des feuilles intracommunautaires

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal Intrastat**, puis choisissez le lien associé.  
2. Sur la page **Journal Intrastat**, dans le champ **Nom de lot**, sélectionnez le lot journal concerné, puis sélectionnez **OK**.  
3. Choisissez l'action **Proposer lignes**. Les champs **Date début** et **Date fin** contiennent déjà les dates spécifiées sur la feuille pour la période statistique.  
4. Dans le champ **% régulation coût**, entrez un pourcentage pour couvrir le transport et l'assurance. Lorsque vous saisissez un pourcentage, la valeur du champ **Valeur statistique** de la feuille augmente proportionnellement.  
5. Cliquez sur **OK** pour démarrer le traitement en lot.  

Le traitement en lot récupère toutes les écritures article de la période statistique et les insère sous forme de lignes dans le journal Intrastat. Vous pouvez modifier au besoin les nouvelles lignes.  

> [!IMPORTANT]  
> Le traitement en lot récupère uniquement les écritures qui contiennent un code pays/région pour lequel un code Intrastat a été entré dans la page **Pays/Régions**. Vous devez donc entrer les codes Intrastat correspondant aux codes pays/région pour lesquels vous allez lancer le traitement en lot. Le traitement en lot définit le champ **Numéro de TVA du partenaire** sur *QV999999999999* pour les particuliers ou les entreprises non assujetties à la TVA (clients avec le champ **Type de partenaire Intrastat** défini sur *Personne*), et il utilise la valeur du champ **Type de transaction** de l’écriture article reportée ou de l’écriture projet.

### Pour modifier les lignes des journaux Intrastat

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal Intrastat**, puis choisissez le lien associé.  
2. Sur la page **Journal Intrastat**, dans le champ **Nom de lot**, sélectionnez le lot journal concerné, puis sélectionnez **OK**.  
3. Utilisez le volet de filtre utilisateur pour filtrer les lignes du journal Intrastat en fonction de certains critères. Par exemple, filtrez les champs **Numéro de TVA du partenaire** avec la valeur *QV999999999999*.
4. Choisissez l’icône **Partager**![Partager une page dans une autre application.](media/share-icon.png) et sélectionnez **Modifier dans Excel**
5. Dans Excel, modifiez les lignes de journal Intrastat que vous avez filtrées. Par exemple, modifiez les valeurs du champ **Type de transaction**.  
6. Publiez les modifications que vous avez apportées dans Excel dans [!INCLUDE[prod_short](includes/prod_short.md)]

> [!NOTE]
> Dans les versions de [!INCLUDE[prod_short](includes/prod_short.md)] qui ne prennent pas en charge [**Modifier dans Excel**](across-work-with-excel.md#edit-in-excel) pour les journaux, vous pouvez créer des packages de configuration pour exporter et importer des lignes journal Intrastat vers Excel. Pour plus d’informations, voir [Migrer des données locales vers Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) dans le contenu d’administration.

### Rapport Intrastat sur un formulaire ou un fichier

Pour obtenir les informations requises sur le formulaire Intrastat à partir des autorités statistiques, vous devez imprimer le rapport **Intrastat : Formulaire**. Avant d'effectuer cette opération, vous devez préparer le journal Intrastat et le renseigner. Si vous avez à la fois des transactions d'achat et de vente, vous devez compléter un formulaire distinct pour chaque type et donc imprimer le rapport deux fois.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux Intrastat**, puis choisissez le lien associé.  
2. Sur la page **Journal Intrastat**, choisissez le lot journal concerné dans le champ **Nom du lot**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou sélectionnez l'action **Proposer lignes**.  
4. Choisissez l'action **Imprime le journal Intrastat**.  
5. Sur le raccourci **Ligne journal Intrastat**, ajoutez un filtre **Type**, puis spécifiez s'il s'agit d'une **Réception** ou d'une **Livraison**.  
6. Choisissez **Envoyer à** pour imprimer le rapport.  

### Rapport Intrastat dans un fichier

Vous pouvez envoyer la déclaration Intrastat en tant que fichier. Avant de créer le fichier, vous pouvez imprimer la liste de vérification contenant les mêmes informations que le fichier.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal Intrastat**, puis choisissez le lien associé.  
2. Sur la page **Journal Intrastat**, sélectionnez le lot journal concerné dans le champ **Nom du lot**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou sélectionnez l'action **Proposer lignes**.  
4. Choisissez l'action **Créer fichier**.  
5. Dans la page de traitement en lot, sélectionnez le bouton **OK**.  
6. Choisissez **Enregistrer**.  
7. Sélectionnez l'emplacement d'enregistrement du fichier, entrez son nom, puis choisissez **Enregistrer**.

> [!NOTE]
> Lorsqu’une ligne du rapport Intrastat a une unité de mesure supplémentaire, le poids de l’article ne sera pas affiché, car cette valeur n’est pas requise.

## Réorganiser les journaux Intrastat

Parce que vous devez soumettre un rapport Intrastat chaque mois et créer un nouveau lot journal pour chaque rapport, il peut donc exister de nombreux lots journal. Les lignes journal ne sont pas supprimées automatiquement. Vous pouvez réorganiser régulièrement les noms du lot journal. Pour cela, il suffit de supprimer les lots journal dont vous n'avez plus besoin. Les lignes de ces journaux dans ces lots sont également supprimées.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux Intrastat**, puis choisissez le lien associé.  
2. Pour afficher les options, choisissez le champ **Nom de la feuille**.  
3. Cliquez sur les lots journal à supprimer, puis sélectionnez le bouton **Supprimer**.  

## Nomenclatures produits

Dans de nombreux pays/régions, les autorités douanières et fiscales établissent des codes article à huit unités pour divers articles. Pour que les écritures article comportent les informations nécessaires lorsque le programme les importe vers la ligne journal Intrastat, vous devez avoir saisi les informations concernant la nomenclature produit dans la page **Nomenclatures produits**. Trouvez les codes des articles avec lesquels votre compagnie travaille et saisissez-les dans la fenêtre **Nomenclatures produits**.

Ajoutez tous les codes que vous utilisez dans la page **Nomenclatures produit**. Vous devez saisir les codes sur la fiche article avant de commencer à reporter. Lorsque vous avez créé ces codes, saisissez-les dans le champ **Nomenclature produits** de la fiche article. Vous devez également renseigner le champ **Poids net** de la fiche article.

## Voir aussi .

[Gestion financière](finance.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
