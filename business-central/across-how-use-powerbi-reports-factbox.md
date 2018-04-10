---
title: "Afficher des états Power BI personnalisés| Microsoft"
description: "Vous pouvez utiliser des états Power BI pour obtenir des informations supplémentaires sur les données dans les listes dans Financials."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 06/02/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: 49957527ab1b0217dab151463ccf983c5eeac7a1
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="viewing-list-data-in-power-bi-reports-in-business-central"></a>Affichage de données de liste dans des rapports Power BI dans Business Central 
[!INCLUDE[d365fin](includes/d365fin_md.md)] inclut un élément de contrôle Récapitulatif sur un certain nombre de pages Liste des clés fournissant des informations supplémentaires sur les données de la liste. Lorsque vous vous déplacez entre les lignes de la liste, le rapport est mis à jour et filtré pour l'écriture sélectionnée. Vous pouvez créer des états personnalisés pour qu'ils s'affichent dans ce contrôle, mais il y a certaines règles à suivre lors de la création des états pour s'assurer qu'ils adoptent le comportement souhaité.  

> [!NOTE]  
>   Vous devez disposer d'un compte valide avec [!INCLUDE[d365fin](includes/d365fin_md.md)] et avec Power BI. En outre, vous devez télécharger [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/). Pour plus d'informations, voir [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md).  

## <a name="report-data-set"></a>Ensemble de données de rapport
Lorsque vous créez le rapport dans Power BI Desktop, spécifiez la source de données ou le service Web qui contient les données concernant la liste que vous souhaitez associer au rapport. Par exemple, si vous souhaitez créer un rapport pour la liste Ventes, assurez-vous que l'ensemble des données contient les informations liées aux ventes.  

Pour filtrer des données sur les rapports en fonction de l'enregistrement sélectionné dans la page de liste, la clé primaire doit être utilisée comme filtre de rapport. Les clés primaires devront faire partie de votre ensemble de données pour que les états soient filtrés correctement. Dans la plupart des cas, la clé primaire de la liste est **N°** .  

## <a name="defining-the-report-filter"></a>Définition du filtre de rapport
Le rapport est nécessaire pour avoir un filtre de rapport de base (pas une page ou un filtre visuel, ni un filtre avancé) pour filtrer correctement dans le contrôle Récapitulatif État Power BI. Le filtre qui est transmis au rapport Power BI de chaque page de liste est basé sur la clé primaire, comme décrit dans la section précédente.  

Pour définir un filtre pour l'état, sélectionnez la clé primaire dans la liste des champs disponibles, puis faites glisser ce champ dans la section **Filtre d'état**.  

![Définition du filtre de rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-filter.png)

## <a name="report-size-and-color"></a>Taille et couleur du rapport
La taille du rapport doit être configurée sur 325 pixels par 310 pixels. Cette opération est requise pour la mise à l'échelle appropriée du rapport dans l'espace disponible autorisé par le contrôle Récapitulatif État Power BI. Pour définir la taille du rapport, placez le focus en dehors de la zone de présentation de rapport, puis choisissez l'icône en forme de rouleau de peinture.

![Définition de la largeur et de la hauteur du rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-sizing.png)

Vous pouvez modifier la largeur et la hauteur de l'état en choisissant **Personnalisé** dans le champ **Type**.

De même, si vous souhaitez que l'arrière-plan de l'état se fonde avec la couleur de l'arrière-plan du contrôle Récapitulatif État Power BI, définissez une couleur d'arrière-plan d'état personnalisé de *E5E5E5*. Cette option est facultative.  

## <a name="reports-with-multiple-pages"></a>États avec plusieurs pages
Avec Power BI, vous pouvez créer un seul rapport avec plusieurs pages. Les visuels que vous souhaitez visualiser dans les pages de liste [!INCLUDE[d365fin](includes/d365fin_md.md)] doivent se trouver sur la première page de l'état dans Power BI.  

> [!NOTE]  
>  Le récapitulatif État Power BI affiche uniquement la première page de votre rapport. Pour afficher d'autres pages, vous devez développer le rapport et utiliser les onglets situés au bas du rapport pour accéder aux autres pages.  

## <a name="saving-your-report"></a>Enregistrement de votre rapport

Lorsque vous enregistrez votre rapport, il est recommandé que son nom contienne celui de la page de liste dans laquelle vous souhaitez l'afficher. Par exemple, le mot *Fournisseur* doit se trouver quelque part dans le nom des états que vous souhaitez rendre disponibles dans la liste Fournisseurs.  

Cela n'est pas obligatoire mais ça va accélérer le processus de sélection des états. Lorsque la page de sélection du rapport est ouverte à partir d'une page de liste, nous transférons un filtre basé sur le nom de la page pour limiter les rapports qui s'affichent.  Vous pouvez supprimer le filtre pour obtenir la liste complète des états disponibles dans Power BI.  

## <a name="troubleshooting"></a>Dépannage
Cette section fournit une solution de rechange pour les problèmes les plus courants qui apparaissent lorsque vous créez le rapport Power BI.  

**L'utilisateur ne voit pas l'état sur la page Sélectionner un état qu'il veut sélectionner** Si vous ne pouvez pas sélectionner un état, une solution consiste à vérifier son nom pour vous assurer qu'il contient le nom de la page de liste. Vous pouvez aussi effacer le filtre pour obtenir la liste complète des états disponibles dans Power BI.  

**L'état est chargé mais il est vide, non filtré ou filtré incorrectement** Vérifiez que le filtre de l'état contient la bonne clé primaire. Dans la plupart des cas, il s'agit du champ **N°**, mais dans la table **Écriture**, vous devez utiliser le champ **N° écriture**.

**L'état est chargé, mais il affiche une page non souhaitée** Vérifiez que la page que vous souhaitez afficher est la première page de votre état.  

**L'état apparaît avec des bordures grises non désirées, il est trop petit ou trop grand**

Vérifiez que la taille du rapport est configurée sur 325 pixels x 310 pixels. Enregistrez le rapport, puis actualisez la page de liste.  

## <a name="see-also"></a>Voir aussi
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Mise en route](product-get-started.md)    
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)    
[Finance](finance.md)  

