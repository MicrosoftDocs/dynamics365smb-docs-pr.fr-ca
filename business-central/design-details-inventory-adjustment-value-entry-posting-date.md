---
title: Date de report des écritures valeur
description: Découvrez comment le traitement en lot Ajuster coûts - Écr. article identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: fe03f25c4f9024cb82b83af915e69073d2fdcf1e
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4751515"
---
# <a name="design-details-posting-date-on-adjustment-value-entry"></a>Détails de conception : date de report de l'écriture valeur d'ajustement
Cet article fournit des instructions aux utilisateurs de la fonctionnalité Évaluation stock dans [!INCLUDE[prod_short](includes/prod_short.md)]. L'article spécifique donne des informations sur la façon dont le traitement en lot **Ajuster coûts - Écr. article** identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.  

Tout d'abord, le concept du processus est passé en revue, c'est-à-dire la manière dont le traitement en lot identifie et affecte la date de report à l'écriture valeur à créer. Ensuite, des scénarios communs que l'équipe de support rencontre parfois sont décrits. Enfin, les concepts utilisés à partir de la version 3.0 sont résumés.  

## <a name="the-concept"></a>Le concept  
À partir de la version 5.0, le traitement en lot **Ajuster coûts - Écr. article** affecte une date de report à l'écriture valeur qu'il est sur le point de créer dans les étapes suivantes :  

1.  Initialement, la date de report de l'écriture à créer est la même que celle de l'écriture qu'elle ajuste.  

2.  La date de report est validée par rapport aux périodes d'inventaire et/ou à la configuration du grand livre.  

3.  Affectation d'une date de report : si la date de report initiale n'est pas comprise dans la plage de dates de report autorisées, le traitement en lot affecte une date de report autorisée à partir de la Configuration du grand livre ou de la Période d'inventaire. Si les périodes d'inventaire et les dates de report autorisées dans la configuration du grand livre sont définies, la date la plus récente des deux est affectée à l'écriture valeur d'ajustement.  

 Examinons ce processus plus en détail. Supposons que nous avons une écriture article de type Vente. L'article a été livré le 5 septembre 2013 et il a été facturé le jour suivant.  

![Province des écritures article dans le scénario](media/helene/TechArticleAdjustcost1.png "Province des écritures article dans le scénario")  

La première écriture valeur (379) représente la livraison et utilise la même date de report que l'écriture article parent.  

La deuxième écriture valeur (381) représente la facture.  

 La troisième écriture valeur (391) est un ajustement de l'écriture valeur de facturation (381)  

 ![Province des écritures valeur dans le scénario](media/helene/TechArticleAdjustcost2.png "Province des écritures valeur dans le scénario")  

 Étape 1 : l'écriture valeur d'ajustement à créer a la même date de report que l'écriture qu'elle ajuste, comme illustré ci-dessus par l'écriture valeur 391.  

 Étape 2 : validation de la date de report affectée initiale.  

Le traitement en lot **Ajuster coûts - Écr. article** détermine si la date de report initiale de l'écriture valeur d'ajustement est comprise dans la plage de dates de report autorisées en fonction des périodes d'inventaire et/ou de la configuration du grand livre.  

 Examinons la vente mentionnée ci-dessus en ajoutant la configuration des plages de dates de report autorisées.  

 Périodes d'inventaire :  

![Périodes d'inventaire dans le scénario](media/helene/TechArticleAdjustcost3.png "Périodes d'inventaire dans le scénario")

 La première date de report autorisée est le premier jour de la première période ouverte. 1er septembre 2013.  

 Configuration du grand livre :  

![Configuration grand livre dans le scénario](media/helene/TechArticleAdjustcost4.png "Configuration grand livre dans le scénario")

 La première date de report autorisée est la date indiquée dans le champ Début période report : 10 septembre 2013.  

 Si les périodes d'inventaire et les dates de report autorisées dans la configuration du grand livre sont définies, la date la plus récente des deux définit la plage de dates de report autorisées.  

 Étape 3 : affectation d'une date de report autorisée.  

 La date de report affectée initiale était le 6 septembre, comme illustré à l'étape 1. Toutefois, dans la 2e étape, le traitement en lot Ajuster coûts - Écr. article identifie que la date de report autorisée la plus proche est le 10 septembre et affecte donc le 10 septembre à l'écriture valeur d'ajustement ci-dessous.  

 ![Province des écritures valeur dans le scénario 2](media/helene/TechArticleAdjustcost5.png "Province des écritures valeur dans le scénario 2")

 Nous avons passé en revue le concept d'affectation de dates de report aux écritures valeur créées par le traitement en lot Ajuster coûts - Écr. article.  

 Examinons maintenant certains scénarios que l'équipe de support rencontre parfois pour les dates de report affectées dans le traitement en lot Ajuster coûts – Écr article et les configurations associées.  

## <a name="scenarios"></a>Cas de figure  

### <a name="scenario-i-posting-date-is-not-within-your-range-of-allowed-posting-dates"></a>Scénario I : « La date de report n'est pas incluse dans la plage de dates de report autorisées... »  
 Dans ce scénario, l'utilisateur reçoit le message d'erreur indiqué lorsque le traitement en lot Ajuster coûts – Écr article est exécuté.  

 Dans la section précédente qui décrit le concept d'affectation de dates de report, l'intention du traitement en lot Ajuster coûts – Écr article est de créer une écriture valeur avec la date de report du 10 septembre.  

![Message d'erreur sur la date de report](media/helene/TechArticleAdjustcost6.png "Message d'erreur sur la date de report")

 Nous passons à la configuration des utilisateurs :  

![Configuration des dates de report autorisées de l'utilisateur](media/helene/TechArticleAdjustcost7.png "Configuration des dates de report autorisées de l'utilisateur")

 L'utilisateur dans ce cas a une plage de dates de report autorisées allant du 11 au 30 septembre et n'est donc pas autorisé à reporter l'écriture valeur d'ajustement avec la date de report du 10 septembre.  

![Aperçu de la configuration de la date de report impliquée](media/helene/TechArticleAdjustcost8.png "Aperçu de la configuration de la date de report impliquée")

 L'article de la Base de connaissances [952996](https://mbs2.microsoft.com/Knowledgebase/kbdisplay.aspx?WTNTZSMNWUKNTMMYXUPYZQPOUXNXSPSYOQQYYMLUQLOYYMWP) décrit des scénarios supplémentaires associés au message d'erreur indiqué.  

### <a name="scenario-ii-posting-date-on-adjustment-value-entry-versus-posting-date-on-entry-causing-the-adjustment-such-as-revaluation-or-item-charge"></a>Scénario II : comparaison entre la date de report de l'écriture valeur d'ajustement et la date de report de l'écriture à l'origine de l'ajustement, comme une réévaluation ou des frais annexes.  

### <a name="revaluation-scenario"></a>Scénario de réévaluation :  
 Conditions préalables :  

 Configuration de l'inventaire :  

-   Report coûts automatique = Oui  

-   Ajustement automatique des coûts = Toujours  

-   Type calcul coût moyen = Article  

-   Période coût moyen = Jour  

 Configuration du grand livre :  

-   Début période report = 1er janvier 2014  

-   Fin période report = Vide  

 Configuration des utilisateurs :  

-   Début période report = 1er décembre 2013.  

-   Fin période report = Vide  

##### <a name="to-test-the-scenario"></a>Pour tester le scénario  

1.  Créez un article TEST :  

     Unité de mesure de base = PCS  

     Mode évaluation stock = Moyen  

     Sélectionnez des groupes de report facultatifs.  

2.  Ouvrez le journal article, puis créez et reportez une ligne comme suit :  

     Date de report = 15 décembre 2013  

     Article = TEST  

     Type écriture = Achat  

     Quantité = 100  

     Montant unitaire = 10  

3.  Ouvrez le journal article, puis créez et reportez une ligne comme suit :  

     Date = 20 décembre 2013  

     Article = TEST  

     Type écriture = Ajustement négatif  

     Quantité = 2  

4.  Ouvrez le journal article, puis créez et reportez une ligne comme suit :  

     Date = 15 janvier 2014  

     Article = TEST  

     Type écriture = Ajustement négatif  

     Quantité = 3  

5.  Ouvrez le journal réévaluation, puis créez et reportez une ligne comme suit :  

     Article = TEST  

     Écriture référence = Sélectionnez l'écriture achat reportée à l'étape 2. La date de report de la réévaluation est identique à l'écriture qu'elle ajuste.  

     Coût unitaire réévalué = 40  

 Les écritures article et les écritures valeur suivantes ont été reportées :  

![Aperçu des écritures article et valeur article résultantes 1](media/helene/TechArticleAdjustcost9.png "Aperçu des écritures article et valeur article résultantes 1")

 ![Aperçu des écritures article et valeur article résultantes 2](media/helene/TechArticleAdjustcost10.png "Aperçu des écritures article et valeur article résultantes 2")

 Le traitement en lot Ajuster coûts – Écr article a identifié une modification du coût et ajusté les ajustements négatifs.  

 **Révision des dates de report des écritures valeur d'ajustement créées :** la date de report autorisée la plus proche à laquelle le traitement en lot Ajuster coûts – Écr article doit faire référence est le 1er janvier 2014, comme indiqué dans la configuration du grand livre.  

 **Ajustement négatif à l'étape 3 :** la date de report affectée est le 1er janvier, qui est fournie par la configuration du grand livre. La date de report de l'écriture valeur concernée par l'ajustement est le 20 décembre 2013. Selon la configuration du grand livre, la date n'est pas comprise dans la plage de dates de report autorisées. Par conséquent, la date de report indiquée dans le champ Début période report de la configuration du grand livre est affectée à l'écriture valeur d'ajustement.  

 **Ajustement négatif à l'étape 4 :** la date de report affectée est le 15 janvier. L'écriture valeur concernée par l'ajustement a une date de report fixée au 15 janvier, qui est comprise dans la plage de dates de report autorisées selon la configuration du grand livre.  

 L'ajustement effectué pour l'ajustement négatif à l'étape 3 fait l'objet d'une discussion. La date de report favorable pour l'écriture valeur d'ajustement aurait été le 20 décembre ou au moins une date en décembre, car la réévaluation à l'origine du changement de COGS a été reportée en décembre.  

 Pour procéder à l'ajustement en décembre de l'ajustement négatif à l'étape 3, le champ Début période report dans la configuration du grand livre doit indiquer une date en décembre.  

 **Conclusion :**  

 Avec les expériences tirées de ce scénario et en tenant compte de la configuration la plus appropriée de la plage de dates de report autorisées pour une compagnie, la recommandation suivante peut être utile : tant que les modifications de la valeur d'inventaire peuvent être reportées dans une période, décembre en l'occurrence, la configuration utilisée par la compagnie pour les plages de dates de report autorisées doit être alignée sur cette décision. Lorsque l'option Début période report dans la configuration du grand livre est définie sur le 1er décembre, la réévaluation effectuée en décembre peut être transférée vers les écritures sortantes affectées dans la même période.  

 Les groupes d'utilisateurs qui ne sont pas autorisés à effectuer des reports en décembre mais en janvier, ce qui était probablement censé être limité par la configuration du grand livre dans ce scénario, devront plutôt être gérés via la configuration des utilisateurs.  

### <a name="item-charge-scenario"></a>Scénario de frais annexes :  
 Conditions préalables :  

 Configuration de l'inventaire :  

-   Report coûts automatique = Oui  

-   Ajustement automatique des coûts = Toujours  

-   Type calcul coût moyen = Article  

-   Période coût moyen = Jour  

 Configuration du grand livre :  

-   Début période report = 1er décembre 2013.  

-   Fin période report = Vide  

 Configuration des utilisateurs :  

-   Début période report = 1er décembre 2013.  

-   Fin période report = Vide  

##### <a name="to-test-the-scenario"></a>Pour tester le scénario  

1.  Créez des frais annexes :  

     Unité de mesure de base = PCS  

     Mode évaluation stock = Moyen  

     Sélectionnez des groupes de report facultatifs.  

2.  Créer un bon de commande  

     Numéro du fournisseur : 10000  

     Date de report = 15 décembre 2013  

     N° facture fournisseur : 1234  

     Sur la ligne bon de commande :  

     Article = FRAIS  

     Quantité = 1  

     Coût unitaire direct = 100  

     Reportez la réception et la facture.  

3.  Créez un document de vente :  

     N° débiteur : 10000  

     Date de report = 16 décembre 2013  

     Sur la ligne document de vente :  

     Article = FRAIS  

     Quantité = 1  

     Prix unitaire = 135  

     Reportez la livraison et la facture.  

4.  Configuration du grand livre :  

     Début période report = 1er janvier 2014  

     Fin période report = Vide  

5.  Créez un bon de commande :  

     Numéro du fournisseur : 10000  

     Date de report = 2 janvier 2014  

     N° facture fournisseur : 2345  

     Sur la ligne bon de commande :  

     Frais annexes = JB-FREIGHT  

     Quantité = 1  

     Coût unitaire direct = 3  

     Affectez les frais annexes à la réception achat à l'étape 2.  

     Reportez la réception et la facture.  

     ![Aperçu des écritures article et valeur article résultantes 3](media/helene/TechArticleAdjustcost11.png "Aperçu des écritures article et valeur article résultantes 3")

6.  À la date du 3 janvier arrive une facture achat, contenant des frais annexes supplémentaires pour l'achat effectué à l'étape 2. La date de document de cette facture est le 30 décembre, elle est donc reportée avec la date de report du 30 décembre 2013.  

     Créez un bon de commande :  

     Numéro du fournisseur : 10000  

     Date de report = 30 décembre 2013  

     N° facture fournisseur : 3456  

     Sur la ligne bon de commande :  

     Frais annexes = JB-FREIGHT  

     Quantité = 1  

     Coût unitaire direct = 2  

     Affectez les frais annexes à la réception achat à l'étape 2  

     Reportez la réception et la facture.  

   ![Aperçu des écritures article et valeur article résultantes 4](media/helene/TechArticleAdjustcost12.png "Aperçu des écritures article et valeur article résultantes 4")

 Le rapport Évaluation de l'inventaire est imprimé à la date du 31 décembre 2013  

![Contenu du rapport d'évaluation de l'inventaire](media/helene/TechArticleAdjustcost13.png "Contenu du rapport d'évaluation de l'inventaire")

 **Résumé du scénario :**  

 Le scénario décrit se termine avec un rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur = 2. Les frais annexes reportés à l'étape 11 font partie de la valeur d'augmentation d'inventaire de décembre alors que la diminution d'inventaire pour la même période n'est pas affectée.  

 Définir l'option Début période report au 1er janvier dans la configuration du grand livre était recommandé pour les premiers frais annexes. Les coûts de l'augmentation et de la diminution d'inventaire ont été enregistrés dans la même période. Cependant, pour les deuxièmes frais annexes, le changement de COGS est reconnu dans la période suivante.  

 **Conclusion :**  

 Il est difficile d'avoir le rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur <> 0. Dans ce cas, il est également plus difficile d'exprimer des paramètres optimaux, étant donné que les factures achat arrivent le même jour mais couvrent différentes périodes ou même différents exercices financiers. Le passage à un nouvel exercice financier nécessite généralement une planification et à cet effet, le processus Ajuster coûts – Écr article qui reconnaît COGS, doit être pris en compte.  

 Dans ce scénario, une solution aurait pu être que le champ Début période report dans la Configuration du grand livre indique une date en décembre pour quelques jours de plus et que le report des premiers frais annexes soit postposé pour que tous les coûts de la période ou de l'exercice financier précédent soient reconnus pour la période à laquelle ils appartiennent. Ainsi, le traitement en lot Ajuster coûts – Écr. article serait exécuté et la date de report autorisée serait déplacée vers la nouvelle période ou le nouvel exercice financier. Les premiers frais annexes avec la date de report du 2 janvier peuvent ensuite être reportés.  

## <a name="history-of-adjust-cost--item-entries-batch-job"></a>Historique du traitement en lot Ajuster coûts – Écr. article  
 Voici un résumé du concept d'affectation de dates de report aux écritures valeur d'ajustement par le traitement en lot Ajuster coûts – Écr article depuis la version 3.0.  

### <a name="from-version-30370a"></a>À partir de la version 3.0..3.70.A  
 Dans le formulaire de demande du traitement en lot Ajuster coûts - Écr. article, la date de report doit être saisie par l'utilisateur. Le traitement en lot exécute toutes les modifications nécessaires et crée des écritures valeur avec la date de report saisie dans le formulaire de demande. La date de report suggérée à utiliser est la date du jour.  

### <a name="version-370b40"></a>Version 3.70.B..4.0  
 Dans le formulaire de demande du traitement en lot Ajuster coûts - Écr. article, la date de report écriture période fermée doit être saisie par l'utilisateur. Le traitement en lot exécute toutes les modifications nécessaires et crée des écritures valeur avec la date de report de l'écriture article parent (date de livraison de la vente concernée par l'ajustement). Si la date de report de l'écriture article parent n'est pas comprise dans la plage de dates de report autorisées, la date de report indiquée comme date de report écriture période fermée sera affectée à l'écriture valeur d'ajustement. Une date est considérée comme incluse dans une période fermée lorsqu'elle est antérieure à la date indiquée dans le champ Début période report dans la Configuration du grand livre.  

### <a name="from-version-50"></a>À partir de la version 5.0 :  
 Il n'est plus nécessaire d'indiquer une date de report dans le formulaire de demande du traitement en lot Ajuster coûts - Écr. article. Le traitement en lot exécute toutes les modifications nécessaires et crée des écritures valeur avec la date de report de l'écriture valeur qu'il ajuste. Si la date de report n'est pas comprise dans la plage de dates de report autorisées dans le champ Début période report de la configuration du grand livre ou si les périodes d'inventaire sont utilisées, la date la plus récente des deux sera utilisée. Reportez-vous au concept décrit ci-dessus.  

## <a name="history-of-post-inventory-cost-to-gl-batch-job"></a>Historique du traitement en lot Reporter le coût de l'inventaire dans le grand livre  
 Le traitement en lot Reporter le coût de l'inventaire dans le grand livre est étroitement lié au traitement en lot Ajuster coûts – Écr article. C'est pourquoi l'historique de ce traitement en lot est résumé et partagé ici également.  

### <a name="from-version-30370a"></a>À partir de la version 3.0..3.70.A  
 Dans le formulaire de demande du traitement en lot Reporter le coût de l'inventaire dans le grand livre, une date de report doit être saisie par l'utilisateur. Le traitement en lot exécute toutes les écritures valeur correspondant au filtre, le cas échéant, et crée des écritures avec la date de report saisie dans le formulaire de demande.  

### <a name="version-370b40"></a>Version 3.70.B..4.0  
 Dans le formulaire de demande du traitement en lot Reporter le coût de l'inventaire dans le grand livre, le champ Date de report écriture période fermée est disponible. L'application utilise la date que vous saisissez dans ce champ comme date de report pour les écritures qu'il crée pour les écritures valeur dont les dates de report se trouvent dans des périodes comptables fermées. Sinon, les écritures auront la même date de report que les écritures valeur d'origine. Une date est considérée comme incluse dans une période fermée lorsqu'elle est antérieure à la date indiquée dans le champ Début période report dans la Configuration du grand livre. En cas de report dans le grand livre par groupe de report, les écritures auront la date de report spécifiée dans le champ Date de report du formulaire de demande.  

 Dans la version 3 et 4, le traitement en lot analyse toutes les écritures valeur pour détecter s'il existe des écritures valeur dont le coût indiqué (réel) diffère du coût reporté au GL. Si une différence est détectée, le montant différent sera reporté dans une écriture. Si le report des coûts prévus est utilisé, les champs correspondants sont traités de la même manière.  

![Coût réel comparé au coût prévu](media/helene/TechArticleAdjustcost14.png "Coût réel comparé au coût prévu")

### <a name="from-version-50"></a>À partir de la version 5.0 :  
 Il n'est plus nécessaire d'indiquer une date de report dans le formulaire de demande du traitement en lot Reporter le coût de l'inventaire dans le grand livre. L'écriture est créée avec la même date de report que l'écriture valeur associée. Pour exécuter le traitement en lot, la plage de dates de report autorisées doit autoriser la date de report de l'écriture créée. Sinon, la plage de dates de report autorisées doit être temporairement rouverte en modifiant ou en supprimant les dates des champs Début période report et Fin période report dans la configuration du grand livre. Pour éviter les problèmes de rapprochement, la date de report de l'écriture doit correspondre à la date de report de l'écriture valeur.  

 Le traitement en lot analyse la table 5811 - Reporter l'écriture de valeur au GL pour identifier les écritures valeur concernées par le report au grand livre. Une fois l'exécution réussie, la table est vidée.

## <a name="see-also"></a>Voir aussi  
[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : Affectation article](design-details-item-application.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]