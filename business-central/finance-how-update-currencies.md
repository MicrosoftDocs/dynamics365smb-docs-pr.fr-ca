---
title: Mettre à jour des taux de change devise
description: Suivez des montants dans différentes devises à l'aide de codes devise, et laissez Business Central ajuster les taux de change des écritures reportées avec un service externe.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: multiple currencies, adjust exchange rates
ms.date: 06/03/2021
ms.author: edupont
ms.openlocfilehash: 75f8f3ead0bdf0e09ca2484d1a0c91ee771cb837
ms.sourcegitcommit: 1aab52477956bf1aa7376fc7fb984644bc398c61
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/04/2021
ms.locfileid: "6184459"
---
# <a name="update-currency-exchange-rates"></a>Mettre à jour des taux de change devise

Étant donné que les compagnies opèrent dans un nombre croissant de pays/régions, il devient essentiel qu’elles puissent échanger et générer des informations financières dans plusieurs devises. La devise locale ($) est définie dans la page **Configuration grand livre**, comme décrit dans l’article [ Configuration de Finance](finance-setup-finance.md). Une fois la devise locale ($) définie, elle sera représentée en tant que devise vide. Ainsi, lorsque le champ **Devise** est vide, cela signifie que la devise est $.  

Ensuite, vous devez configurer des codes devise pour chaque devise que vous utilisez si vous achetez ou vendez dans des devises autres que votre devise locale ($). Des comptes bancaires peuvent également être créés à l’aide de devises. Il est possible d’enregistrer des transactions GL dans différentes devises, cependant, la transaction GL sera toujours reportée dans la devise locale ($).

> [!Important]
> Ne créez pas le code devise locale à la fois dans la page **Configuration grand livre** et dans la page **Devises**. Cela créera une confusion entre la devise vide et le code $ dans le tableau des devises, et il se pourrait que des comptes bancaires, des clients ou des fournisseurs soient créés accidentellement, certains avec la devise vide et d’autres avec le code $.

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change des devises. Si vous désignez une deuxième devise comme « devise de report additionnelle », [!INCLUDE[prod_short](includes/prod_short.md)] enregistre automatiquement les montants en $ et dans cette devise de report additionnelle pour chaque écriture, ainsi que pour d'autres écritures, telles que les écritures TVA. Pour plus d'informations, voir [Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md). La devise de report additionnelle est le plus souvent utilisée pour faciliter les rapports financiers pour les propriétaires qui résident dans des pays/régions utilisant des devises différentes de la devise locale ($).

## <a name="currencies"></a>Devises

Vous spécifiez les codes devise dans **Devises**, y compris les informations supplémentaires et les paramètres nécessaires pour chaque code devise.

> [!TIP]
> Créez les devises avec le code ISO international pour simplifier l’utilisation de la devise à l’avenir.

|Champ|Description|  
|---------------------------------|---------------------------------------|  
|**Code**|Identificateur de la devise.|
|**Description**|Description libre de la devise.|
|**Code ISO**|Code international à trois lettres pour la devise défini dans la norme ISO 4217.|
|**Code numérique ISO**|Référence numérique internationale pour la devise définie dans la norme ISO 4217.|
|**Date du taux de change**|La dernière date de taux de change effectif.|
|**Devise U.M.E.**|Indique si la devise est une devise de l’U.M.E. (Union économique et monétaire), telle que EUR.|
|**Cpte gains constatés report**|Compte sur lequel le gain réel sera reporté lorsque vous recevrez des paiements pour des créances ou enregistrerez le taux de change réel sur les paiements de dépenses. Pour consulter un exemple de transaction en devise comptable, voir l’exemple sous ce tableau. |
|**Cpte pertes constatées report**|Compte sur lequel la perte réelle sera reportée lorsque vous recevrez des paiements pour des créances ou enregistrerez le taux de change réel sur les paiements de dépenses. Pour consulter un exemple de transaction en devise comptable, voir l’exemple sous ce tableau. |
|**Compte gains non réalisés**|Compte sur lequel le gain théorique sera reporté lorsque vous effectuerez un ajustement de devise.|
|**Compte pertes non réalisées**|Compte sur lequel la perte théorique sera reportée lorsque vous effectuerez un ajustement de devise.|
|**Précision arrondissement montant**|Certaines devises ont d’autres formats pour les montants facture que ceux définis dans la page **Configuration grand livre**. Si vous modifiez la précision d'arrondissement su montant pour une devise, tous les montants facture dans cette devise seront arrondis avec la précision mise à jour.|
|**Nombre décimales montant**|Certaines devises ont d’autres formats pour les montants facture que ceux définis dans la page **Configuration grand livre**. Si vous modifiez le nombre décimales montant pour une devise, tous les montants facture dans la devise seront arrondis avec les décimales mises à jour.|
|**Type arrondissement facture**|Spécifie la méthode à utiliser si les montants doivent être arrondis. Les options sont **Au plus près**, **Vers le haut** et **Vers le bas**.|
|**Précision arrondissement montant unitaire**|Certaines devises ont d’autres formats pour les montants unitaires que ceux définis dans la page **Configuration grand livre**. Si vous modifiez la précision d'arrondissement du montant unitaire pour une devise, tous les montants unitaires dans la devise seront arrondis avec la précision mise à jour.|
|**Nombre décimales montant unitaire**|Certaines devises ont d’autres formats pour les montants unitaires que ceux définis dans la page **Configuration grand livre**. Si vous modifiez le nombre décimales montant unitaire pour une devise, tous les montants unitaires dans la devise seront arrondis avec les décimales mises à jour.|
|**Précision arrondissement affectation**|Spécifie la taille de l'intervalle autorisé comme différence d'arrondissement lorsque vous affectez des écritures entre elles dans différentes devises.|
|**Compte débit arrondissement conversion $**|Spécifie les informations de conversion qui doivent également contenir un compte débit si vous souhaitez insérer des lignes correction pour les différences d’arrondissement dans les journaux généraux en utilisant l’action **Insérer lignes arr. conv. $**.|
|**Compte crédit arrondissement conversion $**|Spécifie les informations de conversion qui doivent également contenir un compte crédit si vous souhaitez insérer des lignes correction pour les différences d’arrondissement dans les journaux généraux en utilisant l’action **Insérer lignes arr. conv. $**.|
|**Date dern. ajust. automatique**|Date du dernier ajustement de devise.|
|**Date dern. modification**|Date de la modification dans la configuration de la devise.|
|**% tolérance de règlement**|% de tolérance de règlement maximum défini pour cette devise. Pour plus d’informations, consultez [Tolérance de règlement et tolérance d’escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md). |
|**Montant tolérance de règlement max.**|Montant de tolérance de règlement maximum défini pour cette devise. Pour plus d’informations, consultez [Tolérance de règlement et tolérance d’escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md). |
|**Facteur devise**|Spécifie la relation entre la devise et la devise locale à l’aide du taux de change réel.|
|**Cpte GL gains réalisés**|Indique le compte du grand livre utilisé pour reporter les gains sur taux de change pour les ajustements de devise entre la devise locale ($) et la devise de report additionnelle. Les gains sur taux de change sont calculés lorsque le traitement en lot Ajuster taux de change est exécuté pour ajuster les comptes GL. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Compte GL pertes réalisées**|Indique le compte du grand livre utilisé pour reporter les pertes sur taux de change pour les ajustements de devise entre la devise locale ($) et la devise de report additionnelle. Les gains sur taux de change sont calculés lorsque le traitement en lot Ajuster taux de change est exécuté pour ajuster les comptes GL. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Compte gains résiduels DR**|Indique le compte du grand livre utilisé pour reporter les montants des gains résiduels (différences d’arrondissement) lorsqu’une devise de report additionnelle est utilisée dans le module de grand livre. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Compte pertes résiduelles DR**|Indique le compte du grand livre utilisé pour reporter les montants des pertes résiduelles (différences d’arrondissement) lorsqu’une devise de report additionnelle est utilisée dans le module de grand livre. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Différence TVA max. autorisée**|Montant maximum autorisé pour les différences de TVA dans cette devise. Pour plus d’informations, consutez [Correction manuelle des montants de TVA dans des documents achat et vente](finance-work-with-vat.md#correcting-vat-amounts-manually-in-sales-and-purchase-documents). Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Type arrondissement TVA**|Spécifie la méthode d’arrondissement pour corriger manuellement les montants TVA dans les documents vente et achat. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|

### <a name="example-of-a-receivable-currency-transaction"></a>Exemple de transaction en devise comptabilité

Dans l’exemple suivant, une facture est reçue le 1er janvier avec le montant en devise 1 000. À ce moment là, le taux de change est 1,123.

|Date|Action|Montant devise|Taux document|Montant en $ sur le document|Taux ajustement|Montant gains non réalisés|Taux règlement|Montant pertes constatées report|  
|-----|----------|------------|-----------|---------|-----------|-------------|---------|---------|
|1/1|**Facture**|1000|1,123|1123|||||
|1/31|**Ajustement**|1000||1125|1,125|2|||
|2/15|**Ajustement Contrepassation sur paiement**|1000||||-2|||
|2/15|**Règlement**|1000||1120|||1,120|-3|

À la fin du mois, un ajustement de devise est effectué lorsque le taux de change d’ajustement a été fixé à 1,125, ce qui déclenche un gain non réalisé de 2.

Au moment du paiement, le taux de change réel enregistré sur la transaction bancaire indique un taux de change de 1,120.

Ici, il y a une transaction non réalisée. Elle sera donc inversée avec le paiement.

Enfin, le paiement est enregistré et la perte réelle est reportée sur le compte des pertes réalisées.

## <a name="available-currency-functions"></a>Fonctions de devise disponibles

Le tableau suivant décrit les actions clés sur la page ***Devises**. Certaines des actions sont expliquées dans les sections suivantes.  

|Menu|Action|Description|
|-------------|--------------|------------------------------|
|**Traitement**|**Proposer des comptes**|Utilisez des comptes des autres devises. Les comptes les plus fréquemment utilisés seront insérés.|
||Modifier la tolérance de règlement|Modifiez la tolérance de règlement maximum, le pourcentage de tolérance de règlement ou les deux, et filtrez par devise. Pour plus d’informations, consultez [Tolérance de règlement et tolérance d’escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md).|
||**Taux change**|Affichez les taux de change mis à jour pour les devises que vous utilisez.|
||**Ajuster taux de change**|Ajuster les écritures GL, client, fournisseur et compte bancaire pour obtenir un solde mis à jour si le taux de change a évolué depuis le report des écritures.|
||**Registre d’ajust. taux de change**|Affichez les résultats de l’exécution du traitement en lot **Ajuster taux de change**. Une ligne est créée pour chaque devise et pour chaque combinaison de devise et de groupe de report comprise dans l’ajustement.|
|**Service de taux de change**|**Services de taux de change**|Affichez ou modifiez la configuration des services qui sont paramétrés pour extraire les taux de change de devise mis à jour lorsque vous sélectionnez l’action **Mettre à jour les taux de change**.|
||**Mettre à jour les taux de change**|Obtenez les récents taux de change des devises auprès d’un fournisseur de services.|
|**Rapports**|**Solde devise étrangère**|Affichez les soldes de tous les clients et fournisseurs en devise étrangère et en devise locale ($). Le rapport affiche deux soldes en $. L’un correspond au solde en devise étrangère converti en $ en utilisant le taux de change en vigueur au moment de la transaction. L’autre correspond au solde en devise étrangère converti en $ en utilisant le taux de change à la date de travail.|

## <a name="exchange-rates"></a>Taux de change

Les taux de change permettent de calculer la valeur en devise locale ($) de chaque transaction en devise. La page **Taux d’échange** comprend les champs suivants :

|Champ|Description|  
|---------------------------------|---------------------------------------|  
|**Date début**|Date à laquelle le taux de change a été effectué|  
|**Code devise**|Code devise lié à ce taux de change|  
|**Code devise liée**|Si cette devise fait partie d’un calcul de devise triangulaire, le code devise associé peut être configuré ici|  
|**Montant taux de change**|Le montant du taux de change est le taux à utiliser pour le code devise sélectionné sur la ligne. Il s’agit normalement de 1 ou 100|  
|**Montant taux de change lié**|Le montant du taux de change lié concerne le taux à utiliser pour le code devise liée.|  
|**Montant taux de change ajust.**|Le montant du taux de change d’ajustement est le taux à utiliser pour le code devise sélectionné sur la ligne à utiliser pour le traitement en lot **Ajuster taux de change**.|  
|**Montant taux change lié ajust.**|Le montant du taux de change d’ajustement lié est le taux à utiliser pour le code devise sélectionné sur la ligne à utiliser pour le traitement en lot **Ajuster taux de change**.|  
|**Fixer montant taux de change**|Spécifie si le taux de change de la devise peut être modifié sur les factures et les lignes journal.|  

En général, les valeurs des champs **Montant taux de change** et **Montant taux de change lié** sont utilisées comme taux de change par défaut sur tous les nouveaux documents client et fournisseur créés à l’avenir. Le taux de change est affecté au document en fonction de la date de travail actuelle.  

> [!Note]
> Le taux de change réel sera calculé à l’aide de cette formule :
> 
> `Currency Amount = Amount / Exchange Rate Amount * Relational Exch. Rate Amount`

Le montant du taux de change d’ajustement ou le montant du taux de change d’ajustement lié sera utilisé pour mettre à jour toutes les transactions banque, client ou fournisseur.  

> [!Note]
> Le taux de change réel sera calculé à l’aide de cette formule :
> 
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## <a name="adjusting-exchange-rates"></a>Ajustement des taux de change

Comme les taux de change ne cessent de fluctuer, il convient d'ajuster périodiquement les équivalents devise supplémentaires de votre système. À défaut d'effectuer ces ajustements, les montants convertis à partir de devises étrangères (ou additionnelles) et reportés dans le grand livre en $ risquent d'être erronés. En outre, les écritures quotidiennes reportées avant la saisie d'un taux de change quotidien dans l'application doivent être mises à jour après la saisie quotidienne des informations de taux de change.

Le traitement en lot **Ajuster taux de change** permet d'ajuster manuellement les taux de change des écritures client, fournisseur et compte bancaire reportées. D'autres montants en devise de report additionnelle peuvent également être mis à jour dans les écritures.  

> [!TIP]
> Vous pouvez utiliser un service pour mettre à jour automatiquement les taux de change dans le système. Pour plus d'informations, reportez vous à [Configurer un service de taux de change des devises](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service). Cependant, cela n’ajuste pas les taux de change sur les transactions déjà reportées. Pour mettre à jour les taux de change sur les écritures reportées, utilisez le traitement en lot **Ajuster les taux de change**.

### <a name="effect-on-customers-and-vendors"></a>Effet sur les clients et fournisseurs

Pour les comptes client et fournisseur, le traitement en lot ajuste la devise en utilisant le taux de change qui est valide à la date de report spécifiée dans le traitement en lot. Le traitement en lot calcule les différences pour chaque solde en devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains non réalisés** ou **Compte pertes non réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur le compte client/fournisseur dans le grand livre.

Ce traitement en lot traite toutes les écritures client et toutes les écritures fournisseur ouvertes. En cas de différence du taux de change d'une écriture, le traitement en lot crée une écriture client ou fournisseur détaillée reflétant le montant ajusté dans l'écriture client ou fournisseur.

#### <a name="dimensions-on-customer-and-vendor-ledger-entries"></a>Dimensions sur des écritures client et fournisseur
Les dimensions des écritures client/fournisseur sont affectées aux écritures ajustement et les ajustements sont reportés par combinaison de valeurs de dimension.

### <a name="effect-on-bank-accounts"></a>Effet sur les comptes bancaires
Pour les comptes bancaires, le traitement en lot ajuste la devise en utilisant le taux de change qui est valide à la date de report spécifiée dans le traitement en lot. Le traitement en lot calcule les différences pour chaque compte bancaire possédant un code devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains réalisés** ou **Compte pertes réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur les comptes bancaires du grand livre spécifiés dans les groupes de report compte bancaire. Le traitement en lot calcule une écriture par devise et par groupe de report.

#### <a name="dimensions-on-bank-account-entries"></a>Dimensions sur des écritures compte bancaire
Les dimensions par défaut du compte bancaire sont affectées aux écritures ajustement pour le compte GL du compte bancaire et pour le compte gain/perte.

### <a name="effect-on-gl-accounts"></a>Effet sur les comptes du grand livre
Si vous effectuez le report dans une devise de report additionnelle, vous pouvez demander au traitement en lot de créer de nouvelles écritures pour les ajustements de devise entre devise locale ($) et devise de report additionnelle. Le traitement en lot calcule les différences pour chaque écriture GL et ajuste l'écriture GL en fonction de la valeur du champ **Ajustement taux de change** de chaque compte GL.

##### <a name="dimensions-on-gl-account-entries"></a>Dimensions sur des écritures compte du grand livre
Les dimensions par défaut des comptes dans lesquels elles sont reportées sont affectées aux écritures ajustement.

> [!Important]
> Avant de pouvoir utiliser le traitement en lot, vous devez entrer les taux de change ajustement qui sont utilisés pour ajuster les soldes en devises étrangères. Pour ce faire sur la page **Taux de change devise**.<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Q24s?rel=0]

## <a name="to-set-up-a-currency-exchange-rate-service"></a>Configurer un service de taux de change des devises
Vous pouvez utiliser un service externe pour tenir vos taux de change des devises à jour, par exemple FloatRates.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Services de taux de change devise**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Service de taux de change devise**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Activez le bouton bascule **Activé** pour activer le service.

> [!NOTE]
> La vidéo suivante montre un exemple de connexion à un service de taux de change des devises, en prenant l’exemple de la Banque Centrale Européenne. Dans le segment qui décrit comment configurer les mappages de champs, le paramètre de la colonne **Source** pour **Nœud parent pour code devise** ne renverra que la première devise trouvée. Le paramètre doit être **/gesmes:Enveloppe/Code/Code/Code**.

<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4A1jy?rel=0]

## <a name="to-update-currency-exchange-rates-through-a-service"></a>Pour mettre à jour les taux de change des devises à partir d'un service
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Devises**, puis sélectionnez le lien associé.
2. Choisissez l'option **Mettre à jour les taux de change**.

La valeur dans le champ **Taux de change** de la page **Devises** est mise à jour avec le dernier taux de change des devises.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi
[Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
