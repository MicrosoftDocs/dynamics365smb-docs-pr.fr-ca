---
title: Gérer les paramètres enregistrés pour les rapports et les traitements en lot
description: Décrit comment l’administrateur peut configurer des options et des filtres prédéfinis pour un rapport et partager ces paramètres avec un ou tous les utilisateurs.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'customization, personalization'
ms.date: 12/21/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Gérer les paramètres enregistrés pour les rapports et les traitements en lot

Lors de l'exécution d'un rapport, les utilisateurs voient généralement une page qui leur permet de sélectionner des options et de définir des filtres pour modifier les données incluses dans le rapport généré. Cette page est appelée la *page de demande*. Un rapport peut inclure un ou plusieurs *paramètres enregistrés* que les utilisateurs peuvent appliquer au rapport à partir de la page de demande. Les *Paramètres enregistrés* sont essentiellement des options et des filtres prédéfinis. Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates. Pour plus d’informations, voir [Utiliser les paramètres enregistrés](ui-work-report.md#SavedSettings).

> [!NOTE]
> Cette rubrique fait référence aux *rapports*, mais des informations similaires s’appliquent aux *traitements en lot*.

Si vous avez les bonnes autorisations, vous pouvez visualiser, créer et modifier les paramètres enregistrés pour tous les rapports pour tous les utilisateurs d'une compagnie. Vous pouvez attribuer les paramètres enregistrés d'un rapport à des utilisateurs en particulier ou à tous les utilisateurs de la compagnie.

## Gérer les paramètres enregistrés

Vous devez gérer les paramètres enregistrés à partir de la page **Paramètres des rapports**. Deux méthodes sont disponibles pour ouvrir cette page :

- Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Paramètres du rapport**, puis choisissez le lien associé.
- Sur la page de demande d’un rapport, sélectionnez la fonction de recherche dans le champ **Utiliser les valeurs par défaut de**, puis choisissez l’action **Sélectionner dans la liste complète**.

    Ce champ n’est visible que si vous avez exécuté le rapport au moins une fois auparavant. La liste n’affichera que les paramètres qui sont disponibles pour vous, soit parce qu’il s’agit de vos propres paramètres, soit parce que les paramètres sont partagés avec vous.

La page **Paramètres du rapport** affiche toutes les entrées de paramètres enregistrés existants pour tous les utilisateurs. Si un nom d'utilisateur est indiqué dans le champ **Affecté à**, seul cet utilisateur peut utiliser les paramètres enregistrés pour le rapport associé. Si le champ **Partager avec tous les utilisateurs** est coché, tous les utilisateurs peuvent utiliser les paramètres enregistrés pour le rapport.  

> [!TIP]
> Lorsqu’un utilisateur a exécuté un rapport qui prend en charge les paramètres partagés, ses paramètres sont enregistrés et ajoutés à cette liste. Dans la plupart des cas, l’administrateur peut ensuite modifier ces paramètres et choisir de partager les paramètres avec tous les utilisateurs.
>
> Cependant, dans certains cas, les paramètres ne peuvent pas être partagés et l’administrateur ne peut pas non plus les modifier. La plupart des traitements en lot ne prennent pas en charge les paramètres partagés.  

## Créer ou modifier les paramètres enregistrés pour tous les utilisateurs

Dans la page **Paramètres du rapport**, vous pouvez :

- Sélectionner l'action **Nouveau** pour créer une nouvelle entrée de paramètres enregistrés.
- Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir l'action **Copier** pour créer une copie.
- Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir l'action **Modifier** pour la modifier.

> [!Important]
> Définir le nom que vous souhaitez affecter à une entrée de paramètres enregistrés. Si vous créez une entrée de paramètres enregistrés pour tous les utilisateurs et vous lui donnez le même nom que l'entrée de paramètres enregistrés existants qui est affectée à un utilisateur spécifique, alors cet utilisateur ne pourra pas utiliser l'entrée de paramètres enregistrés qui est affectée à tous.  Dans la section **Paramètres enregistrés** dans la page de demande de l'état, l'utilisateur verra deux entrées de paramètres enregistrés avec le même nom. Toutefois, peu importe l'option qu'il choisit, l'entrée de paramètres enregistrés qui lui est spécifique sera utilisée.

> [!NOTE]
> La possibilité d’enregistrer les paramètres n’est disponible que pour les rapports où la [propriété SaveValues](/dynamics365/business-central/dev-itpro/developer/properties/devenv-savevalues-property) de la page de demande du rapport est définie sur **Oui**. La propriété **SaveValues** est définie par le développeur.  

## Voir aussi

[Utiliser des rapports, des traitements en lot et des XMLports](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]