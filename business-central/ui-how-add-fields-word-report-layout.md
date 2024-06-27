---
title: "Procédure\_: ajouter des champs à une présentation de rapport Word"
description: Cette rubrique décrit comment ajouter des champs d’un ensemble de données de rapport à une présentation de rapport Word existante pour un rapport.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 01/25/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
---

# <a name="work-with-word-layouts"></a>Utiliser des présentations Word

Une présentation de rapport Word détermine le contenu et le format d’un rapport lorsqu’il est prévisualisé et imprimé à partir de Business Central. Vous devez créer et modifier ces présentations à l’aide de Microsoft Word.

[![Exemple de document de présentation de rapport Word pour Business Central.](media/word-layout.png)](media/word-layout.png#lightbox) 

Lorsque vous modifiez une présentation de rapport Word, vous devez spécifier les champs du jeu de données de rapport à inclure dans le rapport et la manière dont les champs sont organisés. Vous devez également définir le format général du rapport, tel que la police et la taille du texte, les marges et les images d’arrière-plan. Vous devez en général organiser le contenu du rapport en ajoutant des tableaux à la mise en page.

Pour apporter des modifications générales de mise en forme et de disposition (par exemple modifier la police texte, ajouter et modifier un tableau ou supprimer un champ de données), utilisez les fonctions de base d'édition de Word, tout comme vous le faites avec n'importe quel document Word.

Si vous créez une présentation de rapport Word de A à Z ou en ajoutant de nouveaux champs de données, commencez par ajouter un tableau comprenant des lignes et colonnes qui finiront par contenir les champs de données.

> [!TIP]  
> Affiche les quadrillages de façon à visualiser les contours des cellules de la table. Pensez à masquer les quadrillages lorsque vous avez terminé l’édition. Pour masquer ou afficher des quadrillages dans la table, sélectionnez la table, puis sous **Mise en page** sous l'onglet **Table**, sélectionnez **Afficher les quadrillages**.

## <a name="embedding-fonts-in-word-layouts-for-consistency"></a>Incorporation de polices dans des présentations Word pour des raisons de cohérence

Pour vous assurer que les rapports affichent et impriment toujours avec les polices prévues, quel que soit l’emplacement où les utilisateurs ouvrent ou impriment des rapports, vous pouvez incorporer des polices au document Word. Toutefois, sachez qu’incorporer des polices peut augmenter de façon significative la taille des fichiers Word. Pour plus d'informations sur l'incorporation de polices à Word, voir [Incorporer des polices à Word, PowerPoint ou Excel](https://support.office.com/article/Embed-fonts-in-Word-PowerPoint-or-Excel-cb3982aa-ea76-4323-b008-86670f222dbc).

## <a name="adding-data-fields"></a>Ajout de champs de données

Un ensemble de données de rapport peut être constitué de champs affichant des étiquettes, des données et des images. Cette rubrique décrit la procédure pour ajouter des champs d'un ensemble de données de rapport à une présentation de rapport Word pour un rapport. Vous ajoutez des champs à l'aide du composant XML personnalisé Word pour le rapport et en ajoutant des contrôles de contenu qui correspondent aux champs de l'ensemble de données de rapport. L'ajout de champs requiert que vous ayez des connaissances sur l'ensemble des données de rapport afin que vous puissiez identifier les champs que vous souhaitez ajouter à la présentation.  
  
> [!NOTE]  
>  Vous ne pouvez pas modifier les présentations de rapport intégrées<!--Onprem. Built-in layouts can only be modified by using the development environment-->.  

### <a name="to-open-the-custom-xml-part-for-the-report-in-word"></a><a name="OpenXMLPart"></a>Pour ouvrir le composant XML personnalisé du rapport dans Word
  
1. Si ce n'est pas déjà le cas, ouvrez le document de présentation de rapport Word dans Word.  
  
     Pour plus d'informations, voir [Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md).  
  
2. Afficher l'onglet **Développeur** dans le ruban de Microsoft Word.  
  
     Par défaut, l'onglet **Développeur** n'est pas affiché dans le ruban. Pour plus d’informations, voir [Afficher l’onglet Développeur sur le ruban](/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon).  
  
3. Sous l'onglet **Développeur**, sélectionnez **Volet de mappage XML**.  
  
4. Dans le volet **Mappage XML**, dans la liste déroulante **Partie XML personnalisée**, choisissez la partie XML personnalisée pour le rapport [!INCLUDE[prod_short](includes/prod_short.md)], qui est généralement le dernier de la liste. Le nom de la partie XML personnalisée présente le format suivant :  
  
     `urn:microsoft-dynamics-nav/reports/<report_name>/<ID>`  

     `<report_name>` représente le nom affecté au rapport. 

     `<ID>` représente le numéro d’identification du rapport.  
  
     Après avoir sélectionné la partie XML personnalisée, le volet de mappage XML affiche les étiquettes et les contrôles de champ disponibles pour le rapport.  
  
### <a name="to-add-a-label-or-data-field"></a>Pour ajouter un champ étiquette ou données
  
1. Placez votre curseur dans le document dans lequel vous souhaitez ajouter le contrôle.  
  
2. Dans le volet **Mappage XML**, cliquez avec le bouton droit sur le contrôle que vous souhaitez ajouter, sélectionnez **Insérer contrôle de contenu**, puis sélectionnez **Texte brut**.  
  
    > [!NOTE]  
    >  Vous ne pouvez pas ajouter un champ en tapant manuellement le nom du champ de l'ensemble de données dans le contrôle de contenu. Vous devez utiliser le volet **Mappage XML** pour mapper les champs.  
  
### <a name="to-add-repeating-rows-of-data-fields-to-create-a-list"></a>Pour ajouter des lignes à répétition des champs de données pour créer une liste
  
1. Dans un tableau, ajoutez une ligne de tableau incluant une colonne pour chaque champ dont vous souhaitez qu'il soit répété.  
  
   Cette ligne agira comme un espace réservé pour les champs de répétition.  
  
2. Sélectionnez toute la ligne.  
  
3. Dans le volet **Mappage XML**, cliquez avec le bouton droit sur le contrôle qui correspond à l'élément de données de rapport qui contient les champs que vous souhaitez voir répétés, sélectionnez **Insérer contrôle de contenu**, puis sélectionnez **Répéter**.  
  
4. Ajoutez les champs de répétition à la ligne comme suit :  
  
    1. Placez votre pointeur dans une colonne.  
  
    2. Dans le volet **Mappage XML**, cliquez avec le bouton droit sur le contrôle que vous souhaitez ajouter, sélectionnez **Insérer contrôle de contenu**, puis sélectionnez **Texte brut**.  
  
    3. Pour chaque champ, répétez les étapes a et b.  
  
## <a name="adding-image-fields"></a>Ajout de champs d’image

Un ensemble de données de rapport peut inclure un champ qui contient une image, par exemple un logo de la compagnie ou une photo d'un article. Pour ajouter une image de l'ensemble de données de rapport, vous insérez un contrôle de contenu **Image**.  
  
Les images s'alignent dans le coin supérieur gauche du contrôle de contenu et sont automatiquement redimensionnés proportionnellement conformément à la limite du contrôle de contenu.  
  
> [!IMPORTANT]  
> Vous ne pouvez ajouter que des images dont le format est pris en charge par Word (par ex., .bmp, .jpeg et .png). Si vous ajoutez une image dont le format n’est pas pris en charge par Word, vous obtenez une erreur lorsque vous exécutez le rapport à partir du client [!INCLUDE[prod_short](includes/prod_short.md)].  
  
### <a name="to-add-an-image"></a>Pour ajouter une image
  
1. Placez votre pointeur dans le document dans lequel vous souhaitez ajouter le contrôle.  
  
2. Dans le volet **Mappage XML**, cliquez avec le bouton droit sur le contrôle que vous souhaitez ajouter, sélectionnez **Insérer contrôle de contenu**, puis sélectionnez **Image**.  
  
3. Pour développer ou réduire la taille de l'image, faites glisser une poignée de redimensionnement pour l'éloigner ou la rapprocher du centre du contrôle de contenu.  

## <a name="removing-label-and-data-fields"></a><a name="RemoveField"></a>Suppression des champs d’étiquette et de données

L'étiquette et les champs de données d'un rapport sont contenus dans des contrôles de contenu dans Word. La figure ci-après illustre un contrôle de contenu lorsqu’il est sélectionné dans le document Word.  

![Contrôle de contenu d’un champ dans une présentation de rapport Word.](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  

Le nom de l'étiquette ou le nom du champ de données s'affiche dans le contrôle de contenu. Dans l'exemple, le nom du champ est CompanyAddr1.  

### <a name="to-remove-a-label-or-data-field"></a>Pour supprimer un champ étiquette ou données

1. Cliquez avec le bouton droit sur le champ que vous voulez supprimer, puis choisissez **Supprimer le contrôle de contenu**.  

     Le contrôle de contenu est supprimé, mais le nom du champ reste sous forme de texte.  

2. Supprimez le texte restant selon vos besoins.

## <a name="custom-xml-part-overview"></a>Aperçu des parties XML personnalisées

Les présentations de rapport Word sont basées sur des *parties XML personnalisées*. Une partie XML personnalisée pour un rapport regroupe des éléments qui correspondent aux éléments de données, colonnes et étiquettes comprenant l'ensemble de données du rapport. <!--OnPrem The data as defined in the Report Dataset Designer in Microsoft Dynamics NAV Development Environment. -->La partie XML personnalisée est utilisée pour associer les données dans un rapport lorsque le rapport est exécuté.

### <a name="xml-structure-of-custom-xml-part"></a>Structure XML du composant XML personnalisé

Le tableau suivant fournit un aperçu simplifié du XML d'une partie XML personnalisée.  
  
|Éléments XML|Description|  
|------------------|-----------------|  
|`<?xml version="1.0" encoding="utf-16"?>`|En-tête|  
|`<WordReportXmlPart xmlns="urn:microsoft-dynamics-365/report/<reportname>/<id>/"`|Spécification de l'espace de noms XML. `<reportname>` est le nom affecté au rapport. `<id>` est le code affecté au rapport.|  
|`..<Labels>`<br /><br /> `....<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<br /><br /> `....<LabelName>LabelCaption</LabelName>`<br /><br /> `..</Labels>`|Contient toutes les étiquettes pour le rapport.<!--OnPren The element includes labels that are related to columns that have the IncludeCaption Property.--><br />-   Les éléments d’étiquette associés aux colonnes sont au format `<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<!--OnPrem where `ColumnName` is determined by the column's Name Property.-->.<br />-  Les éléments d'étiquette sont au format `<LabelName>LabelName</LabelName`<!--OnPrem where LabelName is determined by the label's Name Property.-->.<br />-   Les étiquettes sont répertoriées par ordre alphabétique.|  
|`..<DataItem1>`<br /><br /> `....<DataItem1Column1>DataItem1Column1</DataItem1Column1>`|Données article et colonnes de haut niveau. Les colonnes sont répertoriées par ordre alphabétique.<!--OnPrem <br /><br /> The element names and values are determined by the Name Property of the data item or column.-->|  
|`....<DataItem2>`<br /><br /> `......<DataItem2Column1>DataItem2Column1</DataItem2Column1>`<br /><br /> `....</DataItem2>`<br /><br /> `....<DataItem3>`<br /><br /> `......<DataItem3Column1>DataItem3Column1</DataItem3Column1>`<br /><br /> `....</DataItem3>`|Les données article et colonnes imbriquées dans les données article de haut niveau. Les colonnes sont répertoriées par ordre alphabétique sous chaque donnée.|  
|`..</DataItem1>`<br /><br /> `</WordReportXmlPart>`|Élément de fermeture.|  
  
### <a name="custom-xml-part-in-word"></a>Partie XML personnalisée dans Word

 Dans Word, vous ouvrez la partie XML personnalisée dans le volet **Mappage XML** puis utilisez le volet pour mapper les éléments aux contrôles de contenu dans le document Word. Le volet **Mappage XML** est accessible depuis l’onglet **Développeur** (pour plus d’informations, voir [Afficher l’onglet Développeur sur le ruban](/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon)).  
  
 Les éléments figurant dans le volet de **Mappage XML** s'affichent dans une structure qui est similaire à la source XML. Les champs d'étiquette sont rassemblés sous un élément **Étiquettes** commun et les données article et colonnes sont organisées dans une structure hiérarchique qui correspond à la source XML, avec les colonnes répertoriées dans l'ordre alphabétique. Les éléments sont identifiés par leur nom de colonne tel que défini dans l’ensemble de données du rapport en code AL. Pour en savoir plus, consultez [Définition de l’ensemble de données du rapport](/dynamics365/business-central/dev-itpro/developer/devenv-report-dataset).  
  
 La figure ci-après illustre la partie XML personnalisée simple de la section précédente dans le volet **Mappage XML** d'un document Word.  
  
 ![Clip du volet Mappage XML dans Word.](media/nav_reportlayout_xmlmappingpane.png "NAV_ReportLayout_XMLMappingPane")  
  
* Pour ajouter une étiquette ou un champ à la présentation, vous insérez un contrôle de contenu qui correspond à l'élément dans le volet **Mappage XML**.  
  
* Pour créer des lignes de colonnes à répétition, insérez un contrôle de contenu **Répétition** pour l'élément d'article parent, puis ajoutez le contrôle de contenu pour les colonnes.  
  
* Pour les étiquettes, le texte qui apparaît dans le rapport généré est la valeur de la propriété **Légende** pour le champ dans le tableau données d'article (si l'étiquette est liée à la colonne dans l'ensemble des données de rapport) ou une étiquette dans le Générateur d'étiquettes de rapport (si l'étiquette n'est pas liée à une colonne dans l'ensemble de données).  
  
* La langue de l'étiquette qui s'affiche lorsque vous exécutez le rapport dépend du paramétrage de langue de l'objet de rapport.  
  
## <a name="see-also"></a>Voir aussi

[Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md)   


[!INCLUDE[footer-include](includes/footer-banner.md)]
