---
title: "Tolérance de règlement et tolérance d'escompte de paiement | Microsoft Docs"
description: "Vous pouvez configurer la tolérance de règlement de manière à fermer une facture lorsque le paiement ne couvre pas entièrement le montant de la facture."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/10/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 434e18ed539a189e8f041c914cfdcdf2c1e0532f
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-work-with-payment-tolerances-and-payment-discount-tolerances"></a>Procédure : Utilisation des tolérances de règlement et des tolérances d'escompte de paiement
Vous pouvez configurer une tolérance de règlement de manière à fermer une facture lorsque le paiement ne couvre pas entièrement le montant de la facture. Vous pouvez configurer une tolérance d'escompte de paiement pour accorder un escompte de paiement après expiration de la date d'escompte de paiement.  

Vous pouvez utiliser les tolérances de règlement pour qu'une tolérance de règlement maximum autorisée soit définie pour chaque montant restant dû. Si la tolérance de règlement est respectée, le montant règlement est analysé. Si le montant règlement est un moins-perçu, alors le montant en commande est totalement fermé par le moins-perçu. Une écriture détaillée est reportée dans l'écriture règlement de sorte qu'il ne subsiste aucun montant ouvert dans l'écriture facture affectée. Si le montant règlement est un trop-perçu, alors une nouvelle écriture détaillée est reportée dans l'écriture règlement de sorte qu'il ne subsiste aucun montant ouvert dans l'écriture règlement.

Vous pouvez utiliser des tolérances d'escompte de paiement au cas où vous accepteriez un escompte de paiement après la date d'escompte de paiement. Il sera alors toujours reporté dans le compte escompte de paiement ou dans un compte tolérance de règlement.

## <a name="applying-payment-tolerance-to-multiple-documents"></a>Application de la tolérance de règlement à plusieurs documents  
Un document unique comporte la même tolérance de règlement, qu'il soit affecté seul ou avec d'autres documents. L'acceptation d'un escompte de paiement en retard, lorsque vous appliquez la tolérance de règlement à plusieurs documents, se produit automatiquement pour chaque document où la règle suivante est vraie :  

*date d'escompte < date de règlement dans l'écriture sélectionnée <= date d'écart de règlement*  

Cette règle détermine également la nécessité d'afficher des alertes lorsque vous affectez la tolérance de règlement à plusieurs documents. L'avertissement lié à la tolérance d'escompte de paiement s'affiche pour chaque écriture répondant aux critères de date. Pour plus d'informations, reportez-vous à la section « Exemple 2 - Calculs de la tolérance pour plusieurs documents ». 

Vous pouvez afficher une alerte en fonction des situations relatives à la tolérance.  

- Le premier avertissement concerne la tolérance d'escompte de paiement. Vous êtes informé que vous pouvez accepter un escompte de paiement en retard. Vous pouvez ensuite décider s'il faut accepter la tolérance sur la date d'escompte.  
- Le second avertissement concerne la tolérance de règlement. Vous êtes informé que toutes les écritures peuvent être fermées car la différence est inférieure à la tolérance de règlement maximum pour les écritures affectées. Vous pouvez ensuite décider s'il faut accepter la tolérance sur le montant du paiement.

Pour plus d'informations, voir la section « Pour activer ou désactiver les alertes de tolérance de règlement ».     

## <a name="to-set-up-tolerances"></a>Pour configurer les écarts  
Le fait de configurer des tolérances pour la date ou le montant permet de fermer une facture alors que le règlement ne couvre pas le montant indiqué sur la facture, que ce soit parce que la date d'échéance de l'escompte de paiement est dépassée ou que des marchandises ont été déduites, ou suite à une erreur anodine. Ceci est également vrai pour les remboursements et les notes de crédit.  

Pour configurer l'écart, vous devez configurer plusieurs comptes écart, spécifier des méthodes de comptabilisation d'écart escompte et d'écart règlement, puis exécuter le traitement par lots **Modifier écart de règlement**.  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration report général**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Configuration report général**, configurez un compte tolérance règlement crédit et débit pour les ventes et un autre pour les achats.  
3. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes de report du client**, puis sélectionnez le lien associé.    
4. Dans la fenêtre **Groupes de report du client**, configurez un compte tolérance règlement débit et un compte tolérance règlement crédit. Pour plus d'informations, voir [Configuration de groupes de report](finance-posting-groups.md).  
5. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration report fournisseur**, puis choisissez le lien associé.  
6. Dans la fenêtre **Groupes de report du fournisseur**, configurez un compte tolérance règlement débit et un compte tolérance règlement crédit.  
7. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres comptabilité**, puis sélectionnez le lien connexe.  
8. Ouvrez la fenêtre **Configuration du grand livre**.  
9. Sur le raccourci **Application**, renseignez les champs **Validation écart d'escompte**, **Période carence escompte** et **Validation écart de règlement**.   
10. Choisissez l'action **Modifier la tolérance de règlement**.
11. Dans la fenêtre **Modifier la tolérance de règlement**, renseignez les champs **% tolérance de règlement** et **Montant tolérance règlement max.**, puis cliquez sur le bouton **OK**.

> [!IMPORTANT]  
>  Vous n'avez configuré la tolérance que pour la devise locale. Si vous souhaitez que [!INCLUDE[d365fin](includes/d365fin_md.md)] gère la tolérance pour les paiements, les notes de crédit et les remboursements en devise étrangère, vous devez exécuter le traitement en lot **Modifier la tolérance de paiement** avec une valeur dans le champ **Code devise**.  

> [!NOTE]  
>  Si vous souhaitez recevoir une alerte tolérance de règlement chaque fois que vous reportez une affectation dans la tolérance, vous devez activer l'avertissement tolérance de règlement. Pour plus d'informations, voir la section « Pour activer ou désactiver les alertes de tolérance de règlement ».  
>   
>  Pour désactiver la tolérance pour un client ou un fournisseur, vous devez bloquer les tolérances sur la fiche client ou fournisseur correspondante. Pour plus d'informations, voir la section « Pour bloquer la tolérance de règlement pour des clients ».  
>   
>  Lorsque vous configurez un écart, [!INCLUDE[d365fin](includes/d365fin_md.md)] vérifie s'il existe des écritures ouvertes et calcule l'écart pour ces écritures.

## <a name="to-enable-or-disable-payment-tolerance-warnings"></a>Pour activer ou désactiver les alertes de tolérance de règlement
L'avertissement de tolérance de règlement apparaît lorsque vous reportez une affectation dont le solde respecte la tolérance autorisée. Vous pouvez alors choisir comment reporter et journaliser le solde.    
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres comptabilité**, puis sélectionnez le lien connexe.  
2. Dans la fenêtre **Paramètres comptabilité**, sur le raccourci **Application**, cochez la case **Alerte écart de règlement** pour activer l'alerte. Pour désactiver l'alerte, désactivez la case à cocher.  

> [!NOTE]  
>  L'option par défaut de la fenêtre **Alerte écart de règlement** est **Laisser le solde ouvert**. L'option par défaut de la fenêtre **Alerte écart d'escompte** est **Ne pas accepter d'escompte tardif**.

## <a name="to-block-payment-tolerance-for-customers"></a>Pour bloquer la tolérance de règlement pour des clients  
Par défaut, une tolérance de règlement est accordée. Pour ne pas accorder une tolérance de règlement à un certain client ou fournisseur, vous devez bloquer la tolérance sur la fiche fournisseur ou client appropriée. Ce qui suit décrit comment l'exécuter pour un client. La procédure est identique pour un fournisseur.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Client** ou **Fournisseur**, puis sélectionnez le lien connexe.  
2. Sur le raccourci **Paiements**, cochez la case **Bloquer écart de règlement**.  

> [!NOTE]  
>  Si le client ou le fournisseur possède des écritures ouvertes, vous devez d'abord supprimer la tolérance de règlement des écritures actuellement ouvertes.

## <a name="example-1---tolerance-calculations-for-a-single-document"></a>Exemple 1 - Calculs de la tolérance pour un seul document
Voici quelques exemples de scénarios illustrant les calculs et reports de tolérance qui sont effectués dans différentes situations.  

La fenêtre **Configuration grand livre** contient les paramètres suivants :
- Délai de grâce escompte de paiement : 5D  
- Tolérance de règlement max : 5  

Scénarios comportant deux alternatives, A et B. En voici la signification :  

- **A** L'avertissement tolérance d'escompte de paiement a été désactivé OU l'avertissement est activé, mais l'utilisateur a accepté l'escompte de paiement en retard (Reporter le solde en tant que tolérance de paiement).  
- **B** L'avertissement est activé et l'utilisateur a choisi de ne pas accepter l'escompte de paiement en retard (Laisser le solde ouvert).  

|—|Fact.|Escompte de paiement|Max<br /><br /> Tolérance règlement|Date d'escompte de paiement|Tolérance d'escompte de paiement Date|Date de paiement|Règl.|Type de tolérance|Toutes les écritures fermées|Tolérance d'escompte de paiement <br /> Cpta/CL|Règl.<br /><br /> Tolérance<br /><br /> Grand livre|  
|-------|----------|----------------|-----------------------|---------------------|--------------------------|------------------|----------|--------------------|------------------------|------------------------------|----------------------------|  
|1|1,000|2.0|5|01/15/03|01/20/03|<=15/01/03|985|Tolérance règlement|Oui|0|-5|  
|2|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**<=15/01/03**|**980**|**Aucun**|**Oui**|**0**|**0**|  
|3|1,000|2.0|5|01/15/03|c|<=15/01/03|975|Tolérance règlement|Oui|0|5|  
|4A|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|1005|Tolérance d'escompte de paiement|Non, 25 sur Règl.|20/-20|0|  
|5A|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|1000|Tolérance d'escompte de paiement|Non, 20 sur Règl.|20/-20|0|  
|6A|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|995|Tolérance d'escompte de paiement|Non, 15 sur Règl.|20/-20|0|  
|4B|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|1005|Tolérance règlement|Oui|0|-5|  
|**5B**|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**16/01/03 20/01/03**|**1000**|**Aucun**|**Oui**|**0**|**0**|  
|6B|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|995|Tolérance règlement|Oui|0|5|  
|7|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|985|Tolérance d'escompte de paiement & Écart règlement|Oui|20/-20|-5|  
|8|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|980|Tolérance d'escompte de paiement|Oui|20/-20|0|  
|9|1,000|2.0|5|01/15/03|01/20/03|16/01/03 20/01/03|975|Tolérance d'escompte de paiement & Écart règlement|Oui|20/-20|5|  
|10|1,000|2.0|5|01/15/03|01/20/03|>20/01/03|1005|Tolérance règlement|Oui|0|-5|  
|**11**|**1,000**|**20**|**5**|**15/01/03**|**20/01/03**|**>20/01/03**|**1000**|**Aucun**|**Oui**|**0**|**0**|  
|12|1,000|2.0|5|01/15/03|01/20/03|>20/01/03|995|Tolérance règlement|Oui|0|5|  
|13|1,000|2.0|5|01/15/03|01/20/03|>20/01/03|985|Aucun|Non, 15 sur la facture|0|0|  
|14|1,000|2.0|5|01/15/03|01/20/03|>20/01/03|980|Aucun|Non, 20 sur la facture|0|0|  
|15|1,000|2.0|5|01/15/03|01/20/03|>20/01/03|975|Aucun|Non, 25 sur la facture|0|0|  

### <a name="payment-range-diagrams"></a>Schémas de chaîne de paiement  
Sur la base du scénario ci-avant, les diagrammes des plages de dates de règlement se présentent sous la forme suivante :  

#### <a name="1-payment-date-011503-scenarios-1-3"></a>(1) Date de règlement <=15/01/03 (scénarios 1-3)  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement uniques &#40;before 03&#47;15&#41;](media/singlePmtTolRules(Pre1503).gif "singlePmtTolRules(Pre1503)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="2-payment-date-is-between-011603-and-012003-scenarios-4-9"></a>(2) La date de règlement est comprise entre le 16/01/03 et le 20/01/03 (scénarios 4-9).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement uniques &#40;grace period&#41;](media/singlePmtTolRules(GracePeriod).gif "singlePmtTolRules(GracePeriod)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="3-payment-date-is-after-012003-scenarios-10-15"></a>(3) La date de règlement est située après le 20/01/03 (scénarios 10-15).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement uniques &#40;before 01&#47;20&#41;](media/singlePmtTolRules(Post0120).gif "singlePmtTolRules(Post0120)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

## <a name="example-2---tolerance-calculations-for-multiple-documents"></a>Exemple 2 - Calculs de la tolérance pour plusieurs documents
Voici quelques exemples de scénarios illustrant les calculs et reports de tolérance qui sont effectués dans différentes situations. Ces exemples sont simplement des scénarios qui entraînent la fermeture de toutes les écritures dans l'application.  

La fenêtre **Configuration grand livre** contient les paramètres suivants :
- Délai de grâce escompte de paiement 5D  
- Tolérance de règlement max 5  

Scénarios comportant deux alternatives, A, B, C ou D. En voici la signification :  

- **A** L'avertissement tolérance d'escompte de paiement a été désactivé OU l'avertissement est activé, mais l'utilisateur a accepté l'escompte de paiement en retard (Reporter en tant que tolérance) pour toutes les factures.  
- **B** L'avertissement est activé et l'utilisateur a choisi de n'accepter l'escompte de paiement en retard pour aucune des factures.  
- **C** : L'avertissement est activé et l'utilisateur a choisi d'accepter l'escompte de paiement en retard pour la première facture, mais non pour la deuxième.  
- **D** : L'avertissement est activé et l'utilisateur a choisi de ne pas accepter l'escompte de paiement en retard pour la première facture, mais de l'accepter pour la seconde.  

|—|Fact.|Escompte|Tolérance règlement max.|Date d'escompte de paiement|Tolérance d'escompte de paiement Date|Date de paiement|Règl.|Type de tolérance|Toutes les écritures fermées|Tolérance d'escompte de paiement <br /> Cpta/CL|Tolérance règlement<br /><br /> Grand livre|  
|-------|----------|---------------|-------------------|---------------------|--------------------------|------------------|---------|--------------------|------------------------|------------------------------|------------------------|  
|1|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|<=15/01/03|1920|Tolérance règlement|Oui|0<br /><br /> 0|-5 <br />-5|  
|**2**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**<=15/01/03**|**1910**|**Aucun**|**Oui**|**0**<br /><br /> **0**|0 <br />0|  
|3|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|<=15/01/03|1900|Tolérance règlement|Oui|0<br /><br /> 0|5 <br />5|  
|4B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1980|Tolérance règlement|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**5B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**16/01/03 17/01/03**|**1970**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|6B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1960|Tolérance règlement|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|7A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1920|Tolérance d'escompte de paiement & Écart règlement|Oui|60/60<br /><br /> 0/0|-5 <br />-5|  
|8A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1910|Tolérance d'escompte de paiement|Oui|60/60<br /><br /> 0/0|0 <br />0|  
|9A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|16/01/03 17/01/03|1900|Tolérance d'escompte de paiement & Écart règlement|Oui|60/60|5 <br />5|  
|10B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|2010|Tolérance règlement|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**11B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**18/01/03 20/01/03**|**2000**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|12B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1990|Tolérance règlement|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|13D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1980|Tolérance d'escompte de paiement & Écart règlement|Oui|0/0<br /><br /> 30/-30|-5 <br />-5|  
|14D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1970|Tolérance d'escompte de paiement|Oui|0/0<br /><br /> 30/-30|0 <br />0|  
|15D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1960|Tolérance d'escompte de paiement & Écart règlement|Oui|0/0<br /><br /> 30/-30|5 <br />5|  
|16D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1950|Tolérance d'escompte de paiement & Écart règlement|Oui|60/-60<br /><br /> 0/0|-5 <br />-5|  
|17D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1940|Tolérance d'escompte de paiement|Oui|60/-60<br /><br /> 0/0|0 <br />0|  
|18D|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1930|Tolérance d'escompte de paiement & Écart règlement|Oui|60/-60<br /><br /> 0/0|5 <br />5|  
|19A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1920|Tolérance d'escompte de paiement & Écart règlement|Oui|60/-60<br /><br /> 30/-30|-5 <br />-5|  
|20A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1910|Tolérance d'escompte de paiement|Oui|60/-60<br /><br /> 30/-30|0 <br />0|  
|21A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|18/01/03 20/01/03|1900|Tolérance d'escompte de paiement & Écart règlement|Oui|60/-60<br /><br /> 30/-30|5 <br />5|  
|22B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|2010|Tolérance règlement|Oui|0<br /><br /> 0|-5<br /><br /> -5|  
|**23B**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**21/01/03 22/01/03**|**2000**|**Aucun**|**Oui**|**0**<br /><br /> **0**|**0**<br /><br /> **0**|  
|24B|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1990|Tolérance règlement|Oui|0<br /><br /> 0|5<br /><br /> 5|  
|25A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1980|Tolérance d'escompte de paiement & Écart règlement|Oui|0/0<br /><br /> 30/30|-5 <br />-5|  
|26A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1970|Tolérance d'escompte de paiement|Oui|0/0<br /><br /> 30/30|0 <br />0|  
|27A|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|21/01/03 22/01/03|1960|Tolérance d'escompte de paiement & Écart règlement|Oui|0/0<br /><br /> 30/30|5 <br />5|  
|28|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|>22/01/03|2010|Tolérance règlement|Oui|0|-5|  
|**29**|**1,000** <br />**1,000**|**60** <br />**30**|**5** <br />**5**|**15/01/03** <br />**17/01/03**|**20/01/03** <br />**22/01/03**|**>22/01/03**|**2000**|**Aucun**|**Oui**|**0**|**0**|  
|30|1,000 <br />1,000|60 <br />30|5 <br />5|01/15/03 <br />01/17/03|01/20/03 <br />01/22/03|>22/01/03|1990|Tolérance règlement|Oui|0|5|  

### <a name="payment-range-diagrams"></a>Schémas de chaîne de paiement  
Sur la base du scénario ci-avant, les diagrammes des plages de dates de règlement se présentent sous la forme suivante :  

#### <a name="1-payment-date-011503-scenarios-1-3"></a>(1) Date de règlement <=15/01/03 (scénarios 1-3)  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement multiples &#40;before 03&#47;15&#41;](media/multiplePmtTolRules(Pre1503).gif "multiplePmtTolRules(Pre1503)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="2-payment-date-is-between-011603-and-011703-scenarios-4-9"></a>(2) La date de règlement est comprise entre le 16/01/03 et le 17/01/03 (scénarios 4-9).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement multiples &#40;grace period&#41;](media/multiplePmtTolRules(GracePeriodInv1).gif "multiplePmtTolRules(GracePeriodInv1)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="3-payment-date-is-between-011803-and-012003-scenarios-10-21"></a>(3) La date de règlement est comprise entre le 18/01/03 et le 20/01/03 (scénarios 10-21).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement multiples &#40;grace period&#41;](media/multiplePmtTolRules(GracePeriodInv1-2).gif "multiplePmtTolRules(GracePeriodInv1-2)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="4-payment-date-is-between-012103-and-012203-scenarios-22-27"></a>(4) La date de règlement est comprise entre le 21/01/03 et le 22/01/03 (scénarios 22-27).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement multiples &#40;grace period&#41;](media/multiplePmtTolRules(GracePeriodInv2).gif "multiplePmtTolRules(GracePeriodInv2)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.  

#### <a name="5-payment-date-is-after-012203-scenarios-28-30"></a>(5) La date de règlement est située après le 22/01/03 (scénarios 28-30).  
Montant ouvert par  

Règles d'affectation normales  

![Règles sur les écarts de règlement multiples &#40;after 01&#47;22&#41;](media/multiplePmtTolRules(Post0122).gif "multiplePmtTolRules(Post0122)")  

(1) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation peuvent être fermées avec ou sans tolérance.  

(2) Si le paiement intervient dans l'une de ces plages, toutes les écritures affectation ne peuvent pas être fermées, même avec tolérance.

## <a name="see-also"></a>Voir aussi  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

