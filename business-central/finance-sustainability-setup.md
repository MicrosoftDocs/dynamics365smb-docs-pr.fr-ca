---
title: Configuration de durabilité
description: Découvrez comment configurer des fonctionnalités de durabilité.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD'
ms.search.form: null
ms.date: 05/08/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Configuration de durabilité

Avant que le module durabilité fonctionne correctement, vous devez configurer certains contrôles et instructions de base liés à l’ensemble des fonctionnalités.

Pour mettre en place un module de durabilité, suivez les étapes suivantes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration durabilité**, puis sélectionnez le lien associé.
2. Sur le **Général** Raccourci, configurez les champs obligatoires liés au modèle de durabilité.

    | Champ | Désignation |
    |-------|-------------|
    | **Code d’unité de mesure émission** | Spécifiez le code d’unité de mesure utilisé pour enregistrer les émissions. |
    | **Décimales d’émission** | Spécifiez le nombre de décimales affichées pour les quantités d’émission. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |
    | **Pays/région obligatoire** | Spécifiez si le pays/la région est obligatoire. Les utilisateurs peuvent définir le champ pays/région dans les journaux même si vous ne sélectionnez pas ce champ. Cependant, en le sélectionnant, vous exigez que les utilisateurs définissent le champ pays/région avant le report. |
    | **Centre de gestion obligatoire** | Spécifiez si le centre de gestion est obligatoire. Le centre de gestion peut être utilisé comme un site, afin que vous puissiez mesurer les émissions des sites. Les utilisateurs peuvent définir le champ centre de gestion dans les journaux même si vous ne sélectionnez pas ce champ. Cependant, en le sélectionnant, vous exigez que les utilisateurs définissent le champ centre de gestion avant le report. |
    | **Bloquer la modification de base de calcul s’il existe des écritures** | Précisez si les changements de la base de calcul (formule) au niveau de la catégorie de compte sont bloqués au moment de la saisie de la durabilité, lorsque la formule a déjà été appliquée. |
    | **Activer la vérification des erreurs en arrière-plan** | Spécifiez si la vérification des erreurs en arrière-plan des lignes journal durabilité est activée. |

    > [!NOTE]
    > Après avoir activé ou désactivé la vérification des erreurs en arrière-plan dans les journaux, vous devrez vous reconnecter avant de démarrer la nouvelle configuration.

3. Sur le raccourci **Calculs**, configurez les champs obligatoires liés aux formules utilisées pour calculer les émissions.

    | Champ | Désignation |
    |-------|-------------|
    | **Décimales carburant/électricité** | Spécifiez le nombre de décimales affichées pour les quantités de carburant/électricité. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |
    | **Décimales distance** | Spécifiez le nombre de décimales affichées pour les mesures des distances. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |
    | **Nombre décimales montant personnalisé** | Spécifiez le nombre de décimales affichées pour les quantités personnalisées. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |

4. Sur le raccourci **Rapports**, terminez la configuration en définissant les champs liés à la déclaration aux autorités.

    > [!NOTE]
    > Dans la version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] ne prend en charge la déclaration à aucune autorité. Par conséquent, les champs liés à la configuration de cette fonctionnalité sur le raccourci **Rapports** sont destinés aux futures fonctionnalités de rapport. Toutefois, les partenaires peuvent également utiliser ces champs dans des versions localisées.

    | Champ | Désignation |
    |-------|-------------|
    | **Code d’unité de mesure pour la déclaration des émissions** | Spécifiez le code d’unité de mesure utilisé pour déclarer les émissions, car vous pouvez utiliser différentes unités de mesure lors de la déclaration aux autorités. Ce champ n’est pas applicable aux rapports standards. |
    | **Facteur UM déclaration** | Spécifiez le facteur d’unité de mesure utilisé pour enregistrer les émissions si vous utilisez différentes unités de mesure lors de la déclaration aux autorités. |
    | **Précision d’arrondissement des émissions** | Spécifiez la taille de l’intervalle utilisé pendant l'arrondissement des quantités d’émissions lors de la déclaration aux autorités. |
    | **Type d’arrondissement des émissions** | Précisez comment le programme arrondit les quantités d’émissions lors de la déclaration aux autorités. Les options suivantes sont disponibles : **Au plus proche**, **Vers le haut** et **Vers le bas**. |

## Voir aussi .

[Finances](finance.md)  
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)  
[Plan comptable et comptabilité de durabilité](finance-sustainability-accounts-ledger.md)  
[Enregistrer les entrées de durabilité](finance-sustainability-journal.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
