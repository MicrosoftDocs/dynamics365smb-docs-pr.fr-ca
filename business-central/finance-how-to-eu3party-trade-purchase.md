---
title: Transactions d’achat tripartite UE
description: Cet article explique comment configurer et utiliser les transactions d’achat auprès de tiers dans l’Union européenne (UE).
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.form: '50, 51, 52, 187, 317'
ms.search.keywords: 'EU3P, EU 3-P, EU 3-Party'
ms.date: 07/05/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="eu-third-party-purchase-transactions"></a>Transactions d’achat tripartite UE

Le commerce avec des tiers de l’Union européenne (UE) se produit lorsque vous recevez une facture achat d’un client dans un pays/une région de l’UE et que les produits sont envoyés dans un autre pays/une autre région de l’UE sans entrer dans le pays de résidence. Le montant de la transaction peut être identifié et déclaré séparément pour se conformer aux exigences de déclaration de la taxe sur la valeur ajoutée (TVA) et du système d’échange d’informations sur la TVA (VIES) de certains pays/régions de l’UE. Microsoft Dynamics 365 Business Central permet de configurer les transactions d’achat en tant que transactions tripartite UE. Les transactions de tiers de l’UE reportées peuvent être filtrées dans les relevés fiscaux et exclues du montant dans la colonne **Ventes au client** du rapport **TVA - Décl. intracommunautaire**.

Même si la fonctionnalité est préinstallée en tant qu’extension, elle n’est pas activée par défaut. Procédez comme suit pour activer la fonctionnalité.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") accédez à l’espace de travail **Gestion des fonctionnalités** et sélectionnez le lien associé.
2. Dans la liste, trouvez et sélectionnez **Mise à jour des fonctionnalités : Remplacez la fonctionnalité de transaction d’achat tripartite UE existante par la nouvelle extension de transaction d’achat tripartite UE**.
3. Dans la colonne **Activé pour**, sélectionnez **Tous les utilisateurs**.

> [!NOTE]
> Si vous utilisez la localisation allemande ou italienne, vous ne pourrez pas activer cette application car elle n’est pas compatible avec certaines fonctionnalités de TVA dans ces localisations.  

## <a name="enable-eu-third-party-trade-functionality-for-a-purchase"></a>Activer la fonctionnalité de transaction tripartite UE pour un achat

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration TVA**, puis sélectionnez le lien associé.
2. Sur la page **Configuration de la TVA**, cochez le champ **Activer l’achat tripartite UE**.

## <a name="use-eu-third-party-trade-functionality"></a>Utiliser la fonctionnalité de transaction tripartite UE

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Facture achat** (ou tout autre document achat), puis sélectionnez le lien associé.
2. Sélectionnez une facture achat existante ou sélectionnez **Nouveau** pour en créer une.
3. Dans l’onglet **Détails de la facture**, cochez la case **Transaction tripartite UE**.
4. Sélectionnez **OK**.

## <a name="include-or-exclude-eu-third-party-trade-records-on-the-vat-statement"></a>Inclure ou exclure les enregistrements de transaction tripartite UE sur le relevé fiscal

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Relevé fiscal**, puis sélectionnez le lien associé.
2. Sur la page **Relevé fiscal**, sélectionnez l’une des options suivantes pour afficher les enregistrements de transaction tripartite UE à l’aide du champ **Filtre de transaction tripartite UE**.

    | Option | Désignation |
    |--------|-------------|
    | Tout | Afficher tous les enregistrements, que le champ **Transaction tripartite UE** dans les documents ait été coché ou non. |
    | UE3 | Afficher uniquement les enregistrements où le champ **Transaction tripartite UE** dans les documents a été coché. |
    | Non tripartite UE | Afficher uniquement les enregistrements où le champ **Transaction tripartite UE** dans les documents n’a pas été coché. |


## <a name="see-also"></a>Voir aussi .
[Gestion financière](finance.md)  
[Utiliser Business Central](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
