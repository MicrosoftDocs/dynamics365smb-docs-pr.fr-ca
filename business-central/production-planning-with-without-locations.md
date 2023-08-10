---
title: Planification avec/sans emplacement
description: "Dans cette rubrique, découvrez la production et la fabrication, y compris la planification des approvisionnements, dans Business\_Central."
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 09/15/2022
ms.author: edupont
---
# <a name="planning-with-or-without-locations"></a>Planification avec/sans emplacement

Avant de commencer à utiliser le moteur de planification, nous vous recommandons de décider d’utiliser ou non les emplacements. Il existe deux principaux moyens simples :

* Les lignes demande indiquent systématiquement le code d'emplacement et le système exploite intégralement les unités de stock, y compris la configuration d'emplacement pertinente. En savoir plus sur [Demande à l'emplacement](#demand-at-location).  
* Les lignes de demande ne comportent jamais de codes d’emplacement et le système utilise la fiche article. Voir le scénario [Demande dans un « emplacement vide »](#demand-at-blank-location) ci-dessous.

## <a name="demand-at-location"></a>Demande à l'emplacement

Lorsque le système de planification détecte une demande dans un emplacement (identifiée par une ligne avec code d'emplacement), il peut procéder de plusieurs manières en fonction de 2 valeurs de configuration critiques.  

Lors de l'exécution de la planification, le système recherche ces 2 valeurs de configuration l'une après l'autre et effectue la planification en conséquence :  

1. Existe-t-il une unité de stock pour l’article à l'emplacement demandé ?  

    Si oui :  

    L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.  

    Si non :  

2. Le champ **Composantes à l’emplacement** de la page **Configuration production** contient-il le code d’emplacement demandé?  

    Si oui :  

    L'article est planifié en fonction des paramètres de planification de la fiche article.  

    Si non :  

    L’article est planifié selon « l’alternative minimale » qui couvre la demande exacte. Les paramètres de planification sont définis comme suit : Stratégie réapprovisionnement = *Lot pour Lot*, Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide. (Les articles qui suivent l’*ordre* de la méthode réapprovisionnement continuent à *le* suivre, tout comme les autres paramètres.)

> [!TIP]
> Si vous planifiez souvent des demandes à différents emplacements, nous vous recommandons d’utiliser la fonction Unités de stock et d’éviter toute demande dans un emplacement vide. Pour en savoir plus, voir [Configurer les unités de stock](inventory-how-to-set-up-stockkeeping-units.md)

Consultez les variantes des [cas de figure ci-dessous](#scenarios).

> [!NOTE]
> Ce champ **Composantes à l'emplacement** sur la page **Configuration production** joue un rôle fondamental quant à la faon dont le système gère les lignes demande production.
>
> Concernant la demande de production, [!INCLUDE [prod_short](includes/prod_short.md)] utilise, pour le sous-ensemble et les composantes, l'emplacement mentionné sur le bon de production. Toutefois, en complétant ce champ, vous pouvez rediriger le sous-ensemble et les composantes vers un autre emplacement.
>
> Vous pouvez également définir ceci pour une unité de stock précise en sélectionnant un code d’emplacement différent dans le champ **Mag. composante par déf** de la fiche unité de stock. Remarquez toutefois que cette action est rarement utilisée, comme la logique planification peut être altérée lors de la planification pour la composante unité de stock.

## <a name="demand-at-blank-location"></a>Demande dans un « emplacement vide »

En général, lorsque le système de planification détecte une demande à un emplacement vide (une ligne sans code emplacement), l’article est planifié en fonction des paramètres de planification de la fiche article.

Le champ **Emplacements obligatoires** de la page **Configuration inventaire**, le champ **Composantes à l’emplacement** de la page **Configuration production** ou les unités de stock affecteront la façon dont le système de planification traite les lignes de demande avec ou sans codes emplacement. Si une des instructions suivantes est vraie, la demande dans l'emplacement vide est également considérée comme un écart et le système de planification réagira en utilisant la « solution minimale » : l’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

* Le champ **Composantes à l'emplacement** sur la page **Configuration de la fabrication** a une valeur.
* Une unité de stock existe pour l’article planifié.
* Le champ **Emplacement obligatoire** est sélectionné.

## <a name="scenarios"></a>Cas de figure

Consultez les variantes des scénarios de configuration ci-dessous.

### <a name="setup-1"></a>Configuration 1

* Emplacement obligatoire = *Oui*  
* L'unité de stock a pour valeur *OUEST*  
* Composante à l'emplacement = *EST*  

#### <a name="case-11-demand-is-at-west-location"></a>Situation 1.1 : la demande concerne un emplacement *OUEST*

L'article est planifié en fonction des paramètres de planification de la fiche unité de stock (y compris, un éventuel transfert).

#### <a name="case-12-demand-is-at-east-location"></a>Situation 1.2 : la demande concerne un emplacement *EST*

L'article est planifié en fonction des paramètres de planification de la fiche article.

#### <a name="case-13-demand-is-at-north-location"></a>Situation 1.3 : la demande concerne un emplacement *NORD*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-14-demand-is-at-blank-location"></a>Situation 1.4 : la demande concerne un emplacement *VIDE*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

### <a name="setup-2"></a>Configuration 2

* Emplacement obligatoire = *Oui*  
* Il n'existe pas d'unité de stock  
* Composante à l'emplacement = *EST*  

#### <a name="case-21-demand-is-at-west-location"></a>Situation 2.1 : la demande concerne un emplacement *OUEST*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-22-demand-is-at-east-location"></a>Situation 2.2 : la demande concerne un emplacement *EST*

L'article est planifié en fonction des paramètres de planification de la fiche article.  

### <a name="setup-3"></a>Configuration 3

* Emplacement obligatoire = *Non*  
* Il n'existe pas d'unité de stock  
* Composante à l'emplacement = *EST*  

#### <a name="case-31-demand-is-at-west-location"></a>Situation 3.1 : la demande concerne un emplacement *OUEST*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-32-demand-is-at-east-location"></a>Situation 3.2 : la demande concerne un emplacement *EST*

L'article est planifié en fonction des paramètres de planification de la fiche article.  

#### <a name="case-33-demand-is-at-blank-location"></a>Situation 3.3 : la demande concerne un emplacement *VIDE*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

### <a name="setup-4"></a>Configuration 4

* Emplacement obligatoire = *Non*  
* Il n'existe pas d'unité de stock  
* Composante à l'emplacement = *VIDE*  

#### <a name="case-41-demand-is-at-east-location"></a>Situation 4.1 : la demande concerne un emplacement *EST*

L’article est planifié comme suit : Stratégie réapprovisionnement = *Lot pour Lot* (l’*ordre* conserve la valeur *Ordre*), Inclure inventaire = *Oui*. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-42-demand-is-at-blank-location"></a>Situation 4.2 : la demande concerne un emplacement *VIDE*

L'article est planifié en fonction des paramètres de planification de la fiche article.

Comme vous pouvez le voir au dernier cas de figure, le seul moyen d'obtenir des résultats corrects pour une ligne de demande sans code d'emplacement consiste à désactiver toutes les valeurs de configuration relatives aux emplacements. De la même manière, le seul moyen d'obtenir des résultats de planification stables pour les demandes dans des magasins consiste à utiliser des points de stock.  

Par conséquent, si vous planifiez souvent des demandes dans des emplacements, nous vous recommandons d’utiliser la fonction unités de stock.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/training/paths/trade-get-started-dynamics-365-business-central/).

## <a name="see-also"></a>Voir aussi .

[Planification](production-planning.md)  
[Configurer la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Stock](inventory-manage-inventory.md)  
[Configurer des unités de stock](inventory-how-to-set-up-stockkeeping-units.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
