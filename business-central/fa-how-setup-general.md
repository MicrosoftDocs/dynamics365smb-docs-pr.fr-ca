---
title: Configurer grand livre immobilisation| Microsoft Docs
description: Avant d'utiliser des immobilisations, vous devez paramétrer des comptes GL par défaut, des groupes de report, des clés d'affectation, des modèles et lots de journal, ainsi que des codes de classe.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 62eeab6d03f0fde0b1f55f414d48c2d3cd3f573c
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5380212"
---
# <a name="set-up-general-fixed-assets-information"></a>Configurer des informations générales pour les immobilisations
Avant de pouvoir gérer les immobilisations, vous devez configurer les comptes du grand livre par défaut, les clés d'affectation, les modèles journal et les lots pour le report et le reclassement des immobilisations. Vous pouvez classer les immobilisations par catégorie, telles que Corporelles et Incorporelles.

## <a name="to-set-up-general-default-values-for-fixed-assets"></a>Pour configurer des valeurs générales par défaut pour les immobilisations
Vous définissez le comportement général ou la fonctionnalité immobilisation et configurez les séries de numéros document sur la page **Configuration immobilisations**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration immobilisations**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-fixed-asset-posting-groups"></a>Pour configurer des groupes de validation immobilisation
Les groupes comptabilisation permettent de définir des groupes d'immobilisations. Les écritures de ces groupes de report sont reportées dans les mêmes comptes du grand livre.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report immo.**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche groupe de report immo.**, renseignez les champs, le cas échéant.

    > [!NOTE]  
    >   Pour veiller à ce que les comptes de contrepartie pour différentes validations d'immobilisation soient automatiquement insérés lorsque vous sélectionnez l'action **Insérer contrepartie immo.** sur les lignes feuille, procédez comme suit, selon la validation de réévaluation.
4. Sur le raccourci **Compte contrepartie**, dans le champ **Contrep. réévaluation**, sélectionnez le compte général dans lequel vous souhaitez valider les écritures contrepartie pour la réévaluation.

Pour en savoir plus sur l'utilisation de l'action **Insérer contrepartie immo.** sur les lignes feuille compta. immo., voir, par exemple, [Réévaluer les immobilisations](fa-how-revalue.md).

## <a name="to-set-up-fixed-asset-allocation-keys"></a>Pour configurer les clés de ventilation d'immobilisations
Vous pouvez affecter les transactions à plusieurs départements ou projets sur la base de clés d'affectation paramétrables. Vous pouvez, par exemple, définir une clé d'affectation pour affecter les coûts d'amortissement des véhicules entre le service administratif pour 35 % et le service commercial pour 65 %. Pour plus d'informations, reportez vous à [Répartition des coûts et du revenu](year-allocate-costs-income.md).

Les clés d'affectation s'appliquent à des classes d'immobilisations et non à des immobilisations individuelles.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report immo.**, puis sélectionnez le lien associé.  
2. Sur la page **Groupes de report immo.**, sélectionnez l'action **Affectations**, puis choisissez un type de report.
3. Sur la page **Affectations immo.**, renseignez les champs selon vos besoins.
4. Répétez les phases 2 et 3 pour chacun des types de report pour lesquels vous souhaitez définir des clés d'affectation.

## <a name="to-set-up-fixed-asset-journal-templates"></a>Pour configurer les modèles journal immobilisation
Un modèle est une présentation de journal prédéfinie. Le modèle affiche des informations sur les codes suivi, les rapports et les séries de numéros. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

[!INCLUDE[prod_short](includes/prod_short.md)] crée automatiquement un modèle journal immobilisation la première fois que vous ouvrez la page **Journal immobilisation**. Vous pouvez cependant configurer d'autres modèles journal.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles journal immo.**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-journal-batches"></a>Pour configurer des lots journal immobilisation
Vous pouvez configurer plusieurs lots journal, c'est-à-dire des journaux individuels pour chaque modèle journal. Par exemple, chaque employé peut avoir son propre journal dont le nom correspond à ses initiales. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles journal immo.**, puis sélectionnez le lien associé.  
2. Sélectionnez le modèle feuille pertinent, puis l'action **Lots**.
3. Sur la page **Lots journal immo.**, renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-reclassification-journal-templates"></a>Pour configurer des modèles journal reclassement immobilisation
Vous pouvez utiliser les feuilles reclassement dédiées lorsque vous devez transférer, fractionner ou regrouper des immobilisations. [!INCLUDE[prod_short](includes/prod_short.md)] crée automatiquement un modèle journal reclassement immobilisation la première fois que vous ouvrez la page **Journal reclass. immo**. Vous pouvez configurer d'autres modèles journal reclassement. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles journal reclass. immo**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-reclassification-journal-batches"></a>Pour configurer les lots journal reclassement immobilisation
Vous pouvez configurer plusieurs lots journal, c'est-à-dire des journaux individuels pour chaque modèle journal reclassement. Par exemple, chaque employé peut avoir son propre journal reclassement dont le nom correspond à ses initiales. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles journal reclass. immo**, puis sélectionnez le lien associé.  
2. Sélectionnez le modèle feuille pertinent, puis l'action **Lots**.
3. Sur la page **Lots journal reclass. immo.**, renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-class-codes"></a>Pour configurer les codes classe immobilisation
Les codes classe immobilisation peut être utilisé pour grouper des immobilisations, par exemple les immobilisations corporelles et les immobilisations incorporelles.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Classes immo.**, puis sélectionnez le lien associé.
2. Saisissez les codes et les noms des classes que vous souhaitez créer.

## <a name="to-set-up-fixed-asset-subclass-codes"></a>Pour configurer les codes sous-classe immobilisation
Le code sous-classe immobilisation permet de regrouper des immobilisations en catégories, comme les bâtiments, les véhicules, le mobilier et les machines.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Sous-classes immo.**, puis sélectionnez le lien associé.
2. Saisissez les codes et les noms des classes que vous souhaitez créer.

## <a name="to-set-up-fixed-asset-location-codes"></a>Pour configurer les codes emplacement immobilisation
Les codes emplacement immobilisation permettent d'enregistrer l'emplacement de l'immobilisation, tel que le service commercial, l'accueil, l'administration, la production ou un entrepôt. Ces informations sont utiles à des fins d'assurance et de suivi de l'inventaire.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Emplacements immo.**, puis sélectionnez le lien associé.
2. Saisissez les codes et les noms des emplacements immobilisation que vous souhaitez créer.

## <a name="to-register-opening-entries"></a>Pour enregistrer des écritures d'ouverture
Si vous utilisez les immobilisations dans [!INCLUDE[prod_short](includes/prod_short.md)] pour la première fois, vous devez d'abord paramétrer le module de comptabilité avant de définir des immobilisations. La manière de procéder est différente si les immobilisations sont intégrées dans le grand livre.  

 La procédure suivante est utilisée si les transactions immobilisation doivent être reportées dans le grand livre.  

1. Assurez-vous que vous avez suivi les procédures de configuration de base pour les immobilisations.  
2. Créez une fiche immobilisation pour chaque immobilisation existante.  
3. Créez une loi d'amortissement d'une immobilisation pour chaque type d'amortissement (par exemple les états financiers). Pour chaque registre amortissement, vous devez définir des conditions, par exemple son intégration avec le grand livre.  

    Activez l'intégration dans le grand livre en procédant comme suit. Premièrement, assurez-vous que l'intégration dans le grand livre est désactivée pour tous les registres amortissement, puis reportez les écritures ouvertes, et enfin activez l'intégration dans le grand livre.  
4. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Registres amortissement**, puis sélectionnez le lien associé.  
5. Sélectionnez le registre amortissement pertinent, puis choisissez l'action **Modifier** pour ouvrir la page **Fiche registre amortissement**.
6. Sur le raccourci **Intégration**, assurez-vous que tous les champs sont vides en retirant toutes les coches. Si vous disposez de plusieurs registres amortissement, désactivez l'intégration avec le grand livre pour chacune d'elles.  
7. Dans le journal immobilisation, entrez les lignes suivantes pour chaque immobilisation :
   * Ligne avec le coût d'acquisition.
   * Une ligne avec l'amortissement cumulé jusqu'à la fin de l'exercice financier précédent.
   * Une ligne avec l'amortissement cumulé du début de l'exercice comptable en cours jusqu'à la date à laquelle [!INCLUDE[prod_short](includes/prod_short.md)] est défini pour démarrer le calcul de l'amortissement.

    Si vous disposez d'autres soldes ouverts, vous pouvez également les saisir maintenant (dépréciation, appréciation, par exemple).  
8. Une fois que vous avez saisi et reporté les lignes journal pour chaque immobilisation, activez l'intégration dans le grand livre dans les registres amortissement.

Si les immobilisations ne sont pas intégrées au grand livre, ignorez les étapes 6 et 8.

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Immobilisations](fa-manage.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]