---
title: "Configuration des devises supplémentaires | Microsoft Docs"
description: "Votre grand livre est configuré pour utiliser votre devise locale ($) et une autre devise est configurée comme devise additionnelle, à laquelle est affecté un taux de change courant."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies
ms.date: 01/07/2019
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: a98027c3ef3171491f84197897f93cbed4e288c2
ms.openlocfilehash: 294ed8019b12287e4b4ad59d46e842e4022a637f
ms.contentlocale: fr-ca
ms.lasthandoff: 01/07/2019

---
# <a name="set-up-an-additional-reporting-currency"></a>Configurer une devise de report additionnelle
Les compagnies opérant dans un nombre croissant de pays/régions, il est de plus en plus important qu'elles puissent consulter et générer des rapports de données financières dans plusieurs devises.

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change courant. Si vous désignez une deuxième devise comme « devise de report additionnelle », [!INCLUDE[d365fin](includes/d365fin_md.md)] enregistre automatiquement les montants en $ et dans cette devise de report additionnelle pour chaque écriture, ainsi que pour d'autres écritures, telles que les écritures TVA.

> [!Warning]
> Il est déconseillé d'utiliser la fonctionnalité de devise de report additionnelle comme base pour une conversion d'état financier. Cet outil ne permet pas d'effectuer une conversion d'états financiers de filiale étrangère dans le cadre d'une consolidation de compagnie. La fonctionnalité de devise de report additionnelle peut uniquement être utilisée pour préparer des rapports dans une autre devise, comme s'il s'agissait de la devise locale de la compagnie.

## <a name="displaying-reports-and-amounts-in-the-additional-reporting-currency"></a>Affichage de rapports et de montants dans la devise de report additionnelle
L'utilisation d'une devise de report additionnelle peut faciliter le processus de génération de rapports d'une compagnie dans les cas suivants :

- Compagnies situées dans des pays/régions extérieur(e)s à l'UE qui effectuent un grand nombre de transactions avec des compagnies situées dans des pays/régions de l'UE. Dans ce cas, la compagnie extérieure à l'UE peut vouloir générer des rapports financiers en euros afin qu'ils soient plus lisibles pour les partenaires commerciaux de l'UE.
- Compagnies qui souhaitent pouvoir générer des rapports financiers dans une devise davantage utilisée au niveau commerce étranger que leur devise locale.

Plusieurs rapports financiers sont basés sur les écritures. Pour afficher les données de rapport dans la devise de report additionnelle, activez simplement le champ **Afficher les montants dans la devise de report additionnelle** sur le raccourci **Options** pour le rapport GL approprié.

## <a name="adjusting-exchange-rates"></a>Ajustement des taux de change
Comme les taux de change ne cessent de fluctuer, il convient d'ajuster périodiquement les équivalents devise supplémentaires de votre système. À défaut d'effectuer ces ajustements, les montants convertis à partir de devises étrangères (ou additionnelles) et reportés dans le grand livre en $ risquent d'être erronés. En outre, les écritures quotidiennes reportées avant la saisie d'un taux de change quotidien dans le programme doivent être mises à jour après la saisie quotidienne des informations de taux de change. Le traitement par lots **Ajuster taux de change** permet d'ajuster les taux de change d'écritures client, fournisseur et compte bancaire validées. D'autres montants en devise de report additionnelle peuvent également être mis à jour dans les écritures. Pour plus d'informations, voir [Mettre à jour les taux de change devise](finance-how-update-currencies.md).

## <a name="setting-up-an-additional-reporting-currency"></a>Configuration d'une devise de report additionnelle
Pour configurer une devise de report additionnelle, procédez comme suit :

-   Spécifiez les comptes du grand livre pour le report des ajustements de taux de change.  
-   Spécifiez la méthode d'ajustement de taux de change pour tous les comptes généraux.  
-   Spécifiez la méthode d'ajustement de taux de change pour les écritures TVA.  
-   Activez la devise de report additionnelle.  

### <a name="to-specify-general-ledger-accounts-for-posting-exchange-rate-adjustments"></a>Pour spécifier les comptes du grand livre pour le report des ajustements de taux de change  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Devises**, puis choisissez le lien associé.  
2. Sur la page **Devises**, renseignez les champs suivants pour la devise de report additionnelle.  

|Champ|Description|  
|---------------------------------|---------------------------------------|  
|**Cpte gains constatés report**|Numéro du compte du grand livre sur lequel les gains de change sur ajustements de devise entre devise locale et devise de report additionnelle sont reportés.|  
|**Cpte pertes constatées report**|Numéro du compte du grand livre sur lequel les pertes de change sur ajustements de devise entre devise locale et devise de report additionnelle sont reportés.|  
|**Compte gains résiduels DR**|Compte du grand livre dans lequel les montants résiduels qui correspondent à des gains sont reportés si vous reportez dans le module de grand livre en $ ainsi qu'en devise de report additionnelle.|  
|**Compte pertes résiduelles DR**|Compte de grand livre dans lequel les montants résiduels qui correspondent à des pertes sont reportés si vous reportez dans le module de grand livre en $ ainsi qu'en devise de report additionnelle.|

> [!NOTE]  
>  Des montants résiduels peuvent apparaître lorsque [!INCLUDE[d365fin](includes/d365fin_md.md)] arrondit des montants débit et crédit convertis de DS en devise report.  

Pour chaque compte du grand livre, vous devez spécifier la manière dont les montants de grand livre du compte sont ajustés en fonction des fluctuations de taux de change entre $ et la devise de report additionnelle.  

### <a name="to-specify-the-exchange-rate-adjustment-method-for-all-general-ledger-accounts"></a>Pour spécifier la méthode d'ajustement de taux de change pour tous les comptes généraux  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable**, puis sélectionnez le lien associé.  
2. Sur la page **Plan comptable**, sélectionnez le compte approprié, puis cliquez sur l'action **Modifier**.  
3. Sur la page **Fiche compte général**, sélectionnez la méthode adéquate dans le champ **Ajustement taux de change**.  

    Si vous reportez dans une devise de report additionnelle, spécifiez, dans le champ **Ajustement taux de change**, la manière dont ce compte du grand livre est ajusté en fonction des fluctuations de taux de change entre $ et devise de report additionnelle. Le tableau suivant répertorie les options au choix.  

    |Champ|Description|  
    |----------------------------------|---------------------------------------|  
    |**Aucun ajustement**|Aucun ajustement de taux de change n'est effectué sur le compte du grand livre. C'est l'option par défaut.<br /><br /> **NOTE :** sélectionnez cette option si le taux de change entre DS et la devise report est toujours fixe.|  
    |**Ajuster montant**|La devise locale est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  
    |**Ajuster montant devise report**|La devise de report additionnelle est ajustée pour les gains ou les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant devise additionnelle**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  

    Les gains et les pertes sur taux de change sont reportés lorsque vous exécutez le traitement en lot **Ajuster taux de change**. Dans le cadre de ce traitement en lot, le taux de change d'ajustement est identifié sur la page **Taux de change devise**, puis les montants des champs **Montant** et **Montant devise additionnelle** de l'écriture GL sont comparés afin de déterminer s'il y a gain ou perte sur le taux de change. Le traitement en lot utilise l'option que vous sélectionnez dans le champ **Ajustement taux de change** pour déterminer comment calculer et reporter des gains ou des pertes sur le taux de change pour des comptes du grand livre.  

4.  Fermez la page **Fiche compte du grand livre**.  

### <a name="to-specify-exchange-rate-adjustment-method-for-vat-entries"></a>Pour spécifier la méthode d'ajustement de taux de change pour toutes les écritures TVA  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration du grand livre**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration du grand livre**, sélectionnez la méthode adéquate dans le champ **Ajustement tx de change TVA**.  
3. Si vous reportez dans une devise de report additionnelle, vous pouvez spécifier dans le champ **Ajustement taux de change TVA** la manière dont les comptes configurés pour le report de la TVA sur la page **Configuration report TVA** sont ajustés pour les fluctuations de taux de change entre $ et devise de report additionnelle.  

    Lorsque vous exécutez le traitement en lot **Ajuster taux de change**, le taux de change ajustement est identifié sur la page **Taux de change devise**, puis les montants des champs **Montant** et **Montant devise additionnelle** de l'écriture TVA sont comparés afin de déterminer s'il y a gain ou perte sur le taux de change. Le traitement en lot utilise l'option sélectionnée dans ce champ pour déterminer la manière de reporter les gains et pertes de change pour les comptes TVA.  

    Vous disposez des mêmes options qu'avec les écritures mais, dans ce cas, les écritures ajustées sont les écritures TVA. Le tableau suivant répertorie les options au choix.

    |Champ|Description|  
    |----------------------------------|---------------------------------------|  
    |**Aucun ajustement**|Aucun ajustement de taux de change n'est effectué sur le compte du grand livre. C'est l'option par défaut.|  
    |**Ajuster montant**|La devise locale est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  
    |**Ajuster montant devise report**|La devise de report additionnelle est ajustée pour les gains ou les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant devise additionnelle**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  

### <a name="to-activate-the-additional-reporting-currency"></a>Pour activer la devise de report additionnelle  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration du grand livre**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration du grand livre**, choisissez le champ **Devise de report additionnelle** pour sélectionner la devise additionnelle que vous souhaitez utiliser pour vos déclarations.  
3. Lorsque vous quittez le champ, [!INCLUDE[d365fin](includes/d365fin_md.md)] affiche un message de confirmation décrivant les effets de l'activation de la devise report.  
4. Cliquez sur **Oui** pour confirmer que vous souhaitez activer la devise.  
5. Le traitement par lots **Ajuster devise report** s'ouvre.

    Ce traitement en lot convertit les montants en devise locale des écritures existantes en devise de report additionnelle. Le traitement en lot utilise un taux de change par défaut copié à partir du taux de change, qui est valide à la date de travail sur la page **Taux de change devise**. Les montants résiduels qui résultent d'une conversion de $ en devise de report additionnelle sont reportés sur les comptes de gains et pertes résiduels spécifiés sur la page **Devises**. La date de report et le numéro de document pour ces écritures sont les mêmes que pour l'écriture originale. Une fois toutes ces écritures résiduelles reportées, le traitement en lot reporte une écriture arrondissement à la date de fermeture de chaque exercice fermé dans le compte de bénéfices non répartis. Cela résulte de la nécessité de s'assurer que le solde de fermeture des comptes produit pour chaque exercice fermé est 0 tant en $ que dans la devise de report additionnelle.
6. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]      
7. Pour lancer le traitement en lot, cliquez sur le bouton **OK**.  

Après exécution du traitement en lot, les montants des écritures existantes suivantes sont exprimés en $ et dans la devise de report additionnelle :  

- Écritures  
- Écritures d'affectation article  
- Écritures TVA  
- Écritures de grand livre projet  
- Écritures valeur  
- Lignes bon de production  
- Écritures bon de production  

En outre, toutes les écritures futures du même type ont des montants enregistrés en $ et dans la devise de report additionnelle.  

> [!NOTE]  
>  Le champ **Devise report** n'est activé qu'après que vous avez cliqué sur le bouton **OK** dans le traitement par lots **Ajuster devise report**.  

## <a name="see-also"></a>Voir aussi
[Mettre à jour des taux de change devise](finance-how-update-currencies.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

