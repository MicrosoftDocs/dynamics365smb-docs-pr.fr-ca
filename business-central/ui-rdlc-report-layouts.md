---
title: Utilisation des présentations RDLC
description: Obtenez une introduction aux présentations de rapport RDLC.
author: jswymer
ms.topic: conceptual
ms.service: dynamics-365-business-central
ms.search.keywords: 'customized report, document layout, logo, personalize'
ms.search.form: '9650, 9652'
ms.date: 12/04/2023
ms.author: jswymer
ms.reviewer: jswymer
---
# <a name="working-with-rdlc-layouts"></a>Utilisation des présentations RDLC

Les présentations RDLC sont basées sur les fichiers de présentation de définition de rapport (types de fichier .rdl ou .rdlc). Les concepts de présentations RDLC sont similaires à ceux des autres types de présentations. La présentation détermine les champs à afficher et la façon dont ils sont disposés. Toutefois, la conception de présentations RDLC est plus avancée que celles de Word et Excel.

[![Affiche les différents éléments d’une présentation RDLC.](media/rdlc-layout.png)](media/rdlc-layout.png#lightbox)

## <a name="required-tools"></a>Outils requis

Pour modifier les présentations RDL, vous pouvez utiliser soit Microsoft SQL Server Report Builder, soit Microsoft Visual Studio avec l’extension RDLC Report Designer.

- Report Builder est une application autonome installée sur votre ordinateur par vous ou un administrateur. Avec Business Central sur site, Report Builder est automatiquement installé avec l’installation de Business Central Server. Pour plus d’informations sur l’installation de Report Builder, voir [Installer Report Builder](/sql/reporting-services/install-windows/install-report-builder) dans la documentation de SQL Server.

- RDLC Report Designer est une extension pour Visual Studio 2019 et versions ultérieures. Vous pouvez télécharger et installer RDLC Report Designer à partir de [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftRdlcReportDesignerforVisualStudio-18001).

## <a name="create-and-modify-rdlc-layouts"></a>Créer et modifier des présentations RDLC

La création et la modification des présentations RDLC est une tâche avancée, qui est généralement effectuée par des utilisateurs expérimentés ou des développeurs. Les concepts de base ne sont pas spécifiques aux présentations de rapport Business Central. C’est pourquoi, nous vous renvoyons à la documentation suivante :

- [Créer une présentation de rapport RDL](/dynamics365/business-central/dev-itpro/developer/devenv-howto-rdl-report-layout)

   Cet article explique comment créer une présentation de rapport RDLC à partir du code AL.

- [Rapports, parties de rapports et définitions de rapport ](/sql/reporting-services/report-design/reports-report-parts-and-report-definitions-report-builder-and-ssrs?)

   Ces liens vous renvoient à la documentation de SQL Server rapport Services pour RDL/RDLC. Cet article explique les concepts de RDL/RDLC et comment utiliser Report Builder.

> [!NOTE]
> Report Builder ne reconnaît que le type de fichier .rdl, pas .rdlc. Les fichiers de présentation exportés depuis Business Central sont des types de fichiers .rdlc. Donc, pour modifier ces présentations dans Report Builder, renommez le type de fichier en .rdl.

## <a name="see-also"></a>Voir aussi

[Gestion des présentations de rapport](ui-manage-report-layouts.md)  
[Définition de la disposition utilisée par un rapport](ui-set-report-layout.md)  
[Bien démarrer avec la création de présentations de rapport](ui-get-started-layouts.md)  
[Utilisation des rapports, des traitements en lot et des objets XMLport](ui-work-report.md)  
[Veille économique](bi.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Analyse des données de rapport avec Excel](report-analyze-excel.md).

[!INCLUDE[footer-include](includes/footer-banner.md)]
