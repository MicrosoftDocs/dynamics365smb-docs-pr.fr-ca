---
title: Tolérance de règlement et tolérance d’escompte de paiement
description: Vous pouvez configurer la tolérance de règlement de manière à fermer une facture lorsque le paiement ne couvre pas entièrement le montant de la facture.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 118, 314, 395
ms.date: 10/29/2021
ms.author: edupont
ms.openlocfilehash: fa9e4abb37788b7aa8261ab0a5a705edef27e3c4
ms.sourcegitcommit: 2ab6709741be16ca8029e2afadf19d28cf00fbc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/14/2022
ms.locfileid: "7972496"
---
# <a name="work-with-payment-tolerances-and-payment-discount-tolerances"></a>Utilisation des tolérances de règlement et des tolérances d'escompte de paiement
Vous pouvez configurer une tolérance de règlement de manière à fermer une facture lorsque le paiement ne couvre pas entièrement le montant de la facture. Par exemple, les tolérances de règlement concernent généralement de petits montants qui coûteraient plus cher à corriger qu'à simplement accepter. Vous pouvez configurer une tolérance d'escompte de paiement pour accorder un escompte de paiement après expiration de la date d'escompte de paiement.  

Vous pouvez utiliser les tolérances de règlement pour qu'une tolérance de règlement maximum autorisée soit définie pour chaque montant restant dû. Si la tolérance de règlement est respectée, le montant règlement est analysé. Si le montant règlement est un moins-perçu, alors le montant en commande est totalement fermé par le moins-perçu. Une écriture détaillée est reportée dans l'écriture règlement de sorte qu'il ne subsiste aucun montant ouvert dans l'écriture facture affectée. Si le montant règlement est un trop-perçu, alors une nouvelle écriture détaillée est reportée dans l'écriture règlement de sorte qu'il ne subsiste aucun montant ouvert dans l'écriture règlement.

Vous pouvez utiliser des tolérances d'escompte de paiement au cas où vous accepteriez un escompte de paiement après la date d'escompte de paiement. Il sera alors toujours reporté dans le compte escompte de paiement ou dans un compte tolérance de règlement.

## <a name="applying-payment-tolerance-to-multiple-documents"></a>Application de la tolérance de règlement à plusieurs documents  
Un document unique comporte la même tolérance de règlement, qu'il soit affecté seul ou avec d'autres documents. L'acceptation d'un escompte de paiement en retard, lorsque vous appliquez la tolérance de règlement à plusieurs documents, se produit automatiquement pour chaque document où la règle suivante est vraie :  

*date d'escompte < date de règlement dans l'écriture sélectionnée <= date d'écart de règlement*  

Cette règle détermine également la nécessité d'afficher des alertes lorsque vous affectez la tolérance de règlement à plusieurs documents. L'avertissement lié à la tolérance d'escompte de paiement s'affiche pour chaque écriture répondant aux critères de date. Pour plus d'informations, voir [Exemple 2 - Calculs de la tolérance pour plusieurs documents](finance-payment-tolerance-and-payment-discount-tolerance.md#example-2---tolerance-calculations-for-multiple-documents).

Vous pouvez afficher une alerte en fonction des situations relatives à la tolérance.  

- Le premier avertissement concerne la tolérance d'escompte de paiement. Vous êtes informé que vous pouvez accepter un escompte de paiement en retard. Vous pouvez ensuite décider s'il faut accepter la tolérance sur la date d'escompte.  
- Le second avertissement concerne la tolérance de règlement. Vous êtes informé que toutes les écritures peuvent être fermées car la différence est inférieure à la tolérance de règlement maximum pour les écritures affectées. Vous pouvez ensuite décider s'il faut accepter la tolérance sur le montant du paiement.

> [!NOTE]
> L'activation du message d'avertissement vous permettra de choisir comment traiter les paiements dans les limites de la tolérance. Si vous n'activez pas le message et qu'un niveau de tolérance est spécifié, les factures dont les montants se situent dans la tolérance seront automatiquement fermées et vous ne pourrez pas choisir de laisser le montant restant. 

Pour plus d'informations, voir [Pour activer ou désactiver l'avertissement de tolérance de règlement](finance-payment-tolerance-and-payment-discount-tolerance.md#to-enable-or-disable-payment-tolerance-warnings). 

## <a name="to-set-up-tolerances"></a>Pour configurer les tolérances  
Le fait de configurer des tolérances pour la date ou le montant permet de fermer une facture alors que le règlement ne couvre pas le montant indiqué sur la facture, que ce soit parce que la date d'échéance de l'escompte de paiement est dépassée ou que des marchandises ont été déduites, ou suite à une erreur anodine. Ceci est également vrai pour les remboursements et les notes de crédit.  

Pour configurer l'écart, vous devez configurer plusieurs comptes écart, spécifier des méthodes de comptabilisation d'écart escompte et d'écart règlement, puis exécuter le traitement par lots **Modifier écart de règlement**.  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du report général**, puis choisissez le lien associé.  
2. Sur la page **Configuration report général**, configurez un compte tolérance de règlement crédit et débit pour les ventes et un autre pour les achats.  
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report client**, puis choisissez le lien associé.    
4. Sur la page **Groupes report client**, configurez un compte tolérance de règlement débit et un compte tolérance de règlement crédit. Pour plus d'informations, voir [Configuration de groupes de report](finance-posting-groups.md).  
5. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du report fournisseur**, puis choisissez le lien associé.  
6. Sur la page **Groupes report fournisseur**, configurez un compte tolérance de règlement débit et un compte tolérance de règlement crédit.  
7. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.  
8. Ouvrez la page **Configuration du grand livre**.  
9. Sur le raccourci **Affectation**, renseignez les champs **Report tolérance d’escompte de paiement**, **Période carence escompte de paiement** et **Report tolérance de règlement**.   
10. Choisissez l'action **Modifier la tolérance de règlement**.
11. Sur la page **Modifier tolérance de règlement**, renseignez les champs **% tolérance de règlement** et **Montant tolérance de règlement max.**, puis cliquez sur le bouton **OK**.

> [!IMPORTANT]  
>  Vous n'avez configuré la tolérance que pour la devise locale. Si vous souhaitez que [!INCLUDE[prod_short](includes/prod_short.md)] gère la tolérance pour les paiements, les notes de crédit et les remboursements en devise étrangère, vous devez exécuter le traitement en lot **Modifier la tolérance de paiement** avec une valeur dans le champ **Code devise**.  

> [!NOTE]  
>  Si vous souhaitez recevoir une alerte tolérance de règlement chaque fois que vous reportez une affectation dans la tolérance, vous devez activer l'avertissement tolérance de règlement. Pour plus d'informations, voir [Pour activer ou désactiver l'avertissement de tolérance de règlement](finance-payment-tolerance-and-payment-discount-tolerance.md#to-enable-or-disable-payment-tolerance-warnings).  
>   
>  Pour désactiver la tolérance pour un client ou un fournisseur, vous devez bloquer les tolérances sur la fiche client ou fournisseur correspondante. Pour plus d'informations, voir [Pour bloquer la tolérance de règlement pour des clients](finance-payment-tolerance-and-payment-discount-tolerance.md#to-block-payment-tolerance-for-customers).  
>   
>  Lorsque vous configurez une tolérance, [!INCLUDE[prod_short](includes/prod_short.md)] vérifie s'il existe des écritures ouvertes et calcule la tolérance pour ces écritures.

## <a name="to-enable-or-disable-payment-tolerance-warnings"></a>Pour activer ou désactiver les alertes de tolérance de règlement
L'avertissement de tolérance de règlement apparaît lorsque vous reportez une affectation dont le solde respecte la tolérance autorisée. Vous pouvez alors choisir comment reporter et journaliser le solde.    
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.  
2. Sur la page **Configuration du grand livre**, sur le raccourci **Application**, activez le bouton bascule **Alerte tolérance de règlement** pour activer l'alerte. Pour désactiver l'avertissement, désactivez le bouton bascule.  

> [!NOTE]  
>  L'option par défaut de la page **Alerte tolérance de règlement** est **Laisser le solde ouvert**. L’option par défaut de la page **Alerte tolérance d’escompte de paiement** est **Ne pas accepter d’escompte de paiement en retard**.

## <a name="to-block-payment-tolerance-for-customers"></a>Pour bloquer la tolérance de règlement pour des clients  
Par défaut, une tolérance de règlement est accordée. Pour ne pas accorder une tolérance de règlement à un certain client ou fournisseur, vous devez bloquer la tolérance sur la fiche fournisseur ou client appropriée. Ce qui suit décrit comment l'exécuter pour un client. La procédure est identique pour un fournisseur.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Client** ou **Fournisseur**, puis choisissez le lien associé.  
2. Sur le raccourci **Paiements**, cochez la case **Bloquer écart de règlement**.  

> [!NOTE]  
>  Si le client ou le fournisseur possède des écritures ouvertes, vous devez d'abord supprimer la tolérance de règlement des écritures actuellement ouvertes.

## <a name="example-1---tolerance-calculations-for-a-single-document"></a>Exemple 1 - Calculs de la tolérance pour un seul document
Voici quelques exemples de scénarios illustrant les calculs et reports de tolérance qui sont effectués dans différentes situations.  

La page **Configuration du grand livre** contient la configuration suivante :
- Délai de grâce escompte de paiement : 5D  
- Tolérance de règlement max : 5  

Scénarios comportant deux alternatives, A et B. En voici la signification :  

- **A** L'avertissement tolérance d'escompte de paiement a été désactivé OU l'avertissement est activé, mais l'utilisateur a accepté l'escompte de paiement en retard (Reporter le solde en tant que tolérance de paiement).  
- **B** L'avertissement est activé et l'utilisateur a choisi de ne pas accepter l'escompte de paiement en retard (Laisser le solde ouvert).  

|—|Fact.|Escompte de paiement|Tolérance de règlement max.|Date d’escompte de paiement|Date de tolérance d’escompte de paiement|Date de paiement|Règlement|Type de tolérance|Toutes les écritures fermées|Tolérance d’escompte de paiement GL/CL|Tolérance de règlement GL|  
|-------|----------|----------------|-----------------------|---------------------|--------------------------|------------------|----------|--------------------|------------------------|------------------------------|----------------------------|  
|1|1,000|20|5|01/15/03|01/20/03|<=15/01/03|985|PaymentTolerance|Oui|0|-5|  
|2|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**<=15/01/03**|**980**|**Aucun**|**Oui**|**0**|**0**|  
|3|1,000|20|5|01/15/03|f|<=15/01/03|975|PaymentTolerance|Oui|0|5|  
|4A|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|1005|PaymentDiscountTolerance|Non, 25 sur le règlement|20/-20|0|  
|5A|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|1000|PaymentDiscountTolerance|Non, 20 sur le règlement|20/-20|0|  
|6A|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|995|PaymentDiscountTolerance|Non, 15 sur le règlement|20/-20|0|  
|4B|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|1005|PaymentTolerance|Oui|0|-5|  
|**5B**|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**16/01/03 20/01/03**|**1000**|**Aucun**|**Oui**|**0**|**0**|  
|6B|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|995|PaymentTolerance|Oui|0|5|  
|7|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|985|PaymentDiscountTolerance et PaymentTolerance|Oui|20/-20|-5|  
|8|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|980|PaymentDiscountTolerance|Oui|20/-20|0|  
|9|1,000|20|5|01/15/03|01/20/03|16/01/03 20/01/03|975|PaymentDiscountTolerance et PaymentTolerance|Oui|20/-20|5|  
|10|1,000|20|5|01/15/03|01/20/03|>20/01/03|1005|PaymentTolerance|Oui|0|-5|  
|**11**|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**>20/01/03**|**1000**|**Aucun**|**Oui**|**0**|**0**|  
|12|1,000|20|5|01/15/03|01/20/03|>20/01/03|995|PaymentTolerance|Oui|0|5|  
|13|1,000|20|5|01/15/03|01/20/03|>20/01/03|985|Aucun|Non, 15 sur la facture|0|0|  
|14|1,000|20|5|01/15/03|01/20/03|>20/01/03|980|Aucun|Non, 20 sur la facture|0|0|  
|15|1,000|20|5|01/15/03|01/20/03|>20/01/03|975|Aucun|Non, 25 sur la facture|0|0|  

### <a name="payment-range-diagrams"></a>Schémas de chaîne de paiement  
Sur la base du scénario ci-avant, les diagrammes des plages de dates de règlement se présentent sous la forme suivante :  

#### <a name="1-payment-date-011503-scenarios-1-3"></a>(1) Date de règlement <=15/01/03 (scénarios 1-3)  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les tolérances de règlement uniques 1.](media/singlePmtTolRules_Pre1503.gif "Règles sur les tolérances de règlement uniques 1")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="2-payment-date-is-between-011603-and-012003-scenarios-4-9"></a>(2) La date de règlement est comprise entre le 16/01/03 et le 20/01/03 (scénarios 4-9).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les tolérances de règlement uniques 2.](media/singlePmtTolRules_GracePeriod.gif "Règles sur les tolérances de règlement uniques 2")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="3-payment-date-is-after-012003-scenarios-10-15"></a>(3) La date de règlement est située après le 20/01/03 (scénarios 10-15).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les tolérances de règlement uniques 3.](media/singlePmtTolRules_Post0120.gif "Règles sur les tolérances de règlement uniques 3")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

## <a name="example-2---tolerance-calculations-for-multiple-documents"></a>Exemple 2 - Calculs de la tolérance pour plusieurs documents
Voici quelques exemples de scénarios illustrant les calculs et reports de tolérance qui sont effectués dans différentes situations. Ces exemples sont simplement des scénarios qui entraînent la fermeture de toutes les écritures dans l'application.  

La page **Configuration du grand livre** contient la configuration suivante :
- Délai de grâce escompte de paiement 5D  
- Tolérance de règlement max 5  

Scénarios comportant deux alternatives, A, B, C ou D. En voici la signification :  

- **A** L'avertissement tolérance d'escompte de paiement a été désactivé OU l'avertissement est activé, mais l'utilisateur a accepté l'escompte de paiement en retard (Reporter en tant que tolérance) pour toutes les factures.  
- **B** L'avertissement est activé et l'utilisateur a choisi de n'accepter l'escompte de paiement en retard pour aucune des factures.  
- **C** : L'avertissement est activé et l'utilisateur a choisi d'accepter l'escompte de paiement en retard pour la première facture, mais non pour la deuxième.  
- **D** : L'avertissement est activé et l'utilisateur a choisi de ne pas accepter l'escompte de paiement en retard pour la première facture, mais de l'accepter pour la seconde.  

|—|Fact.|Escompte de paiement|Tolérance de règlement max.|Date d’escompte de paiement|Date de tolérance d’escompte de paiement|Date de paiement|Règlement|Type de tolérance|Toutes les écritures fermées|Tolérance d’escompte de paiement GL/CL|Tolérance de règlement GL|  
|-------|----------|---------------|-------------------|---------------------|--------------------------|------------------|---------|--------------------|------------------------|------------------------------|------------------------|  
|1|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|<=15/01/03|1920|PaymentTolerance|Oui|0<br /><br /> 0|-5 <br />-5|  
|**2**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**<=15/01/03**|**1910**|**Aucun**|**Oui**|**0**<br /><br /> **0**|0 <br />0|  
|3|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|<=15/01/03|1900|PaymentTolerance|Oui|0<br /><br /> 0|5 <br />5|  
|4B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1980|PaymentTolerance|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**5B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**16/01/03 17/01/03**|**1970**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|6B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1960|PaymentTolerance|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|7A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1920|PaymentDiscountTolerance et PaymentTolerance|Oui|60/60<br /><br /> 0/0|-5 <br />-5|  
|8A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1910|PaymentDiscountTolerance|Oui|60/60<br /><br /> 0/0|0 <br />0|  
|9A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1900|PaymentDiscountTolerance et PaymentTolerance|Oui|60/60|5 <br />5|  
|10B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|2010|PaymentTolerance|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**11B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**18/01/03 20/01/03**|**2000**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|12B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1990|PaymentTolerance|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|13D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1980|PaymentDiscountTolerance et PaymentTolerance|Oui|0/0<br /><br /> 30/-30|-5 <br />-5|  
|14D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1970|PaymentDiscountTolerance|Oui|0/0<br /><br /> 30/-30|0 <br />0|  
|15D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1960|PaymentDiscountTolerance et PaymentTolerance|Oui|0/0<br /><br /> 30/-30|5 <br />5|  
|16D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1950|PaymentDiscountTolerance et PaymentTolerance|Oui|60/-60<br /><br /> 0/0|-5 <br />-5|  
|17D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1940|PaymentDiscountTolerance|Oui|60/-60<br /><br /> 0/0|0 <br />0|  
|18D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1930|PaymentDiscountTolerance et PaymentTolerance|Oui|60/-60<br /><br /> 0/0|5 <br />5|  
|19A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1920|PaymentDiscountTolerance et PaymentTolerance|Oui|60/-60<br /><br /> 30/-30|-5 <br />-5|  
|20A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1910|PaymentDiscountTolerance|Oui|60/-60<br /><br /> 30/-30|0 <br />0|  
|21A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1900|PaymentDiscountTolerance et PaymentTolerance|Oui|60/-60<br /><br /> 30/-30|5 <br />5|  
|22B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|2010|PaymentTolerance|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**23B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**21/01/03 22/01/03**|**2000**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|24B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1990|PaymentTolerance|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|25A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1980|PaymentDiscountTolerance et PaymentTolerance|Oui|0/0<br /><br /> 30/30|-5 <br />-5|  
|26A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1970|PaymentDiscountTolerance|Oui|0/0<br /><br /> 30/30|0 <br />0|  
|27A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1960|PaymentDiscountTolerance et PaymentTolerance|Oui|0/0<br /><br /> 30/30|5 <br />5|  
|28|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|>22/01/03|2010|PaymentTolerance|Oui|0|-5|  
|**29**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**>22/01/03**|**2000**|**Aucun**|**Oui**|**0**|**0**|  
|30|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|>22/01/03|1990|PaymentTolerance|Oui|0|5|  

### <a name="payment-range-diagrams"></a>Schémas de chaîne de paiement  
Sur la base du scénario ci-avant, les diagrammes des plages de dates de règlement se présentent sous la forme suivante :  

#### <a name="1-payment-date-011503-scenarios-1-3"></a>(1) Date de règlement <=15/01/03 (scénarios 1-3)  
Montant ouvert par  

Règles d'affectation normales  

:::image type="content" source="media/multiplePmtTolRules_Pre1503.gif" alt-text="Règles sur les tolérances de règlement multiples 1a":::

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="2-payment-date-is-between-011603-and-011703-scenarios-4-9"></a>(2) La date de règlement est comprise entre le 16/01/03 et le 17/01/03 (scénarios 4-9).  
Montant ouvert par  

Règles d'affectation normales  

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv1-2.gif" alt-text="Règles sur les tolérances de règlement multiples 2":::

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="3-payment-date-is-between-011803-and-012003-scenarios-10-21"></a>(3) La date de règlement est comprise entre le 18/01/03 et le 20/01/03 (scénarios 10-21).  
Montant ouvert par  

Règles d'affectation normales  

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv1.gif" alt-text="Règles sur les tolérances de règlement multiples 3":::

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="4-payment-date-is-between-012103-and-012203-scenarios-22-27"></a>(4) La date de règlement est comprise entre le 21/01/03 et le 22/01/03 (scénarios 22-27).  
Montant ouvert par  

Règles d'affectation normales  

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv2.gif" alt-text="Règles sur les tolérances de règlement multiples 4":::

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="5-payment-date-is-after-012203-scenarios-28-30"></a>(5) La date de règlement est située après le 22/01/03 (scénarios 28-30).  
Montant ouvert par  

Règles d'affectation normales  

:::image type="content" source="media/multiplePmtTolRules_Post0122.gif" alt-text="Règles sur les tolérances de règlement multiples 5":::

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.

## <a name="see-also"></a>Voir aussi  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]