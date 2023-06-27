---
title: Configuration de groupe de report
description: Aperçu des groupes de report que vous pouvez utiliser pour gagner du temps et éviter des erreurs lorsque vous reportez des transactions.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'posting setup, initialize'
ms.search.form: '312, 313'
ms.date: 08/26/2022
ms.author: bholtorf
---
# <a name="set-up-posting-groups" />Configuration des groupes de report

Les groupes de report mappent des entités à des comptes GL. Les clients, les fournisseurs, les articles, les ressources et les documents vente et achat sont des exemples d’entités. Les groupes de report vous font gagner du temps et permettent d’éviter des erreurs lorsque vous reportez des transactions. Les valeurs de transaction vont dans les comptes spécifiés dans le groupe de report pour cette entité particulière. Il vous suffit seulement d'avoir un plan comptable. Pour plus d'informations, reportez-vous à [Configuration du plan comptable](finance-setup-chart-accounts.md).  

Les groupes comptabilisation sont traités dans trois catégories :  

* Général

  Définit à qui vous vendez et à qui vous achetez, et ce que vous vendez et ce que vous achetez. Vous pouvez aussi combiner des groupes pour spécifier des éléments comme les comptes états des résultats sur lesquels reporter ou utiliser des groupes pour filtrer les rapports.  
* Spécifique

  Permet d’utiliser des documents vente au lieu de reporter directement dans le grand livre. Lors de la création d'écritures dans le grand livre client, les écritures correspondantes sont passées dans le grand livre.  
* Taxes

  Définit les pourcentages de taxes et les types de calcul qui s’appliquent à l’acheteur et au vendeur, et à ce que vous vendez et ce que vous achetez.

Les sections suivantes décrivent les groupes de report dans chaque catégorie.  

## <a name="general-posting-groups" />Groupes de report généraux

Le tableau suivant décrit les groupes de report généraux.

| Type | Description |
| --- | --- |
| Groupes comptabilisation marché |Affectez ce groupe aux clients et aux fournisseurs pour spécifier à qui vous vendez, et à qui vous achetez. Définissez ces groupes de report sur la page **Groupes de report marché**. Lorsque vous effectuez cette opération, vous devez prendre en compte le nombre de groupes nécessaires pour répartir les ventes et les achats. Par exemple, les groupes clients et fournisseurs peuvent être répartis par zone géographique ou par type d'activité. |
| Groupes comptabilisation produit |Affectez ce groupe à des articles et des ressources pour spécifier les éléments que vous vendez, et que vous achetez. Définissez ces groupes de report sur la page **Groupes de report produit**. Lorsque vous effectuez cette opération, vous devez considérer le nombre de groupes nécessaires pour répartir les ventes par article et ressource, et pour répartir les achats par article. Par exemple, divisez ces groupes par Matières premières, Vte détail, Ressources, Capacités, etc. |
| Config. paramètres report |Combinez les groupes de report marché et produit, puis choisissez les comptes à reporter. Pour chaque combinaison de groupes comptabilisation marché et produit, vous pouvez affecter un ensemble de comptes généraux. Par exemple, vous pouvez reporter la vente d’un même article dans différents comptes GL car les clients sont affectés à différents groupes de report marché. Définissez ces configurations sur la page **Configuration du report général**. |

## <a name="specific-posting-groups" />Groupes de report spécifiques

Le tableau suivant décrit les groupes de report spécifiques aux types de données.

|Type | Description |
| --- | --- |
| Groupes de report du client |Définissez les comptes à utiliser lorsque vous reportez des transactions Comptabilité client. Si vous utilisez un inventaire conjointement avec des clients, les comptes dans lesquels les écritures lignes document de vente sont reportées sont déterminés par le groupe de report marché affecté au client et le groupe de report produit affecté à l’article en inventaire. Voir *Groupes de report marché* et *Groupes de report produit* dans la section [Groupes de report généraux](#general-posting-groups). Définissez ces groupes de report sur la page **Groupes de report client**. |
| Groupes de report du fournisseur |Définissez où reporter les transactions des comptes fournisseur, des comptes frais forfaitaires, et des comptes d'escompte de paiement. Cela est similaire aux groupes comptabilisation client. Définissez ces groupes de report sur la page **Groupes de report fournisseur**. |
| Groupes de report inventaire |Définissez des groupes de report inventaire que vous devez ensuite affecter aux comptes article appropriés sur la page **Configuration report inventaire**. Ainsi, lorsque vous reportez des écritures concernant un article, le système effectue le report sur le compte du grand livre qui est configuré pour la combinaison groupe de report inventaire/emplacement liée à l'article. Des groupes de report inventaire constituent également un moyen idéal d'organiser votre inventaire. Ainsi, vous pouvez séparer des articles par groupe de report lors de la génération de rapports. Définissez ces groupes de report sur la page **Groupes de report inventaire**. |
| Groupes de report compte bancaire |Définissez les compte GL dans lesquels les écritures compte bancaire sont reportées. Par exemple, cela peut simplifier les processus de traçabilité des transactions et des rapprochements bancaires. Définissez ces groupes de report sur la page **Groupes de report compte bancaire**. Nous recommandons que le champ **Report direct** de ces comptes du grand livre soient définis sur *Non*. |
| Groupes comptabilisation immobilisations |Définissez des comptes pour les différents types de dépenses et frais, tels que les coûts d'acquisition, les montants d'amortissement cumulés, les coûts d'acquisition sur cession, l'amortissement cumulé sur cession, les gains sur cession, les pertes sur cession, les frais d'entretien et les frais d'amortissement. Définissez ces groupes de report sur la page **Groupes de report immo.**. |

### <a name="allowing-substitute-customer-or-vendor-posting-groups-on-documents" />Autorisation de groupes de report client ou fournisseur de remplacement sur les documents

[!INCLUDE [preview](includes/preview.md)]

Vous pouvez permettre aux utilisateurs de choisir des groupes de report client et fournisseur différents de ceux par défaut lorsqu’ils utilisent des documents et des journaux vente ou achat.

Pour autoriser les modifications des groupes de report client, choisissez **Autoriser plusieurs groupes de report** sur les pages **Configuration ventes & à recevoir** et **Configuration Gestion des services**, et sur la page **Configuration achats && à payer** pour les modifications des groupes de report fournisseur.

Sur les pages **Groupes de report client** ou **Groupes de report fournisseur**, vous pouvez spécifier les groupes de report à autoriser comme substituts en choisissant **Substitutions**. Les groupes de report de substitution peuvent remplacer les groupes de report client ou fournisseur par défaut spécifié pour un client ou un fournisseur.

Après avoir configuré cela, vous pouvez choisir parmi les groupes de report de substitution autorisés et modifier le groupe de report client ou fournisseur lors du report des documents et des journaux vente ou achat. Les groupes de report client ou fournisseur de substitution sont copiés dans les documents et journaux reportés, et les écritures à recevoir ou à payer sont reportées dans les comptes du grand livre spécifiés pour les substituts.

Lors de l’affectation, par exemple, d’une facture et d’un paiement qui sont reportés avec différents groupes de report client ou fournisseur (différents comptes du grand livre), [!INCLUDE[prod_short](includes/prod_short.md)] transfère les montants entre les comptes du grand livre pour les équilibrer.

## <a name="tax-posting-groups" />Groupes de report TVA

Le tableau suivant décrit les groupes de report associés aux taxes.

| Type | Description |
| --- | --- |
| Paramètres report marché fiscal |Déterminez la manière de calculer et de reporter la taxe de vente pour les clients et les fournisseurs. Définissez ces groupes de report sur la page **Groupes de report marché TVA**. Lorsque vous le faites, pensez au nombre de groupes dont vous avez besoin. De nombreux facteurs peuvent entrer en jeu, notamment la législation locale, et le fait de travailler sur le marché national et international. |
| Paramètres report produit fiscal |Indiquez les calculs TVA nécessaires pour les types d'articles ou de ressources que vous achetez ou vendez. |
| Configuration de report de taxe |Combinez des groupes compta. marché et des groupes compta. produit TVA. Lorsque vous renseignez une ligne dans un journal général, une ligne achat, ou une ligne vente, nous allons consulter la combinaison pour identifier les comptes à utiliser. |

Si votre pays utilise la taxe sur la valeur ajoutée (TVA), voir [Configurer des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md).  

## <a name="example-of-linking-posting-groups" />Exemple de liaison de groupes comptabilisation

Voici un scénario.  

Ces groupes comptabilisation sont choisis dans la fiche client :  

* Groupe de report marché
* Groupe de report client  

Ces groupes comptabilisation sont choisis dans la fiche article :  

* Groupe de report produit  
* Groupe de report inventaire  

Lors de la création d'un document vente, l'en-tête vente utilise les informations de la fiche client et les lignes ventes utilisent les informations de la fiche article.  

* Le report revenus (état des résultats) est déterminée par la combinaison du groupe de report marché et du groupe de report produit.  
* Le report des ventes (bilan) est déterminé par le groupe de report client.  
* Le report de l'inventaire (bilan) est déterminé par le groupe de report inventaire.  
* Le report coût des biens vendus (état des résultats) est déterminé par la combinaison du groupe de report marché et du groupe de report produit.  

Votre configuration détermine quand le report a lieu. Par exemple, la synchronisation est affectée au moment où vous exécutez des activités périodiques, par exemple : reporter des coûts inventaire ou ajuster des écritures coût article.

## <a name="copying-posting-setup-lines" />Copie de lignes configuration report

Plus il y a de groupes de report produit et marché, plus la page **Configuration du report général** contient de lignes. Cela peut entraîner la nécessité d’entrer un grand nombre de données pour configurer la configuration du report général pour la compagnie. S'il peut y avoir un grand nombre de combinaisons différentes de groupes de report marché et produit, différentes combinaisons peuvent encore reporter dans les mêmes comptes du grand livre. Pour limiter le nombre de saisies manuelles, copiez les comptes GL à partir d'une ligne existante sur la page **Configuration report général**.

## <a name="set-up-posting-groups-on-the-go" />Configurer des groupes de report en déplacement

Pour que les utilisateurs démarrent plus rapidement, [!INCLUDE[prod_short](includes/prod_short.md)] peut afficher des notifications de comptes du grand livre manquants dans diverses configurations de groupe de report. Pour recevoir ces notifications, assurez-vous que la notification **Compte du grand livre manquant dans le groupe de report ou la configuration** est sélectionnée dans la page **Mes notifications**, à laquelle vous pouvez accéder à partir du champ **Modifier lorsque je reçois des notifications** dans la page **Mes paramètres**.  

De cette façon, lorsque vous travaillez sur un document qui utilise une configuration ou un groupe de report pour lequel il manque un compte GL requis, vous recevez une notification. Choisissez le lien dans la notification pour ouvrir une page où vous pouvez apporter les modifications appropriées, à condition que vous y soyez autorisé.  

> [!NOTE]
> Afin de vous diriger directement vers la configuration ou le groupe de report auquel il manque un compte GL, [!INCLUDE[prod_short](includes/prod_short.md)] crée un espace réservé pour une configuration ou un groupe de report. Les configurations et les groupes de report constituent, pour le comptable, un moyen de contrôler la manière dont les écritures sont reportées dans le grand livre. Ainsi, la création juste à temps de configurations et de groupes de report peut ne pas être autorisée dans votre organisation.  
>
> Dans ce cas, désactivez la notification *Compte du grand livre manquant dans le groupe de report ou la configuration*, puis collaborez avec votre comptable pour apporter les modifications appropriées au groupe de report, à la configuration ou à votre document. Il s’agit d’une étape importante, car une fois les documents reportés, les paramètres ou les groupes de report utilisés de manière incorrecte ne peuvent pas être supprimés car des écritures sont créées pour eux.

À partir de la 1re vague de lancement 2022, vous pouvez utiliser le champ **Bloqué** sur la page **Configuration du report général** pour empêcher les utilisateurs d’utiliser par erreur une configuration qui n’est plus pertinente pour les nouveaux reports.  

## <a name="troubleshooting-posting-group-errors" />Résolution des erreurs de groupe de report

Les groupes de report sont l’un des concepts les plus avancés à configurer dans [!INCLUDE[prod_short](includes/prod_short.md)]. S’ils ne sont pas configurés correctement, des erreurs peuvent se produire lors du report de documents ou de lignes journal. Par exemple, ces erreurs sont généralement causées par une erreur d’affectation des comptes du grand livre ou de combinaison des groupes de report.

Quand quelque chose ne va pas, [!INCLUDE[prod_short](includes/prod_short.md)] affiche la page **Messages d’erreur**. La page **Messages d’erreur** peut faciliter l’identification et la résolution du problème. Cette page propose une description de l’erreur qui signale la configuration du groupe de report qui nécessite une attention particulière. Par exemple, le message peut indiquer « Il manque une configuration de report générale au compte paiement anticipé vente ». Il existe également un lien pour ouvrir la page qui est à l’origine du problème, afin que vous puissiez le résoudre rapidement.  

> [!NOTE]
> La gestion des erreurs décrite ci-dessus n’est pas disponible sur les journaux article, ressource, employé et immobilisation, ni pour les comptes du grand livre ajoutés dans des versions locales des groupes de report.

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/modules/posting-groups-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
