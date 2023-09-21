---
title: Variantes
description: Procédure pas à pas pour savoir comment mettre à jour la prévision de la demande pour chaque variante d’un produit dans Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
author: brentholtorf
ms.author: bholtorf
---

# Procédure pas à pas : variantes

Dans cet article, nous vous expliquons comment utiliser les données de démonstration de Contoso Coffee pour en savoir plus sur les variantes.

## Scénario

Vous êtes planificateur de production chez Contoso Coffee. Vous devez mettre à jour la prévision de la demande pour chaque variante de l’article SP-SCM1006, AutoDripLite. Comme les couleurs sont différentes, vous devez vous assurer que la bonne nomenclature (BOM) est utilisée pour chaque variante. Exécutez la feuille planification pour calculer l’approvisionnement.  

## Étapes

1. Configurez les unités de stock pour l’article SP-SCM1006, AutoDripLite. Attribuez une nomenclature pour l'unité de stock avec les variantes ROUGE et BLANC.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez *articles*, puis choisissez le lien associé.  

    2. Ouvrez l’élément **SP-SCM1006, AutoDripLite**.

    3. Choisissez l'action **Créer unité de stock**.  

    4. Définissez le champ **Créer par** sur *Emplacement et variante*.

    5. Définissez un filtre pour l'emplacement sur *Nord*, puis cliquez sur le bouton **OK**.

    6. Choisissez l’action **Unités de stock**.  

    7. Mettez à jour les nomenclatures de production pour les unités de stockage suivantes :

        1. ROUGE sur NORD, définissez SP-SCM1006-RED  

        2. BLANC sur NORD, définissez SP-SCM1006-WHITE  

        3. Gardez le numéro de nomenclature de production vide pour NOIR sur NORD  

2. Mettez à jour la configuration production et respectez les prévisions de demande sur les emplacements et les variantes.  

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez *Configuration production*, puis choisissez le lien associé.  

    2. Activez le champ **Prévision sur emplacement**.

    3. Activez le champ **Utiliser prévisions sur variantes**.

    4. Fermez la fenêtre **Configuration production**.

3. Créez une prévision de la demande mensuelle, *AUTODRIP*. Filtrez-la par l’article SP-SCM1006 et l'emplacement NORD. Définissez la demande pour Mai pour chaque variante. 

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez *Prévision de la demande*, puis sélectionnez le lien associé.

    2. Créez une prévision de la demande et nommez-la *AUTODRIP*.

    3. Choisissez l’action **Modifier la prévision de la demande**.

    4. Dans le champ **Afficher par**, sélectionnez *Mois*.

    5. Dans le champ **Filtre article**, sélectionnez *SP-SCM1006*

    6. Activez le champ **Prévision sur emplacement**.

    7. Dans le champ **Filtre emplacement**, sélectionnez *NORD*.

    8. Activez le champ **Utiliser prévisions sur variantes**.

    9. Pour chaque ligne, les valeurs sont mises à jour dans la colonne Mai

        1. ROUGE sur NORD, défini sur 100

        2. BLANC sur NORD, défini sur 200

        3. NOIR sur NORD, défini sur 300

    10. Fermer les fenêtres de prévision de la demande

4. Exécutez le plan MPS en mai pour les prévisions de demande créées. Examinez les composantes pour vérifier que la couleur de l’article correspond à la variante.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez *Feuille planification*, puis choisissez le lien associé.

    2. Choisissez l'action **Calculer planning régénératif**.

    3. Activez le champ **MPS**.

    4. Désactivez le champ **MPS**.

    5. Dans le champ **Date début**, sélectionnez *1er mai*

    6. Dans le **Date de fin**, sélectionnez *31 mai*

    7. Dans le champ **Utiliser prévisions**, sélectionnez *AUTODRIP*

    8. Sélectionnez l’action **OK**.

    9. Pour chaque ligne créée, choisissez l’action **Composantes** et vérifiez quelle couleur est utilisée.  

## Voir aussi

[Introduction aux données de démonstration Contoso Coffee](../contoso-coffee-intro.md)  
