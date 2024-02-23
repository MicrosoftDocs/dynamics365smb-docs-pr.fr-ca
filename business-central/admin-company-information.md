---
title: Présentation des informations sur la compagnie
description: 'La page Informations compagnie spécifie les informations de base d’une entité commerciale, telles que le nom, les adresses et les informations d’expédition.'
author: jswymer
ms.topic: conceptual
ms.search.form: 1
ms.date: 09/24/2023
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Présentation des informations sur la compagnie

[!INCLUDE[prod_short](includes/prod_short.md)] organise les entités commerciales en *compagnies*. Pour chaque compagnie, vous devez remplir certains des détails de base et des informations pertinentes sur la page **Informations compagnie**. Les informations de la page [**Informations compagnie**](https://businesscentral.dynamics.com/?page=1) sont utilisées dans des documents, tels que les en-têtes facture. Vous pouvez paramétrer plusieurs compagnies, par exemple une compagnie mère et une filiale.  

Si les entrepôts de la compagnie sont situés à une adresse différente du siège social, vous pouvez renseigner les divers champs destinataire et le champ **Code emplacement** du raccourci **Expédition**. Les informations de ces champs sont alors imprimées sur les bons de commande, afin que les livraisons soient effectuées à la bonne adresse.  

Pour chaque compagnie que vous configurez, vous devez renseigner la page **Informations compagnie**, ainsi que la page **Configuration du grand livre**. Vous devez également configurer chaque zone dans [!INCLUDE [prod_short](includes/prod_short.md)], comme la page **Configuration ventes**, pour chaque compagnie. Pour plus d’informations, consultez [Aperçu des tâches permettant de paramétrer [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md).  

En fonction de votre pays/région, la page **Informations compagnie** contient différents champs et raccourcis. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Le tableau suivant décrit les raccourcis les plus couramment utilisés.

[!INCLUDE [admin-company-info-fasttabs](includes/admin-company-info-fasttabs.md)]

Une fois que vous avez terminé de remplir les informations, vous pouvez fermer la page.  

## Travailler avec plusieurs compagnies

Si votre [!INCLUDE [prod_short](includes/prod_short.md)] inclut plusieurs compagnies, vos utilisateurs souhaiteront peut-être utiliser des *badges de compagnie* pour identifier rapidement et suivre avec quelle compagnie ils travaillent actuellement. Pour en savoir plus, voir [Afficher un badge de compagnie](#badge).

Il existe quelques fonctionnalités que vous pouvez utiliser pour changer de compagnie, comme le sélecteur de compagnie (<kbd>Ctrl</kbd>+<kbd>O</kbd>). Pour en savoir plus, voir [Passer à une autre compagnie ou un autre environnement](ui-organization-switch.md).

## <a name="badge"></a>Afficher un badge de compagnie

Lorsqu’il y a plusieurs compagnies ou environnements, vous verrez le sélecteur de compagnie sur le côté supérieur droit de la barre d’application, près de l’icône de recherche dans la barre d’application. Par défaut, le sélecteur de compagnie utilise une icône de compagnie standard, comme le ![Lanceur Icône de la compagnie.](media/ui-experience/company-icon.png "Affiche l’icône de changement de compagnie utilisée lorsqu’il n’y a qu’un seul environnement") et ![company-icon-mult-env](media/ui-experience/company-icon-multi-env.png "Affiche l’icône de changement de compagnie utilisée lorsqu’il y a plusieurs environnements").

:::image type="content" source="media/ui-experience/company-switch-2.png" alt-text="Affiche l’icône de changement de compagnie dans l’en-tête du client Business Central.":::  

À partir de la 2e vague de lancement 2023, version 23, le badge de la compagnie apparaît dans l’onglet du navigateur lors de l’utilisation du client Web. Il est également inclus dans les liens de pages que vous [copiez et collez](across-share-data-features.md#copying-a-link) dans des éditeurs de texte enrichi, comme Word, Outlook et Teams.
 
### Définir le badge de la compagnie

En utilisant la page **Informations sur la compagnie**, vous pouvez remplacer l’icône standard de la compagnie par un badge personnalisé pour chaque compagnie si le badge de compagnie permet aux utilisateurs d’identifier plus facilement la compagnie dans laquelle ils travaillent.

1. Sur le raccourci **Badge compagnie**, renseignez les champs, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
2. Cela fait, actualisez le navigateur (sélectionnez <kbd>Ctrl</kbd>+<kbd>F5</kbd>) pour mettre à jour le badge dans le client.  

> [!NOTE]
> Le sélecteur de compagnie a été introduit dans la 2e vague de lancement 2022, version 21. Dans les versions antérieures, le badge de compagnie n’était pas utilisé pour changer de compagnie. Il s’affiche dans le coin supérieur droit de la plupart des pages, même lorsqu’il n’y a qu’une seule compagnie. Le sélectionner affichera le nom complet de la compagnie et le nom de l’environnement.

## Modifier le nom d’affichage de la compagnie

Le nom de la compagnie est toujours affiché dans le coin supérieur gauche et fonctionne comme une action que vous pouvez choisir pour revenir dans le Tableau de bord. Vous pouvez changer ce nom sur la page **Informations compagnie**.

1. Choisissez l’icône ![Pignon pour ouvrir le menu Paramètres.](media/ui-experience/settings_icon_small.png) puis choisissez l’action **Informations sur la compagnie**.
2. Dans le champ **Nom**, saisissez le nom de la nouvelle compagnie.
3. Quittez la page. Le système redémarre et affiche la nouvelle compagnie dans le coin supérieur gauche.

## Expérience

L’expérience utilisateur par défaut dans une version d’évaluation de [!INCLUDE [prod_short](includes/prod_short.md)] ne révèle pas toutes les fonctionnalités. Vous pouvez passer à l’expérience complète sur la page **Informations compagnie**.  

Pour plus d’informations, accédez à [Modifier les fonctionnalités affichées](ui-experiences.md).  

## Voir aussi .

[Aperçu des tâches permettant de paramétrer [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Démarrage rapide de Informations compagnie](quick-start-company-information.md)  
[Configurer les informations sur la compagnie en Italie](LocalFunctionality/Italy/how-to-set-up-company-information.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Création de compagnies](about-new-company.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
