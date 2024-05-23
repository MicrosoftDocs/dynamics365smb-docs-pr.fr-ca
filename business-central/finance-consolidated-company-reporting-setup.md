---
title: Configurer la consolidation de la compagnie
description: Découvrez comment vous pouvez configurer la manière dont les données de différentes compagnies dans Business Central sont transmises à une compagnie de consolidation.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.date: 03/14/2024
ms.custom: bap-template
ms.search.keywords: 'consolidation, subsidiaries, consolidate'
ms.search.form: '1826, 1827'
ms.service: dynamics-365-business-central
---

# Configurer la consolidation de la compagnie

Avant de pouvoir consolider les écritures de deux ou plusieurs compagnies (filiales) dans une compagnie consolidée, vous devez préparer les plans comptables et la compagnie de consolidation.  

En fonction de la complexité de vos entreprises, il existe deux façons de configurer la consolidation :

* Si les paramètres avancés ne sont pas nécessaires, par exemple inclure une compagnie que vous détenez en partie, vous pouvez utiliser le guide de configuration **Consolidation de la compagnie** pour configurer rapidement une consolidation. Le guide vous aide à effectuer les étapes de base.
* Si des paramètres plus avancés sont nécessaires, vous pouvez configurer vous-même la compagnie consolidée et les unités fonctionnelles.
  * Dans chaque unité fonctionnelle, spécifiez les comptes du grand livre à inclure dans la consolidation et la méthode de conversion pour chaque compte.
  * Dans la compagnie consolidée, configurez une fiche unité fonctionnelle pour chaque compagnie à inclure dans la consolidation. La fiche unité fonctionnelle contient des informations, telles que les dates de l’exercice financier de l'unité fonctionnelle et le pourcentage de chaque compte à inclure dans la consolidation.

## Configuration d’une consolidation simple

Si votre consolidation est simple, car vous détenez en totalité les unités fonctionnelles à consolider, le guide de configuration **Consolidation de la compagnie** vous aide à effectuer les étapes suivantes :

* Créez une nouvelle compagnie consolidée ou consolidez une compagnie que vous avez déjà créée. La compagnie ne doit pas contenir de transactions.
* Affichez un aperçu des résultats. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie que vous pouvez transférer correctement les données principales et les transactions vers la compagnie consolidée.

Pour utiliser le guide de configuration assistée, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration assistée**, puis choisissez le lien associé.
2. Choisissez **Traiter les consolidations**, puis effectuez chaque étape du guide de configuration assistée Consolidation de la compagnie.

## Configuration d’une consolidation avancée

Si des paramètres plus avancés sont nécessaires pour votre consolidation, vous pouvez configurer manuellement la consolidation. Par exemple, si vous détenez partiellement des compagnies ou si vous ne souhaitez pas inclure des compagnies.  

### Configurer la compagnie consolidée

D’abord, vous devez définir la compagnie consolidée. Vous configurez la compagnie consolidée de la même manière que vous configurez d'autres compagnies. Pour en savoir plus sur la configuration d’une compagnie, consultez [Se préparer à faire des affaires](ui-get-ready-business.md).  

La liste suivante illustre les principaux aspects de la compagnie consolidée.

1. Configurez le plan comptable.

    Pour en savoir plus sur la configuration d’un plan comptable, consultez [Configuration ou modification du plan comptable](finance-setup-chart-accounts.md).  

    Le plan comptable peut être identique entre une unité fonctionnelle et la compagnie consolidée, ou la compagnie consolidée peut avoir un autre plan comptable. Si le plan comptable d’une unité fonctionnelle diffère de celui de la compagnie consolidée, vous devez mapper les comptes avec ceux de l'unité fonctionnelle. Pour en savoir plus, consultez la section [Préparer les comptes GL pour la consolidation](#glacc).

2. Ajoutez des unités fonctionnelles.

    Pour consolider les données de plusieurs compagnies, vous devez configurer les filiales en tant qu'unités fonctionnelles et spécifier la quantité de leurs soldes à inclure. Pour en savoir plus sur les unités fonctionnelles, consultez la section [Ajouter des unités fonctionnelles](#busunit).

3. Spécifiez les taux de change, si nécessaire.

    Spécifiez les taux de change si vous consolidez les données des unités fonctionnelles qui utilisent des devises différentes. Les trois taux de change que vous pouvez utiliser sont : **Taux moyen (manuel)**, **Taux de fermeture** et **Dernier taux de fermeture**. Pour en savoir plus sur les taux de change, consultez la section [Spécifier les taux de change pour les consolidations](#exchrates).

4. Consolidez les informations de dimension et les comptes GL.

    Pour en savoir plus, consultez la section [Inclure ou exclure des dimensions](#dim).

### <a name="busunit"></a>Ajouter des unités fonctionnelles

Dans la compagnie consolidée, configurez chaque compagnie dont vous souhaitez consolider les données en tant qu'unité fonctionnelle. Avant d’exécuter une consolidation et de générer votre rapport de consolidation, il est recommandé de vérifier les données financières dans chaque unité fonctionnelle.

Une grande partie de la configuration de l'unité fonctionnelle consiste à spécifier comment l'unité fonctionnelle partage ses données financières avec la compagnie consolidée. Il existe des options manuelles et automatisées :

* Pour utiliser un processus manuel, pour [!INCLUDE [prod_short](includes/prod_short.md)] en ligne et local, vous pouvez exporter un fichier .xml contenant les écritures du grand livre de l'unité. Ensuite, importez le fichier dans la compagnie consolidée.
* Pour automatiser l’échange de données, pour [!INCLUDE [prod_short](includes/prod_short.md)] en ligne, vous pouvez utiliser une API fournie par [!INCLUDE [prod_short](includes/prod_short.md)] pour partager des données entre les environnements. Si vos compagnies se trouvent dans le même environnement, vous pouvez utiliser l’option **Base de données**.

> [!NOTE]
> L’option API vous permet également de partager les écritures d’autres environnements [!INCLUDE [prod_short](includes/prod_short.md)]. Pour utiliser l’option API, l’utilisateur qui configure la consolidation doit avoir l’autorisation d’accéder aux écritures GL. Par exemple, les ensembles d’autorisations D365 Basic et D365 Read fournissent l’accès.

#### Configurer les devises des unités fonctionnelles

Lorsque vous exécutez une consolidation pour des unités fonctionnelles qui utilisent une devise étrangère, vous devez accorder une attention particulière aux taux de change utilisés par différentes parties du processus, d’autant plus si vous réexécutez la consolidation. Pour ce faire, utilisez la page **Configurer les devises des unités fonctionnelles** pour suivre facilement les taux.

La page **Configurer les devises des unités fonctionnelles** vous donne les dernières valeurs pour le taux moyen, le taux de fermeture et le dernier taux de fermeture. Vous pouvez rechercher les taux de change dans le tableau des taux de change, ce qui facilite la validation des taux. Vous pouvez modifier les taux pour l’exécution en cours en saisissant les valeurs ou en les copiant des exécutions précédentes. Pour copier les taux, choisissez **Sélectionner à partir d’une consolidation précédente**. Cette page est particulièrement utile lorsque vous souhaitez réexécuter une consolidation précédente, où vous devez utiliser un taux de fermeture précédent. Ceci est nécessaire pour réévaluer correctement vos postes de bilan. La page **Sélectionner à partir de la consolidation précédente** est également utile si vous souhaitez simplement afficher les taux qui ont été utilisés, par exemple, lors d’un dépannage. La page est filtrée sur les exécutions incluant l’unité fonctionnelle sélectionnée.

Vous démarrez le traitement en lot **Exécuter la consolidation** à partir de la page de liste **Unités fonctionnelles** . Vous pouvez également accéder à la page **Configurer les devises des unités fonctionnelles** en choisissant l’action **Taux de change** .

> [!NOTE]
> Les pages de configuration du taux de change pour le taux moyen, le taux de fermeture et le dernier taux de fermeture actuellement disponibles sur la fiche **Unité fonctionnelle** seront obsolètes dans une version ultérieure. Toutefois, vous pouvez toujours conserver ces taux si vous disposez d’unités fonctionnelles que vous importez via des fichiers.

#### Créer une unité fonctionnelle

1. Connectez-vous à la compagnie consolidée.
2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unités fonctionnelles**, puis choisissez le lien associé.  
3. Choisissez **Nouveau**, puis remplissez les champs obligatoires dans les raccourcis **Général** et **Comptes du grand livre**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!IMPORTANT]
    > Lorsque vous renseignez les champs **Date début** et **Date de fin**, assurez-vous de vous conformer aux règles GAAP concernant les périodes fiscales de l'unité fonctionnelle par rapport à la compagnie mère.
4. Dans le raccourci **Importation de données**, dans le champ **Importation de données par défaut**, spécifiez comment vous partagez les écritures avec la compagnie consolidée :

   * Pour partager des données entre des compagnies dans le même environnement, choisissez **Base de données**.
   * Pour partager des données entre des compagnies dans des environnements différents, choisissez **API**, puis remplissez le champ **Point de terminaison de l’API**.
        
        Pour obtenir l’URL du point de terminaison, dans le [!INCLUDE [prod_short](includes/prod_short.md)] de la compagnie de l'unité fonctionnelle, ouvrez la page **Fiche unité fonctionnelle** et choisissez l’action **Configurer**. 
   * Pour exporter un fichier .xml et le partager manuellement, choisissez **Format de fichier**.

### <a name="glacc"></a>Préparer les comptes GL pour la consolidation

Le plan comptable d’une compagnie qui sera consolidée doit spécifier des comptes pour consolidation. Pour chaque compte GL de report dans chaque compagnie, vous devez spécifier le compte GL dans la compagnie consolidée vers lequel transférer le solde. Ce mappage vous permet de consolider des compagnies avec des plans comptables différents.

Si le plan comptable de l'unité fonctionnelle diffère de celui de la compagnie consolidée, vous devez préparer les comptes GL pour la consolidation. Vous pouvez spécifier les comptes sur lesquels reporter les débits et crédits et la méthode à utiliser pour convertir des devises dans la compagnie consolidée.

1. Dans chaque unité fonctionnelle [!INCLUDE [prod_short](includes/prod_short.md)], sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
2. Ouvrez la fiche du compte, puis renseignez les champs du raccourci **Consolidation**. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> Si vous ne remplissez pas les champs **Compte débit consolidation** et **Compte crédit consolidation**, [!INCLUDE [prod_short](includes/prod_short.md)] suppose qu’ils sont mappés aux mêmes comptes dans la compagnie consolidée.

> [!TIP]
> Il peut y avoir des scénarios dans lesquels vous ne souhaitez pas inclure un compte dans une consolidation. Par exemple, si vous souhaitez que votre compagnie de consolidation reflète uniquement les bilans des filiales. Pour exclure un compte de la consolidation, activez le bouton **Exclure de la consolidation** pour le compte.

### <a name="exchrates"></a>Indiquer des taux de change pour les consolidations

Si une unité fonctionnelle utilise une devise différente de celle de la compagnie consolidée, vous devez spécifier des méthodes de conversion de taux de change pour chaque compte avant la consolidation. Pour chaque compte, la valeur du champ **Consolider la méthode de traduction** détermine le taux de change. Dans la compagnie consolidée, sur chaque fiche unité fonctionnelle, dans le champ **Table Taux de change devise**, vous spécifiez si la consolidation utilise les taux de change de l’unité fonctionnelle ou de la compagnie consolidée. Si vous utilisez les taux de change de la compagnie consolidée, vous pouvez les modifier pour une unité fonctionnelle. Pour les unités fonctionnelles, si le champ **Table Taux de change devise** de la fiche unité fonctionnelle contient la valeur **Local**, vous pouvez modifier le taux de change à partir de la fiche unité fonctionnelle. Les taux de change sont copiés à partir de la table **Taux de change devise**, mais vous pouvez les modifier avant la consolidation.

Le tableau suivant décrit les méthodes de conversion de taux de change que vous pouvez utiliser pour les comptes.

|Taux de change | Utilisation courante |
|---|---|
|Taux moyen (manuel) | Vous calculez manuellement le taux moyen pour la période à consolider. Calculez une moyenne arithmétique ou une estimation au plus près, puis spécifiez le résultat pour chaque unité fonctionnelle. Utilisez-le pour les comptes de résultats.|
|Taux de fermeture | Utilisé pour les comptes de bilan.|
|Dernier taux de fermeture | Taux valide sur le marché des changes à la date pour laquelle le bilan ou l'état des résultats est préparé. Entrez ce taux pour chaque unité fonctionnelle. Utilisez-le pour les comptes de bilan.|
|Taux historique | Taux de change valide au moment de la transaction.|
|Taux composite | Les montants de la période en cours sont convertis au taux moyen et ajoutés au solde précédemment enregistré dans la compagnie consolidée. Vous utilisez généralement cette méthode pour les comptes de bénéfices non répartis. Ces comptes incluent des montants de différentes périodes, ils contiennent donc des montants convertis avec différents taux de change.|
|Taux des fonds propres | Cette option est similaire au **Taux composite**. Les différences sont reportées sur des comptes GL distincts.|

Pour spécifier des taux de change pour une unité fonctionnelle, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unités fonctionnelles**, puis choisissez le lien associé.  
2. Sur la page **Liste des unités fonctionnelles**, choisissez l’unité fonctionnelle, puis l’action **Taux de change**.  
3. Sur la page **Configurer les devises des unités fonctionnelles**, renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="dim"></a>Inclure ou exclure des dimensions

Vous pouvez consolider des informations de dimension et des comptes GL.

* Sur les dimensions, spécifiez le champ **Code de consolidation** ou laissez-le vide.
  * Pour exclure une dimension de la consolidation, laissez le champ **Code de consolidation** vide sur la dimension et ne choisissez pas de dimensions dans les champs **Copier les dimensions** dans toutes les fonctions ou rapports de consolidation.
  * Pour inclure les informations de dimension dans la consolidation, laissez le champ **Code de consolidation** vide. Toutefois, la consolidation ne fonctionne que si les valeurs de dimension de l'unité fonctionnelle sont les mêmes que celles de la compagnie consolidée.
  * Pour consolider le code valeur de dimension dans l'unité fonctionnelle avec un autre code valeur de dimension dans la compagnie consolidée, renseignez le champ **Code de consolidation** dans les dimensions.  
* Ajoutez les dimensions aux comptes GL.

### <a name="exclude"></a>Exclure une compagnie de la consolidation

Si vous ne souhaitez pas inclure une unité fonctionnelle dans la consolidation, vous pouvez l’exclure. Pour ce faire, accédez à la fiche unité fonctionnelle et désactivez la case à cocher **Consolider**.

### <a name="include"></a>Inclure une compagnie partiellement détenue dans la consolidation

Si vous détenez une compagnie en partie, vous pouvez ajouter un pourcentage de chaque transaction qui reflète le pourcentage que vous détenez. Par exemple, si vous possédez 70 % de la compagnie, la consolidation inclut 70 USD d’une facture de 100 USD. Pour spécifier le pourcentage de la compagnie que vous détenez, accédez à la fiche unité fonctionnelle et saisissez le pourcentage dans le champ **% consolidation**.  

## Voir aussi

[Consolidation des données financières de plusieurs compagnies](finance-consolidated-company-reporting.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]