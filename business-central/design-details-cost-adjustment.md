---
title: "Détails de conception\_: ajustement des coûts"
description: 'L’ajustement des coûts transfère les changements depuis les coûts des sources de coût aux destinataires de coût, selon le mode évaluation inventaire d’un article, pour fournir une évaluation de l’inventaire correcte.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/14/2021
ms.author: edupont
---
# <a name="design-details-cost-adjustment"></a><a name="design-details-cost-adjustment"></a>Détails de conception : ajustement des coûts

L'objet principal de l'ajustement des coûts est de transférer les changements depuis les sources de coût aux destinataires de coût, selon le mode d'évaluation coût d'un article, pour fournir une évaluation de l'inventaire correcte.  

Un article peut faire l'objet d'une facture vente avant d'avoir été l'objet d'une facture achat, de sorte que la valeur d'inventaire enregistrée de la vente ne corresponde pas au coût d'achat réel. L'ajustement des coûts met à jour le coût des marchandises vendues (COGS) pour les écritures vente historiques afin de s'assurer qu'elles correspondent aux coûts des transactions entrantes sur lesquelles elles sont affectées. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-application.md).  

Voici l'autre objectif ou les autres fonctions de l'ajustement des coûts :  

* Facturer les ordres de fabrication terminés :  

  * Modifiez le statut des écritures valeur de **Prévu** en **Réel**.  
  * Effacer les comptes TEC. Pour plus d'informations, voir [Détails de conception : validation d'ordre de fabrication](design-details-production-order-posting.md).  
  * Reportez l'écart. Pour plus d'informations, consultez [Détails de conception : écart](design-details-variance.md)  
  * Mettre à jour le coût unitaire de la fiche article.  

Les coûts d'inventaire doivent être ajustés avant que les écritures valeur associées puissent être rapprochées avec les écritures. Pour plus d'informations, voir [Détails de conception : rapprochement de comptabilité](design-details-reconciliation-with-the-general-ledger.md).  

## <a name="detecting-the-adjustment"></a><a name="detecting-the-adjustment"></a>Détection de l'ajustement

La tâche consistant à détecter si l'ajustement des coûts doit se produire est principalement effectuée par la routine Ligne report - journal article, tandis que la tâche consistant à calculer et générer des écritures d'ajustement des coûts est effectuée par le traitement en lot **Ajuster coûts - Écr. article**.  

Pour pouvoir transférer les coûts, le mécanisme de détection de détermine quelles sources ont changé en termes de coûts et vers quelle destination ces coûts doivent être transférés. Les trois fonctions de détection suivantes sont disponibles dans [!INCLUDE[prod_short](includes/prod_short.md)] :  

* Écriture affectation article  
* Point d'entrée d'ajustement de coût moyen  
* Niveau de commande  

### <a name="item-application-entry"></a><a name="item-application-entry"></a>Écriture affectation article

Cette fonction de détection est utilisée pour les articles qui utilisent les méthodes de coûts FIFO, LIFO, Standard et Specific et pour les scénarios d'applications fixes. La fonction opère comme suit :  

* L'ajustement des coûts est détecté en marquant les écritures comptables article d'origine en tant qu'*Écriture lettrée à ajuster* lorsqu'une écriture comptable article ou une écriture valeur article est validée.  
* Les coûts sont transférés en fonction des chaînes de coût qui sont stockées dans la table **Ecriture lettrage article**.  

### <a name="average-cost-adjustment-entry-point"></a><a name="average-cost-adjustment-entry-point"></a>Point d'entrée d'ajustement de coût moyen

Cette fonction de détection est utilisée pour les articles qui utilisent le mode de coûts Average. La fonction opère comme suit :  

* L'ajustement des coûts est détecté en marquant un enregistrement dans la table **Point d'entrée ajustement coût moyen** chaque fois qu'une écriture valeur est validée.  
* Les coûts sont transférés en appliquant les coûts ajustés aux écritures valeur avec une date évaluation ultérieure.  

### <a name="order-level"></a><a name="order-level"></a>Niveau de commande

Cette fonction de détection est utilisée pour les scénarios de conversion, la production et l'assemblage. La fonction opère comme suit :  

* L'ajustement des coûts est détecté en marquant la commande chaque fois que des matières/ressources sont reportées comme étant consommées/utilisées pour la commande.  
* Les coûts sont transférés en appliquant les coûts des matières/ressources aux écritures de production liées à la même commande.  

La fonction Niveau de commande est utilisée pour détecter les ajustements dans le report d'assemblage. Le graphique suivant montre la structure d'écriture d'ajustement :  

![Flux des écritures dans l’ajustement des coûts.](media/design_details_assembly_posting_3.png "Flux des écritures dans l'ajustement des coûts")  

Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-assembly-order-posting.md).  

## <a name="manual-versus-automatic-cost-adjustment"></a><a name="manual-versus-automatic-cost-adjustment"></a>Comparaison entre ajustement des coûts automatique et manuel

Vous pouvez exécuter l'ajustement des coûts de deux manières :  

* Manuellement, en exécutant le traitement en lot **Ajuster coûts - Écr. article**. Vous pouvez exécuter ce traitement en lot pour tous les articles ou pour certains articles ou catégories d'article uniquement. Ce traitement en lot effectue un ajustement des coûts pour les articles de l'inventaire pour lesquels une transaction entrante a été réalisée, tel qu'un achat. Pour les articles qui utilisent le mode évaluation stock moyen, le traitement en lot effectue également un ajustement si les transactions sortantes sont créées.  
* Automatiquement, en ajustant les coûts chaque fois que vous reportez une transaction d'inventaire et que vous fermez un bon de production. L'ajustement des coûts est effectué uniquement pour l'article ou les articles spécifiques affectés par le report. Ceci est configuré lorsque vous cochez la case **Ajustement automatique des coûts** sur la page **Configuration inventaire**.  

C'est une bonne pratique d'exécuter l'ajustement des coûts automatiquement lors du report, car les coûts unitaires sont plus fréquemment mis à jour et donc plus précis. L'inconvénient est que les performances de la base de données peut être affectées en exécutant l'ajustement des coûts si souvent.  

Comme il est important de mettre le coût unitaire d'un article à jour, il est recommandé d'exécuter le traitement en lot pour **Ajuster coûts - Écr. article** aussi souvent que possible, en dehors des heures de travail. Sinon, utilisez l'ajustement automatique des coûts. Cela garantit que le coût unitaire est mis à jour quotidiennement pour les articles.  

Que l'exécution de l'ajustement des coûts soit manuel ou automatique, le processus d'ajustement et ses conséquences sont les mêmes. [!INCLUDE[prod_short](includes/prod_short.md)] calcule la valeur de la transaction entrante et affecte également ce coût à toutes les transactions sortantes, telles que les ventes ou les consommations, qui ont été lettrées sur la transaction entrante. L'ajustement des coûts crée des écritures valeur qui contiennent des montants d'ajustement et des montants qui compensent l'arrondissement.  

Les nouvelles écritures valeur ajustement et arrondissement ont la date de report de la facture associée. Exceptions : si les écritures valeur tombent dans une période comptable ou une période d'inventaire fermée ou si la date de report est antérieure à la date du champ **Début période report** sur la page **Configuration du grand livre**. Si cela se produit, le traitement en lot affecte la date de report comme la première date de la période ouverte suivante.  

## <a name="adjust-cost---item-entries-batch-job"></a><a name="adjust-cost---item-entries-batch-job"></a>Traitement en lot Ajuster coûts - Écr. article

Lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**, vous avez la possibilité d'exécuter le traitement en lot pour tous les articles ou pour certains articles ou catégories uniquement.  

> [!NOTE]  
> Nous vous recommandons de toujours exécuter le traitement en lot pour tous les articles et utilisez uniquement l'option de filtrage pour réduire le temps d'exécution du traitement en lot, ou pour résoudre le coût d'un article donné.  

### <a name="example"></a><a name="example"></a>Exemple :

L'exemple suivant montre le cas où vous reportez un article acheté comme étant reçu et facturé le 01/01/20. Vous reportez ultérieurement l'article vendu comme étant livré et facturé le 01-15-20. Ensuite, vous exécutez les traitements en lot **Ajuster &amp;coûts - Écr. article** et **Reporter le coût de l'inventaire au grand livre**. Les écritures suivantes sont créées.  

#### <a name="value-entries-1"></a><a name="value-entries-1"></a>Écritures valeur (1)

|Date de report|Type d'écriture gr. livre art.|Coût indiqué (réel)|Coût reporté dans grand livre|Quantité facturée|N° séquence |  
|------------|----------------------|--------------------|------------------|-----------------|---------|  
|01/01/20|Achat|10.00|10.00|1|1|  
|15/01/20|Vente|-10,00|-10,00|-1|2|  

#### <a name="relation-entries-in-the-gl--item-ledger-relation-table-1"></a><a name="relation-entries-in-the-gl--item-ledger-relation-table-1"></a>Liens écritures dans le grand livre – Table liens grand livre article (1)

|N° écriture comptable|N° écriture valeur|N° registre GL|  
|-------------|---------------|----------------|  
|1|1|1|  
|2|1|1|  
|3|2|1|  
|4|2|1|  

#### <a name="general-ledger-entries-1"></a><a name="general-ledger-entries-1"></a>Écritures de grand livre (1)

|Date de report|Compte du grand livre|N° compte (démonstration Fr-FR)|Montant|N° séquence |  
|------------------|------------------|---------------------------------|------------|---------------|  
|01/01/20|[Compte inventaire]|2130|10.00|1|  
|01/01/20|[Compte coût direct affecté]|7291|-10,00|2|  
|15/01/20|[Compte inventaire]|2130|-10,00|3|  
|15/01/20|[Compte variation stock]|7290|10.00|4|  

Ultérieurement, vous reportez des frais annexes achat associés de 2,00 $ facturés le 10/02/20. Vous exécutez le traitement en lot **Ajuster &amp;coûts - Écr. article**, puis le traitement en lot **Reporter le coût de l'inventaire au grand livre**. Le traitement en lot d'ajustement des coûts ajuste le coût de la vente de 2,00 $ en conséquence, et le traitement en lot **Reporter le coût de l'inventaire au grand livre** reporte les nouvelles écritures valeur dans le grand livre. Le résultat est le suivant.  

#### <a name="value-entries-2"></a><a name="value-entries-2"></a>Écritures valeur (2)

|Date de report|Type d'écriture gr. livre art.|Coût indiqué (réel)|Coût reporté dans grand livre|Quantité facturée|Ajustement|N° séquence |  
|------------|----------------------|--------------------|------------------|-----------------|----------|---------|  
|10/02/20|Achat|2.00|2.00|0|Non|3|  
|15/01/20|Vente|-2,00|-2,00|0|Oui|4|  

#### <a name="relation-entries-in-the-gl--item-ledger-relation-table-2"></a><a name="relation-entries-in-the-gl--item-ledger-relation-table-2"></a>Liens écritures dans le grand livre – Table liens grand livre article (2)

|N° écriture comptable|N° écriture valeur|N° registre GL|  
|-------------|---------------|----------------|  
|5|3|2|  
|6|3|2|  
|7|4|2|  
|8|4|2|  

#### <a name="general-ledger-entries-2"></a><a name="general-ledger-entries-2"></a>Écritures de grand livre (2)

|Date de report|Compte du grand livre|N° compte (démonstration Fr-FR)|Montant|N° séquence |  
|------------|-----------|------------------------|------|---------|  
|10/02/20|[Compte inventaire]|2130|2.00|5|  
|10/02/20|[Compte coût direct affecté]|7291|-2,00|6|  
|15/01/20|[Compte inventaire]|2130|-2,00|7|  
|15/01/20|[Compte variation stock]|7290|2.00|8|  

## <a name="automatic-cost-adjustment"></a><a name="automatic-cost-adjustment"></a>Ajustement automatique des coûts

Pour configurer l'exécution automatique de l'ajustement des coûts lorsque vous reportez une transaction d'inventaire, utilisez le champ **Ajustement automatique des coûts** sur la page **Configuration inventaire**. Ce champ vous permet de sélectionner jusqu'où dans le passé vous voulez que l'ajustement automatique des coûts soit effectué. Les options possibles sont les suivantes.  

|Option|Description|
|------|-----------|
|Jamais|Les coûts ne sont pas ajustés lors du report.|  
|Jour|Les coûts sont ajustés si le report a lieu dans la journée commençant à la date de travail.|  
|Semaine|Les coûts sont ajustés si le report a lieu dans la semaine commençant à la date de travail.|  
|Mois|Les coûts sont ajustés si le report a lieu dans le mois commençant à la date de travail.|  
|Trimestre|Les coûts sont ajustés si le report a lieu dans le trimestre commençant à la date de travail.|  
|Année|Les coûts sont ajustés si le report a lieu dans l'année commençant à la date de travail.|  
|Toujours|Les coûts sont systématiquement ajustés lors du report, quelle que soit la date de report.|  

La sélection effectuée dans le champ **Ajustement automatique des coûts** est importante pour les performances et la précision et de vos coûts. Des périodes plus courtes, telles que **Jour** ou **Semaine**, affectent moins les performances système, car elles offrent la condition plus stricte que seuls les prix validés le jour ou la semaine précédente peuvent être automatiquement ajustés. Cela signifie que l'ajustement automatique des coûts n'est pas effectué aussi fréquemment et affecte donc moins les performances du système. Toutefois, cela signifie également que les coûts unitaires peuvent être moins précis.  

### <a name="example-1"></a><a name="example-1"></a>Exemple :

L'exemple suivant présente scénario d'ajustement automatique des coûts :  

* Le 10 janvier, vous reportez un article acheté comme étant reçu et facturé.  
* Le 15 janvier, vous reportez un document de vente pour l'article comme étant livré et facturé.
* Le 5 février, vous recevez une facture pour des frais de transport sur l'achat initial. Vous reportez ces frais de fret, en les affectant à la facture achat originale, qui augmente le coût de l'achat d'origine.  

Si vous avez défini l'ajustement automatique des coûts pour l'affecter aux reports qui se produisent à un mois ou un trimestre de la date en cours, l'ajustement automatique des coûts fonctionne et transmet le coût de l'achat à la vente.  

Si vous avez configuré l'ajustement automatique des coûts pour l'affecter aux reports qui se produisent dans la journée ou la semaine à partir de la date en cours, l'ajustement automatique des coûts ne fonctionne pas, et le coût de l'achat n'est pas transmis à la vente tant que vous n'exécutez pas le traitement en lot **Ajuster &amp;coûts - Écr. article**.  

## <a name="see-also"></a><a name="see-also"></a>Voir aussi

[Ajuster coûts et prix article](inventory-how-adjust-item-costs.md)  
[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : rapprochement de GL](design-details-reconciliation-with-the-general-ledger.md)  
[Détails de conception : report inventaire](design-details-inventory-posting.md)  
[Détails de conception : écart](design-details-variance.md)  
[Détails de conception : Report d'ordre d'assemblage](design-details-assembly-order-posting.md)  
[Détails de conception : validation d'ordre de fabrication](design-details-production-order-posting.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
