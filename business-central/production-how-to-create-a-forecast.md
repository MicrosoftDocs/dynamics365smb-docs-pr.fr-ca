---
title: 'Procédure : Créer une prévision de la demande'
description: Découvrez les fonctionnalités de prévision de la demande et comment créer des prévisions de vente et de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/22/2021
ms.author: edupont
ms.openlocfilehash: 9c3097e102de7b0f4be6da114245ac1bbb4f4fe0
ms.sourcegitcommit: c35a132cc615629e4f873177755a39ab58783e38
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643977"
---
# <a name="create-a-demand-forecast"></a>Créer une prévision de la demande
Vous pouvez créer des prévisions de vente et de production à l'aide de la page **Prévision demande**.  

La fonctionnalité de prévision permet de créer une demande anticipée ; la demande réelle est créée à partir de commandes vente et fabrication. Lors de la création du calendrier de production principal (MPS), la prévision est ajustée par rapport aux commandes de vente et aux bons de production. L'option *Composant* sur la prévision détermine le type d'exigences à prendre en considération dans le processus d'ajustement. Si la prévision a trait à un article vente, seules les commandes vente ajustent la prévision. Si elle concerne les composantes, seule la demande dépendante des composantes bon de production ajuste la prévision.  

Les prévisions permettent à votre compagnie de créer des scénarios basés sur des hypothèses, de planifier et de répondre à la demande de façon efficace et rentable. Des prévisions précises peuvent faire la différence au niveau de la satisfaction de la clientèle en relation avec les dates promesse des livraisons et la ponctualité de ces dernières.  

## <a name="sales-forecasts-and-production-forecasts"></a>Prévisions de vente et de fabrication  
La fonctionnalité de prévision de l'application permet de générer des prévisions de vente ou de fabrication, de façon combinée ou indépendante. Par exemple, la plupart des compagnies qui fabriquent à la commande ne gèrent pas un inventaire de produits finis parce que chaque article est produit au moment de la commande. L'anticipation sur les commandes (prévision de vente) est essentielle pour aboutit à un délai de production raisonnable des produits finis (prévision de production). À titre d'exemple, les composantes nécessitant un délai de livraison important, si elles ne sont pas en commande ou dans l'inventaire, peuvent retarder la fabrication.  

-   La prévision de vente est le meilleur indicateur du service commercial en relation avec les ventes futures et est spécifiée par article et par période. Toutefois, la prévision de vente n'est pas toujours appropriée pour la fabrication.  
-   La prévision de production est l'estimation par le gestionnaire de production du nombre d'articles finis et de sous-ensembles à produire dans des périodes données afin de satisfaire les prévisions de vente.  

Dès lors, le plus souvent, le gestionnaire de production modifie la prévision de vente pour l'adapter aux conditions de production, tout en satisfaisant à la prévision de vente.  

Vous créez des prévisions manuellement sur la page **Prévision demande**. Plusieurs prévisions peuvent exister dans le système, qui se différencient par leur nom et leur type. Vous pouvez copier et modifier les prévisions si nécessaire. Notez qu'il ne peut y avoir qu'une seule prévision valide à la fois en relation avec la planification.  

La prévision consiste en un certain nombre d'enregistrements indiquant un numéro d'article, une date de prévision et une quantité prévue. La prévision d'un article couvre une période qui est définie par la date prévision et la date prévision de l'enregistrement prévision suivant. Du point de vue de la planification, la quantité prévue doit être disponible au début de la période de demande.  

Vous devez désigner une prévision comme *Article vente*, *Composant* ou *Les deux*. Le type prévision *Article vente* est utilisé pour la prévision de vente. La prévision de production est créée à l'aide du type *Composant*. Le type de prévision *Les deux* n'est utilisé que pour donner au gestionnaire un aperçu de la prévision de vente et de la prévision de production. Avec cette option, les écritures prévisions ne sont pas modifiables. En désignant ces types de prévision ici, vous pouvez utiliser la même feuille pour entrer une prévision de vente que pour une prévision de production, ainsi qu'utiliser la même feuille pour afficher les deux prévisions simultanément. Notez que le système traite les différentes entrées (vente et production) de façon différente lors du calcul de la planification, en fonction de la configuration de l'article, de la fabrication et de la production.  

## <a name="component-forecast"></a>Prévision composante  
La prévision composante peut être considérée comme une prévision d'option en relation avec un article parent. Cela peut, par exemple, être utile si le gestionnaire peut estimer la demande pour la composante.  

Du fait que la prévision composante sert à définir des options pour un article parent, la valeur de prévision composante doit être inférieure ou égale à la quantité de vente d’article prévue. Si la valeur de prévision composante est supérieure à la prévision de vente d’article, le système traite la différence entre ces deux types de prévisions comme une demande indépendante.  

## <a name="forecasting-periods"></a>Périodes de prévision  
La période de prévision est valide de la date début jusqu'à la date début de la prévision suivante. La page d'intervalle de temps offre plusieurs choix pour insérer la demande à une date spécifique dans une période. Il est donc recommandé de ne pas modifier l'étendue de la période de prévision à moins de déplacer toutes les écritures de prévision à la date début de cette période.  

## <a name="forecast-by-locations"></a>Prévision par magasin  
Sur la page **Configuration production**, vous pouvez spécifier la manière dont vous voulez prendre en compte les emplacements définis dans les prévisions lorsque vous calculez des plans. 

### <a name="use-forecast-by-locations"></a>Utiliser Prévision par emplacements

Si vous activez le bouton de basculement **Prévision sur emplacement**, [!INCLUDE[prod_short](includes/prod_short.md)] respectera tous les codes d'emplacement spécifiés pour chaque écriture de prévision de la demande et calculera la prévision restante pour chaque emplacement.  

Prenons cet exemple : votre compagnie achète et vend des articles dans deux emplacements : EAST et WEST. Pour les deux emplacements, vous avez configuré une politique de réorganisation de lot à lot. Vous créez une prévision pour les deux emplacements :

- 10 pièces pour l'emplacement EAST
- 4 pièces pour l'emplacement WEST

Ensuite, vous créez un document de vente avec une quantité de 12 sur l'emplacement WEST. Le système de planification vous suggérera de faire ce qui suit :

- Reconstituez 10 pièces pour l'emplacement EAST, en fonction des données des prévisions.  
- Reconstituez 12 pièces pour l'emplacement WEST, en fonction du document de vente. Les quatre pièces spécifiées dans la prévision sont entièrement consommées par la demande réelle du document de vente. Pour plus d’informations, reportez-vous à la section [La demande de prévision est réduite par les documents de vente](design-details-balancing-demand-and-supply.md#forecast-demand-is-reduced-by-sales-orders). 

> [!NOTE]  
>  Si les prévisions basées sur l'emplacement sont consultées isolément, il se peut que la prévision globale ne soit pas représentative.

### <a name="do-not-use-forecast-by-locations"></a>Ne pas utiliser Prévision par emplacements
Si vous désactivez le bouton de basculement **Prévision sur emplacement**, [!INCLUDE[prod_short](includes/prod_short.md)] ignorera les codes d'emplacement spécifiés pour chaque écriture de prévision de la demande et agrégera les prévisions en une prévision pour les emplacements vides.  

Prenons cet exemple : votre compagnie achète et vend des articles dans deux emplacements : EAST et WEST. Pour les deux emplacements, vous avez configuré une politique de réorganisation de lot à lot. Vous créez une prévision pour les deux emplacements :

- 10 pièces pour l'emplacement EAST
- 4 pièces pour l'emplacement WEST

Ensuite, vous créez un document de vente avec une quantité de 12 sur l'emplacement WEST. Le système de planification vous suggérera de faire ce qui suit :

- Reconstituez 12 pièces pour l'emplacement WEST, en fonction du document de vente. 
- Reconstituez 2 pièces pour l'emplacement vide. Les 10 et 4 pièces spécifiées dans la prévision sont partiellement consommées par la demande réelle du document de vente. [!INCLUDE[prod_short](includes/prod_short.md)] a ignoré les codes d'emplacement spécifiés par l’utilisateur et utilise à la place un emplacement vide.

> [!NOTE]  
>  Vous pouvez définir un filtre par emplacement, mais les résultats basés sur l’emplacement peuvent ne pas correspondre aux résultats de planification sans filtres.

## <a name="to-create-a-demand-forecast"></a>Pour créer une prévision de la demande

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prévision de la demande**, puis sélectionnez le lien associé.  
2. Sur le raccourci **Général**, choisissez une prévision dans le champ **Nom prévision demande**. Plusieurs prévisions peuvent exister, qui se différencient par leur nom et leur type.  
3. Dans le champ **Filtre magasin**, sélectionnez le magasin auquel s'applique la prévision.
4. Dans le champ **Afficher par** pour modifier la période affichée dans chaque colonne. Vous pouvez choisir entre les intervalles suivants : **Jour**, **Semaine**, **Mois**, **Trimestre**, **Année** ou **Période comptable**, tel que paramétré dans votre espace financier.    

> [!NOTE]  
>  Vous devez choisir l'intervalle de temps que vous voulez utiliser pour les prévisions futures de façon à ce qu'il soit toujours cohérent. Lorsque vous entrez une quantité prévision, elle vaut dès le premier jour de l'intervalle de temps que vous sélectionnez. Par exemple, si vous sélectionnez un mois, vous devez entrer la quantité prévision au premier jour du mois. Si vous sélectionnez un trimestre, vous devez entrer la quantité prévision au premier jour du premier mois du trimestre.

5. Dans le champ **Afficher en tant que**, sélectionnez la manière dont seront affichées les quantités prévision pour l'intervalle de temps. Si vous sélectionnez **Solde période**, le solde période est affiché pour l'intervalle de temps. Si vous sélectionnez **Solde au**, la page affiche le solde au dernier jour de l'intervalle de temps.  
6. Dans le champ **Type prévision**, choisissez **Article vente**, **Composant** ou **Les deux**. Si vous sélectionnez **Article vente** ou **Composant**, vous pouvez modifier la quantité par période. Si vous sélectionnez **Les deux**, vous ne pouvez pas modifier la quantité mais vous pouvez choisir le bouton flèche déroulante afin de visualiser les écritures prévision demande.  
7. Spécifiez un **filtre date** si vous voulez limiter la quantité de données affichées.  
8. Sur le raccourci **Matrice Prévision demande**, entrez les quantités prévues en saisissant une quantité dans la cellule représentant un article à une date ou une période particulière. Notez que dans les cellules vides, le bouton de recherche ouvre une page vide indiquant que vous devez saisir manuellement une valeur.   

> [!NOTE]  
>  Vous pouvez également modifier une prévision existante. Sur la page **Matrice Prévision demande**, choisissez l'action **Copier prévision demande** et renseignez la page **Prévision demande** à l'aide de la prévision existante. Vous pouvez alors modifier les quantités en fonction des besoins.  

## <a name="see-also"></a>Voir aussi  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
