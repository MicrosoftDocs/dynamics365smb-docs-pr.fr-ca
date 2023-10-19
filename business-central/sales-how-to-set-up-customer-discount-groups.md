---
title: Configurer des groupes escomptes client
description: Découvrez comment configurer des groupes escomptes client et créer des escomptes ligne vente pour ces groupes.
author: brentholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 06/08/2022
ms.author: bholtorf
---
# <a name="set-up-customer-discount-groups"></a>Configurer des groupes escomptes client

Vous pouvez définir des escomptes ligne vente pour un groupe de clients au lieu de les appliquer individuellement.

Les **groupes escomptes client** fonctionnent de la même manière que les [groupes tarifs client](sales-how-to-set-up-customer-price-groups.md), mais peuvent être combinés avec des groupes escomptes article pour définir rapidement des escomptes ligne sur de nombreux articles pour des clients sélectionnés.

## <a name="create-sales-line-discounts-for-a-customer-group"></a>Créer des escomptes ligne vente pour un groupe de clients

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes escomptes client**, puis sélectionnez le lien associé.
2. Sur la page **Groupes escomptes client**, sélectionnez **Nouveau** pour créer un groupe d'escomptes et lui donner un nom dans la colonne **Code** et ajoutez une description.
3. Sélectionnez l’action **Naviguer** et choisissez **Escomptes ligne vente**.
4. Remplissez la colonne **Code vente** avec le groupe escomptes que vous avez créé à la page précédente.
5. Dans les champs des différentes lignes, renseignez les valeurs pour **Type** (Article ou groupe escomptes article), **Code**, **Code d'unité de mesure** et **% escompte ligne**.
6. Si le groupe de clients doit acheter une quantité minimum pour bénéficier de l'escompte, renseignez le champ **Quantité minimum**.
7. Si nécessaire, saisissez la **Date début** et la **Date fin** pour le groupe d'escomptes.
8. Le cas échéant, vous pouvez également spécifier le **Code devise** ou le **Code variante** après [avoir personnalisé les colonnes](ui-personalization-user.md).

Répétez les étapes 4 à 8 pour chacun des articles ou chacun des groupes escomptes article pour lesquels vous souhaitez créer un escompte ligne vente.

## <a name="assign-a-customer-to-a-discount-group"></a>Affecter un client à un groupe d'escomptes

Une fois ces groupes escomptes client configurés, vous pouvez entrer les codes groupe escomptes client sur les fiches client.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction de recherche 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la **fiche client** correspondant au client que vous voulez associer à un groupe escomptes client.
3. Sur le raccourci **Facturation**, dans le champ **Groupe escomptes client**, sélectionnez le code groupe.

## <a name="see-also"></a>Voir aussi .

[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Enregistrement des prix de vente spéciaux et des escomptes](sales-how-record-sales-price-discount-payment-agreements.md)  
[Configuration de groupes tarifs client](sales-how-to-set-up-customer-price-groups.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
