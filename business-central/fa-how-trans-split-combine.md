---
title: Reclassification d’immobilisations
description: 'Vous reclassez une immobilisation pour la transférer vers un autre service, la fractionner, ou la combiner avec d''autres immobilisations.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: '5638, 5636, 5640, 5637'
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Transférer, fractionner ou regrouper les immobilisations

Vous pouvez utiliser le journal reclassement immobilisation pour transférer, fractionner et regrouper des immobilisations. Vous visualisez ou imprimez les résultats d'un reclassement immobilisation avec l'état **Immo. - Valeur comptable 02**.

## Pour transférer une immobilisation vers un autre département

Vous pouvez transférer une immobilisation vers un autre département lorsque, par exemple, vous placez une immobilisation dans le département production lorsqu'elle est en construction, puis la déplacez vers le département administration lorsqu'elle est finalisée.  

1. Définissez une nouvelle immobilisation. Entrez le nouveau département en tant que dimension.  
2. Affectez un registre amortissement immobilisation à la nouvelle immobilisation. Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux reclassement immobilisation**, puis choisissez le lien associé.
4. Créez une ligne journal lorsque le champ **N° immo.** contient l'immobilisation initiale, et le champ **Nouveau N° immo.** indique la nouvelle immobilisation à déplacer. Renseignez les autres champs, comme nécessaire.  
5. Sélectionnez l'action **Reclasser**.

    Deux lignes sont maintenant créées dans le journal GL immobilisation à l'aide du modèle et du lot que vous avez indiqués sur la page **Configuration du journal d'immobilisation** pour le registre amortissement spécifié. Pour en savoir plus, voir [Configurer l'amortissement d'immobilisation](fa-how-setup-depreciation.md).
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.    
7. Sur la page **Journal GL immo.**, sélectionnez l'action **Reporter** pour reporter le reclassement que vous avez effectué aux étapes 4 et 5.

Si vous avez reporté un coût d'acquisition pour une immobilisation, vous pouvez utiliser le journal reclassement immobilisation pour répartir ce coût sur plusieurs immobilisations.  

## Pour fractionner une immobilisation en trois immobilisations
Vous pouvez fractionner une immobilisation en plusieurs immobilisations, par exemple lorsque vous devez distribuer une immobilisation auprès de trois départements. Dans ce cas, vous pouvez déplacer, par exemple, 25 % du coût d'acquisition et de l'amortissement de l'immobilisation d'origine vers une autre, et 45 % vers une troisième. Les 30 % restants sont maintenus dans l'immobilisation d'origine.

1. Configurez deux nouvelles immobilisations. Entrez les nouveaux départements en tant que dimensions.  
2. Affectez des lois d'amortissement d'immobilisation aux nouvelles immobilisations. Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux reclassement immobilisation**, puis choisissez le lien associé.
4. Créez deux lignes journal reclassement, une pour chaque nouvelle immobilisation.
5. Sur la première ligne, entrez la deuxième immobilisation dans le champ **Nouveau N° immo.** et 25 dans le champ **Reclass. coût acq. %**.
6. Sur la deuxième ligne, entrez la troisième immobilisation dans le champ **Nouveau N° immo.** et 40 dans le champ **Reclass. coût acq. %**.
7. Sur les deux lignes, cochez les cases **Reclass. coût acq.** et **Reclass. amortissement**.  
8. Sélectionnez l'action **Reclasser**.  

    Deux lignes sont maintenant créées dans le journal GL immobilisation à l'aide du modèle et du lot que vous avez indiqués sur la page **Configuration du journal d'immobilisation** pour le registre amortissement spécifié. Pour en savoir plus, voir [Configurer l'amortissement d'immobilisation](fa-how-setup-depreciation.md).    
9. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.
10. Sur la page **Journal GL immo.**, sélectionnez l'action **Reporter** pour reporter le reclassement que vous avez effectué aux étapes 4 à 8.

## Pour regrouper deux immobilisations en une

Vous pouvez regrouper plusieurs immobilisations en une, par exemple lorsque vous déplacez les immobilisations distribuées dans un département. Si vous avez reporté les coûts d'acquisition et l'amortissement pour l'immobilisation à déplacer, ces valeurs seront regroupées dans l'immobilisation unique.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux reclassement immobilisation**, puis choisissez le lien associé.
2. Créez un journal reclassement dans lequel le champ **N° immo.** contient l'immobilisation à déplacer/combiner, et le champ **Nouveau N° immo.** contient l'immobilisation qui lui sera combinée.
3. Laissez le champ **Reclass. coût acq. %** vide pour déplacer/regrouper le coût total de l'acquisition.  
4. Cochez les deux cases **Reclass. coût acq.** et **Reclass. amortissement**.
5. Sélectionnez l'action **Reclasser**.

    Deux lignes sont maintenant créées dans le journal GL immobilisation à l'aide du modèle et du lot que vous avez indiqués sur la page **Configuration journal immo.** pour le registre amortissement sélectionné. Pour en savoir plus, voir [Configurer l'amortissement d'immobilisation](fa-how-setup-depreciation.md).   
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux GL immobilisation**, puis choisissez le lien associé.
7. Sur la page **Journal GL immo.**, sélectionnez l'action **Reporter** pour reporter le reclassement que vous avez effectué aux étapes 2 à 5.

## Pour afficher les valeurs du registre amortissement modifiées en raison d'un reclassement immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Valeur comptable 02 de l’immobilisation**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.  

## Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
