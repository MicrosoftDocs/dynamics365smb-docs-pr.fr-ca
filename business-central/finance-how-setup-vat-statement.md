---
title: Configurer un relevé fiscal
description: Cette rubrique vous explique comment configurer un modèle de relevé fiscal et des noms de relevé fiscal pour répondre aux exigences en pleine évolution de l’administration fiscale.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'VAT, posting, tax, value-added tax'
ms.search.form: '317, 318, 320, 474'
ms.date: 06/16/2021
ms.author: bholtorf
---
# <a name="set-up-vat-statement-templates-and-vat-statement-names" />Configurer des modèles de relevé fiscal et des noms de relevé fiscal

Les autorités fiscales peuvent modifier et modifient leurs exigences de report de la TVA. Les modèles de relevé fiscal et les noms de relevé fiscal peuvent vous aider à vous préparer aux changements à venir et à vous conformer en douceur aux nouvelles exigences. Vous pouvez utiliser des modèles de relevé fiscal pour configurer différents rapports lorsque vous choisissez d'imprimer le relevé. Chaque modèle de relevé fiscal peut avoir plusieurs noms de relevé fiscal qui, à leur tour, définissent les calculs, et vous pouvez créer un nouveau nom de relevé fiscal lorsque les exigences changent. Par exemple, un nom peut calculer la TVA pour cette année en fonction des exigences actuelles, et un autre modèle peut calculer la TVA en fonction des exigences de l'année suivante. Les noms permettent également de conserver un historique des formats de relevé fiscal, par exemple pour vous permettre de déterminer comment la TVA a été calculée dans les années précédentes.

## <a name="to-define-a-vat-statement" />Pour définir un relevé fiscal

Les relevés fiscaux vous permettent de calculer le montant du relevé fiscal pour une période donnée, par exemple, un trimestre.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Relevés fiscaux**, puis choisissez le lien associé.  
2. Choisissez le champ **Nom**, puis sélectionnez **Nouveau** sur la page **Noms de relevé fiscal**.
3. Renseignez les champs requis. Généralement, vous souhaitez avoir un paramètre pour chaque combinaison de groupe de report marché TVA/groupe de report produit TVA. Pour les numéros de ligne, il est logique d'utiliser des numéros ou des codes équivalents comme dans votre relevé fiscal officiel [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!Tip]
> Vous pouvez filtrer les informations de la déclaration, selon votre sélection dans le champ **Type**. L'option **Totalisation comptes** est utile lorsque vous souhaitez calculer la TVA à partir d'un compte spécifique.
L'option **Total écriture TVA** permet d'obtenir la TVA pour les comptes affectés aux sélections dans les champs **Type de report général**, **Groupe de report de marché TVA** et/ou **Groupe de report produit TVA**. L'option **Total de lignes** permet de saisir une valeur ou des critères de filtre rapide dans le champ **Total de lignes**. Pour plus d'informations, voir [Recherche, filtrage et tri des données](ui-enter-criteria-filters.md). L'option **Description** est souvent utilisée pour ajouter une note à la déclaration. Par exemple, vous pouvez l'utiliser comme en-tête si vous avez utilisé Total de lignes.

## <a name="to-preview-the-vat-statement" />Afficher le relevé fiscal

Après avoir défini un relevé fiscal, vous pouvez en afficher un aperçu pour vérifier qu'il répond à vos besoins.
> [!Tip]
> Il est préférable d'avoir une section de la déclaration TVA utilisant comme **Type** **Totalisation de l'écriture TVA** et une autre section en dessous utilisant comme **Type** **Totalisation comptes** pour rapprocher les montants en fonction de la table **Écriture TVA** par rapport au montant des **comptes du grand livre**. Vous pouvez également utiliser le rapport **GL - Rapprochement TVA** à cet effet.

1. Choisissez **Aperçu**.
2. Entrez un filtre de date pour limiter la déclaration à une période spécifique. Pour plus d'informations sur la personnalisation de la page pour afficher le filtre de date, voir [Recherche, filtrage et tri des données](ui-enter-criteria-filters.md).
3. Vous pouvez sélectionner diverses options pour indiquer le type des écritures TVA à inclure dans la déclaration.
4. Sur les lignes où le champ **Type** indique la valeur **TVA**, vous pouvez afficher la liste des écritures TVA en choisissant le montant figurant dans le champ **Montant colonne**.
5. Vous pouvez utiliser la personnalisation pour afficher plus de champs dans les lignes. Par exemple, le montant de base non réalisé et le montant de TVA non réalisé, si vous utilisez la TVA non réalisée.

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/paths/process-vat-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Configuration de la TVA](finance-setup-vat.md)  
[Configuration de la TVA sur encaissement](finance-setup-unrealized-vat.md)  
[Déclarer la TVA à une autorité fiscale](finance-how-report-vat.md)  
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  
[Fonctionnalités locales dans Business Central](about-localization.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
