---
title: Date de report sur l’écriture valeur d’ajustement par rapport à l’écriture source
description: "Découvrez le scénario «\_Comparaison entre la date de report de l’écriture valeur d’ajustement et la date de report de l’écriture à l’origine de l’ajustement, comme une réévaluation ou des frais annexes\_» lors de l’exécution du traitement en lot Ajuster coûts\_: Écr. article."
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 09/17/2021
ms.author: edupont
---

# <a name="posting-date-on-adjustment-value-entry-compared-to-the-source-entry"></a><a name="posting-date-on-adjustment-value-entry-compared-to-the-source-entry"></a><a name="posting-date-on-adjustment-value-entry-compared-to-the-source-entry"></a>Date de report sur l’écriture valeur d’ajustement par rapport à l’écriture source

Cet article compare la date de report de l’écriture valeur d’ajustement et la date de report de l’écriture à l’origine de l’ajustement provoquant l’exécution du traitement en lot Ajuster coûts : Écr. article, en particulier un scénario de réévaluation et un scénario de frais annexes.

Le traitement en lot **Ajuster coûts : Écr. article** traitera vos données en fonction de votre scénario et de la configuration de [!INCLUDE[prod_short](includes/prod_short.md)]. Dans cette section, nous décrivons deux processus distincts et, pour chacun, nous montrons le type d’impact du traitement en lot Ajuster coûts : Écr. article sur les données.

## <a name="revaluation-scenario"></a><a name="revaluation-scenario"></a><a name="revaluation-scenario"></a>Scénario de réévaluation

### <a name="prerequisites"></a><a name="prerequisites"></a><a name="prerequisites"></a>Conditions préalables

Veuillez saisir les valeurs suivantes :

**Configuration de l'inventaire** :  

- Report coûts automatique = Oui  

- Ajustement automatique des coûts = Toujours  

- Type calcul coût moyen = Article  

- Période coût moyen = Jour  

**Configuration du grand livre** :  

- Début période report = 1er janvier 2021  

- Autoriser Fin période report = Vide  

**Configuration utilisateur** :  

- Début période report = 1er décembre 2020  

- Autoriser Fin période report = Vide  

### <a name="to-test-the-scenario"></a><a name="to-test-the-scenario"></a><a name="to-test-the-scenario"></a>Pour tester le scénario

Testez ce scénario en effectuant les étapes suivantes.

1. Créez un **Article** appelé TEST avec les valeurs suivantes :  

     - Unité de mesure de base = PCS  

     - Mode évaluation stock = Moyen  

     - Sélectionnez des groupes de report facultatifs.  

2. Ouvrez un **journal article**, puis créez une écriture et reportez une ligne comme suit :  

     - Date de report = 15 décembre 2020  

     - Article = TEST  

     - Type écriture = Achat  

     - Quantité = 100  

     - Montant unitaire = 10  

3. Ouvrez un **journal article**, puis créez une écriture et reportez une ligne comme suit :  

     - Date = 20 décembre 2020  

     - Article = TEST  

     - Type écriture = Ajustement négatif  

     - Quantité = 2  

4. Ouvrez un **journal article**, puis créez une écriture et reportez une ligne comme suit :  

     - Date = 15 janvier 2021  

     - Article = TEST  

     - Type écriture = Ajustement négatif  

     - Quantité = 3  

5. Ouvrez un **journal réévaluation article**, puis créez une écriture et reportez une ligne comme suit :  

     - Article = TEST  

     - Écriture référence = Sélectionnez l'écriture achat reportée à l'étape 2. La date de report de la réévaluation est identique à l'écriture qu'elle ajuste.  

     - Coût unitaire (réévalué) = 40  

Le **grand livre article** et les **écritures valeur** suivantes ont été reportées :  

**Écriture du grand livre d’articles - achat** :  

|Numéro d’écriture  |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|317     |TEST         |2020/12/15         |Achat         |T00001         |100         |4000         |95        |

**Écritures de valeur**  

|Numéro d’écriture  |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  |Quantité écriture numéro article  |Coût indiqué (réel)  |Coût reporté dans grand livre  |Ajustement  |Écriture lettrage  |Code journal  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|376     |TEST|   2020/12/15    |317         |Achat         |Coût direct         |T00001         |100         |1 000,00          |1 000,00    |Non         |0         |ITEMNL         |
|379     |TEST   |**2020-12-15**    |317         |Achat         |Réévaluation         |T04002         |0         |3 000,00         |3 000,00         |Non         |0         |REVALINL         |

**Écriture du grand livre d’articles - ajustement négatif, étape 3**  

|N° séquence   |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|318     |TEST      |2020/12/20   |Ajustement négatif  |T00002         |-2         |-80         | 0        |

**Écritures de valeur**  

|Numéro d’écriture  |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  |Quantité écriture numéro article  |Coût indiqué (réel)  |Coût reporté dans grand livre  |Ajustement  |Écriture lettrage  |Code journal  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|377     |TEST|   2020/12/20    |318         |Ajustement négatif         |Coût direct         |T00002         |-2         |-20          |-20    |Non         |0         |ITEMNL         |
|380     |TEST   |**2021-01-01**    |318         |Ajustement négatif         |Coût direct         |T04002         |0         |-60         |-60         |Oui         |377         |INVTADAMT         |

**Écriture du grand livre d’articles - ajustement négatif, étape 4**  

|N° séquence   |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|319     |TEST      |2021/01/15   |Ajustement négatif  |T00003         |-3         |-120         | 0        |

**Écritures de valeur**  

|Numéro d’écriture  |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  |Quantité écriture numéro article  |Coût indiqué (réel)  |Coût reporté dans grand livre  |Ajustement  |Écriture lettrage  |Code journal  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|378     |TEST|   2021/01/15    |319         |Ajustement négatif         |Coût direct         |T00003         |-3         |-30          |-30    |Non         |0         |ITEMNL         |
|381     |TEST   |**2021-01-15**    |319         |Ajustement négatif         |Coût direct         |T04003         |0         |-90         |-90         |Oui         |378         |INVTADAMT         |

Le traitement en lot **Ajuster coûts – Écr. article** a identifié une modification du coût et ajusté les ajustements négatifs.  

**Révision des dates de report des écritures valeur d’ajustement créées :** la date de report autorisée la plus proche à laquelle le traitement en lot Ajuster coûts – Écr article doit faire référence est le 1er janvier 2021, comme indiqué dans la configuration grand livre.  

**Ajustement négatif à l'étape 3 :** la date de report affectée est le 1er janvier, qui est fournie par la configuration du grand livre. La date de report de l’écriture valeur concernée par l’ajustement est le 20 décembre 2020. Selon la configuration du grand livre, la date n'est pas comprise dans la plage de dates de report autorisées. Par conséquent, la date de report indiquée dans le champ Début période report de la configuration du grand livre est affectée à l'écriture valeur d'ajustement.  

**Ajustement négatif à l’étape 4 :** la date de report affectée est le 15 janvier. L’écriture valeur concernée par l’ajustement a une date de report fixée au 15 janvier, qui est comprise dans la plage de dates de report autorisées selon la configuration du grand livre.  

L'ajustement effectué pour l'ajustement négatif à l'étape 3 fait l'objet d'une discussion. La date de report favorable pour l'écriture valeur d'ajustement aurait été le 20 décembre ou au moins une date en décembre, car la réévaluation à l'origine du changement de COGS a été reportée en décembre.  

Pour procéder à l’ajustement en décembre de l’ajustement négatif à l’étape 3, le champ Début période report dans la configuration du grand livre doit indiquer une date en décembre.  

### <a name="conclusion"></a><a name="conclusion"></a><a name="conclusion"></a>Conclusion

Avec l’expérience acquise dans ce scénario, lorsque vous envisagez la configuration la plus appropriée pour une plage de dates de report autorisées pour une compagnie, vous pouvez tenir compte des éléments suivants. Tant que vous autorisez le report des modifications de la valeur inventaire au cours d’une période, telle que décembre dans ce cas, la configuration que la compagnie utilise pour les plages de dates de report autorisées doit être alignée sur cette décision. Lorsque l'option Début période report dans la configuration du grand livre est définie sur le 1er décembre, la réévaluation effectuée en décembre peut être transférée vers les écritures sortantes affectées dans la même période.  

Les groupes d'utilisateurs qui ne sont pas autorisés à effectuer des reports en décembre mais en janvier, ce qui était probablement censé être limité par la configuration du grand livre dans ce scénario, devront plutôt être gérés via la configuration des utilisateurs.  

## <a name="item-charge-scenario"></a><a name="item-charge-scenario"></a><a name="item-charge-scenario"></a>Scénario de frais annexes

### <a name="prerequisites-1"></a><a name="prerequisites-1"></a><a name="prerequisites-1"></a>Conditions préalables

Veuillez saisir les valeurs suivantes :

**Configuration de l'inventaire** :  

- Report coûts automatique = Oui  

- Ajustement automatique des coûts = Toujours  

- Type calcul coût moyen = Article  

- Période coût moyen = Jour  

**Configuration du grand livre** :  

- Début période report = 1er décembre 2020.  

- Autoriser Fin période report = Vide  

**Configuration utilisateur** :  

- Début période report = 1er décembre 2020.  

- Autoriser Fin période report = Vide  

### <a name="to-test-the-scenario-1"></a><a name="to-test-the-scenario-1"></a><a name="to-test-the-scenario-1"></a>Pour tester le scénario

Testez ce scénario en effectuant les étapes suivantes :

1.  Créez un frais **Article** avec les valeurs suivantes :  

     - Unité de mesure de base = PCS  

     - Mode évaluation stock = Moyen  

     - Sélectionnez des groupes de report facultatifs.  

2.  Créez un **bon de commande** avec les valeurs suivantes :  

     - Numéro du fournisseur : 10000  

     - Date de report = 15 décembre 2020

     - N° facture fournisseur : 1234  

     Sur la ligne de bon de commande, sélectionnez les valeurs suivantes :  

     - Article = FRAIS  

     - Quantité = 1  

     - Coût unitaire direct = 100  

     Pour terminer l’étape, reportez le document comme reçu et facturé.  

3.  Créez un **document de vente** avec les valeurs suivantes :  

     - N° débiteur : 10000  

     - Date de report = 16 décembre 2020  

     Sur la ligne document de vente :  

     - Article = FRAIS  

     - Quantité = 1  

     - Prix unitaire = 135  

     Pour terminer l’étape, reportez le document comme reçu et facturé.  

4.  Entrez des valeurs pour la page **Configuration du grand livre** :  

     - Début période report = 1er janvier 2021  

    -  Fin période report = Vide  

5.  Créez un **bon de commande** avec les valeurs suivantes :  

     - Numéro du fournisseur : 10000  

     - Date de report = 2 janvier 2021  

     - N° facture fournisseur : 2345  

     Sur la ligne de bon de commande :  

     - Frais annexes = JB-FREIGHT  

     - Quantité = 1  

     - Coût unitaire direct = 3  

     - Affectez les frais annexes à la réception achat à l’étape 2.  

     Pour terminer l’étape, reportez le document comme reçu et facturé.  


**État écriture du grand livre d’articles achat, étape 2** :  
  
|Numéro d’écriture  |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|324     |FRAIS         |2020/12/15         |Achat         |107030         |1         |105         |0        |

**Écritures de valeur**  

|Numéro d’écriture |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  | N° frais annexes    |  Quantité écriture du grand livre d’articles   |Coût indiqué (réel)     |Coût reporté dans grand livre |Ajustement |Écriture affectée à |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|397      |FRAIS|   2020/12/15    |324         |Achat         |Coût direct         |108029         |         |1          |100    |100         |Nº         |0         |
|399      |FRAIS   |2021/01/02    |324         |Achat         |Coût direct         |108009         |JBFREIGHT         |0         |3         |3         |Nº         |0         |

**État écriture du grand livre d’articles vente** :  
  
|N° séquence   |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|325     |FRAIS         |2020/12/16         |Vente         |102035         |-1         |-105         |0        |

**Écritures de valeur**  

|Numéro d’écriture |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  | N° frais annexes    |  Quantité écriture du grand livre d’articles   |Coût indiqué (réel)     |Coût reporté dans grand livre |Ajustement |Écriture affectée à |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|398      |FRAIS|   2020/12/16    |325         |Vente         |Coût direct         |109024         |         |-1          |-100    |-100         |Nº         |0         |
|400      |FRAIS   |2021/01/01    |325         |Vente         |Coût direct         |109024         |         |0         |-3         |-3         |Oui         |398         |

6.  À la date du 3 janvier arrive une facture achat, contenant des frais annexes supplémentaires pour l’achat effectué à l’étape 2. La date de document de cette facture est le 30 décembre, elle est donc reportée avec la date de report du 30 décembre 2020.  

     Créez un **bon de commande** avec les valeurs suivantes :  

     - Numéro du fournisseur : 10000  

     - Date de report = 30 décembre 2020  

     - N° facture fournisseur : 3456  

     Sur la ligne de bon de commande, sélectionnez les valeurs suivantes :  

     - Frais annexes = JB-FREIGHT  

     - Quantité = 1  

     - Coût unitaire direct = 2  

     Affectez les frais annexes à la réception achat de l’étape 2.  

     Pour terminer l’étape, reportez le document comme reçu et facturé.  


**État écriture du grand livre d’articles achat** :  

|Numéro d’écriture  |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|324     |FRAIS         |2020/12/15         |Achat         |107030         |1         |105         |0        |

**Écritures de valeur**  

|N° séquence  |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  | N° frais annexes    |  Quantité écriture du grand livre d’articles   |Coût indiqué (réel)     |Coût reporté dans grand livre |Ajustement |Écriture affectée à |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|397      |FRAIS   |2020/12/15    |324         |Achat         |Coût direct         |108029         |            |1         |100    |100         |Non         |0         |
|399      |FRAIS   |2021/01/02    |324         |Achat         |Coût direct         |108030         |JBFREIGHT   |0         |3         |3         |Non         |0         |
|401      |FRAIS   |**2020-12-30**    |324         |Achat         |Coût direct         |108031         |JBFREIGHT   |0         |2         |2         |Non         |0         |

**État écriture du grand livre d’articles vente** :  
  
|Numéro d’écriture  |N° article  |Date de report  |Type écriture  |N° du document  |Quantité  |Coût indiqué (réel)  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|325     |FRAIS         |2020/12/16         |Vente         |102035         |-1         |-105         |0        |

**Écritures de valeur**  

|N° séquence  |N° article  |Date de report  |N° écriture article gr. livre  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  | N° frais annexes    |  Quantité écriture du grand livre d’articles   |Coût indiqué (réel)     |Coût reporté dans grand livre |Ajustement |Écriture affectée à |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|398      |FRAIS   |2020/12/16        |325         |Vente         |Coût direct         |103024         |            |-1         |-100       |-100         |Non         |0         |
|400      |FRAIS   |2021/01/01        |325         |Vente         |Coût direct         |103024         |            |0          |-3         |-3         |Oui         |398         |
|402      |FRAIS   |**2021-01-01**    |325         |Vente         |Coût direct         |103024         |            |0          |-2         |-2         |Oui         |398         |

Le rapport Évaluation de l'inventaire est imprimé à la date du 31 décembre 2020

![Contenu du rapport d’évaluation de l'inventaire.](media/helene/TechArticleAdjustcost13.png "Contenu du rapport d'évaluation de l'inventaire")

**Résumé du scénario :**  

Le scénario décrit se termine avec un rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur = 2. Les frais annexes reportés à l'étape 6 font partie de la valeur d'augmentation d'inventaire de décembre alors que la diminution d'inventaire pour la même période n'est pas affectée.  

Définir l’option Début période report au 1er janvier dans la configuration du grand livre était recommandé pour les premiers frais annexes. Les coûts de l'augmentation et de la diminution d'inventaire ont été enregistrés dans la même période. Cependant, pour les deuxièmes frais annexes, le changement de COGS est reconnu dans la période suivante.  

**Conclusion :**  

Il est difficile d’obtenir un rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur <> 0. Dans ce cas, il est également plus difficile d’exprimer des paramètres optimaux, étant donné que les factures achat arrivent le même jour mais couvrent différentes périodes ou même différents exercices financiers. Le passage à un nouvel exercice financier nécessite généralement une planification et, à cet effet, il est bon d’envisager le processus Ajuster coûts – Écr. article qui reconnaît COGS.  

Dans ce scénario, une solution aurait pu être que le champ Début période report dans la Configuration du grand livre indique une date en décembre pour quelques jours de plus et que le report des premiers frais annexes soit postposé pour que tous les coûts de la période ou de l'exercice financier précédent soient reconnus pour la période à laquelle ils appartiennent. Ainsi, le traitement en lot Ajuster coûts – Écr. article serait exécuté et la date de report autorisée serait déplacée vers la nouvelle période ou le nouvel exercice financier. Les premiers frais annexes avec la date de report du 2 janvier peuvent ensuite être reportés.  

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi

[Détails de conception : date de report de l'écriture valeur d'ajustement](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : Affectation article](design-details-item-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
