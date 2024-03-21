---
title: Démarrage rapide de la sortie de rapports et de documents de base
description: 'Business Central propose des modèles intégrés pour les rapports et les documents, avec de nombreuses options de personnalisation pour les adapter aux besoins de votre entreprise.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: quickstart
ms.search.form: null
ms.date: 08/15/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Démarrage rapide de la sortie de rapports et de documents de base

Pour adapter [!INCLUDE[prod_short](includes/prod_short.md)] aux besoins de votre entreprise, paramétrez et utilisez des rapports et des documents personnalisés adaptés aux processus et à l’identité visuelle de votre entreprise.

## Ajouter un logo d’entreprise aux documents

[!INCLUDE[prod_short](includes/prod_short.md)] possède des modèles définis pour utiliser le logo de votre entreprise pour vous faire gagner du temps en personnalisant des documents tels que des factures, des commandes et des relevés.

1. Choisissez l’icône ![Pignon pour ouvrir le menu Paramètres.](media/ui-experience/settings_icon_small.png) puis choisissez l’action **Informations compagnie**.
2. Sélectionnez l’action **Image**, puis sélectionnez **Choisir**.
3. Sélectionnez le fichier image sur votre appareil.

Vous pouvez voir les instructions ci-dessus dans [cette vidéo YouTube](https://www.youtube.com/watch?v=AatXbKF1NGg). Une fois l’image affichée dans le champ **Image**, vous pouvez fermer la page **Informations compagnie**.

## Exécuter des rapports

Les rapports organisent les informations provenant de différentes sources dans [!INCLUDE[prod_short](includes/prod_short.md)] et les présentent d’une manière lisible qui peut être facilement imprimée ou partagée numériquement. Les rapports peuvent être trouvés sur les pages auxquelles ils sont contextuellement associés. Par exemple, la page **Articles** répertorie les rapports liés aux niveaux d'inventaire, aux achats, aux ventes, etc.

1. Ouvrez la page associée au rapport demandé, comme la page **Articles**.
2. Choisissez le rapport **Inventaire : Palmarès articles** dans le menu **Rapports**.
3. Sur la page de demande de rapport, définissez des filtres pour affiner la plage de dates ou modifier l’unité de mesure de référence utilisée dans le rapport.
4. Choisissez l’action **Imprimer** et suivez les étapes d’impression de l’appareil.
    1. Sinon, sélectionnez l’action **Aperçu** pour afficher le rapport à l’écran.

Pour en savoir plus sur le filtrage des données, la planification des rapports et plus encore, voir [Exécuter et imprimer des rapports](ui-work-report.md).

## Enregistrer des rapports sous la forme de documents PDF, Excel ou Word

Pour partager rapidement des rapports, vous pouvez enregistrer des rapports [!INCLUDE[prod_short](includes/prod_short.md)] directement au format PDF, Microsoft Excel ou Microsoft Word.

1. Répétez les étapes 1 à 3 de la section [Exécuter des rapports](#run-reports) ci-dessus.
2. Sélectionnez l’action **Envoyer à**.
3. Sélectionnez le type de fichier et choisissez **OK**.
r Le fichier de rapport généré est automatiquement enregistré dans le dossier de téléchargement de votre navigateur.

### Modifier les présentations de rapport et de document

[!INCLUDE[prod_short](includes/prod_short.md)] est fourni avec de nombreuses présentations intégrées pour vos rapports et autres documents générés, tels que les factures vente. Vous pouvez utiliser des applications comme Microsoft Word ou Excel pour modifier les modèles de présentation des documents et des rapports, comme décrit dans l’exemple suivant :

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Présentations de rapport**, puis choisissez le lien associé.
2. Sur la page **Présentations de rapport**, sélectionnez l’action **Rechercher** pour sélectionner la présentation *StandardSalesInvoice.docx*, puis choisissez l’action **Exporter présentation** pour télécharger le fichier modèle de présentation.

    Un document Word est enregistré sur votre appareil, avec le même nom de fichier que celui affiché sur la page **Présentations de rapport**.
3. Ouvrez le fichier de mise en page dans Microsoft Word et modifiez le document, par exemple en déplaçant le champ de date (*Date du document*) ou votre logo, ou en modifiant la taille des polices, puis enregistrez le fichier.
4. De retour sur la page **Présentations de rapport**, sélectionnez l’action **Nouvelle présentation**.
5. Sur la page **Ajouter une nouvelle présentation pour un rapport**, entrez un nom et une description dans les champs **Nom de la présentation** et **Description**, respectivement, pour faciliter la recherche de la présentation.
6. Sélectionnez l’option **Mot** dans le champ **Options de format**, puis choisissez **OK**.
7. Sur la page **Choisir un fichier de disposition Word**, sélectionnez **Choisir** pour ouvrir le fichier de mise en page modifié sur votre appareil.
8. Testez la nouvelle présentation en choisissant l’action **Exécuter un rapport**.

Pour en savoir plus sur la personnalisation des rapports et des documents en fonction des besoins de votre entreprise, voir [Présentations des rapports et des documents](ui-manage-report-layouts.md).

## Voir aussi .

[Utilisation des rapports dans le travail quotidien](reports-use-reports.md)  
[Rapports disponibles dans [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
[Sélection de rapport de document](across-report-selections.md)  
[Démarrage rapide de Business Central](quick-start-business-central.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
