---
title: Comptabilité et tenue de livres
description: Cet article fournit des informations qui vous aideront à utiliser Microsoft Dynamics 365 Business Central pour effectuer correctement la comptabilité et la tenue de livres de votre compagnie.
author: altotovi
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'accounting, bookkeeping'
ms.search.form: '16, 39, 108'
ms.date: 03/14/2023
ms.author: altotovi
---

# <a name="accounting-and-bookkeeping" />Comptabilité et tenue de livres

La comptabilité est une fonction essentielle de toute solution de planification des ressources d’entreprise (ERP), ainsi que de la plupart des entreprises. La comptabilité représente le processus d’enregistrement et de catalogage des transactions financières d’une compagnie, puis de récupération, de mesure, de synthèse et de présentation des résultats sous la forme de différents rapports souvent requis par la législation locale. L’objectif principal de ce processus est d’aider la direction de la compagnie à comprendre les finances de l’entreprise et à mesurer les résultats des activités économiques de la compagnie.

La tenue de livres fait partie du processus comptable et consiste à enregistrer régulièrement toutes les transactions financières d’une entreprise. [!INCLUDE[prod_short](includes/prod_short.md)] est un système ERP qui comprend des outils intégrés pour faciliter la tenue des livres dans le système. De nombreuses actions peuvent être effectuées automatiquement.

Cet article fournit un aperçu des processus de tenue de livres, y compris les règles, les procédures et d’autres directives incluses dans [!INCLUDE[prod_short](includes/prod_short.md)]. Le contenu de cet article est destiné à aider les comptables et les aides-comptables à accomplir leur travail quotidien dans ce système ERP. Pour une aide supplémentaire, un assistant contextuel est intégré à [!INCLUDE[prod_short](includes/prod_short.md)]. Cet assistant contient des liens vers des informations liées à la page en cours et des instructions de travail avec le processus concerné. Pour y accéder, sélectionnez le bouton [**Aide**](product-help-and-support.md) dans le coin supérieur droit pour ouvrir le volet **Aide**. Utilisez ensuite les liens des sections **À propos de cette tâche ou de cette page** et **Ressources connexes de Microsoft Learn**.

La vidéo suivante présente certaines des fonctionnalités clés de la comptabilité et de la tenue de livres.

> [!Video https://www.microsoft.com/videoplayer/embed/RE4Fss4?rel=0]

Le tableau suivant décrit une série de tâches et fournit des liens vers les articles qui les décrivent.

| Tâche | Article |
|------|---------|
| Afficher ou modifier les comptes GL pour lesquels toutes les écritures sont reportées. | [Configurer ou modifier le plan comptable](finance-setup-chart-accounts.md) |
| Indiquer comment vos clients vous paieront et comment vous paierez vos fournisseurs. | [Configuration des modes de règlement](finance-payment-methods.md) |
| Spécifier les modalités de paiement pour gérer les dates d’échéance et calculer les escomptes de paiement possibles. | [Configurer des modalités de paiement](finance-payment-terms.md) |
| Spécifier les groupes de report qui mappent des entités (telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat) dans des comptes GL. | [Configurer des groupes de report](finance-posting-groups.md)|
| Créer des rapports financiers et définir des catégories de compte pour définir le contenu des graphiques et rapports financiers, tels que les rapports **Bilan** et **État des résultats**. | [Préparation de Financial Reporting avec des données financières et des catégories de compte](bi-how-work-account-schedule.md)|
| Configurer la valeur de tolérance que le système utilise pour fermer une facture même si le règlement, tenant compte d’éventuels escomptes, ne couvre pas intégralement le montant de la facture. | [Utiliser des tolérances de paiement et des tolérances d’escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md) |
| Définir les périodes fiscales. | [Utiliser des périodes et exercices financiers comptables](finance-accounting-periods-and-fiscal-years.md) |
| Configurer des conditions de facturation qui rappellent à vos clients d’effectuer les paiements. | [Configurer des niveaux et modalités de rappel](finance-setup-reminders.md)|
| Définir comment déclarer les montants de taxe sur la valeur ajoutée (TVA) que vous avez recueillis sur les ventes aux autorités fiscales. | [Configuration de la TVA (taxe sur la valeur ajoutée)](finance-setup-vat.md) |
| Déterminer comment vous allez gérer la TVA non réalisée en association avec des méthodes comptables basées sur la trésorerie. | [Configurer la TVA non réalisée pour la comptabilité basée sur la trésorerie](finance-setup-unrealized-vat.md) |
| Définir les devises étrangères dans lesquelles vous achetez, vendez ou faites rapport des transactions. | [Configurer des devises](finance-set-up-currencies.md) |
| Définir vos fonctionnalités de vente et d’achat pour gérer les paiements dans des devises étrangères. | [Activer l’affectation d’écritures dans des devises différentes](finance-how-enable-application-ledger-entries-different-currencies.md) |
| Définir une ou plusieurs devises supplémentaires afin que les montants soient automatiquement reportés dans la devise locale et dans une devise de report additionnelle supplémentaires sur toutes les écritures de grand livre et d’autres écritures. | [Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md) |
| Ajuster régulièrement les équivalents en devise supplémentaire pour compenser la fluctuation des taux de change. | [Mise à jour des taux de change devise](finance-how-update-currencies.md)|
| Définir plusieurs taux d’intérêt pour différentes périodes associées aux paiements en retard dans les transactions commerciales. | [Configuration de plusieurs taux d’intérêt](finance-how-to-set-up-multiple-interest-rates.md) |
| Faire en sorte que les montants soient automatiquement arrondis au fur et à mesure que les factures sont créées. | [Configurer l’arrondissement facture](finance-set-up-invoice-rounding.md) |
| Ajouter de nouveaux comptes au plan comptable (COA) existant. | [Configuration du plan comptable](finance-setup-chart-accounts.md) |
| Configurez les graphiques de veille économique pour analyser la trésorerie. | [Configuration d'une analyse de trésorerie](finance-setup-cash-flow-analyses.md) |
| Permettre aux clients qui ne sont pas configurés dans le système d’être facturés. | [Configuration des clients effectuant un achat en espèces](finance-how-to-set-up-cash-customers.md) |
| Configurez le rapport Intrastat et envoyez-le à une administration. | [Configurer et enregistrer un rapport Intrastat](finance-how-setup-report-intrastat.md) |
| Vérifier qu’une écriture journal est affectée à plusieurs comptes lors du report du journal, soit par quantité, pourcentage ou montant. | [Utiliser des clés d’affectation dans les journaux généraux](ui-how-use-allocation-keys-general-journals.md) |
| Configurer des codes journaux et des codes motif à utiliser pour suivre les pistes d’audit. | [Configuration des codes source et des codes de motif pour les pistes d'audit](finance-setup-trail-codes.md) |
| Spécifier les rapports par défaut utilisés pour différents types de documents. | [Sélection des rapports dans Business Central](across-report-selections.md) |
| Affecter des paiements entrants, rapprocher des comptes bancaires pendant l'affectation de paiement et collecter des soldes échus. | [Gestion des comptes client](receivables-manage-receivables.md) |
| Effectuer des paiements, affecter des paiements sortants et traiter des chèques. | [Gestion des comptes fournisseur](payables-manage-payables.md) |
| Demander à vos clients d'envoyer leur règlement avant la livraison ou envoyer le paiement à vos fournisseurs avant qu’ils n’effectuent la livraison. | [Facturation de paiements anticipés](finance-invoice-prepayments.md) |
| Rapprocher et transférer des fonds entre comptes bancaires. | [Rapprochement de comptes bancaires](bank-manage-bank-accounts.md) |
| Configurer les partenaires intercompagnies et traiter manuellement ou automatiquement les transactions entre les personnes morales dans la même compagnie. | [Gestion des transactions intersociétés](intercompany-manage.md) |
| Analyser les coûts de fonctionnement de votre activité en affectant les coûts réels et budgétés des opérations, des départements, des produits et des projets relatifs aux centres de coûts. | [Comptabilité pour les coûts](finance-manage-cost-accounting.md) |
| Gérez les coûts d'inventaire et de fabrication, et déclarez les coûts et rapprochez-les avec le grand livre. | [Gestion des coûts ajustés](finance-manage-inventory-costs.md) |
| Gérer et déclarer les encaissements et les décaissements. | [Vue d’ensemble de la trésorerie]( finance-cash-flow-overview.md) |
| Contrôler le flux de trésorerie entrant et sortant de votre entreprise. | [Analyse des trésoreries de votre compagnie](finance-analyze-cash-flow.md) |
| Suivre un processus de bout en bout qui utilise les rapports financiers pour effectuer des prévisions de la trésorerie. | [Créer des prévisions de la trésorerie à l’aide de rapports financiers](walkthrough-making-cash-flow-forecasts-by-using-account-schedules.md) |
| En savoir plus sur le grand livre et le COA. | [Familiarisation avec les écritures comptables et les COA](finance-general-ledger.md) |
| Combiner des écritures du grand livre de plusieurs compagnies dans une compagnie consolidée virtuelle pour l'analyse financière. | [Consolidation des données financières de plusieurs compagnies](finance-consolidated-company-reporting.md)|
| Ajouter des dimensions pour une BI plus riche. | [Utilisation des dimensions](finance-dimensions.md) |
| Créer des budgets grand livre pour prévoir différentes activités financières et affecter des dimensions aux fins de BI. | [Créer des budgets GL](finance-how-create-budgets.md) |
| Enregistrez les revenus et les dépenses directement dans le grand livre sans reporter les documents commerciaux appropriés. | [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md) |
| Inversez les écritures pour annuler les reports de valeur dans le journal général ou les reports de quantité sur des documents achat et vente. | [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md) |
| Ventiler une écriture d'un journal général dans différents comptes lorsque vous reportez le journal. | [Répartition des coûts et du revenu](year-allocate-costs-income.md) |
| Affecter les surcoûts, tels que le fret et la manutention que vous encourez lors de la transaction, jusqu’aux articles qui sont impliqués. Le coût est alors reflété dans l’évaluation de l’inventaire. | [Utilisation des frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md) |
| Reporter les dépenses des employés pour les activités liées au travail et effectuer les remboursements directement sur les comptes bancaires des employés. | [Enregistrement et remboursement des frais des employés](finance-how-record-reimburse-employee-expenses.md) |
| Affecter les revenus et les dépenses à des périodes qui diffèrent des périodes au cours desquelles les transactions ont été réellement reportées. | [Échelonnement des recettes et des dépenses](finance-how-defer-revenue-expenses.md) |
| Découvrez les options disponibles pour envoyer automatiquement les factures d’abonnement à vos clients et enregistrer les revenus récurrents. | [Utiliser des revenus récurrents](finance-recurring-invoicing.md) |
| Utiliser des devises supplémentaires et mettre à jour automatiquement les taux de change devise. | [Mise à jour des taux de change devise](finance-how-update-currencies.md) |
| Importez des transactions de paie de votre fournisseur de paie dans le grand livre. | [Importation des transactions de paie](finance-how-import-payroll-transactions.md) |
| Calculer la TVA sur les transactions de vente et d’achat afin de pouvoir déclarer les montants aux autorités fiscales. | [Utilisation de la TVA sur les ventes et les achats](finance-work-with-vat.md) |
| Préparer une déclaration qui répertorie la TVA des ventes, et envoyer la déclaration aux autorités fiscales de l’UE. | [Déclarer la TVA aux autorités fiscales](finance-how-report-vat.md) |
| Convertir manuellement les contrats de service pour modifier leur taux de TVA. | [Conversion des contrats de service, y compris des montants TVA](service-how-to-convert-service-contracts.md) |
| Utiliser des états financiers et des aperçus dans Microsoft Excel. | [Analyse des états financiers dans Excel](finance-analyze-excel.md) |
| Utiliser le tableau de bord Comptable, inviter un comptable externe et utiliser le Hub Entreprise pour gérer les comptes de plusieurs clients. | [Expériences des comptables dans Business Central](finance-accounting.md) |
| Configurez les rapports Intrastat pour assurer le commerce avec les autres membres de l’UE conformément à la législation locale. | [Configurer des rapports Intrastat]( finance-how-setup-report-intrastat.md) |
| Remplir, valider et soumettre un rapport Intrastat. | [Utiliser les rapports Intrastat]( finance-how-report-intrastat.md) |
| Configurer, remplir, valider et soumettre le rapport de déclaration de services pour les échanges de services dans toute l’UE. | [Configurer et utiliser la déclaration de services]( finance-how-setup-use-service-declaration.md) |
| Créer des immobilisations, affecter des méthodes d'amortissement, reporter des acquisitions et des valeurs résiduelles et imprimer les listes d'immobilisations. | [Acquérir des immobilisations](fa-how-acquire.md) |
| Enregistrer les visites de service, reporter les coûts d'entretien et surveiller les coûts d'entretien. | [Mettre à jour des immobilisations](fa-how-maintain.md) |
| Mettre à jour les informations d'assurance, reporter les coûts d'acquisition vers les polices d'assurance, modifier la couverture assurance, visualiser les statistiques assurance et répertorier les polices d'assurance. | [Assurer les immobilisations](fa-how-insure.md) |
| Reclasser les immobilisations, les transférer vers d’autres emplacements, et les diviser ou les combiner. | [Transfert, fractionnement ou regroupement des immobilisations](fa-how-trans-split-combine.md) |
| Ajuster la valeur des immobilisations, reporter les appréciations et les transactions de dépréciation. | [Réévaluation des immobilisations](fa-how-revalue.md) |
| Calculer et reporter l’amortissement, et analyser l’amortissement dans les rapports sur les immobilisations. | [Amortissement des immobilisations](fa-how-depreciate-amortize.md) |
| Reporter les transactions de cession, visualiser les écritures cession et reporter les cessions partielles. | [Céder ou annuler des immobilisations](fa-how-dispose-retire.md) |
| Gérer les budgets d'immobilisations, budgéter les coûts d'acquisition, les cessions d'immobilisations et l'amortissement. | [Gestion des budgets pour les immobilisations](fa-how-manage-budgets.md) |
| Configurer des utilisateurs du flux de travail approbation, spécifier comment les utilisateurs sont notifiés et créer des flux de travail. Pour de nouveaux flux de travail pour des scénarios non pris en charge, implémentez les éléments requis du flux de travail en personnalisant le code d’application. | [Configuration des flux de travail d’approbation](across-set-up-workflows.md) |
| Activer les flux de travail approbation, agir sur les notifications de flux de travail (par exemple, en demandant et en approuvant une étape de flux de travail), et archiver et supprimer des flux de travail. | [Utilisation des flux de travail approbation](across-use-workflows.md) |
| Afficher les montants réels comparés aux montants budgétés pour tous les comptes et pour plusieurs périodes. | [Analyser les montants réalisés et les montants budgétés](bi-how-analyze-actual-versus-budget.md) |
| Créez de nouveaux rapports financiers pour définir les déclarations financières aux fins de rapport ou pour les afficher comme graphiques. | [Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md) |
| Analyser vos performances financières en définissant des KPI (Indicateurs de performances clés) basés sur les rapports financiers, et publier les KPI en tant que services web. Les KPI des rapports financiers publiés peuvent être affichés sur un site web ou être importés dans Excel à l’aide des services web OData. | [Configurer et publier des services web d’indicateurs de performances clés sur la base de rapports financiers](bi-how-to-set-up-and-publish-kpi-web-services-based-on-account-schedules.md) |
| Configurer des vues pour analyser des données à l’aide de dimensions. | [Analyse des données par dimensions](bi-how-analyze-data-dimension.md) |
| Créer de nouveaux rapports d'analyse pour les ventes, les achats et l'inventaire, et configurer des modèles d'analyse. | [Créer des rapports d'analyse](bi-how-create-analysis-views-reports.md) |
| Activer la génération d’états financiers généraux par des organisations comptables internationales à l’aide de la norme eXtensible Business Reporting Language (XBRL). | [Création d'états avec XBRL](bi-create-reports-with-xbrl.md) |
| Modifier l’accès intentionnel à la base de données sur les rapports, les pages du type API et les requêtes pour réduire la charge et améliorer les performances. | [Gestion de l’intention d’accès à la base de données](admin-data-access-intent.md) |

## <a name="see-also" />Voir aussi .

[Configuration de Finance](finance-setup-finance.md)  
[Ventes](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Clôture des périodes fiscales](year-close-years-periods.md)  
[Gestion des projets](projects-manage-projects.md)  
[Importation des données à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
