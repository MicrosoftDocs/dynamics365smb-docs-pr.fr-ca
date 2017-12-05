---
title: "Configurer et créer un rapport Intrastat | Microsoft Docs"
description: "Apprendre à configurer les fonctionnalités de rapport Intrastat et à créer un rapport sur les transactions avec des compagnies dans d'autres pays/régions."
services: project-madeira
documentationcenter: 
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.date: 08/15/2017
ms.author: bholtorf
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: 973c42642f88024de9d8924b675496015ce60983
ms.contentlocale: fr-ca
ms.lasthandoff: 11/10/2017

---
# <a name="how-to-set-up-and-report-intrastat"></a>Procédure : configurer et soumettre une déclaration Intrastat
Toutes les compagnies de l'Union européenne doivent déclarer leurs échanges avec les autres pays/régions de l'Union européenne. Vous devez déclarer les mouvements de marchandises aux autorités statistiques de votre pays/région mensuellement et le rapport doit être remis aux autorités fiscales. Il s'agit de la déclaration Intrastat. La page **Journal Intrastat** permet de remplir des rapports Intrastat périodiques.  

## <a name="required-and-optional-setups"></a>Paramètres obligatoires et facultatifs
Avant d'utiliser le journal Intrastat pour déclarer des informations Intrastat, plusieurs éléments doivent être configurés :  

* **Modèles de journal Intrastat** : Vous devez configurer les lots et les modèles de journal Intrastat que vous utiliserez. Comme la déclaration Intrastat doit être soumise mensuellement, vous devez créer 12 lots journal Intrastat basés sur le même modèle.  
* **Codes marchandise** : les autorités douanières et fiscales ont établi des codes numériques pour classer les articles et les services. Vous spécifiez ces codes sur les articles.
* **Codes nature de transaction** : les pays et les régions ont différents codes pour les types de transactions Intrastat, comme l'achat et la vente ordinaires, l'échange de marchandises retournées et l'échange de marchandises non retournées. Configurez tous les codes qui s'appliquent à votre pays/région. Utilisez ces codes dans les documents achat et vente, et lorsque vous traitez des retours.  
* **Modes de transport**: Il existe sept codes à un chiffre pour les modes de transport Intrastat. **1** Mer, **2** Chemin de fer, **3** Route, **4** Air **5** Voie postale, **7** Transports fixes et **9** Propulsion propre (par exemple le transport en voiture en la conduisant). [!INCLUDE[d365fin](includes/d365fin_md.md)] ne requiert pas ces codes, cependant, il est préférable que les descriptions offrent une signification similaire.  

Éventuellement, vous pouvez également configurer :

* **Régimes** : Vous pouvez les utiliser pour renseigner les descriptions des types de transaction.  
* **Dépts destination/provenance** : Vous pouvez les utiliser pour renseigner des informations sur les pays et les régions.  
* **Pays destination/provenance** : Vous pouvez les utiliser pour spécifier les emplacements dans lesquels vous livrez ou recevez des articles vers ou à partir d'autres pays. L'aéroport de Heathrow est un exemple de pays destination/provenance. Vous pouvez saisir des points d'entrée et de sortie sur les documents vente et achat sur le raccourci **Commerce étranger**. Ces informations sont également copiées à partir des écritures article lorsque vous créez le journal Intrastat.  

### <a name="to-set-up-intrastat-templates-and-batches"></a>Pour configurer des modèles et des lots Intrastat
Les traitements en lot Intrastat incluent uniquement des écritures articles et non des écritures GL. Si certaines écritures doivent être incluses dans la déclaration Intrastat, vous devez les saisir manuellement. Par exemple, si vous achetez un ordinateur dans un autre pays ou une autre région de l'UE, cet ordinateur n'est pas comptabilisé dans l'inventaire, mais reporté sur un compte du grand livre. Vous devez saisir manuellement ce type d'écriture dans le journal Intrastat.  

Vous pouvez exporter les écritures vers un fichier que vous pouvez envoyer à vos administrations Intrastat. Vous pouvez également imprimer un rapport, entrer manuellement les informations sur les formulaires de vos administrations, et envoyer les informations.

>  [!Note]
> Nous vous recommandons de configurer un lot journal Intrastat pour chaque mois.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles de journal Intrastat**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Créez un modèle pour chaque formulaire Intrastat que vous utilisez.  
3. Pour créer des feuilles, choisissez l'onglet **Naviguer**, puis choisissez **Noms feuilles**.  
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Créez un modèle pour chaque formulaire Intrastat que vous utilisez.  

> [!Note]
> Dans le champ **Période statistique**, entrez la période statistique sous la forme d'un nombre à quatre chiffres, les deux premiers chiffres représentant l'année et les deux suivants, le mois. Par exemple, saisissez 1706 pour juin 2017.

### <a name="to-set-up-commodity-codes"></a>Pour configurer des codes marchandise
Tous les articles que vous achetez ou vendez doivent avoir un code marchandise.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Codes marchandise**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Pour affecter un code marchandise à un article, accédez à la page **Fiche article**, développez le raccourci **Coûts et validation**, puis saisissez le code dans le champ **Code marchandise**.   

### <a name="to-set-up-transaction-nature-codes"></a>Pour configurer des codes nature de transaction
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Codes nature transaction**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!Tip]
> Si vous utilisez souvent un code nature de transaction spécifique, vous pouvez le définir comme valeur par défaut. Pour ce faire, accédez à la page **Configuration Intrastat** et choisissez le code.

### <a name="to-set-up-transport-methods"></a>Pour configurer des modes de transport
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modes de transport**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-report-intrastat"></a>Pour soumettre une déclaration Intrastat
Après avoir renseigné le journal Intrastat, vous pouvez imprimer le rapport **Liste de vérification** pour vérifier que toutes les informations du journal sont correctes. Ensuite, vous pouvez imprimer un rapport Intrastat en tant que formulaire, ou créer un fichier à envoyer à l'administration fiscale de votre pays/région.  

### <a name="to-fill-in-intrastat-journals"></a>Pour renseigner des feuilles intracommunautaires  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Sur la page **Journal Intrastat**, dans le champ **Nom de lot**, sélectionnez le lot journal concerné, puis sélectionnez **OK**.  
3. Choisissez l'action **Proposer lignes**. Les champs **Date début** et **Date fin** contiennent déjà les dates spécifiées sur la feuille pour la période statistique.  
4. Dans le champ **% régulation coût**, entrez un pourcentage pour couvrir le transport et l'assurance. Lorsque vous saisissez un pourcentage, la valeur du champ **Valeur statistique** de la feuille augmente proportionnellement.  
5. Cliquez sur **OK** pour démarrer le traitement en lot.  

Le traitement en lot récupère toutes les écritures article de la période statistique et les insère sous forme de lignes dans le journal Intrastat. Vous pouvez modifier au besoin les nouvelles lignes.  

> [!IMPORTANT]  
>  Le traitement en lot récupère uniquement les écritures qui contiennent un code pays/région pour lequel un code Intrastat a été entré dans la page **Pays/Régions**. Vous devez donc entrer les codes Intrastat correspondant aux codes pays/région pour lesquels vous allez lancer le traitement en lot.  

### <a name="how-to-report-intrastat-on-a-form-or-a-file"></a>Procédure : soumettre une déclaration Intrastat sur un formulaire ou un fichier
Pour obtenir les informations requises sur le formulaire Intrastat à partir des autorités statistiques, vous devez imprimer le rapport **Intrastat : Formulaire**. Avant d'effectuer cette opération, vous devez préparer le journal Intrastat et le renseigner. Si vous avez à la fois des transactions d'achat et de vente, vous devez compléter un formulaire distinct pour chaque type et donc imprimer le rapport deux fois.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Sur la page **Journal Intrastat**, choisissez le lot journal concerné dans le champ **Nom du lot**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou sélectionnez **Proposer lignes**.  
4. Choisissez l'action **Imprime le journal Intrastat**.  
5. Sur le raccourci **Ligne journal Intrastat**, ajoutez un filtre **Type**, puis spécifiez s'il s'agit d'une **Réception** ou d'une **Livraison**.  
6. Choisissez **Envoyer à** pour imprimer le rapport.  

### <a name="how-to-report-intrastat-in-a-file"></a>Procédure : soumettre une déclaration Intrastat dans un fichier
Vous pouvez envoyer la déclaration Intrastat en tant que fichier. Avant de créer le fichier, vous pouvez imprimer la liste de vérification contenant les mêmes informations que le fichier.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Feuille intracomm.**, sélectionnez la feuille concernée dans le champ **Nom de la feuille**.  
3. Si ce n'est déjà fait, renseignez le journal manuellement ou en sélectionnant **Proposer lignes**.  
4. Choisissez l'action **Créer fichier**.  
5. Dans la fenêtre de traitement en lot, choisissez **OK**.  
6. Choisissez **Enregistrer**.  
7. Sélectionnez l'emplacement d'enregistrement du fichier, entrez son nom, puis choisissez **Enregistrer**.

## <a name="how-to-reorganize-intrastat-journals"></a>Procédure : réorganisation des feuilles intracommunautaires
Parce que vous devez soumettre un rapport Intrastat chaque mois et créer un nouveau lot journal pour chaque rapport, il peut donc exister de nombreux lots journal. Les lignes journal ne sont pas supprimées automatiquement. Vous pouvez réorganiser régulièrement les noms du lot journal. Pour cela, il suffit de supprimer les lots journal dont vous n'avez plus besoin. Les lignes de ces journaux dans ces lots sont également supprimées.  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal Intrastat**, puis sélectionnez le lien associé.  
2. Pour afficher les options, choisissez le champ **Nom de la feuille**.  
3. Cliquez sur les lots journal à supprimer, puis choisissez **Supprimer**.  

## <a name="see-also"></a>Voir aussi
[Gestion financière](finance.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]

