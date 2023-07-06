---
title: Passer à une autre compagnie ou un autre environnement
description: 'Si vous travaillez pour plusieurs organisations, vous pouvez rapidement passer d''un environnement et d''une compagnie à l''autre.'
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: 'environments, companies, tenants, organization'
ms.search.form: '9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017'
ms.date: 08/16/2022
ms.author: bholtorf
---

# <a name="switching-to-another-company-or-environment"></a><a name="switching-to-another-company-or-environment"></a><a name="switching-to-another-company-or-environment"></a>Passer à une autre compagnie ou un autre environnement

[!INCLUDE [prod_short](includes/prod_short.md)] est disponible dans de nombreux pays différents et prend en charge de nombreux types d’organisations. Votre organisation peut choisir d’organiser le travail dans [!INCLUDE [prod_short](includes/prod_short.md)] en plusieurs *compagnies* et *environnements*. Cet article vous aide à comprendre les principales différences et à les surmonter.

## <a name="about-companies-and-environments"></a><a name="about-companies-and-environments"></a><a name="about-companies-and-environments"></a>À propos des compagnies et environnements

[!INCLUDE [company_environment](includes/company_environment.md)]

> [!TIP]
> Si vous changez souvent de compagnie ou utilisez [!INCLUDE[prod_short](includes/prod_short.md)] depuis une autre application comme Microsoft Teams, vous pouvez facilement perdre de vue où vous êtes. Pour vous aider à garder le fil, vous pouvez ajouter un badge qui affichera le nom de la compagnie, afin que vous puissiez rapidement vérifier que vous êtes au bon endroit. Pour en savoir plus, voir [Afficher un badge de compagnie](admin-company-information.md#badge).
> 
> Selon votre navigateur, vous pouvez également épingler les différentes compagnies à votre barre de favoris.  

<!--
[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]-->

## <a name="features-for-switching-company-or-environment"></a><a name="features-for-switching-company-or-environment"></a><a name="features-for-switching-company-or-environment"></a>Fonctionnalités pour basculer d’une compagnie à une autre ou d’un environnement à un autre

Il existe quelques fonctionnalités que vous pouvez utiliser pour changer de compagnie ou d’environnement pendant que vous travaillez. Le tableau suivant compare les capacités de la fonctionnalité, qui sont expliquées plus en détail dans les sections qui suivent.

|Fonctionnalité|Changer de compagnie|Changer d’environnement|Basculer dans le nouvel onglet du navigateur| Disponible en local|
|-------|--------------|------------------|-------------------------|----------------------|
|[Sélecteur de compagnie](#use-the-company-switcher)|![coche](media/check.png "coche")|![coche](media/check.png "coche")|![coche](media/check.png "coche")|![coche](media/check.png "coche")|
|[Lanceur d’application](#use-the-app-launcher)||![coche](media/check.png "coche")|![coche](media/check.png "coche")||
|[Mes paramètres](#use-my-settings)|![coche](media/check.png "coche")|||![coche](media/check.png "coche")|
|[Hub Entreprise](#use-company-hub)|![coche](media/check.png "coche")|![coche](media/check.png "coche")|![coche](media/check.png "coche")||

## <a name="use-the-company-switcher"></a><a name="use-the-company-switcher"></a><a name="use-the-company-switcher"></a>Utiliser le sélecteur de compagnie

L’utilisation du sélecteur de compagnie est probablement le moyen le plus rapide et le plus polyvalent de changer de compagnie. Le sélecteur de compagnie est un volet facilement accessible depuis n’importe quelle page. Le volet donne un aperçu de toutes les compagnies dans tous les environnements auxquels vous avez accès et vous permet de passer directement à l’une d’entre elles&mdash; soit dans le même onglet du navigateur, soit dans un nouveau. C’est particulièrement utile lorsque vous travaillez dans de nombreuses compagnies dans différents environnements.

1. Dans le coin supérieur droit, près de l’icône de recherche, vous voyez l’icône standard de la compagnie, comme ![Lanceur icône de la compagnie.](media/ui-experience/company-icon.png "Affiche l’icône de changement de compagnie utilisée lorsqu’il n’y a qu’un seul environnement") et ![company-icon-mult-env](media/ui-experience/company-icon-multi-env.png "Affiche l’icône de changement de compagnie utilisée lorsqu’il y a plusieurs environnements"), ou un [badge personnalisé](admin-company-information.md#badge) pour la compagnie avec laquelle vous travaillez actuellement. Sélectionnez l’icône pour ouvrir le volet de changement de compagnie.

   :::image type="content" source="media/ui-experience/company-switch-2.png" alt-text="Affiche l’icône de changement de compagnie dans l’en-tête du client Business Central.":::  

   > [!TIP]
   > Vous pouvez également utiliser le raccourci clavier <kbd>Crtl</kbd>+<kbd>O</kbd> pour ouvrir le volet.
2. Dans le volet **Compagnies disponibles**, sélectionnez la compagnie vers laquelle vous souhaitez basculer, sélectionnez la flèche **Changer**, puis choisissez l’une des options suivantes :

   |Option|Désignation|
   |------|-----------|
   |Basculer|Ouvre le tableau de bord de la compagnie sélectionnée dans le même onglet de navigateur que celui dans lequel vous travaillez. La compagnie devient la compagnie par défaut qui s’ouvre dans Business Central, jusqu’à ce que vous changiez à nouveau ou que vous changiez de compagnie à l’aide de **Mes paramètres**. |
   |Ouvrir dans un nouvel onglet|Ouvre le tableau de bord de la compagnie sélectionnée dans un nouvel onglet du navigateur, en gardant la compagnie d’origine ouverte dans l’autre onglet.|
   |Ouvrir dans un nouvel onglet et accéder à la même page|Cette option n’est active que sur les pages de liste, comme les clients, les documents de vente ou les articles. Elle ouvre la même liste, mais pour la compagnie sélectionnée, dans un nouvel onglet du navigateur. |

> [!TIP]
> Appuyez sur <kbd>F5</kbd> pour actualiser la liste des environnements et des compagnies.

## <a name="use-the-app-launcher"></a><a name="use-the-app-launcher"></a><a name="use-the-app-launcher"></a>Utiliser le lanceur d’application

Lorsque vous êtes connecté à [!INCLUDE[prod_short](includes/prod_short.md)], les environnements auxquels vous pouvez accéder sont disponibles sur le site Office.com.  

1. Sélectionnez l’icône **Lanceur d’applications** ![Lanceur d’applications.](media/app-launcher-icon.png "Le lanceur d'applications donne accès à plus de fonctionnalités").
2. Dans le volet qui s’ouvre, recherchez et sélectionnez [!INCLUDE[prod_short](includes/prod_short.md)]. Si vous ne voyez pas [!INCLUDE[prod_short](includes/prod_short.md)], choisissez **Toutes les applications**, puis saisissez **Business Central** dans la zone de **recherche**.

   :::image type="content" source="media/app-launcher-bc-tile.png" alt-text="Lanceur d'applications Microsoft 365 affichant la vignette Business Central.":::  

3. S’il existe plusieurs environnements, il vous sera demandé de choisir l’environnement auquel accéder.

<!--
The following image shows tiles for accessing production and sandbox environments on the Dynamics 365 Home page.

:::image type="content" source="media/app-picker-environments.png" alt-text="The Dynamics 365 Home page showing production and sandbox environments.":::
-->
## <a name="use-my-settings"></a><a name="use-my-settings"></a><a name="use-my-settings"></a>Utiliser Mes paramètres

Lorsque vous êtes connecté à [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez rapidement passer à une autre compagnie dans le même environnement. Après avoir effectué le changement, la compagnie que vous choisissez devient votre compagnie par défaut et s’ouvrira la prochaine fois que vous vous connecterez.

1. Dans le coin supérieur droit, sélectionnez l’icône **Paramètres** ![Paramètres.](media/ui-experience/settings_icon_small.png "Icône Paramètres du tableau de bord"), puis choisissez l’action **Mes paramètres**.

    > [!TIP]
    > Vous pouvez également utiliser le raccourci clavier <kbd>Alt</kbd>+<kbd>T</kbd> pour ouvrir rapidement la page Mes paramètres.

2. Sur la page **Mes paramètres**, dans le champ **Compagnie**, sélectionnez la compagnie.  
3. Choisissez le bouton **OK**.

> [!TIP]
> Une bonne façon d'aller directement à votre compagnie par défaut lorsque vous vous connectez et d'éviter d'avoir à spécifier un environnement consiste à ajouter l'URL à votre liste de favoris après vous être connecté.

## <a name="use-company-hub"></a><a name="use-company-hub"></a><a name="use-company-hub"></a>Utiliser le Hub Entreprise

*Hub Entreprise* est un tableau de bord hautement spécialisé qui donne un aperçu financier de toutes les compagnies et de tous les environnements. Disponible en tant qu’[extension](ui-extensions-company-hub.md), le hub Entreprise fournit un tableau de bord avec des données récapitulatives pour chaque compagnie à laquelle vous avez accès. La page d’accueil affiche les KPI financiers ainsi qu’un lien direct vers les différents environnements et compagnies. Pour plus d’informations, voir [Gérer le travail entre plusieurs compagnies dans le Hub Entreprise](company-hub.md).

[![Affiche la page Hub Entreprise qui répertorie toutes les compagnies.](media/company-hub.png)](media/company-hub.png#lightbox)  

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi .

[Création de compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)]](about-new-company.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Environnements et compagnies (en anglais uniquement)](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology)  
[Informations compagnie](admin-company-information.md)  
[Centre d'administration Business Central](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
