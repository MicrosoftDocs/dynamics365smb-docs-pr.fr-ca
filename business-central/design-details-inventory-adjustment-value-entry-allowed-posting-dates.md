---
title: "Message d’erreur\_: «\_La date de report n’est pas incluse dans la plage de dates de report autorisées\_»"
description: "Résolvez l’erreur sous-jacente au message «\_La date de report n’est pas incluse dans la plage de dates de report autorisées\_» lorsque vous exécutez le traitement en lot Ajuster coûts\_: Écr. article."
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 09/17/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# <a name="error-message-posting-date-is-not-within-your-range-of-allowed-posting-dates"></a>Message d’erreur : « La date de report n’est pas incluse dans la plage de dates de report autorisées... »

Lors de l’utilisation du traitement en lot **Ajuster coûts : Écr. article**, vous pouvez rencontrer le message d’erreur suivant :

**La date de report n’est pas dans votre plage de dates de report autorisées**

Ce message d’erreur indique que l’utilisateur n’est pas autorisé à reporter des écritures pour la date en question, et cela peut être résolu en modifiant la configuration utilisateur.

## <a name="change-the-user-setup"></a>Modifier la configuration utilisateur

|Code utilisateur  |Début période report  | Fin période report  |
|---------|---------|--------|
|EUROPE  |  2020/09/11      |2020/09/30      |

L’utilisateur dans ce cas a une plage de dates de report autorisées allant du 11 au 30 septembre et n’est donc pas autorisé à reporter l’écriture valeur d’ajustement avec la date de report du 10 septembre.  

### <a name="overview-of-the-posting-date-setup"></a>Aperçu de la configuration de la date de report impliquée

#### <a name="inventory-periods"></a>Périodes d'inventaire

|Date de fin  |Nom  |Fermé  |
|---------|---------|---------|
|2020/01/31     |2020 janvier      |  Oui    |
|2020/02/28     |Février 2020     |  Oui    |
|2020/03/31     |Mars 2020        |  Oui    |
|2020/04/30     |Avril 2020        |  Oui    |
|2020/05/31     |Mai 2020        |  Oui    |
|2020/06/30     |Juin 2020       |  Oui    |
|2020/07/31     |Juillet 2020        |   Oui   |
|2020/08/31     |Août 2020     |   Oui   |
|2020/09/30     |Septembre 2020  |         |
|2020/10/31     |Octobre 2020    |         |
|2020/11/30     |Novembre 2020   |         |
|2020/12/31     |Décembre 2020   |         |  

#### <a name="general-ledger-setup"></a>Configuration du grand livre

|Champ|Valeur|
|---------|---------|
|Début période report :  |  2020/09/10      |
|Fin période report :    |  2020/09/30      |
|Registre temps :       |         |
|Format adresse local :|   Code postal      |  

#### <a name="user-setup"></a>Configuration utilisateur

|Code utilisateur  |Début période report  | Fin période report  |
|---------|---------|--------|
|USERNAME |  2020/09/10      |2020/09/30      |

En attribuant une plage de dates de report autorisée plus large que dans la période d'inventaire ou la configuration du grand livre, il devient possible d’éviter le conflit à l’origine du message d’erreur. L’écriture valeur d’ajustement avec la date de report du 10 septembre sera reportée avec succès avec cette configuration.
  
## <a name="see-also"></a>Voir aussi

[Détails de conception : date de report de l'écriture valeur d'ajustement](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : Affectation article](design-details-item-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
