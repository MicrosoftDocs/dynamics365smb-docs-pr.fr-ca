---
title: Configuration de durabilité
description: Découvrez comment configurer des fonctionnalités de durabilité.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, equivalent, CO2e, CO2, carbon, role center, fees'
ms.search.form: '6221, 6235, 6245'
ms.date: 08/22/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="sustainability-module-setup"></a>Configuration du module de durabilité

Avant que le module durabilité fonctionne correctement, vous devez configurer certains contrôles et instructions de base liés à l’ensemble des fonctionnalités.

Pour mettre en place un module de durabilité, suivez les étapes suivantes :

## <a name="role-center"></a>Centre de rôle

Pour les personnes dont les responsabilités principales impliquent des processus de développement durable, il est recommandé d’utiliser le centre de rôles  *Responsable du développement durable* . Pour configurer ce centre de rôles, suivre les étapes :  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Mes paramètres**, puis Sélectionner le lien associé.
2. Dans le champ **Rôle**, Sélectionner la page **Rôles disponibles** .
3. Choisissez la ligne **Sustainability Manager** .
4. Sélectionnez **OK**.

Le centre de rôles  *Responsable du développement durable* facilite la gestion efficace de tous les domaines clés liés au développement durable. Il englobe les principales caractéristiques de durabilité, ainsi que les processus financiers et d’approvisionnement. En outre, il offre une visibilité sur les indicateurs clés de performance les plus critiques liés au développement durable.

## <a name="sustainability-setup"></a>Configuration de durabilité

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

3. Dans l’onglet rapide  **Achats**, configurez les champs obligatoires liés à l’utilisation des fonctionnalités de durabilité dans le processus d’achat.  

    | Champ | Désignation |
    |-------|-------------|
    | **Utiliser les émissions dans les documents d’achat** | Si vous activez ce champ, les champs et fonctionnalités liés au développement durable apparaîtront dans les documents d’achat, tels que **Compte de développement durable** ou différentes émissions. |

4. Sur le raccourci **Calculs**, configurez les champs obligatoires liés aux formules utilisées pour calculer les émissions.

    | Champ | Désignation |
    |-------|-------------|
    | **Décimales carburant/électricité** | Spécifiez le nombre de décimales affichées pour les quantités de carburant/électricité. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |
    | **Décimales distance** | Spécifiez le nombre de décimales affichées pour les mesures des distances. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |
    | **Nombre décimales montant personnalisé** | Spécifiez le nombre de décimales affichées pour les quantités personnalisées. Le paramètre par défaut, *2:5* spécifie qu’un minimum de 2 décimales et un maximum de 5 décimales sont affichés pour tous les montants. Vous pouvez également saisir un numéro fixe. Par exemple, si vous entrez *2*, deux décimales sont affichées pour tous les montants. |

5. Sur le raccourci **Rapports**, terminez la configuration en définissant les champs liés à la déclaration aux autorités.

    > [!NOTE]
    > Dans la version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] ne prend en charge la déclaration à aucune autorité. Par conséquent, les champs liés à la configuration de cette fonctionnalité sur le raccourci **Rapports** sont destinés aux futures fonctionnalités de rapport. Toutefois, les partenaires peuvent également utiliser ces champs dans des versions localisées.

    | Champ | Désignation |
    |-------|-------------|
    | **Code d’unité de mesure pour la déclaration des émissions** | Spécifiez le code d’unité de mesure utilisé pour déclarer les émissions, car vous pouvez utiliser différentes unités de mesure lors de la déclaration aux autorités. Ce champ n’est pas applicable aux rapports standards. |
    | **Facteur UM déclaration** | Spécifiez le facteur d’unité de mesure utilisé pour enregistrer les émissions si vous utilisez différentes unités de mesure lors de la déclaration aux autorités. |
    | **Précision d’arrondissement des émissions** | Spécifiez la taille de l’intervalle utilisé pendant l'arrondissement des quantités d’émissions lors de la déclaration aux autorités. |
    | **Type d’arrondissement des émissions** | Précisez comment le programme arrondit les quantités d’émissions lors de la déclaration aux autorités. Les options suivantes sont disponibles : **Au plus proche**, **Vers le haut** et **Vers le bas**. |

## <a name="emission-fees"></a>Frais d’émission

Pour suivre les frais carbone internes ou calculer vos émissions à l’aide d’équivalents de dioxyde de carbone (CO2), vous devez configurer la page  **Frais d’émission** . Pour configurer ces informations, suivre ces étapes :  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône, entrez **Frais d’émission**, puis Sélectionner le lien associé. 
2. Dans le champ **Type d’émission**, choisissez l’émission de GES que vous souhaitez configurer : **CO2**, **CH4** ou **N2O**. Cette option est obligatoire.   
3. Vous pouvez spécifier davantage le **Type de portée**. Si vous laissez ce champ vide, il s’appliquera à toutes les étendues, mais vous pouvez configurer pour chaque étendue.  
4. Vous pouvez configurer **la date de début** et **la date de fin**. Cela signifie notamment que vous pouvez utiliser différentes configurations pour différentes périodes. 
5. Le **code pays/région** et **code de responsabilité** sont des champs facultatifs et vous pouvez choisir si vous souhaitez les utiliser. Ces champs peuvent être utiles car il est possible d’avoir des frais carbone différents par pays ou d’utiliser différentes conversions de CO2e par pays ou par installation (centre de responsabilité).  
6. Le champ  **Taxe carbone** représente la taxe carbone interne qu’une entreprise se facture pour chaque unité d’équivalent CO2 qu’elle émet. Il peut être utilisé en fonction de certaines réglementations locales ou régionales, mais également pour des calculs internes. **Les frais carbone** seront calculés à chaque fois que vous publierez des émissions et ces informations seront visibles dans les **écritures du grand livre de développement durable**, sans aucune publication supplémentaire dans le **grand livre général**. Vous pouvez définir des frais carbone par unité de mesure dans la configuration de durabilité et ils ne peuvent être renseignés que pour la ligne où le type d’émission est CO2. **·**  **·**  **·**  **·** 
7. Le **facteur d’équivalent carbone** spécifie le coefficient qui convertit l’impact de divers gaz à effet de serre en quantité équivalente de dioxyde de carbone en fonction de leur potentiel de réchauffement climatique. Si le **type d’émission** est CO2, le **facteur d’équivalent carbone** sera toujours *1* et vous ne pouvez pas modifier cette valeur, car le CO2 est le gaz de référence utilisé pour calculer le potentiel de réchauffement global (PRG) des autres gaz à effet de serre ; puisque le CO2 est la référence, son PRG est fixé à *1*. Pour les autres gaz à effet de serre, les utilisateurs doivent configurer les valeurs manuellement. Pour effectuer un calcul correct, vous pouvez utiliser l’exemple suivant : si nous supposons que 1 kilogramme de N2O équivaut à 298 kilogrammes de CO2, vous devez calculer 1/298 et le résultat que vous devez renseigner sera 0.00336.  

> [!NOTE]
> **Le champ Frais carbone** des **entrées du grand livre de développement durable** ne sera pas calculé sur la base des valeurs **Émissions de CO2** . Au lieu de cela, comme base pour cette formule, nous utiliserons le champ  [!INCLUDE[prod_short](includes/prod_short.md)] Émission de CO2e **.**  **Le champ Émission de CO2e** sera calculé en fonction de toutes les émissions enregistrées à l’entrée et du **facteur d’équivalent carbone** configuré pour chacun des gaz sur la page **Frais d’émission** .  

Si vous n’avez pas configuré les **Frais d’émission** avant de publier vos entrées de développement durable et que vous souhaitez calculer vos frais carbone et votre CO2e de manière rétroactive, vous devez exécuter l’action **Calculer les frais d’émission** pour mettre à jour les valeurs des **Entrées du grand livre de développement durable**.  

## <a name="see-also"></a>Voir aussi .

[Finances](finance.md)    
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)    
[Plan comptable et comptabilité de durabilité](finance-sustainability-accounts-ledger.md)    
[Enregistrer les entrées de durabilité](finance-sustainability-journal.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
