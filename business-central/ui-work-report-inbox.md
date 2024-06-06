---
title: Partager et exporter des rapports avec la boîte de réception Rapport
description: 'Utilisez la page Boîte de réception Rapport pour télécharger, partager et exporter des rapports dans Business Central.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'task, process, report, print, schedule, save, Excel, PDF, dataset, export, report inbox, onedrive,'
ms.search.form: 680
ms.date: 08/08/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Partager et exporter des rapports avec la boîte de réception Rapport

La page **Boîte de réception Rapport** répertorie les rapports programmés générés par l’utilisateur dans [!INCLUDE[prod_short](includes/prod_short.md)], et peut être utilisée non seulement pour accéder aux rapports générés, mais également pour partager et ouvrir des fichiers dans OneDrive for Business.

> [!TIP]
> Les actions suivantes sont également disponibles dans la partie **Boîte de réception rapport** dans le tableau de bord. Si la pièce ne s’affiche pas dans votre interface, découvrez comment personnaliser votre tableau de bord ici : [Personnaliser votre espace de travail](ui-personalization-user.md).

## Télécharger les rapports générés

Pour enregistrer les rapports précédents, ouvrez la page **Boîte de réception rapport** en suivant ces étapes :

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Boîte de réception rapport**, puis choisissez le lien associé.  
2. Sur la page **Boîte de réception rapport**, choisissez le rapport souhaité.

> [!NOTE]
> La page ne répertorie pas les rapports précédents générés à l’aide de l’action **Imprimer** ou enregistrés sous forme de fichier dans le menu **Rapports**.
>
> Les fichiers générés sont enregistrés dans le format défini lors de la programmation du rapport et peuvent être modifiés sur la page **Écritures file d’attente des travaux**, ainsi que la récurrence et d’autres paramètres. Pour savoir comment modifier le format du fichier de rapport et définir des options supplémentaires, voir [Gérer les rapports récurrents programmés](ui-work-report.md#manage-scheduled-recurring-reports).

## Ouvrir les rapports générés dans OneDrive

Pour exporter le fichier de rapport vers Microsoft OneDrive for Business, sélectionnez le rapport sur la page **Boîte de réception rapport** et choisissez l’action **Ouvrir dans OneDrive**. Le rapport est ensuite copié dans le dossier [!INCLUDE[prod_short](includes/prod_short.md)] dans OneDrive et ouvert dans une nouvelle fenêtre de navigateur, où vous pouvez imprimer et gérer le fichier du document.

> [!IMPORTANT]
>
> Les rapports devant expirer sur la page **Programmer un rapport** et copiés dans OneDrive ne sont pas automatiquement supprimés du dossier partagé.

## Partager les rapports programmés

Le partage de rapports avec des collaborateurs est également possible sur la page **Boîte de réception rapport**. Sélectionnez le rapport et choisissez l’action **Partager**. Sur la page **Envoyer un lien**, sélectionnez qui peut ouvrir le fichier, définissez les autorisations de modification, puis choisissez **Envoyer** pour envoyer un lien pour accéder au rapport enregistré.

> [!NOTE]
> En apprendre davantage sur l’intégration OneDrive et les fonctionnalités sur [!INCLUDE[prod_short](includes/prod_short.md)], y compris la configuration initiale et les options permettant de gérer les conflits de noms de fichiers, lisez l’article [Ouverture et partage de fichiers dans OneDrive](across-share-onedrive.md).
>
> Utiliser l’action **Partager** rend le fichier de rapport généré accessible aux autres utilisateurs uniquement sur OneDrive for Business et ne répertorie pas le rapport programmé sur leur **Boîte de réception Rapport**.

## Voir aussi .

[Exécuter et imprimer des rapports](ui-work-report.md)  
[Rapports disponibles dans [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
[Utilisation des rapports dans le travail quotidien](reports-use-reports.md)  
[Vue d’ensemble de Business Intelligence et de la génération de rapports](reports-bi-reporting.md)  
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Utiliser les dates civiles et les heures](ui-enter-date-ranges.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Intégration de [!INCLUDE[prod_short](includes/prod_short.md)] et de OneDrive](across-onedrive-overview.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
