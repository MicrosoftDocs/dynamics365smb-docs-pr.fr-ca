---
title: Configuration de la TVA
description: Assurez-vous de calculer, de reporter et de déclarer correctement la TVA pour les ventes et les achats. Il est recommandé d'utiliser le guide de configuration assistée pour configurer la TVA.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 06/16/2021
ms.author: bholtorf
ms.openlocfilehash: e62a4709b493d44487d189dfd9ec5b76bc6987b8
ms.sourcegitcommit: 41876b559872fe7adbfa5b59a6e1a71dc907fb15
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/14/2021
ms.locfileid: "7921030"
---
# <a name="set-up-calculations-and-posting-methods-for-value-added-tax"></a>Configurer des méthodes de calcul et de report de la taxe sur la valeur ajoutée

Les clients et les entreprises payent la TVA lorsqu'ils achètent des biens ou des services. Le montant de la TVA à payer peut varier en fonction de plusieurs facteurs. Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous configurez la TVA pour spécifier les taux à utiliser pour calculer les montants de taxe sur la base des éléments suivants :

* À qui vous vendez  
* À qui vous achetez  
* Ce que vous vendez  
* Ce que vous achetez  

Vous pouvez configurer manuellement les calculs de la TVA, mais cette procédure peut être délicate et longue. Pour vous faciliter la tâche, nous avons fourni un guide de configuration assistée appelé **Paramètres TVA** pour vous aider. Il est recommandé d'utiliser le guide de configuration assistée pour configurer la TVA.

> [!NOTE]  
> Vous pouvez utiliser le guide uniquement si vous avez créé un profil Ma compagnie, et si vous n'avez pas reporté de transactions incluant la TVA. Sinon, il serait très facile d'utiliser différents taux de TVA par erreur et de générer des états de TVA erronés.  

Si vous souhaitez configurer vous-même les calculs de TVA, ou en savoir plus sur chaque étape, cette rubrique contient des descriptions de chaque étape.  

> [!TIP]
> [!INCLUDE [prod_short](includes/prod_short.md)] est disponible dans les pays qui n’utilisent pas la TVA. Pour plus d’informations sur la configuration et la déclaration des taxes dans votre pays, consultez les articles de la section [Fonctionnalités locales dans Business Central](about-localization.md).  

## <a name="to-use-the-vat-setup-assisted-setup-guide-to-set-up-vat-recommended"></a>Pour utiliser le guide de configuration assistée Configuration TVA pour configurer la TVA (recommandé)

Il est recommandé d'utiliser le guide de configuration assistée Paramètres TVA pour configurer la TVA dans [!INCLUDE[prod_short](includes/prod_short.md)].

Pour démarrer le guide de configuration assistée, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration assistée**.  
2. Choisissez **Configuration TVA** et finalisez la procédure.
3. Une fois la configuration assistée terminée, visitez la page **Configuration report TVA** et vérifiez si vous devez renseigner d'autres champs en fonction des exigences locales de votre version de [!INCLUDE [prod_short](includes/prod_short.md)]. Pour plus d'informations, voir [Fonctionnalité locale dans Business Central](about-localization.md).  

## <a name="to-set-up-vat-registration-numbers-for-your-country-or-region"></a>Pour configurer les numéros d'identification intracommunautaire pour votre pays ou région

Pour garantir que les personnes entrent des numéros d'identification intracommunautaire valides, vous pouvez définir des formats pour les numéros d'identification intracommunautaire utilisés dans des pays ou des régions dans lesquels vous travaillez. [!INCLUDE[prod_short](includes/prod_short.md)] affichera un message d'erreur lorsque un employé fait une erreur ou utilise un format incorrect pour le pays ou la région.

Pour configurer des numéros d'identification intracommunautaire, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Pays/Régions**.
2. Choisissez le pays ou la région, puis sélectionnez l'action **Formats N° d'inscription TPS/TVH**.
3. Dans le champ **Formats**, définissez le format en saisissant un ou plusieurs des caractères suivants :  

* **#** Requiert un numéro à un seul chiffre.  
* **@** Requiert une lettre. Ce texte n'est pas sensible à la casse.  
* **?** Tout caractère est autorisé.  

    > [!Tip]
    > Vous pouvez utiliser d'autres caractères tant qu'ils sont présents dans le format du pays ou de la région. Par exemple, si vous souhaitez inclure un point ou un trait d'union entre des séries de chiffres, vous pouvez définir le format sous la forme ##.####.### ou @@-###-###.  

## <a name="to-set-up-vat-business-posting-groups"></a>Pour configurer des groupes comptabilisation marché TVA
Les groupes de report marché TVA doivent représenter les marchés dans lesquels vous faites des affaires avec les clients et fournisseurs, et définissent comment calculer et reporter la TVA dans chaque marché. Des exemples de groupes comptabilisation marché TVA sont **France** et **Union Européenne (UE)**.  

Utilisez des codes faciles à retenir et qui décrivent le groupe comptabilisation marché, tels que **UE**, **Non-UE** ou **France**. Le code doit être unique. Vous pouvez créer autant de codes que vous le souhaitez, mais vous ne pouvez pas avoir le même code deux fois dans une table.

Pour configurer un groupe de report marché TVA, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupe de report marché TVA**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.

Paramétrez les groupes comptabilisation marché TVA par défaut en les liant à des groupes comptabilisation marché. [!INCLUDE[prod_short](includes/prod_short.md)] affecte automatiquement le groupe comptabilisation marché TVA lorsque vous affectez le groupe comptabilisation marché à un client, un fournisseur ou un compte général.

## <a name="to-set-up-vat-product-posting-groups"></a>Pour paramétrer des groupes comptabilisation produit TVA
Les groupes de report produit TVA représentent les articles et les ressources que vous achetez ou vendez et déterminent la manière de calculer et de reporter la TVA en fonction du type d'article ou de ressource acheté ou vendu.  
Il est recommandé d'utiliser des codes faciles à retenir et qui décrivent le taux, par exemple **SANS TVA** ou **Zéro**, **TVA10** ou **Réduite** pour 10 % de TVA, et **TVA25** ou **Standard** pour 25 %.

Pour configurer un groupe de report marché TVA, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report produit TVA**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-combine-vat-posting-groups-in-vat-posting-setups"></a>Pour regrouper des groupes de report TVA dans les configurations de report TVA
[!INCLUDE[prod_short](includes/prod_short.md)] calcule les montants de TVA sur les ventes et les achats en fonction des paramètres comptabilisation TVA, qui sont des combinaisons de groupes comptabilisation marché et produit TVA. Pour chaque combinaison, vous pouvez spécifier le pourcentage de TVA, le mode calcul TVA et les comptes du grand livre pour le report de la TVA pour les achats, les ventes, ainsi que les frais renversés. Vous pouvez également spécifier si la TVA doit être recalculée lorsqu'un escompte de paiement est affecté ou reçu.  

Définissez autant de combinaisons que nécessaire. Si vous voulez regrouper des combinaisons de paramètres comptabilisation TVA avec des attributs similaires, vous pouvez définir un **Identifiant TVA** pour chaque groupe et affecter l'identifiant aux membres du groupe.

Pour regrouper des configurations report TVA, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration report TVA**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins.

## <a name="to-assign-vat-posting-groups-by-default-to-multiple-entities"></a>Pour affecter des groupes de report TVA par défaut à plusieurs entités
Si vous souhaitez appliquer les mêmes groupes comptabilisation TVA à plusieurs entités, vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour le faire par défaut. Plusieurs méthodes sont disponibles :

* Vous pouvez affecter des groupes comptabilisation marché aux groupes comptabilisation marché généraux ou aux modèles client ou fournisseur
* Vous pouvez affecter des groupes comptabilisation produit TVA aux groupes comptabilisation produit généraux  

Le groupe de report marché ou produit TVA est affecté lorsque vous choisissez un groupe de report marché ou produit pour un client, un fournisseur, un article ou une ressource.

## <a name="assigning-vat-posting-groups-to-accounts-customers-vendors-items-and-resources"></a>Affectation de groupes de report TVA à des comptes, clients, fournisseurs, articles et ressources
Les sections suivantes décrivent comment affecter des groupes comptabilisation TVA à des entités individuelles.

### <a name="to-assign-vat-posting-groups-to-individual-general-ledger-accounts"></a>Pour affecter des groupes comptabilisation TVA à des comptes généraux individuels
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
2. Ouvrez la fiche **Compte général** pour le compte.  
3. Sous le raccourci **Comptabilisation**, dans le champ **Type compta. TVA**, choisissez **Vente** ou **Achat**.  
5. Choisissez les groupes comptabilisation TVA à utiliser pour le compte vente ou achat.  

### <a name="to-assign-vat-business-posting-groups-to-customers-and-vendors"></a>Pour affecter des groupes comptabilisation marché TVA à des clients et des fournisseurs  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Client** ou **Fournisseur**, puis choisissez le lien associé.  
2. Sur la fiche **Client** ou **Fournisseur**, développez le raccourci **Facturation**.  
3. Choisissez le groupe de report marché TVA.  

### <a name="to-assign-vat-product-posting-groups-to-individual-items-and-resources"></a>Pour affecter des groupes comptabilisation produit TVA à des articles et des ressources individuels  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Article** ou **Ressource**, puis choisissez le lien associé.  
2. Exécutez l'une des opérations suivantes :  

* Sur la fiche **Article**, développez le raccourci **Prix et validation**, puis sélectionnez **Afficher plus** pour afficher le champ **Groupe compta. produit TVA**.  
* Sur la fiche **Ressource**, développez le raccourci **Facturation**.  
3. Choisissez le groupe de report produit TVA.  

## <a name="setting-up-clauses-to-explain-vat-exemption-or-non-standard-vat-rates"></a>Configuration de clauses pour expliquer l'exonération de TVA ou les taux de TVA non standard
Vous configurez une clause TVA afin de décrire le type utilisation de TVA qui est appliquée. Les informations peuvent être requises par une réglementation gouvernementale. Après avoir configuré une clause TVA et l'avoir associée à une configuration report TVA, la clause TVA est affichée sur les documents vente imprimés qui utilisent le groupe de configuration report TVA.

Si nécessaire, vous pouvez également spécifier comment convertir les clauses TVA dans d'autres langues. Ensuite, lorsque vous créez et imprimez un document vente qui contient un identificateur TVA, le document inclura la clause TVA traduite. Le code langue spécifié sur la fiche client détermine la langue.

Lorsque des taux de TVA non standard sont utilisés dans différents types de documents, tels que des factures ou des notes de crédit, les compagnies sont généralement tenues d'inclure un texte d'exonération (clause de TVA) indiquant les raisons pour lesquelles un taux de TVA réduit ou nul a été calculé. Vous pouvez définir différentes clauses de TVA à inclure dans les documents commerciaux en fonction du type de document, telles que facture ou note de crédit. Pour ce faire, accédez à la page **Clauses TVA par type doc.**.

Vous pouvez modifier ou supprimer une clause TVA, et les modifications que vous apportez seront visibles dans un rapport généré. Toutefois, [!INCLUDE[prod_short](includes/prod_short.md)] ne crée pas d'historique des modifications. Sur le rapport, les descriptions des clauses TVA sont imprimées et affichées pour toutes les lignes du rapport à côté du montant de la TVA et du montant de base de la TVA. Si aucune clause TVA n'a été définie pour les lignes du document vente, la totalité de la section est omise lors de l'impression du rapport.

### <a name="to-set-up-vat-clauses"></a>Pour configurer des clauses TVA
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clauses TVA**, puis choisissez le lien associé.  
2. Sur la page **Clauses TVA**, créez une ligne.  
3. Dans le champ **Code**, entrez un identificateur pour la clause. Vous utilisez ce code pour affecter la clause à des groupes comptabilisation TVA.  
4. Dans le champ **Description**, saisissez le texte d'exonération de TVA que vous souhaitez afficher sur les documents pouvant inclure la TVA. Dans le champ **Description 2**, entrez du texte supplémentaire, si nécessaire. Le texte sera affiché sur de nouvelles lignes.
5. Choisissez l'action **Description par type de document**.
6. Sur la page **Clauses TVA par type doc.**, remplissez les champs pour définir quel texte d'exonération de TVA afficher sur quel type de document.  
7. Facultatif : pour affecter immédiatement la clause TVA à une configuration report TVA, sélectionnez **Configuration**, puis choisissez la clause. Si vous souhaitez attendre, vous pouvez affecter la clause ultérieurement sur la page **Configuration report TVA**.  
8. Facultatif : pour spécifier comment traduire la clause TVA, sélectionnez l'action **Traductions**.

### <a name="to-assign-a-vat-clause-to-a-vat-posting-setup"></a>Pour affecter une clause TVA à une configuration report TVA
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration report TVA**, puis choisissez le lien associé.  
2. Dans la colonne **Clause TVA**, choisissez la clause à utiliser pour chaque paramètre comptabilisation TVA auquel elle s'applique.  

### <a name="to-specify-translations-for-vat-clauses"></a>Pour spécifier des traductions pour les clauses TVA
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clauses TVA**, puis choisissez le lien associé.  
2. Sélectionnez l'option **Traductions**.  
3. Dans le champ **Code langue**, sélectionnez la langue de traduction.  
4. Dans les champs **Description** et **Description 2**, saisissez les traductions des descriptions. Ce texte s'affiche dans les documents rapport de TVA traduits.  

## <a name="to-create-a-vat-posting-setup-to-handle-import-vat"></a>Pour créer une configuration de report TVA pour traiter la TVA à l'importation
Utilisez la fonction TVA à l'importation pour reporter un document dont le montant entier est TVA. Elle est utile lorsque vous recevez une facture des autorités fiscales pour la TVA sur les biens importés.  

Pour configurer des codes pour la TVA à l'importation, procédez comme suit :  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report produit TVA**, puis choisissez le lien associé.  
2. Sur la page Groupes de report produit TVA, configurez un groupe de report produit TVA pour la TVA à l'importation.  
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration report TVA**, puis choisissez le lien associé.  
4. Sur la page Configuration report de taxe, créez une ligne ou utilisez un groupe report marché TVA existant en combinaison avec le nouveau groupe report produit TVA créé pour la TVA à l'importation.  
5. Dans le champ **Mode calcul TVA**, sélectionnez **Exclusivement TVA**.  
6. Dans le champ **Compte TVA achat**, indiquez le compte général à utiliser pour valider la TVA à l'importation. Tous les autres comptes sont facultatifs.  


## <a name="using-reverse-charge-vat-for-trade-between-eu-countries-or-regions"></a>Utilisation des frais inversés TVA pour le commerce entre pays/régions de l'UE
Certaines compagnies doivent utiliser des frais renversés TVA dans leurs échanges avec d'autres compagnies. Par exemple, cette règle s'applique aux achats effectués auprès de pays/régions de l'Union européenne et aux ventes à des pays/régions de l'Union européenne.  

> [!NOTE]  
> Cette règle s'applique aux échanges avec des compagnies enregistrées comme assujetties à la TVA dans un autre pays/région de l'UE. Si vous commercez directement avec des clients dans d'autres pays/régions de l'UE, nous vous recommandons de prendre contact avec votre administration fiscale afin d'obtenir des informations sur les règles applicables en matière de TVA.  

> [!TIP]  
> Vous pouvez vérifier qu'une compagnie est enregistrée comme assujettie à la TVA dans un autre pays de l'UE en utilisant le service de validation des numéros d'inscription de TVA de l'UE. Le service est disponible gratuitement dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d'informations, voir la section _Vérifier les numéros d'identification TVA_ dans cette rubrique.

### <a name="sales-to-eu-countries-or-regions"></a>Ventes dans des pays/régions de l'UE
La TVA n'est pas calculée sur les ventes à des compagnies assujetties à la TVA situées dans d'autres pays/régions de l'UE. Vous devez déclarer la valeur de ces ventes aux pays/régions de l'UE séparément sur votre relevé fiscal.  

Pour calculer correctement la TVA sur les ventes effectuées dans des pays/régions de l'UE, vous devez procéder comme suit :  

* Configurez une ligne pour les ventes contenant les mêmes informations que pour les achats. Si vous avez déjà configuré des lignes sur la page Configuration du report TVA pour les achats effectués dans des pays/régions de l'UE, vous pouvez également utiliser ces lignes pour les ventes.  
* Affectez des groupes comptabilisation marché TVA dans le champ **Groupe compta. marché TVA** sur le raccourci **Facturation** de la fiche de chaque client de l'UE. Vous devez également saisir le numéro d'identification de TVA du client dans le champ **N° identif. intracomm.** sur le raccourci **Commerce étranger**.  

Lorsque vous reportez une vente à un client situé dans un autre pays/une autre région de l'UE, le montant de TVA est calculé et une écriture TVA est créée à l'aide des informations sur les frais renversés TVA et la base TVA (montant utilisé pour calculer la TVA). Aucune écriture n'est reportée sur les comptes TVA du grand livre.

## <a name="understanding-vat-rounding-for-documents"></a>Comprendre l'arrondissement TVA pour les documents
Les montants figurant dans les documents qui n'ont pas encore été reportés sont arrondis et affichés de façon à correspondre à l'arrondissement final des montants réellement reportés. La TVA est calculée pour un document terminé, ce qui signifie que la TVA calculée est basée sur la somme de toutes les lignes ayant le même identificateur TVA dans le document.




## <a name="see-also"></a>Voir aussi
[Configuration des modèles de relevé fiscal et des noms de relevé fiscal](finance-how-setup-vat-statement.md)   
[Configuration de la TVA non réalisée](finance-setup-unrealized-vat.md)      
[Déclarer la TVA à une autorité fiscale](finance-how-report-vat.md)      
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)    
[Utiliser l'outil de modification du taux de TVA](finance-how-use-vat-rate-change-tool.md)    
[Vérifier les numéros d'identification intracommunautaire](finance-how-validate-vat-registration-number.md)  
[Fonctionnalités locales dans Business Central](about-localization.md)  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/process-vat-dynamics-365-business-central/)


[!INCLUDE[footer-include](includes/footer-banner.md)]