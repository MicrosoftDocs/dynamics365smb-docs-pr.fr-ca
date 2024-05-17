---
title: Configuration de durabilité
description: Découvrez comment configurer des fonctionnalités de durabilité.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD'
ms.search.form: null
ms.date: 04/24/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Configuration de durabilité  

Pour que le module durabilité fonctionne correctement, vous devez d’abord configurer certains contrôles et instructions de base liés à l’ensemble des fonctionnalités.  

Pour mettre en place un module de durabilité, suivez les étapes suivantes :  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration durabilité**, puis sélectionnez le lien associé.  
2. Sur le **Général** Raccourci, configurez les champs obligatoires liés à ce module :   

|  Champ  |  Désignation  |  
|--------|--------------| 
| **Code d’unité de mesure émission** | Spécifie le code d’unité de mesure utilisé pour enregistrer les émissions. |
| **Décimales d’émission** | Spécifie le nombre de décimales affichées pour les quantités d’émission. Le paramètre par défaut, 2:5, spécifie que tous les montants sont affichés avec un minimum de 2 décimales et un maximum de 5 décimales. Vous pouvez également saisir un nombre fixe, tel que 2, ce qui signifie également que les montants sont affichés avec deux décimales. |
| **Pays/région obligatoire** | Spécifie si le pays/la région est obligatoire. Vous pouvez utiliser ce champ dans les journaux sans le configurer, mais vous pouvez le sélectionner si vous souhaitez obliger les utilisateurs à remplir le champ avant d’effectuer le report. |
| **Centre de gestion obligatoire** | Spécifie si le Centre de gestion est obligatoire, car le Centre de gestion peut être utilisé comme installation pour mesurer les émissions des installations. Vous pouvez utiliser ce champ dans les journaux sans le configurer, mais vous pouvez le sélectionner si vous souhaitez obliger les utilisateurs à remplir le champ avant d’effectuer le report. |
| **Bloquer la modification de base de calcul s’il existe des écritures** | Précise si le changement de base de calcul au niveau de la catégorie de compte est bloqué au moment de la saisie de la durabilité, ce qui signifie que cette formule a déjà été appliquée. |
| **Activer la vérification des erreurs en arrière-plan** | Spécifie si la vérification des erreurs en arrière-plan des lignes journal durabilité est activée. |

> [!NOTE]
> Après avoir activé ou désactivé la **Vérification des erreurs en arrière-plan** dans les journaux, vous devrez vous reconnecter avant de démarrer la nouvelle configuration.
 

3.  Sur le **Calculs** Raccourci, configurez les champs obligatoires liés aux formules utilisées pour calculer les émissions :  

|  Champ  |  Désignation  |  
|--------|--------------| 
| **Décimales carburant/électricité** | Spécifie le nombre de décimales affichées pour les quantités de carburant/électricité. Le paramètre par défaut, 2:5, spécifie que tous les montants sont affichés avec un minimum de 2 décimales et un maximum de 5 décimales. Vous pouvez également saisir un nombre fixe, tel que 2, ce qui signifie également que les montants sont affichés avec deux décimales. |
| **Décimales distance** | Spécifie le nombre de décimales affichées pour les mesures des distances. Le paramètre par défaut, 2:5, spécifie que tous les montants sont affichés avec un minimum de 2 décimales et un maximum de 5 décimales. Vous pouvez également saisir un nombre fixe, tel que 2, ce qui signifie également que les montants sont affichés avec deux décimales. |
| **Nombre décimales montant personnalisé** | Spécifie le nombre de décimales affichées pour les quantités personnalisées. Le paramètre par défaut, 2:5, spécifie que tous les montants sont affichés avec un minimum de 2 décimales et un maximum de 5 décimales. Vous pouvez également saisir un nombre fixe, tel que 2, ce qui signifie également que les montants sont affichés avec deux décimales. |

4.  Terminez la configuration sur le raccourci **Rapports**, lié à la déclaration aux autorités :   

|  Champ  |  Désignation  |  
|--------|--------------| 
| **Code d’unité de mesure pour la déclaration des émissions** | Spécifie le code d’unité de mesure utilisé pour déclarer les émissions, puisque vous pouvez utiliser différentes unités de mesure lors de la déclaration aux autorités. Ce champ n’est pas applicable aux rapports standards. |
| **Facteur UM déclaration** | Spécifie le facteur d’unité de mesure utilisé pour enregistrer les émissions si vous utilisez différentes unités de mesure lors de la déclaration aux autorités. |
| **Précision d’arrondissement des émissions** | Spécifie la taille de l’intervalle à utiliser pour arrondir des quantités d’émissions lors de la déclaration aux autorités. |
| **Type d’arrondissement des émissions** | Spécifie comment le programme arrondit une quantité d’émission lors de la déclaration aux autorités, à l’aide des options : la plus proche, vers le haut ou vers le bas. |

>[!NOTE]
> Dans la version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] ne prend pas en charge la déclaration à une autorité. Donc, le champ lié à la configuration sur le raccourci **Rapports** sera utilisé pour les futures fonctionnalités de génération de rapports, mais il pourra également être utilisé par les partenaires dans les versions localisées.

## Voir aussi .  
[Finances](finance.md)  
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)    
[Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md)    
[Procédure pour enregistrer des émissions](finance-sustainability-journal.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
