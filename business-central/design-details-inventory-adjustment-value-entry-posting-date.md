---
title: Date de report des écritures valeur
description: Découvrez comment le traitement en lot Ajuster coûts - Écr. article identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 09/17/2021
ms.author: bholtorf
---
# <a name="design-details-posting-date-on-adjustment-value-entry"></a>Détails de conception : date de report de l'écriture valeur d'ajustement

Cet article fournit des conseils aux utilisateurs de la fonctionnalité Évaluation du coût de l'inventaire dans [!INCLUDE[prod_short](includes/prod_short.md)], et en particulier pour la façon dont le traitement en lot **Ajuster coûts : Écr. article** identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.

## <a name="how-posting-dates-are-assigned"></a>Modalités d’attribution des dates de report

Le traitement en lot **Ajuster coûts - Écr. article** affecte une date de report à l’écriture valeur qu’il est sur le point de créer dans les étapes suivantes :  

1. Initialement, la date de report de l'écriture à créer est la même que celle de l'écriture qu'elle ajuste.  

2. La date de report est validée par rapport aux périodes d'inventaire et/ou à la configuration du grand livre.  

3. Affectation d'une date de report : si la date de report initiale n'est pas comprise dans la plage de dates de report autorisées, le traitement en lot affecte une date de report autorisée à partir de la Configuration du grand livre ou de la Période d'inventaire. Si les périodes d'inventaire et les dates de report autorisées dans la configuration du grand livre sont définies, la date la plus récente des deux est affectée à l'écriture valeur d'ajustement.  

Examinons ce processus plus en détail. Supposons que nous avons une écriture article de type Vente. L’article a été livré le 5 septembre 2020 et il a été facturé le jour suivant.  

#### <a name="item-ledger-entry"></a>Écriture article

|N° séquence   |N° article  |Date de report  |Type écriture  | N° du document |Code d'emplacement  |Quantité  |Coût indiqué (réel)  |Quantité facturée  |Quantité restante  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|319     |A         |2020/09/05     |  Vente       |102033     |  Bleu       | -1    |    -11     |-1     |    0     |

Vous trouverez ci-dessous les écritures de valeur associées :

- **Écriture n°379** représente la livraison et utilise la même date de report que l’écriture article parent.  
- **Écriture n°381** représente la facture.  
- **Écriture n°391** est un ajustement de l’écriture valeur de facturation (Écriture n°381 ci-dessus).  

|N° séquence   |N° article  |Date de report  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  |N° écriture article gr. livre  |Code d'emplacement  |Quantité écriture du grand livre d’articles  |Quantité facturée  |Coût indiqué (réel)  |Coût indiqué (prévu)  |Ajustement  |Écriture affectée à  |Code journal  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|--------|---------|---------|---------|---------|
|379     |  A       |    2020/09/05     |    Vente     | Coût direct   | 102033        |319     | Bleu        | -1       |0         |  0       |     -10   |Non   |0    |Ventes          |
|381     |  A       |    2020/09/06     |    Vente     | Coût direct   | 103022        |319     | Bleu        |  0       |-1        |-10       |    10     | Non  |0      |       Ventes   |
|391     |  A       |    2020/09/10     |    Vente     | Coût direct   | 103022        |319     | Bleu        |  0       |0         |-1        |    0     |Oui   |    181   | AJSTK   |

Pour affecter la date de report pour **Écriture n°391**, les étapes suivantes ont été appliquées :

1. L'**écriture valeur d’ajustement** à créer (**Écriture n° 391**) se voit attribuer la même **Date de report** que l’écriture qu’elle ajuste.

2. Le traitement en lot **Ajuster coûts - Écr. article** détermine si la date de report initiale de l'écriture valeur d'ajustement est comprise dans la plage de dates de report autorisées en fonction des périodes d'inventaire et/ou de la configuration du grand livre.  

Examinons la vente mentionnée ci-dessus en ajoutant la configuration des plages de dates de report autorisées.  
  
#### <a name="inventory-periods"></a>Périodes d'inventaire

|Date de fin  |Nom  |Fermé  |
|---------|---------|---------|
|2020/01/31     |2020 janvier      |  Oui    |
|2020/02/28     |Février 2020     |  Oui    |
|2020/03/31     |Mars 2020        |  Oui    |
|2020/04/30     |Avril 2020        |  Oui    |
|2020/05/31     |Mai 2020        |  Oui    |
|2020/06/30     |Juin 2020       |  Oui    |
|2020/07/31     |Juillet 2020        |  Oui    |
|2020/08/31     |Août 2020     |  Oui    |
|2020/09/30     |Septembre 2020  |         |
|2020/10/31     |Octobre 2020    |         |
|2020/11/30     |Novembre 2020   |         |
|2020/12/31     |Décembre 2020   |         |

La première date de report autorisée est le premier jour de la première période ouverte, qui est le 1er septembre 2020.  

#### <a name="general-ledger-setup"></a>Configuration du grand livre

|Champ|Valeur  |
|---------|---------|
|Début période report :  |  2020/09/10      |
|Fin période report :    |  2020/09/30      |
|Registre temps :       |         |
|Format adresse local :|   Code postal      |  

La première date de report autorisée est la date indiquée dans le champ **Début période report** : 10 septembre 2020. Si les périodes d'inventaire et les dates de report autorisées dans la **configuration du grand livre** sont définies, la date la plus récente des deux définit la plage de dates de report autorisées.  

**Affectation d’une date de report autorisée**  

La date de report initiale était le 6 septembre, comme illustré à l’étape 1. Toutefois, dans la deuxième étape, le traitement en lot Ajuster coûts - Écr. article identifie que la date de report autorisée la plus proche est le 10 septembre et affecte donc le 10 septembre à l’écriture valeur d’ajustement (**Écriture n°391**), ci-dessous.  


|N° séquence   |N° article  |Date de report  |Type d'écriture gr. livre art.  |Type écriture  |N° du document  |N° écriture article gr. livre  |Code d'emplacement  |Quantité écriture du grand livre d’articles  |Quantité facturée  |Coût indiqué (réel)  |Coût indiqué (prévu)  |Ajustement  |Écriture affectée à  |Code journal  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|379     |  A       |    2020/09/05     |    Vente     | Coût direct   | 102033        |319     | Bleu        | -1       |0         |  0       |     -10   |Non   |0    |Ventes          |
|381     |  A       |    2020/09/06     |    Vente     | Coût direct   | 103022        |319     | Bleu        |  0       |-1        |-10       |    10     | Non  |0      |       Ventes   |
|391     |  A       |    **2020-09-10**     |    Vente     | Coût direct   | 103022        |319     | Bleu        |  0       |0         |-1        |    0     |Oui   |    181   | AJSTK   |

## <a name="common-problems-with-the-adjust-cost---item-entries-batch-job"></a>Problèmes courants avec le traitement en lot « Ajuster coûts - Écr. article »

Il existe deux scénarios que l’équipe d’assistance rencontre suffisamment fréquemment pour justifier la rédaction d’articles de résolution de problèmes dédiés.

### <a name="error-message-posting-date-is-not-within-your-range-of-allowed-posting-dates"></a>Message d’erreur : « La date de report n’est pas incluse dans la plage de dates de report autorisées... »

Si vous rencontrez cette erreur, vous devez ajuster les dates pour lesquelles l’utilisateur est autorisé à reporter des écritures. Pour en savoir plus, voir [Message d’erreur : « La date de report n’est pas incluse dans la plage de dates de report autorisées »](design-details-inventory-adjustment-value-entry-allowed-posting-dates.md).

### <a name="posting-date-on-adjustment-value-entry-versus-posting-date-on-entry-causing-the-adjustment-such-as-revaluation-or-item-charge"></a>Comparaison entre la date de report de l’écriture valeur d’ajustement et la date de report de l’écriture à l’origine de l’ajustement, comme une réévaluation ou des frais annexes

Pour en savoir plus, voir [Date de report sur l’écriture valeur d’ajustement par rapport à l’écriture source](design-details-inventory-adjustment-value-entry-source-entry.md).

## <a name="see-also"></a>Voir aussi

[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : Affectation article](design-details-item-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
