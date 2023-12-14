---
title: Configurer des devises
description: Vous devez configurer chaque devise si vous achetez ou vendez avec des devises autres que votre devise locale ($) ou si vous enregistrez des transactions GL dans différentes devises.
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: multiple currencies
ms.search.form: '5, 118'
ms.date: 03/15/2022
ms.author: bholtorf
---
# Configurer des devises

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Utilisez un service externe pour obtenir les derniers taux de change des devises dans la liste **Devises**. Pour plus d'informations, reportez vous à [Configurer un service de taux de change des devises](finance-how-update-currencies.md#set-up-a-currency-exchange-rate-service).  

[!INCLUDE [finance-currencies-lcy](includes/finance-currencies-lcy-note.md)]

## <a name="curr"></a>Devises

Le tableau suivant décrit les champs de la liste **Devises**.

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
|**Différence TVA max. autorisée**|Montant maximum autorisé pour les différences de TVA dans cette devise. Pour plus d’informations, consultez [Correction manuelle des montants de TVA dans des documents achat et vente](finance-work-with-vat.md#correcting-vat-amounts-manually-on-sales-and-purchase-documents). Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|
|**Type arrondissement TVA**|Spécifie la méthode d’arrondissement pour corriger manuellement les montants TVA dans les documents vente et achat. Par défaut, ce champ peut ne pas être visible. Il peut être récupéré en personnalisant la page.|

### Fonctions de devise disponibles

Le tableau suivant décrit les actions clés sur la page **Devises**.  

|Menu|Action|Description|
|-------------|--------------|------------------------------|
|**Traitement**|**Proposer des comptes**|Utilisez des comptes des autres devises. Les comptes les plus fréquemment utilisés seront insérés.|
||**Modifier la tolérance de règlement**|Modifiez la tolérance de règlement maximum, le pourcentage de tolérance de règlement ou les deux, et filtrez par devise. Pour plus d’informations, consultez [Tolérance de règlement et tolérance d’escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md).|
||**Taux de change**|Affichez les taux de change mis à jour pour les devises que vous utilisez.|
||**Ajuster taux de change**|Ajuster les écritures GL, client, fournisseur et compte bancaire pour obtenir un solde mis à jour si le taux de change a évolué depuis le report des écritures.|
||**Registre d’ajustement du taux de change**|Affichez les résultats de l’exécution du traitement en lot **Ajuster taux de change**. Une ligne est créée pour chaque devise et pour chaque combinaison de devise et de groupe de report comprise dans l’ajustement.|
|**Service de taux de change**|**Services de taux de change**|Affichez ou modifiez la configuration des services qui sont paramétrés pour extraire les taux de change de devise mis à jour lorsque vous sélectionnez l’action **Mettre à jour les taux de change**.|
||**Mettre à jour les taux de change**|Obtenez les récents taux de change des devises auprès d’un fournisseur de services.|
|**Rapports**|**Solde devise étrangère**|Affichez les soldes de tous les clients et fournisseurs en devise étrangère et en devise locale ($). Le rapport affiche deux soldes en $. L’un correspond au solde en devise étrangère converti en $ en utilisant le taux de change en vigueur au moment de la transaction. L’autre correspond au solde en devise étrangère converti en $ en utilisant le taux de change à la date de travail.|

## $ et autres devises

[!INCLUDE [finance-currencies-lcy-def](includes/finance-currencies-lcy-def.md)]

## Arrondissement des devises

Pour gérer les devises qui n’utilisent pas de décimales et pour éviter l’emploi de décimales inutiles dans les devises étrangères, vous pouvez utiliser deux fonctions d’arrondissement différentes :

- Arrondissement montant unité  

- Arrondissement montant  

Ces fonctions peuvent fonctionner indépendamment ou conjointement. En outre, les fonctions peuvent fonctionner avec l’arrondissement facture.

Contrairement aux fonctions arrondissement facture, les fonctions arrondissement montant et arrondissement montant unité affectent uniquement les comptes en devise étrangère et non les montants correspondants en $. Ces deux fonctions n’entraînent pas de report dans les comptes GL. C’est pourquoi aucun compte GL ne doit être spécifié dans les groupes de report ou dans d’autres emplacements.

### Arrondissement montant unité

La fonction arrondissement montant unité contrôle la manière dont les prix de vente des articles et ressources en devises étrangères sont arrondis sur les lignes vente et achat. Vous devez spécifier les règles de chaque devise séparément dans le champ **Précis. arrondissement montant unité** de la liste **Devises**.

La fonction arrondissement du montant unité est utilisée automatiquement chaque fois que vous saisissez un article ou un numéro de ressource sur une ligne vente. Si la facture est pour un client avec un code devise, le prix des articles et des ressources est converti dans la devise du client. Le prix est arrondi en fonction de la précision d’arrondissement du montant unité de la devise.

### Arrondissement montant

La fonction arrondissement montant contrôle la manière dont les montants en devises étrangères sont arrondis sur les lignes journal général, vente et achat. Vous devez spécifier les règles de chaque devise séparément dans le champ **Précis. arrondissement montant** de la liste **Devises**.

Les montants en devises étrangères sont arrondis lorsque vous renseignez et reportez les lignes journal général, vente et achat.

## Taux de change

Vous pouvez enregistrer les taux de change de chaque devise étrangère et spécifier les dates à partir desquelles ces taux sont valables. Par exemple, vous pouvez saisir le taux de change pour chaque devise tous les jours, tous les mois ou tous les trimestres.

Vous pouvez conserver les taux de change historiques sur la page **Taux de change devise** à titre de référence. Lorsque vous avez besoin de mettre à jour les taux de change, vous pouvez utiliser le bouton **Mettre à jour les taux de change** pour obtenir les derniers taux de change de la part d’un fournisseur de service externe.

## Comptes GL

Vous ne pouvez pas associer de codes devise aux comptes GL car les montants de ces derniers sont en $. Si vous disposez d’un prêt bancaire en USD et placez des acomptes dans un compte bancaire en SEK, vous pouvez suivre ces comptes en configurant les comptes bancaires en USD et SEK. Avec les groupes de report, vous pouvez associer les comptes aux comptes GL appropriés. Dans le grand livre, la valeur des montants est indiquée en $.

Vous pouvez entrer un code devise sur une ligne journal général et reporter celle-ci dans un compte GL. Le taux de change adéquat permet de convertir le montant en $ avant son report dans le compte GL.  

## Exemple de transaction en devise comptabilité

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Voir aussi

[Mettre à jour des taux de change devise](finance-how-update-currencies.md)  
[Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
