---
title: Utiliser les rapports Intrastat
description: Découvrez comment enregistrer les transactions avec des compagnies dans d’autres pays/régions de l’UE à l’aide du système Intrastat.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'electronic document, Intrastat, trade, EU, European Union'
ms.search.form: '308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 4810, 4811, 8451, 12202, 31077'
ms.date: 09/02/2022
ms.author: altotovi
---
# <a name="work-with-intrastat-reporting"></a>Utiliser les rapports Intrastat

Toutes les compagnies de l’Union européenne (UE) doivent déclarer leurs échanges avec les autres pays/régions de l’Union européenne. Vous devez déclarer les mouvements de marchandises aux autorités statistiques de votre pays/région mensuellement et le rapport doit être remis aux autorités fiscales. Intrastat est le système de collecte des statistiques du commerce des biens au sein de ces pays/régions. Vous utilisez un **Rapport Intrastat** pour générer des rapports Intrastat périodiques (généralement mensuels), collecter, enregistrer et déclarer le commerce de marchandises conformément à la législation administrative locale.

Le rapport Intrastat est basé sur les réglementations de base de l’UE qui s’appliquent à tous les pays/toutes les régions ; cependant, dans la pratique, il existe certaines différences au sein des différents pays/des différentes régions. Chaque pays/région a ses règles précisant exactement quoi déclarer et comment.

> [!IMPORTANT]
> Cet article décrit la nouvelle expérience de rapports Intrastat disponible dans [!INCLUDE[prod_short](includes/prod_short.md)] à partir de la 2e vague de lancement 2022, qui comprend des fonctionnalités étendues et [doit être activée pour les compagnies existantes](finance-how-setup-report-intrastat.md#enable-the-new-intrastat-experience). Contactez votre administrateur pour activer et configurer la nouvelle fonctionnalité.
>
> Lisez l’article sur la configuration et l’utilisation d'Intrastat de la version précédente ici : [Configurer et soumettre un rapport Intrastat](finance-how-setup-report-intrastat-v20.md).

> [!NOTE]
> Les informations Intrastat ne s’appliquent pas aux mouvements de services entre pays/régions, mais uniquement aux biens (articles et immobilisations). Si le gouvernement local exige l’enregistrement du mouvement des services entre les pays/régions, cela est possible en utilisant la fonctionnalité **Déclaration de service**.
>
> Nous prévoyons actuellement que cette fonctionnalité sera disponible à partir de novembre 2022 en tant qu’application sur [AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). A ce moment, pour l’utiliser, vous devrez d’abord l’installer sur la page **Gestion des extensions**.

## <a name="fill-in-the-intrastat-report"></a>Remplir un rapport Intrastat

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Liste Intrastat**, puis choisissez le lien associé.
2. Sélectionnez l’action **Nouveau** pour créer un nouveau **Rapport Intrastat**.
3. Si vous devez saisir des informations internes sur le **Rapport Intrastat**, renseignez ces informations dans le champ **Description**.
4. Dans le champ **Période statistique**, spécifiez le mois pour lequel rapporter les données. Entrez la période sous la forme d’un nombre à quatre chiffres sans espaces ni symboles. Selon votre pays/région, entrez soit le mois d’abord, puis l’année, soit l’inverse. Par exemple; saisissez soit *2206*, soit *0622* pour juin 2022.
5. Choisissez l'action **Proposer lignes**. Les champs **Date début** et **Date fin** contiennent déjà les dates spécifiées dans l’en-tête du rapport Intrastat pour la période statistique.
6. Dans le champ **% régulation coût**, entrez un pourcentage pour couvrir le transport et l'assurance. Lorsque vous saisissez un pourcentage, la valeur du champ **Valeur statistique** de la feuille augmente proportionnellement. Mais si vous voulez utiliser cette fonction, vous devez changer le champ **Montant frais annexes inclus** en **Oui**.
7. Vous pouvez éventuellement configurer des configurations supplémentaires sur le raccourci **Supplémentaire** :
   1. **Ignorer le recalcul des montants nuls** pour spécifier que les lignes sans montant ne seront pas recalculées lors du traitement en lot.
   2. **Ignorer les montants nuls** pour spécifier que les écritures article sans montant ne sont pas incluses dans le traitement en lot.
   3. **Afficher les écritures de frais annexes** pour spécifier si vous souhaitez afficher les coûts directs que votre compagnie a affectés et reportés en tant que frais annexes.
   4. **Ignorer écritures non facturées** pour spécifier si les écritures article livrées ou reçues mais pas encore facturées doivent être exclues du traitement.
8. Cliquez sur **OK** pour démarrer le traitement en lot.

Le traitement en lot récupère toutes les écritures article de la période statistique et les insère sous forme de lignes dans le **Rapport Intrastat**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="modify-the-intrastat-report"></a>Modifier le rapport Intrastat

Si nécessaire, vous pouvez modifier les lignes, mais chaque fois que vous modifiez une valeur dans une ligne du rapport Intrastat, le champ **Correction** est automatiquement marqué comme **Oui**. Vous pouvez éventuellement ajouter une nouvelle ligne manuellement s’il y a une raison à cela. Pour ajouter une nouvelle ligne manuellement :

1. Sur la page **Rapport Intrastat**, sur le raccourci **Lignes**, sélectionnez l’action **Nouvelle ligne**.
2. Sélectionnez l’option **Réception** ou **Livraison** dans le champ **Type**.
3. Dans le champ **Type de source**, choisissez l’une des sources : **Écriture article**, **Écriture immo.** ou **Écriture projet**.
4. Sur la base du **Type de source** dans le champ **Numéro d’article**, vous pouvez choisir un **Article** (dans les deux cas,**Écriture article** ou **Écriture projet**) ou des **Immobilisations**.
5. Remplissez les autres champs dont vous avez besoin pour les rapports Intrastat.

> [!NOTE]
> Lorsque vous ajoutez manuellement une nouvelle ligne au rapport Intrastat, le champ **Date** de la ligne doit se trouver dans la plage **Période statistique** que vous avez ajoutée dans l’en-tête.

## <a name="validate-intrastat-lines"></a>Valider les lignes Intrastat

Après avoir renseigné le **Rapport Intrastat**, vous pouvez exécuter l’action **Rapport liste de vérification** pour vérifier que toutes les informations du **Rapport Intrastat** sont correctes. Les champs obligatoires que vous avez définis sur la page **Liste de vérification Rapport Intrastat** auxquels il manque des valeurs seront affichés dans le récapitulatif **Erreurs et avertissements** de la page **Rapport Intrastat**.

Exécutez le rapport **Liste de vérification Rapport Intrastat** pour vérifier les lignes du rapport Intrastat avant leur exportation au format requis. La vérification est exécutée dans le **Rapport Intrastat**.

## <a name="recalculating-weight-or-supplementary-unit-of-measure"></a>Recalculer le poids ou l’unité de mesure supplémentaire

Si vous recevez le message d’erreur *Le Poids total dans la ligne du rapport Intrastat ne doit pas être vide*, c’est probablement parce que vous n’avez pas défini le champ **Poids net** sur la source, l’article ou l’immobilisation utilisée. Dans ce cas, recherchez la fiche article ou immobilisation et ajoutez la valeur requise. Après cela, il vous suffit de rouvrir le **Rapport Intrastat** et de suivre ces étapes :

1. Sélectionnez l’action **Recalc. Poids/Unité suppl.** pour recalculer le **Poids total** et/ou la **Quantité supplémentaire**.
2. Choisissez l’une des options suivantes :

    1. **Poids** : pour ne recalculer que le **Poids total**, sur la base des informations actuelles sur le **Poids net** sur les fiches article et immobilisation.
    2. **Quantité d’unité de mesure supplémentaire** : pour ne recalculer que la **Quantité supplémentaire** sur la ligne **Rapport Intrastat** si elle existe, sur la base des informations actuelles concernant l'**Unité de mesure supplémentaire** sur les fiches article et immobilisation.
    3. **Les deux** : pour recalculer à la fois le **Poids total** et la **Quantité supplémentaire** sur la base des informations actuelles sur les fiches article et immobilisation.
3. Cliquez sur **OK** pour démarrer le traitement en lot.

## <a name="report-intrastat-in-a-file"></a>Rapport Intrastat dans un fichier

Vous pouvez soumettre le rapport Intrastat sous forme de fichier en fonction des exigences des différentes autorités locales. Avant de créer le fichier, vous devez exécuter le **Rapport liste de vérification** pour vérifier si toutes les lignes contiennent toutes les informations nécessaires et valides. Pour créer un fichier :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Liste Intrastat**, puis choisissez le lien associé.
2. Sélectionnez le **Rapport Intrastat** que vous souhaitez soumettre sous forme de fichier.
3. Si ce n’est déjà fait, renseignez le **Rapport Intrastat** manuellement ou sélectionnez l’action **Proposer lignes**.
4. Choisissez l'action **Créer fichier**.
5. Le fichier Intrastat sera enregistré au format souhaité.

Une fois le fichier créé, [!INCLUDE[prod_short](includes/prod_short.md)] remplira automatiquement les détails suivants concernant la génération de rapports :

* La **Date d’exportation** pour spécifier la date à laquelle le rapport a été exporté.
* L’**Heure d’exportation** pour spécifier l’heure à laquelle le rapport a été exporté.

> [!NOTE]
> La prochaine fois que vous créerez un fichier, les champs **Date d’exportation** et **Heure d’exportation** ne conserveront que les informations sur le dernier fichier que vous avez créé.

## <a name="intrastat-rules"></a>Règles Intrastat

### <a name="grouping-lines"></a>Regrouper des lignes

Dans les lignes d’un **Rapport Intrastat**, il n’existe aucun regroupement par champ. Toutes les écritures sont copiées de la source d’origine, vous pouvez donc les localiser rapidement en fonction de la combinaison du **Type de Source** et du **N° séquence origine**.

Le regroupement requis par les autorités sera fourni dans le fichier exporté. Vous devez le configurer dans la **Définition d’échange de données**, qui est entièrement configurable. Pour plus d’informations, consultez [Configurer les définitions d’échange de données](across-how-to-set-up-data-exchange-definitions.md).

### <a name="fixed-assets-reporting"></a>Génération de rapports sur les immobilisations

Les immobilisations seront affichées dans les lignes Intrastat uniquement si :

* Le **Type report immo.** dans le champ **Écriture TVA** est **Coût acquisition** et si le **Type de document** est **Facture** dans le cas des achats, et
* Le **Type report immo.** dans le champ **Écriture TVA** est **Produit de cession** et si le **Type de document** est **Facture** dans le cas des ventes.

### <a name="intrastat-report-statuses"></a>États du rapport Intrastat

Lorsque vous travaillez avec le **Rapport Intrastat**, vous voyez un champ **État** dans l’en-tête du document. Vous pouvez trouver les états suivants ainsi que les règles associées :

* *Ouvert* : ce état est créé automatiquement lorsque vous créez un nouveau rapport Intrastat et vous pouvez effectuer toutes les opérations dans cet état.
* *Publié* : [!INCLUDE[prod_short](includes/prod_short.md)] change automatiquement l’état en *Publié* lorsque vous créez un fichier. À partir de ce moment, vous ne pouvez plus modifier votre **rapport Intrastat**. Si vous devez modifier quelque chose et soumettre un nouveau rapport, vous pouvez utiliser l’action **Rouvrir** pour rouvrir le rapport Intrastat. Une fois le document rouvert, vous pouvez utiliser l’action **Libérer** pour libérer à nouveau le document.
* **Déclaré** : spécifie si l’écriture a déjà été déclarée aux administrations fiscales. Ce n’est pas un état normal mais un champ indépendant, et même si vous rouvriez le rapport Intrastat, cela montrerait toujours que le fichier est déjà créé pour ce rapport.

### <a name="triangular-trade-in-intrastat"></a>Commerce triangulaire dans Intrastat

Le commerce triangulaire implique des échanges entre trois pays ou régions où les marchandises contournent le pays de la compagnie déclarante. Dans Business Central, cela peut être facilité grâce à la fonctionnalité [Livraison directe](sales-how-drop-shipment.md) . Pour activer cette option, activez le champ **Inclure la livraison directe** dans **Configuration des rapports Intrastat**.  

Lorsque vous activez cette option, le système utilise les règles suivantes, mais uniquement si la **Livraison directe** est marquée dans le **Document de vente** : 

| Expéditeur | Livrer à | Résultat Intrastat attendu |
|----------|------------|----------------------|
| Pays comme dans les **Informations compagnie** | Pays comme dans les **Informations compagnie** | Aucune ligne Intrastat |  
| Pays comme dans les **Informations compagnie** | Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Ligne de livraison Intrastat | 
| Pays comme dans les **Informations compagnie** | Pays hors UE | Aucune ligne Intrastat |   
| Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Pays comme dans les **Informations compagnie** | Ligne de réception Intrastat | 
| Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Aucune ligne Intrastat |
| Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Pays hors UE | Aucune ligne Intrastat | 
| Pays hors UE | Pays comme dans les **Informations compagnie** | Aucune ligne Intrastat |  
| Pays hors UE | Pays de l’UE différent du pays indiqué dans les **Informations compagnie** | Aucune ligne Intrastat |
| Pays hors UE | Pays hors UE | Aucune ligne Intrastat |   

## <a name="see-also"></a>Voir aussi .

[Configurer des rapports Intrastat](finance-how-setup-report-intrastat.md)  
[Gestion financière](finance.md)  
[Livraison directe ](sales-how-drop-shipment.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
