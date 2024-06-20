---
title: Configurer des informations générales pour les immobilisations
description: 'Avant d''utiliser des immobilisations, vous devez paramétrer des comptes GL par défaut, des groupes de report, des clés d''affectation, des modèles et lots de journal, ainsi que des codes de classe.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: '5623, 5615, 5661, 5662, 5627, 5616, 5620, 5629, 5633, 5609, 5631, 5630, 5617, 5612, 5613, 5608, 5609, 5635, 9277'
ms.date: 03/25/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="set-up-general-fixed-assets-information"></a>Configuration des informations générales sur les immobilisations

Avant de pouvoir gérer des immobilisations, vous devez configurer des comptes du grand livre par défaut, des clés d’affectation, des modèles journal et des lots pour reporter et reclasser des immobilisations. Définissez également une hiérarchie de classification (classes et sous-classes) pour structurer vos actifs et, si nécessaire, définissez les emplacements où vous stockez les actifs.

## <a name="to-set-up-general-behavior-for-fixed-assets-functionality"></a>Pour configurer un comportement général pour la fonctionnalité immobilisations

Définissez le comportement général de la fonctionnalité d’immobilisation et des séries de numéros document sur la page **Configuration immobilisations**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration immobilisations**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-fixed-asset-posting-groups"></a>Pour configurer des groupes de validation immobilisation

Utilisez les groupes de report pour définir des groupes d’immobilisations. Les écritures de ces groupes de report sont reportées dans les mêmes comptes GL.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report immo.**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche groupe de report immo.**, renseignez les champs, le cas échéant.

    > [!NOTE]  
    >   Pour veiller à ce que les comptes de contrepartie pour différentes validations d'immobilisation soient automatiquement insérés lorsque vous sélectionnez l'action **Insérer contrepartie immo.** sur les lignes feuille, procédez comme suit, selon la validation de réévaluation.
4. Sur le raccourci **Compte contrepartie**, dans le champ **Contrep. réévaluation**, sélectionnez le compte général dans lequel vous souhaitez valider les écritures contrepartie pour la réévaluation.

Pour en savoir plus sur l’utilisation de l’action **Insérer compte contrepartie immo.** sur les lignes Journal GL immo., voir [Réévaluer les immobilisations](fa-how-revalue.md).

## <a name="to-set-up-fixed-asset-journal-templates"></a>Pour configurer les modèles journal immobilisation

Un modèle est une présentation de journal prédéfinie. Le modèle affiche des informations sur les codes suivi, les rapports et les séries de numéros. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

[!INCLUDE[prod_short](includes/prod_short.md)] crée automatiquement un modèle journal immobilisation la première fois que vous ouvrez la page **Journal immobilisation**. Vous pouvez cependant définir d’autres modèles journal.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles journal immo.**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-class-and-subclass-codes"></a>Pour configurer la classe des immobilisations et les codes sous-classe

Dans les immobilisations, vous pouvez définir une hiérarchie de classification qui peut être utilisée pour regrouper les immobilisations. La hiérarchie comporte deux niveaux : les classes et les sous-classes.

### <a name="fixed-asset-class-codes"></a>Codes classe immobilisation

Les classes d’immobilisations constituent les entrées de niveau supérieur dans la hiérarchie de classification dans laquelle vous regroupez les immobilisations. Par exemple, utilisez des classes pour diviser les actifs en actifs corporels ou incorporels. Vous devez créer au moins une classe d’immobilisations dans votre configuration.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Classes immo.**, puis choisissez le lien associé.
2. Saisissez les codes et les noms des classes immobilisation que vous souhaitez créer.

### <a name="fixed-asset-subclass-codes"></a>Codes sous-classe immobilisation

Les sous-classes d’immobilisations constituent les entrées de niveau secondaire dans la hiérarchie de classification dans laquelle vous regroupez les immobilisations. Chaque sous-classe pointe vers une classe de niveau supérieur. Utilisez code sous-classe immobilisation permet de regrouper des immobilisations dans des catégories plus spécifiques, comme les bâtiments, les véhicules, le mobilier et les machines. Vous devez créer au moins une sous-classe d’immobilisations dans votre configuration.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sous-classes immo.**, puis choisissez le lien associé.
2. Saisissez les codes et les noms des sous-classes immobilisation que vous souhaitez créer.

## <a name="start-to-register-assets"></a>Commencer à enregistrer les actifs

Si vous utilisez les immobilisations dans [!INCLUDE[prod_short](includes/prod_short.md)] pour la première fois, vous devez d’abord configurer le module de grand livre avant de configurer les immobilisations. La manière de procéder est différente si vous intégrez les immobilisations dans le grand livre.  

La procédure suivante est utilisée si les transactions immobilisation doivent être reportées dans le grand livre.  

1. Effectuez les configurations de base pour les immobilisations.  
2. Remplissez une fiche immobilisation pour chaque immobilisation existante.  
3. Créez une loi d'amortissement d'une immobilisation pour chaque type d'amortissement (par exemple les états financiers). Pour chaque registre amortissement, définissez les conditions, par exemple l’intégration avec le grand livre.

    Activez l'intégration dans le grand livre en procédant comme suit. Premièrement, assurez-vous que l’intégration dans le grand livre n’est pas activée pour toutes les registres amortissement, puis reportez les écritures ouvertes, et enfin activez l’intégration dans le grand livre.  
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Registres amortissement**, puis choisissez le lien associé.  
5. Sélectionnez le registre amortissement pertinent, puis choisissez l'action **Modifier** pour ouvrir la page **Fiche registre amortissement**.
6. Sur l’onglet rapide **Intégration** , désactivez toutes les options. Si vous disposez de plusieurs registres amortissement, répétez cette étape pour chacun d’eux.  
7. Dans le journal immobilisation, entrez les lignes suivantes pour chaque immobilisation :
   * Ligne avec le coût d'acquisition.
   * Une ligne avec l'amortissement cumulé jusqu'à la fin de l'exercice financier précédent.
   * Une ligne avec l'amortissement cumulé du début de l'exercice comptable en cours jusqu'à la date à laquelle [!INCLUDE[prod_short](includes/prod_short.md)] est défini pour démarrer le calcul de l'amortissement.

    Si vous disposez d'autres soldes ouverts, vous pouvez également les saisir maintenant (dépréciation, appréciation, par exemple).  
8. Une fois que vous saisi et reporté les lignes journal pour chaque immobilisation, activez l’intégration dans le grand livre dans les registres amortissement.

Si les immobilisations ne sont pas intégrées au grand livre, ignorez les étapes 6 et 8.

## <a name="to-set-up-fixed-asset-location-codes-optional"></a>Pour configurer les codes emplacement immobilisation (facultatif)

Les codes emplacement immobilisation définissent des identificateurs pour l’emplacement des actifs, tels que le service commercial, l’accueil, l’administration, la production ou l’entrepôt. Vous pouvez les utiliser pour enregistrer l’emplacement d’une immobilisation. Ces informations sont utiles à des fins d'assurance et de suivi de l'inventaire.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements immo.**, puis choisissez le lien associé.
2. Saisissez les codes et les noms des emplacements immobilisation que vous souhaitez créer.

## <a name="to-set-up-fixed-asset-allocation-keys-optional"></a>Pour configurer des clés d’affectation d’immobilisations (facultatif)

Utilisez des clés d’affectation pour allouer des transactions à divers départements ou projets. Vous pouvez, par exemple, définir une clé d’affectation pour répartir les coûts d’amortissement des véhicules entre le service administratif pour 35 % et le service commercial pour 65 %. Pour plus d'informations, reportez vous à [Répartition des coûts et du revenu](year-allocate-costs-income.md).

Les clés d'affectation s'appliquent à des classes d'immobilisations et non à des immobilisations individuelles.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report immo.**, puis choisissez le lien associé.  
2. Sur la page **Groupes de report immo.**, sélectionnez l'action **Affectations**, puis choisissez un type de report.
3. Sur la page **Affectations immo.**, renseignez les champs selon vos besoins.
4. Répétez les phases 2 et 3 pour chacun des types de report pour lesquels vous souhaitez définir des clés d'affectation.

## <a name="to-set-up-fixed-asset-journal-batches-optional"></a>Pour configurer les lots journal immobilisation (facultatif)

Vous pouvez configurer plusieurs lots journal, c'est-à-dire des journaux individuels pour chaque modèle journal. Par exemple, chaque employé peut avoir son propre journal dont le nom correspond à ses initiales. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles journal immo.**, puis sélectionnez le lien associé.  
2. Sélectionnez le modèle feuille pertinent, puis l'action **Lots**.
3. Sur la page **Lots journal immo.**, renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-reclassification-journal-templates-optional"></a>Pour configurer des modèles journal reclassement immobilisation (facultatif)

Utiliser les journaux reclassement dédiés pour transférer, fractionner ou regrouper des immobilisations. [!INCLUDE[prod_short](includes/prod_short.md)] crée automatiquement un modèle journal reclassement immobilisation la première fois que vous ouvrez la page **Journal reclass. immo**. Vous pouvez paramétrer d’autres modèles journal reclassement. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles de journaux de reclassement d’immobilisation**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-fixed-asset-reclassification-journal-batches-optional"></a>Pour configurer les lots journal reclassement immobilisation (facultatif)

Vous pouvez configurer plusieurs lots journal, c'est-à-dire des journaux individuels pour chaque modèle journal reclassement. Par exemple, chaque employé peut avoir son propre journal reclassement dont le nom correspond à ses initiales. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles de journaux de reclassement d’immobilisation**, puis sélectionnez le lien associé.  
2. Sélectionnez le modèle feuille pertinent, puis l'action **Lots**.
3. Sur la page **Lots journal reclass. immo.**, renseignez les champs selon vos besoins.

## <a name="see-also"></a>Voir aussi .

[Paramétrage d'immobilisations](fa-setup.md)  
[Vue d’ensemble des immobilisations](fa-manage.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
