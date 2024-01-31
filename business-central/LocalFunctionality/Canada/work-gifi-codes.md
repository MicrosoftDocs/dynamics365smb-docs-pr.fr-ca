---
title: Codes IGRF au Canada
description: 'Au Canada, vous pouvez définir l''Index général des renseignements financiers (IGRF) et l''affecter aux comptes de report.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: local
ms.search.form: 10017
ms.date: 06/29/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Utiliser les codes IGRF dans la version canadienne
Les informations fiscales peuvent inclure des comptes généraux, des états, des comptes de gestion, des bilans et des relevés des bénéfices non répartis. Les informations fiscales sont classifiées par le biais de codes. L'utilisation de codes aide le gouvernemental à traiter les informations, à préparer l'archivage électronique et à valider les informations fiscales par voie électronique. L'utilisation de codes aide également les organisations statistiques à travailler plus efficacement, en rendant les données financières plus facilement disponibles. Pour plus d'informations, reportez-vous au [site Web de l'Agence de revenu du Canada](https://www.cra-arc.gc.ca/).

L'Agence de revenu du Canada utilise les codes IGRF (Index général des renseignements financiers) pour recueillir, valider et traiter les informations financières et fiscales par voie électronique. Les meilleures pratiques suggèrent d'attribuer des codes IGRF uniquement aux comptes de report, afin que tous les totaux soient calculés par votre logiciel d'établissement des déclarations fiscales.

Lorsqu'un compte est associé à un code IGRF, il est enregistré auprès de l'Agence de revenus sous ce code. Plusieurs comptes peuvent avoir le même code IGRF, mais chaque compte doit avoir un seul code IGRF.

Vous pouvez exporter les informations de solde par code IGRF et enregistrer le fichier exporté dans Excel, ce qui est utile pour transférer des informations vers votre logiciel d'établissement des déclarations fiscales.

## Pour configurer des codes IGRF
Dans [!INCLUDE[prod_short](../../includes/prod_short.md)], vous devez configurer des codes IGRF pour les comptes GL, les rapports, les bilans, les états de résultats et les relevés de bénéfices non répartis.

1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Codes IGRF**, puis sélectionnez le lien associé.
2. Sur la page **Codes IGRF**, sélectionnez l'action **Nouveau**.
3. Configurer les codes IGRF en renseignant les champs. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## Pour associer des codes IGRF avec des comptes généraux
Pour enregistrer des données financières par code IGRF, chaque code IGRF doit être associé aux comptes appropriés dans le plan comptable.

1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Plan comptable**, puis sélectionnez le lien associé.
2. Sélectionnez un compte général approprié, puis sélectionnez l'action **Modifier**.
3. Sur le raccourci **Comptabilité analytique**, dans le champ **Code IGRF**, sélectionnez un code IGRF approprié.

## Pour afficher les soldes de compte à l'aide du rapport de code IGRF
Vous pouvez consulter vos soldes de compte par code IGRF par le biais de l'état **Soldes de compte par code IGRF**.

1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Solde des comptes par code IGRF**, puis sélectionnez le lien associé.
2. Spécifiez les éléments à inclure dans le rapport en renseignant les champs. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## Pour exporter les informations de solde à l'aide de codes IGRF
Vous pouvez exporter les informations de solde à l'aide de codes IGRF et enregistrer le fichier exporté dans Excel. Vous pouvez modifier, enregistrer ou supprimer, le fichier. Ce fichier vous permet de transférer des informations vers votre logiciel d'établissement des déclarations fiscales.

1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Exporter données IGRF vers fichier Excel**, puis sélectionnez le lien associé.
2. Spécifiez les éléments à exporter vers Excel en renseignant les champs. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. Cliquez sur le bouton **OK**.

> [!NOTE]  
>   Le fichier Excel est doté des caractéristiques suivantes :

* Le solde est arrondi au point de pourcentage le plus proche, mais la valeur de la cellule indique le même pourcentage que dans le grand livre.
* Les nombres négatifs sont représentés comme des nombres positifs entre parenthèses. Par conséquent, -123 est représenté comme suit : (123).

## Voir aussi
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)   
[Configuration de Finance](../../finance.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]