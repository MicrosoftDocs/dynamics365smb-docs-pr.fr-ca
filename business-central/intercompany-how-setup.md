---
title: Configurer le report des transactions intercompagnies
description: Créez vos fournisseurs et vos clients intersociétés en tant que partenaires intersociétés, et configurez un plan comptable intersociétés.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 79c204a6c8a173985a5d3558d5ce1af5a2d8fc39
ms.sourcegitcommit: 6add995f289c56e5497409308825c73eeaa4f62f
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941527"
---
# <a name="set-up-intercompany-transaction-posting"></a>Configurer le report des transactions intercompagnies

Pour envoyer une transaction (ligne journal vente) à partir d'une compagnie et créer automatiquement la transaction correspondante (ligne journal achat) dans la compagnie partenaire, les compagnies concernées doivent s'accorder sur un plan comptable et un ensemble de dimensions communs à utiliser pour les transactions intercompagnies. Le plan de compte intercompagnie peut être, par exemple, une version simplifiée du plan de compte de la compagnie mère. Chaque compagnie associe son plan de compte au plan de compte intercompagnie partagé, ainsi que ses dimensions aux dimensions intercompagnies.  

Vous devez également configurer un code partenaire Intercompagnie pour chaque compagnie partenaire, ce qui est convenu par toutes les compagnies, puis les affecter respectivement aux fiches client et fournisseur en renseignant le champ **Code partenaire intercompagnie**.  

Si vous créez ou recevez des lignes intersociétés contenant des articles, vous pouvez soit utiliser vos propres numéros d'article, soit configurer ceux de votre partenaire pour chaque article concerné, dans le champ **Référence fournisseur** ou **N° article commun** de la fiche article. Vous pouvez également utiliser la fonction **Référence externe article** pour mapper vos numéros d’article avec vos descriptions de partenaires intercompagnies des articles, ouvrir la fiche de chaque article, puis choisir l’action **Références externes** afin de configurer les références externes entre vos descriptions d’article et celles du partenaire intercompagnie. Pour plus d'informations, voir [Utiliser les références externes article](inventory-how-use-item-cross-refs.md). 

Si vous créez des transactions de vente intercompagnies incluant des ressources, vous devez renseigner le champ **N° cpte G/L partenaire ach. IC** de la fiche ressource de chaque ressource concernée. Il s'agit du numéro du compte GL intercompagnie sur lequel le montant de cette ressource va être reporté dans la compagnie partenaire. Pour plus d'informations, reportez-vous à [Configuration de ressources](projects-how-setup-resources.md).

## <a name="to-set-up-companies-for-intercompany-transactions"></a>Pour configurer des compagnies pour les transactions intercompagnies
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Informations compagnie**, puis sélectionnez le lien associé.  
2. Sur la page **Informations compagnie**, renseignez les champs **Code Partenaire intercompagnie**, **Type de boîte de réception intercompagnie**. et **Détails boîte de réception intersociétés**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-intercompany-partners"></a>Pour paramétrer les partenaires intersociétés
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Partenaires intercompagnie**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Partenaire intercompagnies**, renseignez les champs si nécessaire.[!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> Dans [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, vous ne pouvez pas utiliser les emplacements de fichiers pour transférer des transactions à vos partenaires, car [!INCLUDE[prod_short](includes/prod_short.md)] n’a pas accès à votre réseau local. Par conséquent, si vous choisissez **Emplacement du fichier** dans le champ **Type de transfert**, le champ **Chemin du dossier** n’est pas disponible. Au lieu de cela, le fichier sera téléchargé dans le dossier Téléchargements de votre ordinateur. Vous envoyez ensuite le fichier à une personne de la compagnie partenaire, par exemple par courriel. Pour un processus plus direct, nous vous recommandons de choisir plutôt **Courriel**.

## <a name="to-set-up-intercompany-vendors-and-intercompany-customers"></a>Pour paramétrer des fournisseurs et des clients intersociétés
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Fournisseurs**, puis sélectionnez le lien associé.
2. Autrement, accédez au fournisseur du champ **N° fournisseur** sur la page **Partenaire intercompagnie**.
3. Ouvrez la fiche d'un fournisseur qui est un partenaire intercompagnie. Pour plus d'informations, voir [Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md).
4. Dans le champ **Code Partenaire intercompagnie**, sélectionnez le code partenaire intercompagnie approprié.
5. Répétez les étapes 1 à 4 pour les clients.

## <a name="to-set-up-intercompany-charts-of-accounts"></a>Pour configurer le plan comptable intersociété
Pour qu'un groupe de compagnies puisse créer des transactions intercompagnies, ses membres doivent convenir du plan comptable qui servira de référence commune. Avec vos compagnies partenaires, vous devez décider des numéros de compte à utiliser pour créer des transactions intercompagnies. Par exemple, la compagnie mère du groupe génère une version simplifiée de son propre plan comptable, l'exporte de sa base de données vers un fichier XML et la distribue à chaque compagnie du groupe.  

Si votre compagnie est la compagnie mère qui contient le plan comptable intercompagnie qui servira de référence commune au groupe, suivez la procédure [Configurer le plan comptable intercompagnie de définition](intercompany-how-setup.md#to-set-up-the-defining-intercompany-chart-of-accounts).  

Si votre compagnie est une filiale et que vous recevez un fichier XML contenant le tableau de compte commun intercompagnie, suivez la procédure [Pour importer le plan comptable intercompagnie](intercompany-how-setup.md#to-import-the-intercompany-chart-of-accounts).  

### <a name="to-set-up-the-defining-intercompany-chart-of-accounts"></a>Pour configurer la définition du plan comptable intersociété
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable intersociété**, puis sélectionnez le lien associé.
2. Sur la page **Plan comptable intersociétés**, saisissez chaque compte sur une ligne de la page.  
3. Si votre plan comptable intersociété est identique ou semblable à celui que vous utilisez habituellement, vous pouvez renseigner la page automatiquement en choisissant l'action **Copier à partir du plan comptable**. Vous pouvez modifier au besoin les nouvelles lignes.

### <a name="to-export-an-intercompany-chart-of-accounts"></a>Pour exporter un plan comptable intersociété
Pour permettre à vos partenaires Intersociétés d'importer la définition du plan comptable, vous devez l'exporter vers un fichier.      
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable intersociété**, puis sélectionnez le lien associé.
2. Sur la page **Plan comptable intersociétés**, choisissez l'action **Exporter**, puis choisissez le bouton **Enregistrer**.
3. Indiquez le nom et l'emplacement d'enregistrement du fichier XML, puis cliquez sur le bouton **Enregistrer**.  

### <a name="to-import-the-intercompany-chart-of-accounts"></a>Pour importer le plan comptable intersociétés  
Lorsqu'un fichier existe pour la définition du plan comptable intersociété, les partenaires intersociétés peuvent l'importer pour vérifier qu'ils ont les mêmes comptes.  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable intersociété**, puis sélectionnez le lien associé.  
2. Sur la page **Plan comptable intersociétés**, choisissez l'action **Importer**.  
3. Sélectionnez le nom et l'emplacement du fichier XML, puis cliquez sur le bouton **Ouvrir**.  

La page **Plan comptable IC** est remplie avec les lignes nouvelles ou modifiées du compte du grand livre en fonction du plan comptable intercompagnie dans le fichier. Les lignes existantes non connexes présentes sur la page ne changent pas.

### <a name="to-map-the-intercompany-chart-of-accounts-to-your-companys-chart-of-accounts"></a>Pour associer le plan comptable intercompagnies au plan comptable de votre compagnie  
Après avoir défini ou importé le plan comptable intercompagnie que vous et vos partenaires intercompagnies avez décidé d'utiliser, vous devez associer chaque compte du grand livre intercompagnie à l'un des comptes du grand livre de votre compagnie. Sur la page **Plan comptable IC**, indiquez comment les comptes du grand livre intercompagnies des transactions entrantes doivent être convertis en comptes du grand livre à partir du plan comptable de votre compagnie.

Si les comptes du plan comptable intersociétés possèdent les mêmes numéros que les comptes correspondants dans le plan comptable, vous pouvez les mapper automatiquement.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable intersociété**, puis sélectionnez le lien associé.  
2. Sélectionnez les lignes à associer automatiquement, puis cliquez sur choisissez l'action **Faire correspondre au compte ayant le même numéro**.  
3. Pour chaque compte du grand livre intercompagnie qui n'a pas été associé automatiquement, renseignez le champ **N° cpte G/L de correspondance**.  

## <a name="to-set-up-default-intercompany-partner-general-ledger-accounts"></a>Pour configurer des comptes généraux par défaut des partenaires intersociétés  
Lorsque vous créez une ligne vente ou achat intercompagnie à envoyer comme transaction sortante, vous indiquez un compte du plan comptable intercompagnie en tant que compte par défaut associé au compte de la compagnie de votre partenaire sur lequel le montant est reporté. Sur la page **Plan comptable**, pour les comptes que vous utilisez souvent dans des lignes vente ou achat intercompagnies sortantes, vous pouvez spécifier un compte GL par défaut de partenaire Intercompagnie. Par exemple, pour les comptes client, vous pouvez entrer les comptes fournisseur correspondants du plan comptable intersociété.  

Ensuite, si vous indiquez un compte GL dans le champ **N° compte de solde** d'une ligne intercompagnie avec **Partenaire intercompagnie** dans le champ **Type de compte**, le champ **Compte du grand livre Partenaire IC** est renseigné automatiquement.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Plan comptable**, puis sélectionnez le lien associé.  
2. Sur la ligne d'un compte du grand livre utilisé pour les transactions intercompagnies, dans le champ **Compte du grand livre par défaut de partenaire IC**, entrez le compte GL intercompagnie que votre partenaire utilisera lors du report du compte GL de la ligne.  
3. Répétez l'étape 2 pour chaque compte que vous entrez souvent dans le champ **N° compte de solde** sur une ligne dans un document ou journal intercompagnie.

## <a name="to-set-up-intercompany-dimensions"></a>Pour configurer des dimensions intercompagnies

Si vous et vos partenaires intercompagnies souhaitez pouvoir échanger des transactions auxquelles des dimensions sont liées, vous devrez vous entendre sur les dimensions que vous allez tous utiliser. Par exemple, la compagnie mère du groupe génère une version simplifiée de ses propres dimensions, l'exporte dans un fichier XML et la distribue à chaque compagnie du groupe. Chaque filiale importe ensuite ce fichier XML sur la page **Dimensions intercompagnies** et associe les dimensions intercompagnies à celles figurant dans sa propre page **Dimensions**.  

> [!NOTE]
> Chaque compagnie dans [!INCLUDE [prod_short](includes/prod_short.md)] doit mapper les dimensions avec les dimensions intercompagnie pour les documents sortants et mapper les dimensions intercompagnie avec ses propres dimensions pour les documents entrants. Cette cartographie permet d’assurer la cohérence entre les compagnies. Pour plus d’informations, consultez la section [Pour mapper les dimensions intercompagnie avec les dimensions de votre compagnie](#to-map-intercompany-dimensions-to-your-companys-dimensions).

Si votre compagnie est la compagnie mère qui contient l'ensemble de définition des dimensions intercompagnies qui serviront de référence commune au groupe, suivez la procédure [Définir les dimensions intercompagnies](intercompany-how-setup.md#to-define-the-intercompany-dimensions).

Si votre compagnie est une filiale et que vous recevez un fichier XML contenant les dimensions intercompagnies qui serviront de référence commune au groupe, suivez la procédure [Pour importer des dimensions intercompagnies](intercompany-how-setup.md#to-import-the-intercompany-dimensions).

### <a name="to-define-the-intercompany-dimensions"></a>Pour définir les dimensions intercompagnies
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Dimensions intercompagnies**, puis sélectionnez le lien associé.  
2. Sur la page **Dimensions intercompagnies**, entrez chaque dimension sur une ligne.

    Si vos dimensions intercompagnies sont identiques ou semblables aux dimensions de votre compagnie, vous pouvez renseigner la page automatiquement en utilisant la fonction **Copier à partir des dimensions**, puis modifier les lignes ainsi obtenues.  
3. Pour exporter les dimensions intercompagnies vers un fichier XML afin de le distribuer à vos compagnies partenaires, choisissez l'action **Exporter**.  
4. Indiquez le nom et l'emplacement d'enregistrement du fichier XML, puis cliquez sur le bouton **Enregistrer**.  

### <a name="to-import-the-intercompany-dimensions"></a>Pour importer les dimensions intercompagnies  
Lorsqu'un fichier existe pour la définition des dimensions intercompagnies, les partenaires intercompagnies peuvent l'importer pour vérifier qu'ils ont les mêmes dimensions.  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Dimensions intercompagnies**, puis sélectionnez le lien associé.  
2. Sur la page **Dimensions intercompagnies**, choisissez l'action **Importer**.  
3. Spécifiez le nom et l'emplacement du fichier XML, puis cliquez sur le bouton **Ouvrir**.  

Les lignes des pages **Dimensions intercompagnies** et **Valeurs de dimension intercompagnies** sont importées.  

### <a name="to-map-intercompany-dimensions-to-your-companys-dimensions"></a>Pour associer les dimensions intercompagnies aux dimensions de votre compagnie
Après avoir défini ou importé les dimensions que vos partenaires intercompagnies et vous avez décidé d'utiliser, vous devez associer chaque dimension intercompagnie à l'une des dimensions de votre compagnie, et vice versa. Sur la page **Dimensions intercompagnie**, indiquez comment les dimensions intercompagnie des *transactions entrantes* doivent être converties en dimensions à partir de la liste des dimensions de votre compagnie. Sur la page **Dimensions**, précisez comment vos dimensions doivent être converties en dimensions intercompagnie dans les *transactions sortantes*.

Si certaines dimensions intercompagnies possèdent le même code que les dimensions correspondantes de la liste des dimensions de votre compagnie, vous pouvez demander à l'application d'associer automatiquement les dimensions, ensuite vous pourrez associer automatiquement ces comptes.  

Dans les étapes suivantes, vous devez d’abord mapper les dimensions intercompagnie avec les dimensions pour les documents entrants sur la page **Dimensions intercompagnie**. Ensuite, vous mappez les dimensions avec les dimensions intercompagnie pour les documents sortants sur la page **Dimensions**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Dimensions intercompagnies**, puis sélectionnez le lien associé.
2. Sur la page **Dimensions intercompagnies**, sélectionnez les lignes à associer automatiquement, puis choisissez l'action **Établir une correspondance à la dimension du même code**.
3. Pour chaque dimension intercompagnie qui n'est pas associée automatiquement, renseignez le champ **Code de dimension de correspondance**.

    Vous devrez peut-être ajouter le champ à votre vue. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).
4. Choisissez l'action **Valeurs de dimension intercompagnies**.
5. Sur la page **Valeurs de dimension intercompagnies**, renseignez le champ **Code valeur de dimension correspondance**.

    Continuez à associer les dimensions aux dimensions intercompagnies en exécutant la même procédure.
6. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Dimensions**, puis sélectionnez le lien associé.
7. Sur la page **Dimensions**, sélectionnez les lignes à associer automatiquement, puis choisissez l'action **Établir une correspondance à la dimension IC du même code**.
8. Pour chaque dimension intercompagnie qui n'est pas associée automatiquement, renseignez le champ **Code valeur dimension correspond. IC**.
9. Choisissez l'action **Valeurs de dimension**.
10. Sur la page **Valeurs de dimension**, renseignez le champ **Code valeur de dimension correspond. IC**.

## <a name="see-also"></a>Voir aussi

[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utilisation de journaux généraux](ui-work-general-journals.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]