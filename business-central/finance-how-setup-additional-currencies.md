---
title: Configuration des devises supplémentaires
description: 'Votre grand livre est configuré pour utiliser votre devise locale ($) et une autre devise est configurée comme devise additionnelle, à laquelle est affecté un taux de change courant.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'multiple currencies, foreign exchange rates'
ms.search.form: '5, 16,118, 483, 495'
ms.date: 06/13/2024
ms.service: dynamics-365-business-central
---
# <a name="set-up-an-additional-reporting-currency"></a>Configurer une devise de report additionnelle

Les compagnies opérant dans un nombre croissant de pays/régions, il est de plus en plus important qu’elles puissent consulter et générer des rapports de données financiers dans plusieurs devises.

> [!NOTE]  
> Dans [!INCLUDE[prod_short](includes/prod_short.md)], si vous recherchez des informations en temps réel sur les taux de devise étrangère (FX) ou les taux historiques, sous la désignation de devise. En plus de cet article, consultez aussi [Mettre à jour les taux de change devise](finance-how-update-currencies.md).

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change courant. Si vous désignez une deuxième devise comme devise de report additionnelle (dev. add.), [!INCLUDE[prod_short](includes/prod_short.md)] enregistre automatiquement les montants en $ et en dev. add. sur chaque écriture GL, ainsi que pour d’autres écritures, telles que les écritures TVA.

> [!Warning]
> Vous ne devez pas utiliser la fonctionnalité dev. add. comme base pour la conversion des états financiers à moins que vous ne compreniez ses limites. Cet outil ne peut pas traduire d’états financiers de filiale étrangère dans le cadre d’une consolidation de compagnie. La dev. add. peut uniquement être utilisée pour préparer des rapports dans une autre devise, comme s’il s’agissait de $ pour la compagnie.
>
> Par exemple, vous avez un grand nombre de comptes clients en livres sterling (GBP) et vous avez configuré votre dev. add. en GBP. Dans ce scénario, les montants des comptes clients qui utilisent la livre sterling ne sont pas ajustés pour les gains/pertes de change dans la dev. add., mais uniquement les montants des comptes clients qui sont dans d’autres devises. Cela signifie que si vous utilisez la dev. add. pour déclarer vos rétats financiers, cela peut entraîner des soldes impayés sous-estimés ou surestimés des comptes débiteurs.

## <a name="displaying-reports-and-amounts-in-acy"></a>Afficher les rapports et montants en dev. add.

L'utilisation d'une dev. add. peut faciliter le processus de génération de rapports d'une compagnie dans les cas suivants :

- Compagnies situées dans des pays/régions extérieur(e)s à l'UE qui effectuent un grand nombre de transactions avec des compagnies situées dans des pays/régions de l'UE. Dans ce cas, la compagnie extérieure à l’UE peut vouloir générer des rapports financiers en euros afin qu’ils soient plus lisibles pour les partenaires commerciaux de l’UE.
- Compagnies qui souhaitent pouvoir générer des rapports financiers dans une devise davantage utilisée au niveau commerce étranger que leur devise locale.

Plusieurs rapports financiers sont basés sur les écritures. Pour afficher les données de rapport dans la dev. add., cochez la case **Afficher les montants dans la devise de report additionnelle** sur le raccourci **Options** pour le rapport GL approprié.

## <a name="adjusting-exchange-rates"></a>Ajustement des taux de change

Comme les taux de change ne cessent de fluctuer, il convient d'ajuster périodiquement les équivalents de dev. add. de votre système. À défaut d’effectuer ces ajustements, les montants convertis à partir de devises étrangères (ou additionnelles) et reportés dans le grand livre en $ risquent d’être erronés. En outre, les écritures quotidiennes reportées avant la saisie d'un taux de change quotidien dans l'application doivent être mises à jour après la saisie quotidienne des informations de taux de change. Le traitement en lot **Ajuster taux de change** permet d’ajuster les taux de change des écritures client, fournisseur et compte bancaire reportées. Il peut également mettre à jour des montants en dev. add. sur des écritures GL. Pour plus d'informations, voir [Mettre à jour les taux de change devise](finance-how-update-currencies.md).

## <a name="setting-up-an-acy"></a>Configuration d'une dev. add.

Pour configurer une dev. add., procédez comme suit :

- Spécifiez les comptes du grand livre pour le report des ajustements de taux de change.  
- Spécifiez la méthode d'ajustement de taux de change pour tous les comptes généraux.  
- Spécifiez la méthode d'ajustement de taux de change pour les écritures TVA.  
- Activez la dev. add.  

### <a name="to-specify-general-ledger-accounts-for-posting-exchange-rate-adjustments"></a>Pour spécifier les comptes du grand livre pour le report des ajustements de taux de change

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Devises**, puis choisissez le lien associé.  
2. Sur la page **Devises**, renseignez les champs suivants pour la dev. add.  

|Champ|Désignation|  
|---------------------------------|---------------------------------------|  
|**Cpte gains constatés report**|Numéro du compte GL sur lequel les gains de change pour ajustements de devise entre $ et dev. add. sont reportés.|  
|**Cpte pertes constatées report**|Numéro du compte GL sur lequel les pertes de change pour ajustements de devise entre $ et dev. add. sont reportées.|  
|**Compte de gains résiduels**|Compte GL dans lequel les montants résiduels qui correspondent à des gains sont reportés si vous reportez dans le module de grand livre en $ ainsi qu'en dev. add.|  
|**Compte de pertes résiduelles**|Compte GL dans lequel les montants résiduels qui correspondent à des pertes sont reportés si vous reportez dans le module de grand livre en $ ainsi qu'en dev. add.|

> [!NOTE]  
> Des montants résiduels peuvent apparaître lorsque [!INCLUDE[prod_short](includes/prod_short.md)] arrondit des montants débit et crédit convertis de $ en dev. add.  

Pour chaque compte GL, vous devez spécifier la manière dont les montants GL du compte sont ajustés en fonction des fluctuations de taux de change entre $ et dev. add.  

### <a name="to-specify-the-exchange-rate-adjustment-method-for-all-general-ledger-accounts"></a>Pour spécifier la méthode d'ajustement de taux de change pour tous les comptes généraux

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
2. Sur la page **Plan comptable**, sélectionnez le compte approprié, puis cliquez sur l'action **Modifier**.  
3. Sur la page **Fiche compte général**, sélectionnez la méthode adéquate dans le champ **Ajustement taux de change**.  

    Si vous reportez en dev. add., spécifiez, dans le champ **Ajustement taux de change**, la manière dont ce compte GL est ajusté en fonction des fluctuations de taux de change entre $ et dev. add. Le tableau suivant décrit les options.  

    |Champ|Désignation|  
    |----------------------------------|---------------------------------------|  
    |**Aucun ajustement**|Aucun ajustement de taux de change n'est effectué sur le compte du grand livre. Ce Paramètres l’option par défaut.<br /><br /> **REMARQUE :** Sélectionnez cette option si le taux de change entre $ et dev. add. est toujours fixe.|  
    |**Ajuster montant**|La devise locale est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  
    |**Ajuster montant devise report**|La dev. add. est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant devise additionnelle**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  

    Les gains et les pertes sur taux de change sont reportés lorsque vous exécutez le traitement en lot **Ajuster taux de change**. Dans le cadre de ce traitement en lot, le taux de change d’ajustement est identifié sur la page **Taux de change devise**, puis les montants des champs **Montant** et **Montant devise additionnelle** de l’écriture GL sont comparés afin de déterminer s’il y a gain ou perte sur le taux de change. Le traitement en lot utilise l'option que vous sélectionnez dans le champ **Ajustement taux de change** pour déterminer comment calculer et reporter des gains ou des pertes sur le taux de change pour des comptes du grand livre.  

4.  Fermez la page **Fiche compte du grand livre**.  

### <a name="to-specify-exchange-rate-adjustment-method-for-vat-entries"></a>Pour spécifier la méthode d'ajustement de taux de change pour toutes les écritures TVA

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.  
2. Sur la page **Configuration du grand livre**, sélectionnez la méthode adéquate dans le champ **Ajustement tx de change TVA**.  
3. Si vous reportez en dev. add., dans le champ **Ajustement taux de change TVA**, vous pouvez spécifier la manière dont les comptes définis pour le report de la TVA sur la page **Configuration report TVA** sont ajustés pour les fluctuations de taux de change entre $ et dev. add.  

    Lorsque vous exécutez le traitement en lot **Ajuster taux de change**, le taux de change ajustement est identifié sur la page **Taux de change devise**, puis les montants des champs **Montant** et **Montant devise additionnelle** de l’écriture TVA sont comparés afin de déterminer s’il y a un gain ou une perte de change. Le traitement en lot utilise l'option sélectionnée dans ce champ pour déterminer la manière de reporter les gains et pertes de change pour les comptes TVA.  

    Vous disposez des mêmes options qu’avec les écritures GL mais, dans ce cas, les écritures ajustées sont les écritures TVA. Le tableau suivant décrit les options.

    |Champ|Désignation|  
    |----------------------------------|---------------------------------------|  
    |**Aucun ajustement**|Aucun ajustement de taux de change n'est effectué sur le compte du grand livre. Ce Paramètres l’option par défaut.|  
    |**Ajuster montant**|La devise locale est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  
    |**Ajuster montant devise report**|La dev. add. est ajustée pour tous les gains ou toutes les pertes de change. Les gains ou pertes sur le taux de change sont reportés dans le compte du grand livre, dans le champ **Montant devise additionnelle**, et dans les comptes que vous avez spécifiés pour les gains ou les pertes dans le champ **Cpte gains constatés GL** et **Cpte pertes constatées GL** de la page **Devises**.|  

### <a name="to-activate-the-acy"></a>Pour activer la dev. add.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Paramètres comptables généraux**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration du grand livre**, dans le champ **Devise de report additionnelle**, choisissez la devise supplémentaire que vous souhaitez utiliser pour vos déclarations.  
3. Lorsque vous quittez le champ, [!INCLUDE[prod_short](includes/prod_short.md)] affiche un message de confirmation décrivant les effets de l’activation de la dev. add.  
4. Cliquez sur **Oui** pour confirmer que vous souhaitez activer la devise.  
5. Le traitement par lots **Ajuster devise report** s'ouvre.

    Ce traitement en lot convertit les montants en $ des écritures existantes en dev. add. Le traitement en lot utilise un taux de change par défaut copié à partir du taux de change, qui est valide à la date de travail sur la page **Taux de change devise**. Les montants résiduels qui résultent d’une conversion de $ en dev. add. sont reportés dans les comptes de gains et pertes résiduels spécifiés sur la page **Devises**. La date de report et le numéro de document pour ces écritures sont les mêmes que pour l'écriture originale. Une fois que vous avez reporté toutes les écritures résiduelles, le traitement en lot reporte une écriture arrondissement à la date de fermeture de chaque exercice fermé dans le compte de bénéfices non répartis. Ce report permet de s’assurer que le solde de fermeture des comptes revenus pour chaque exercice fermé est 0 tant en $ qu'en dev. add.
6. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]      
7. Pour lancer le traitement par lots, cliquez sur le bouton **OK**.  

Après avoir exécuté le traitement en lot, les montants des écritures existantes suivantes sont à la fois en $ et en dev. add. :  

- Écritures  
- Écritures d'affectation article  
- Écritures TVA  
- Écritures projet  
- Écritures valeur  
- Lignes bon de production  
- Écritures bon de production  

En outre, toutes les écritures futures du même type ont des montants enregistrés en $ et en dev. add.  

> [!NOTE]  
> Le champ **Devise report** n'est activé qu'après que vous avez cliqué sur le bouton **OK** dans le traitement par lots **Ajuster devise report**.  

## <a name="see-also"></a>Voir aussi .

[Mise à jour des taux de change devise](finance-how-update-currencies.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
