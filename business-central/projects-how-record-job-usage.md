---
title: "Enregistrer l'utilisation facturable et budgétée des ressources de projet| Microsoft Docs"
description: "Décrit comment enregistrer la consommation ou l'utilisation des articles ou des ressources sur des projets pour faciliter la gestion de projets."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, consumption
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: f1b3864eadd616273c3a4a7d061623dab701d01e
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="record-usage-for-jobs"></a>Enregistrer l'utilisation pour les projets
Sur la page **Lignes planification projet**, vous pouvez consulter et enregistrer l'utilisation sur les différentes parties de votre projet, qui est automatiquement mis à jour lorsque vous modifiez et transférez des informations entre les projets et les journaux projet ou les factures projet. Cela suppose d'avoir paramétré un projet afin que **Appliquer le lien d'utilisation par défaut** soit activé. Pour plus d'informations, voir [Configuration de projets](projects-how-setup-jobs.md).  

Par exemple, pour les lignes planning de type **Budget**, vous pouvez saisir la quantité d'une ressource et indiquer la quantité à transférer vers la feuille projet. Si le type de la ligne planning est **Facturable**, vous pouvez saisir la quantité de la ressource et indiquer la quantité à transférer vers une facture. En comparant la quantité qui a été transférée vers le journal ou la facture avec la quantité restante, vous pouvez rapidement vérifier les informations sur l'utilisation.

Les procédures suivantes décrivent comment enregistrer les prix et les coûts réels (facturables) ou budgétés du projet. Pour plus d'informations sur l'estimation des valeurs budgétées lors de la planification, voir [Gérer les budgets de projets](projects-how-manage-budgets.md).

## <a name="to-record-usage-for-a-job-planning-line-of-type-budget"></a>Pour enregistrer l'utilisation d'une ligne planification projet de type Budget
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projets**, puis sélectionnez le lien associé.  
2. Sélectionnez le projet concerné, puis cliquez sur **Lignes planning projet**.
3. Sélectionnez une ligne planning projet de type **Budget** ou **Budget et Facturable** pour laquelle vous voulez enregistrer une activité.
4. Dans le champ **Qté à transférer sur la feuille**, entrez le nombre que vous souhaitez transférer vers la facture. La quantité par défaut est la même valeur que celle du champ **Quantité**.

    Le champ **Quantité restante** indique la quantité qui reste pour terminer le projet et à transférer à la feuille.  
5. Choisissez l'action **Créer des lignes feuille projet**.
6. Sur la page **Projet Transférer la ligne planification projet**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Cliquez sur **Ouvrir la feuille projet**.  
8. Sur la page **Journal projet**, sélectionnez la ligne appropriée, puis cliquez sur **Reporter**.
9. Sur la page **Lignes planification projet**, examinez l'utilisation enregistrée en observant les champs **Quantité**, **Quantité restante** et **Qté à transférer sur le journal**.  
10. Répétez les phases 3 à 8 pour enregistrer l'utilisation supplémentaire.  

## <a name="to-record-usage-for-a-job-planning-line-of-type-billable"></a>Pour enregistrer l'utilisation d'une ligne planification projet de type Facturable
Dans la tâche suivante, vous devez aussi enregistrer l'activité, mais pour une ligne planning projet de type **Facturable**. En général, dans ce cas, vous facturez votre utilisation, mais vous pouvez également la transférer vers un journal. Néanmoins, lorsque vous faites cela, une ligne planning projet de type **Budget** est créée pour correspondre à la ligne facturable. Pour en savoir plus, voir [Gérer les budgets de projets](projects-how-manage-budgets.md).

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projets**, puis sélectionnez le lien associé.
2. Sélectionnez le projet concerné, puis cliquez sur **Lignes planning projet**.  
3. Sélectionnez une ligne planning projet de type **Facturable** pour laquelle vous voulez enregistrer une activité.
4. Dans le champ **Qté à transférer à facturer**, entrez le nombre que vous souhaitez transférer vers la facture. La quantité par défaut est la même valeur que celle du champ **Quantité**.

    Le champ **Quantité à facturer** indique la quantité restante pour terminer le projet et qui doit être facturée.  
5. Cliquez sur **Créer facture vente**.
6. Sur la page **Projet Transférer vers facture vente**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.
7. Sur la page **Lignes planification projet**, sélectionnez la ligne appropriée, puis cliquez sur **Reporter**.
8. Examinez l'activité enregistrée en observant les champs **Quantité**, **Quantité à facturer**, **Qté à transférer à facturer** et vérifiez si la facture vente est validée, ainsi que les champs **Qté facturée**.
9. Répétez les phases 3 à 8 pour enregistrer l'utilisation supplémentaire.  
10. Pour passer en revue une facture vente validée associée, cliquez sur **Avoirs/Factures vente**.  
11. Sur la page **Factures projet**, sélectionnez la facture appropriée et cliquez sur **Ouvrir la facture vente/note de crédit**.         

## <a name="to-create-job-journal-lines-from-job-planning-lines"></a>Pour créer des lignes journal projet à partir de lignes planification projet
Lorsque vous êtes prêt à reporter les données financières pour les projets, vous devez créer des lignes journal projet que vous pouvez reporter.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projets**, puis sélectionnez le lien associé.  
2. Sélectionnez un projet concerné, puis cliquez sur **Lignes planning projet**.  
3. Sur la page **Lignes planification projet**, sur la ligne planification projet souhaitée, dans le champ **Qté à transférer sur le journal**, entrez la quantité que vous souhaitez transférer vers un journal projet.  
4. Choisissez l'action **Créer des lignes feuille projet**.
5. Sur la page **Projet Transférer la ligne planification projet**, renseignez les champs selon vos besoins.  
6. Cliquez sur le bouton **OK**. Des lignes journal projet sont créées.
7. Pour vérifier le transfert, ouvrez le lot journal projet approprié et vérifiez les écritures.  
8. Lorsque les lignes feuilles projets sont renseignées, cliquez sur **Valider**.  

## <a name="to-create-job-journal-lines-manually"></a>Pour créer des lignes journal projet manuellement
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux projet**, puis sélectionnez le lien associé.  
2. Dans le champ **Nom de la feuille**, choisissez un nom de feuille projet approprié.  
3. Dans une nouvelle ligne, entrez le numéro de document, le numéro de projet, le numéro tâche projet, le type et la quantité du type consommé.  
4. Lorsque les lignes feuilles projets sont renseignées, cliquez sur **Valider**.  

## <a name="to-review-planning-lines-for-a-job-ledger-entry"></a>Pour consulter les lignes planification pour une écriture projet
Après avoir reporté les lignes journal projet, vous pouvez voir les lignes planification associées aux écritures journal projet qui ont été reportées.

> [!NOTE]  
>   Cela nécessite que le champ **Appliquer le lien d'utilisation par défaut** ait été sélectionné pour le projet, ou qu'il s'agisse de la configuration par défaut pour tous les projets de votre organisation. Pour plus d'informations, voir [Configuration de projets](projects-how-setup-jobs.md).  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux projet**, puis sélectionnez le lien associé.  
2. Sélectionnez une feuille projet appropriée, puis cliquez sur **Écritures comptables**.  
3. Sur la page **Écritures projet**, cliquez sur **Afficher les lignes planification projet liées**.

## <a name="see-also"></a>Voir aussi
[Gestion de projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Achats](purchasing-manage-purchasing.md)         
[Ventes](sales-manage-sales.md)      
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

