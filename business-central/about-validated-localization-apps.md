---
title: Développement d’applications de localisation validées
description: Conformez-vous aux exigences réglementaires Dynamics 365 Business Central en tant qu’application de localisation validée.
author: altotovi
ms.custom: na
ms.date: 04/10/2024
ms.reviewer: solsen
ms.topic: conceptual
ms.author: altotovi
---


# <a name="development-of-validated-localization-apps"></a>Développement d’applications de localisation validées

Cet article décrit les exigences et les directives pour développer une application de localisation validée pour [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="what-is-a-validated-localization-app"></a>Qu’est-ce qu’une application de localisation validée ?

[!INCLUDE[prod_short](includes/prod_short.md)] est disponible [dans le monde sur plus de 170 marchés](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json). Dans un ensemble de marchés, Microsoft travaille avec des partenaires ISV pour localiser [!INCLUDE[prod_short](includes/prod_short.md)] via les applications de localisation disponibles sur [Microsoft AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). Pour ces régions, les localisations peuvent être disponibles via le programme d’application de localisation préféré. Le programme d’applications de localisation préférées reconnaît les applications créées conformément aux directives de qualité spécifiques de Microsoft. Les partenaires ISV qui respectent ces exigences et directives du programme peuvent bénéficier d’avantages techniques et commerciaux pour servir leurs revendeurs et leurs clients.  

Dans les sections suivantes, vous trouverez les exigences et les directives. Vous pouvez contacter l’équipe du programme si vous souhaitez participer à ce programme et respecter les exigences ci-dessous en nous contactant via l’ [équipe de localisation Microsoft](mailto:d365bcloc@microsoft.com).   

> [!IMPORTANT]
> L’initiative [!INCLUDE[prod_short](includes/prod_short.md)] d’applications de localisation validées est actuellement déployée en tant que programme pilote. Les exigences et avantages ci-dessous peuvent changer en fonction des commentaires des partenaires et des clients.  

Les applications du programme pilote de localisation validé contiennent un ensemble de fonctionnalités répondant aux exigences réglementaires locales qui appartiennent à l’une des catégories de la liste suivante.  

- **Exigences réglementaires** : fonctionnalité locale qui aide les entreprises à remplir leurs exigences légales, telles que la déclaration fiscale, les formats de facturation électronique locaux, les PCGR locaux et d’autres exigences réglementaires.
- **Exigences relatives aux normes nationales** – fonctionnalité locale qui répond aux normes locales, telles que les formats d’adresses, les formats bancaires nationaux ou les interprétations locales des normes mondiales.
- **Langue locale** : langue locale dans l’application de localisation, mais également pour une application de base si cette langue ne figure pas actuellement dans la liste des [langues prises en charge](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).
- **Langue locale** : langue locale dans une application de localisation, mais également pour une application de base si cette langue ne figure pas actuellement dans la liste des [langues prises en charge](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).

> [!NOTE]
> Les besoins du marché local ou les exigences du secteur ne doivent pas être inclus dans les applications de localisation préférées. Si les applications contiennent ces fonctionnalités, elles ne peuvent pas être approuvées en tant qu’applications de localisation validées.

> [!NOTE]
> Les fonctionnalités locales sont bénéfiques pour la productivité des processus métier dans un pays et ajoutent ainsi de la valeur à l’entreprise, mais ne sont pas requises d’un point de vue réglementaire, comme les formats bancaires et de paiement spécifiques, les notes de frais, les fonctionnalités RH, la paie et autres, plus petits ou plus grands, et les fonctionnalités intéressantes devraient être isolées dans d’autres applications. Si les applications contiennent ces fonctionnalités, elles ne peuvent pas être approuvées en tant qu’applications de localisation validées.   

## <a name="validated-localization-app-business-requirements"></a>Exigences commerciales de l’application de localisation validée

- Le fournisseur d’applications de localisation validée se conforme à toutes les exigences pour être un fournisseur indirect CSP.  
- Le fournisseur d’applications de localisation validée met sur le marché un min. d’offres dans cinq pays/régions, qui regroupent Dynamics 365 Business Central avec une application de localisation validée. 
- Le fournisseur d’applications de localisation validée dispose d’un minimum de 10 [!INCLUDE[prod_short](includes/prod_short.md)] clients en ligne disposant d’environnements de production et utilisant activement l’application de localisation validée. 
- Le fournisseur d’applications de localisation validée soumet chaque année un plan d’affaires à l’équipe v du programme. Cela comprend les activités de marketing et de préparation planifiées pour promouvoir l’offre groupée auprès des revendeurs indirects CSP dans les pays/régions concernés. Le plan peut être soumis au début de chaque trimestre à [Équipe de localisation Microsoft](mailto:d365bcloc@microsoft.com).  
- Les applications de localisation validées sont mises à la disposition de tous les clients et partenaires qui souhaitent en bénéficier.  
- Le fournisseur d’applications de localisation validée met sur le marché un min. d’offres dans cinq pays/régions, qui regroupent Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)] avec une application de localisation validée. 
- Le fournisseur d’applications de localisation validée dispose d’un minimum de 10 [!INCLUDE[prod_short](includes/prod_short.md)] clients en ligne disposant d’environnements de production et utilisant activement l’application de localisation validée. 
- Le fournisseur d’applications de localisation validée soumet chaque année un plan d’affaires à l’équipe v du programme. Cela comprend les activités de marketing et de préparation planifiées pour promouvoir l’offre groupée auprès des revendeurs indirects CSP dans les pays/régions concernés. Le plan peut être soumis au début de chaque trimestre à [Équipe de localisation Microsoft](mailto:d365bcloc@microsoft.com).  
- Les applications de localisation validées sont mises à la disposition de tous les clients et partenaires qui souhaitent en bénéficier.  
- Le fournisseur d’applications de localisation validées s’engage dans des flux de travail récurrents avec Microsoft.

## <a name="validated-localization-app-functional-and-technical-requirements"></a>Exigences fonctionnelles et techniques validées de l’application de localisation

### <a name="functionality-requirements"></a>Exigences de fonctionnalité

En plus de répondre aux exigences techniques de l’application de localisation préférée, la portée minimale viable du produit pour l’application de localisation préférée est :  

- Fonctions de réglementation régionale :   
  - Besoins légaux.   
  - Fonctionnalités officiellement obligatoires. 
  - Fonctionnalités horizontales uniquement (non spécifiques à un secteur).  
  - Applicable dans la plupart des entreprises.  
  - Dans le Blueprint suivant :   
    - Domaines de changements législatifs les plus fréquents. 
    - Déjà suivi en tant que localisation dans les localisations Microsoft. 
    - Références de fonctionnalités – rarement nouvelles.  
    - Aucun format, paie ou similaire spécifique au fournisseur/banque. 
    - Pas de fonctionnalités globales si elles ne sont pas construites par Microsoft. 
- Traductions : 
  - Traduction d’une application de localisation dans les langues locales. 
  - Traduction d’une application de base dans les langues locales – si la langue ne l’est pas déjà [prise en charge](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).  
  - Traduction de la documentation d’une application de localisation dans les langues locales. 
- Même si elles font toutes deux partie de la localisation, il est recommandé que les fonctionnalités standard nationales (partie locale) soient créées en tant qu’applications distinctes des fonctionnalités réglementaires locales. 
- Données de démonstration dans la langue locale applicable au marché spécifique.   
- Toutes les fonctionnalités doivent être conçues pour conserver une interface utilisateur simplifiée, notez qu’elles sont principalement destinées au marché des PME.  
- Évitez de créer de nouvelles fonctionnalités si des fonctionnalités identiques ou similaires existent déjà dans l’application de base, telles que la facturation électronique, les exportations d’audit, les fonctionnalités de TVA, l’échange de données et d’autres pour lesquelles la plupart des fonctionnalités sont communes à tous les pays/régions mais il existe certaines règles ou règles locales. formats commerciaux qui sont des extensions de cadres ou de formats globaux. Au lieu de créer de nouvelles fonctionnalités, étendez celles existantes.  
- Préparez des guides de configuration (assistants) pour les zones complexes à configurer afin d’aider les utilisateurs à activer, découvrir et avoir une bonne première expérience d’utilisation de votre application de localisation.  
- Toutes les fonctionnalités doivent être conçues pour conserver une interface utilisateur simplifiée, notez qu’elles sont principalement destinées au marché des PME.  
- Évitez de créer de nouvelles fonctionnalités si des fonctionnalités identiques ou similaires existent déjà dans l’application de base, telles que la facturation électronique, les exportations d’audit, les fonctionnalités de TVA, l’échange de données et d’autres pour lesquelles la plupart des fonctionnalités sont communes à tous les pays/régions mais il existe certaines règles ou règles locales. formats commerciaux qui sont des extensions de cadres ou de formats globaux. Au lieu de créer de nouvelles fonctionnalités, étendez celles existantes.    
- Préparez des guides de configuration (assistants) pour les zones complexes à configurer afin d’aider les utilisateurs à activer, découvrir et avoir une bonne première expérience d’utilisation de votre application de localisation.  
- Les partenaires doivent fournir une documentation fonctionnelle pour tous les aspects de leur localisation.  

### <a name="technical-requirements"></a>Exigences électriques

Vous trouverez ci-dessous une liste de contrôle de toutes les exigences que vous devez remplir avant de soumettre une application de localisation validée en tant extension pour vérification. Cette liste ne modifie pas la [liste de validation technique](/dynamics365/business-central/dev-itpro/developer/devenv-checklist-submission) et étend uniquement les exigences à partir de là.  

- Les fournisseurs d’applications de localisation validées doivent créer l’application de localisation validée basée sur l’application de base W1.  
- Les fournisseurs d’applications de localisation validées doivent suivre les politiques de cycle de vie et de support de Microsoft.   
- L’automatisation obligatoire des tests doit couvrir min. 80 % du code et tous les processus métier qui changent avec l’application de localisation validée doivent être couverts par l’automatisation des tests.  
- Les fournisseurs d’applications de localisation validées doivent mettre à jour et/ou tester leur application de localisation validée avant le lancement officiel de la nouvelle version (au minimum avec le RC avant la nouvelle version) pour confirmer qu’il n’y a aucun problème. 
- Tous les objets du code de l’application de localisation validée doivent être en anglais.   
- Les fournisseurs d’applications de localisation validées doivent suivre la politique de Microsoft relative aux objets obsolètes, aux modifications importantes et aux meilleures pratiques en matière de dépréciation du code AL.  
- Les fournisseurs d’applications de localisation validées doivent ajouter de nouveaux événements si le marché l’exige (autres partenaires de mise en œuvre ou clients) si cela est raisonnable sur le plan commercial, conformément à la politique et aux pratiques de Microsoft. Dans le cas contraire, les fournisseurs d’applications de localisation validés doivent fournir une réponse à ces demandes en justifiant de manière appropriée pourquoi cela n’est pas raisonnablement logique d’un point de vue commercial. 
- Les fournisseurs d’applications de localisation validées doivent fournir des scénarios de test écrits en anglais et permettre à Microsoft d’effectuer des tests manuels si Microsoft l’exige.  
- Si une application de localisation validée étend le [!INCLUDE[prod_short](includes/prod_short.md)] modèle de données avec de nouvelles tables et/ou champs, le fournisseur de l’application de localisation validée doit définir correctement la propriété **DataClassification**.
- Les fournisseurs d’applications de localisation validées doivent créer l’application de localisation validée basée sur l’application de base W1.  
- Les fournisseurs d’applications de localisation validées doivent suivre les politiques de cycle de vie et de support de Microsoft.   

> [!NOTE]  
> Vous pouvez également créer une intégration si vous trouvez avantageux de placer certaines fonctionnalités en dehors de l’ [!INCLUDE[prod_short](includes/prod_short.md)] environnement et de vous y connecter [!INCLUDE[prod_short](includes/prod_short.md)] en utilisant par exemple des API ou des services Web.

## <a name="see-also"></a>Voir aussi .

[Validation technique](/dynamics365/business-central/dev-itpro/developer/devenv-checklist-submission)  
[Développement d’une solution de localisation standard](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-localization)  
[Disponibilité par pays/région et langues prises en charge](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Quelles sont les fonctionnalités locales dans Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)]?](about-localization.md)  
[Disponibilité internationale de Microsoft Dynamics 365](/dynamics365/get-started/availability)  
[Vue d’ensemble de la conformité](compliance/compliance-overview.md)  
[Disponibilité géographique pour Dynamics 365](https://dynamics.microsoft.com/en-us/availability-reports/georeport/)  
