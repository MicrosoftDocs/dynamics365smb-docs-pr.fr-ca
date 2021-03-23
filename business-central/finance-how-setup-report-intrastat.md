---
title: Configurer et créer un rapport Intrastat | Microsoft Docs
description: Apprendre à configurer les fonctionnalités de rapport Intrastat et à créer un rapport sur les transactions avec des compagnies dans d'autres pays/régions.
services: project-madeira
documentationcenter: ''
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.date: 10/01/2020
ms.author: bholtorf
ms.openlocfilehash: 2d6cbf9327e0b1d5b4d61b6ac14d949b8700b833
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5380998"
---
# <a name="set-up-and-report-intrastat"></a>Configurer et enregistrer un rapport Intrastat
Toutes les compagnies de l'Union européenne doivent déclarer leurs échanges avec les autres pays/régions de l'Union européenne. Vous devez déclarer les mouvements de marchandises aux autorités statistiques de votre pays/région mensuellement et le rapport doit être remis aux autorités fiscales. Il s'agit de la déclaration Intrastat. La page **Journal Intrastat** permet de remplir des rapports Intrastat périodiques.  

## <a name="required-and-optional-setups"></a>Paramètres obligatoires et facultatifs
Avant d'utiliser le journal intrastat pour enregistrer des informations Intrastat, plusieurs éléments doivent être configurés :  

* **Configuration Intrastat** : la page Configuration Intrastat permet d'activer la déclaration Intrastat et de définir des valeurs par défaut. Vous pouvez spécifier si vous devez enregistrer la déclaration Intrastat à partir des livraisons (envois), des réceptions (arrivées) ou des deux, selon les seuils définis par vos réglementations locales. Vous pouvez également définir des types de transaction par défaut pour les documents classiques et de retour, utilisés pour la nature des rapports de transaction.
* **Modèles de journal Intrastat** : Vous devez configurer les lots et les modèles de journal Intrastat que vous utiliserez. Comme la déclaration Intrastat doit être soumise mensuellement, vous devez créer 12 lots journal Intrastat basés sur le même modèle.  
* **Codes marchandise** : les autorités douanières et fiscales ont établi des codes numériques pour classer les articles et les services. Vous spécifiez ces codes sur les articles.
* **Codes nature de transaction** : les pays et les régions ont différents codes pour les types de transactions Intrastat, comme l'achat et la vente ordinaires, l'échange de marchandises retournées et l'échange de marchandises non retournées. Configurez tous les codes qui s'appliquent à votre pays/région. Utilisez ces codes dans les documents achat et vente, et lorsque vous traitez des retours.  
* **Modes de transport**: Il existe sept codes à un chiffre pour les modes de transport Intrastat. **1** Mer, **2** Chemin de fer, **3** Route, **4** Air **5** Voie postale, **7** Transports fixes et **9** Propulsion propre (par exemple le transport en voiture en la conduisant). [!INCLUDE[prod_short](includes/prod_short.md)] ne requiert pas ces codes, cependant, il est préférable que les descriptions offrent une signification similaire.  

Éventuellement, vous pouvez également configurer :

* **Régimes** : Vous pouvez les utiliser pour renseigner les descriptions des types de transaction.  
* **Dépts destination/provenance** : Vous pouvez les utiliser pour renseigner des informations sur les pays et les régions.  
* **Pays destination/provenance** : Vous pouvez les utiliser pour spécifier les emplacements dans lesquels vous livrez ou recevez des articles vers ou à partir d'autres pays. L'aéroport de Heathrow est un exemple de pays destination/provenance. Vous pouvez saisir des points d'entrée et de sortie sur les documents vente et achat sur le raccourci **Commerce étranger**. Ces informations sont également copiées à partir des écritures article lorsque vous créez le journal Intrastat.  

### <a name="to-set-up-intrastat-templates-and-batches"></a>Pour configurer des modèles et des lots Intrastat
Les traitements en lot Intrastat incluent uniquement des écritures articles et non des écritures GL. Si certaines écritures doivent être incluses dans la déclaration Intrastat, vous devez les saisir manuellement. Par exemple, si vous achetez un ordinateur dans un autre pays ou une autre région de l'UE, cet ordinateur n'est pas comptabilisé dans l'inventaire, mais reporté sur un compte du grand livre. Vous devez saisir manuellement ce type d'écriture dans le journal Intrastat.  

Vous pouvez exporter les écritures vers un fichier que vous pouvez envoyer à vos administrations Intrastat. Vous pouvez également imprimer un rapport, entrer manuellement les informations sur les formulaires de vos administrations, et envoyer les informations.

> [!Note]
> Nous vous recommandons de configurer un lot journal Intrastat pour chaque mois.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles journal Intrastat**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Créez un modèle pour chaque formulaire Intrastat que vous utilisez.  
3. Pour créer des lots, sélectionnez l'action **Lots**.  
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Créez un modèle pour chaque formulaire Intrastat que vous utilisez. 

> [!Note]
> Dans le champ **Période statistique**, entrez la période statistique sous la forme d'un nombre à quatre chiffres, les deux premiers chiffres représentant l'année et les deux suivants, le mois. Par exemple, saisissez 1706 pour juin 2017.

### <a name="to-set-up-commodity-codes"></a>Pour configurer des codes marchandise
Tous les articles que vous achetez ou vendez doivent avoir un code marchandise.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Codes marchandise**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Pour affecter un code marchandise à un article, accédez à la page **Fiche article**, développez le raccourci **Coûts et validation**, puis saisissez le code dans le champ **Code marchandise**.   

### <a name="to-set-up-transaction-nature-codes"></a>Pour configurer des codes nature de transaction
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Codes nature de transaction**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!Tip]
> Si vous utilisez souvent un code nature de transaction spécifique, vous pouvez le définir comme valeur par défaut. Pour ce faire, accédez à la page **Configuration Intrastat** et choisissez le code.

### <a name="to-set-up-transport-methods"></a>Pour configurer des modes de transport
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modes de transport**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### <a name="to-set-up-which-intrastat-report-fields-are-mandatory"></a>Pour configurer les champs de la déclaration Intrastat obligatoires
Dans certains pays, tels que l'Espagne et le R-U, les autorités nécessitent que les déclarations Intrastat comprennent, par exemple, la méthode de livraison des achats ou d'autres valeurs lorsque les ventes sont supérieures à un certain seuil. Sur la page **Configuration Intrastat**, vous pouvez sélectionner pour faire **Configuration liste de contrôle Intrastat** pour définir les champs obligatoires sur la page **Journal Intrastat**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration Intrastat**, puis sélectionnez le lien associé.
2. Choisissez l'action **Configuration de la liste de vérification Intrastat**.
3. Sur la page **Configuration liste de vérification Intrastat**, cliquez dans **Nom de champ** pour prélever le champ de déclaration Intrastat que vous souhaitez rendre obligatoire.

## <a name="to-report-intrastat"></a>Pour soumettre une déclaration Intrastat
Après avoir renseigné le journal Intrastat, vous pouvez exécuter l'action **Rapport liste de vérification** pour vérifier que toutes les informations du journal sont correctes. Les champs obligatoires que vous avez définis sur la page **Configuration liste de vérification Intrastat** qui ont des valeurs manquantes, seront affichés dans le récapitulatif des erreurs et des avertissements de la page **Journal Intrastat**. Ensuite, vous pouvez imprimer un rapport Intrastat en tant que formulaire, ou créer un fichier à envoyer à l'administration fiscale de votre pays/région.  

### <a name="to-fill-in-intrastat-journals"></a>Pour renseigner des feuilles intracommunautaires  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Sur la page **Journal Intrastat**, dans le champ **Nom de lot**, sélectionnez le lot journal concerné, puis sélectionnez **OK**.  
3. Choisissez l'action **Proposer lignes**. Les champs **Date début** et **Date fin** contiennent déjà les dates spécifiées sur la feuille pour la période statistique.  
4. Dans le champ **% régulation coût**, entrez un pourcentage pour couvrir le transport et l'assurance. Lorsque vous saisissez un pourcentage, la valeur du champ **Valeur statistique** de la feuille augmente proportionnellement.  
5. Cliquez sur **OK** pour démarrer le traitement en lot.  

Le traitement en lot récupère toutes les écritures article de la période statistique et les insère sous forme de lignes dans le journal Intrastat. Vous pouvez modifier au besoin les nouvelles lignes.  

> [!IMPORTANT]  
>  Le traitement en lot récupère uniquement les écritures qui contiennent un code pays/région pour lequel un code Intrastat a été entré dans la page **Pays/Régions**. Vous devez donc entrer les codes Intrastat correspondant aux codes pays/région pour lesquels vous allez lancer le traitement en lot.  

### <a name="report-intrastat-on-a-form-or-a-file"></a>Rapport Intrastat sur un formulaire ou un fichier
Pour obtenir les informations requises sur le formulaire Intrastat à partir des autorités statistiques, vous devez imprimer le rapport **Intrastat : Formulaire**. Avant d'effectuer cette opération, vous devez préparer le journal Intrastat et le renseigner. Si vous avez à la fois des transactions d'achat et de vente, vous devez compléter un formulaire distinct pour chaque type et donc imprimer le rapport deux fois.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux Intrastat**, puis sélectionnez le lien associé.  
2. Sur la page **Journal Intrastat**, choisissez le lot journal concerné dans le champ **Nom du lot**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou sélectionnez l'action **Proposer lignes**.  
4. Choisissez l'action **Imprime le journal Intrastat**.  
5. Sur le raccourci **Ligne journal Intrastat**, ajoutez un filtre **Type**, puis spécifiez s'il s'agit d'une **Réception** ou d'une **Livraison**.  
6. Choisissez **Envoyer à** pour imprimer le rapport.  

### <a name="report-intrastat-in-a-file"></a>Rapport Intrastat dans un fichier
Vous pouvez envoyer la déclaration Intrastat en tant que fichier. Avant de créer le fichier, vous pouvez imprimer la liste de vérification contenant les mêmes informations que le fichier.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Sur la page **Journal Intrastat**, sélectionnez le lot journal concerné dans le champ **Nom du lot**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou sélectionnez l'action **Proposer lignes**.  
4. Choisissez l'action **Créer fichier**.  
5. Dans la page de traitement en lot, sélectionnez le bouton **OK**.  
6. Choisissez **Enregistrer**.  
7. Sélectionnez l'emplacement d'enregistrement du fichier, entrez son nom, puis choisissez **Enregistrer**.

## <a name="reorganize-intrastat-journals"></a>Réorganiser les journaux Intrastat
Parce que vous devez soumettre un rapport Intrastat chaque mois et créer un nouveau lot journal pour chaque rapport, il peut donc exister de nombreux lots journal. Les lignes journal ne sont pas supprimées automatiquement. Vous pouvez réorganiser régulièrement les noms du lot journal. Pour cela, il suffit de supprimer les lots journal dont vous n'avez plus besoin. Les lignes de ces journaux dans ces lots sont également supprimées.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux Intrastat**, puis sélectionnez le lien associé.  
2. Pour afficher les options, choisissez le champ **Nom de la feuille**.  
3. Choisissez les lots journal à supprimer, puis sélectionnez le bouton **Supprimer**.  

## <a name="tariff-numbers"></a>Nomenclatures produits

Dans de nombreux pays, les autorités douanières et fiscales établissent des codes article à huit unités pour divers articles. Pour que les écritures article comportent les informations nécessaires lorsque le programme les importe vers la ligne journal Intrastat, vous devez avoir saisi les informations concernant la nomenclature produit dans la page **Nomenclatures produits**. Trouvez les codes des articles avec lesquels votre compagnie travaille et saisissez-les dans la fenêtre **Nomenclatures produits**.

Ajoutez tous les codes que vous utilisez dans la page **Nomenclatures produit**. Vous devez saisir les codes sur la fiche article avant de commencer à reporter. Lorsque vous avez créé ces codes, saisissez-les dans le champ **Nomenclature produits** de la fiche article. Vous devez également renseigner le champ **Poids net** de la fiche article.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Gestion financière](finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]