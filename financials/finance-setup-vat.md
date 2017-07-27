---
title: "À propos de la configuration de la TVA | Microsoft Docs"
description: "Assurez-vous de calculer, de reporter et de déclarer correctement la TVA pour les ventes et les achats."
services: project-madeira
documentationcenter: 
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 04/20/2017
ms.author: bholtorf
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: ce397b4a492a727211b49d7db2a231bea40d8c43
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---

# <a name="setting-up-to-calculations-and-posting-methods-for-value-added-tax"></a>Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée
Les clients et les entreprises payent la TVA lorsqu'ils achètent des biens ou des services. Le montant de la TVA à payer peut varier en fonction de plusieurs facteurs. Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous configurez la TVA pour spécifier les taux à utiliser pour calculer les montants de taxe sur la base des éléments suivants : 

* À qui vous vendez  
* À qui vous achetez  
* Ce que vous vendez  
* Ce que vous achetez  
  
Vous pouvez configurer manuellement les calculs de la TVA, mais cette procédure peut être délicate et longue. Pour vous faciliter la tâche, nous avons fourni un guide de configuration assistée appelé **Paramètres TVA** pour vous aider. Il est recommandé d'utiliser le guide de configuration assistée pour configurer la TVA.

> [!NOTE]  
>   Vous pouvez utiliser le guide uniquement si vous avez créé un profil Ma compagnie, et si vous n'avez pas reporté de transactions incluant la TVA. Sinon, il serait très facile d'utiliser différents taux de TVA par erreur et de générer des états de TVA erronés.  
  
Si vous souhaitez configurer vous-même les calculs de TVA, ou en savoir plus sur chaque étape, cette rubrique contient des descriptions de chaque étape. Ces descriptions indiquent comment :  
  
* Configurer des groupes comptabilisation marché TVA pour définir les taux de TVA des marchés dans lesquels vous opérez. Vous les affectez aux clients et aux fournisseurs.  
* Configurer des groupes comptabilisation produit TVA pour définir les taux de TVA des produits et services que vous achetez ou vendez.  
  
   > [!NOTE]  
>   Les concepts associés aux groupes comptabilisation marché et produit TVA sont similaires aux groupes comptabilisation généraux. Pour plus d'informations, voir [Paramètres du groupe comptabilisation](finance-posting-groups.md).
* Combinez des groupes de report marché et produit TVA pour créer des configurations TVA permettant de calculer les montants de TVA sur les ventes et les achats.  
* Affecter des groupes comptabilisation produit TVA aux comptes généraux que vous utilisez pour les ventes et les achats, ainsi qu'à des articles et des ressources.  

   > [!NOTE]  
>   Pour configurer la TVA pour les ressources, vous devez activer l'expérience utilisateur **Suite** pour votre société. Pour plus d'informations, voir [Personnalisation de votre expérience Dynamics 365 for Financials](ui-experiences.md).
* Utiliser des frais renversés TVA pour les échanges entre pays/régions de l'UE  
* Comprendre l'arrondissement TVA pour les documents  
* Configurer des clauses pour expliquer l'utilisation de taux de TVA non standard
* Vérifier les numéros d'identification TVA

## <a name="use-the-vat-setup-assisted-setup-guide-to-set-up-vat-recommended"></a>Utiliser le guide de configuration assistée Paramètres TVA pour configurer la TVA (recommandé)
Il est recommandé d'utiliser le guide de configuration assistée Paramètres TVA pour configurer la TVA dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. 

Pour démarrer le guide de configuration assistée, procédez comme suit :
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Configuration assistée**.  
2. Choisissez **Paramètres TVA**.

## <a name="set-up-vat-business-posting-groups"></a>Configurer des groupes comptabilisation marché TVA
Les groupes de report marché TVA doivent représenter les marchés dans lesquels vous faites des affaires avec les clients et fournisseurs, et définissent comment calculer et reporter la TVA dans chaque marché. Des exemples de groupes comptabilisation marché TVA sont **France** et **Union Européenne (UE)**.  

Utilisez des codes faciles à retenir et qui décrivent le groupe comptabilisation marché, tels que **UE**, **Non-UE** ou **France**. Le code doit être unique. Vous pouvez créer autant de codes que vous le souhaitez, mais vous ne pouvez pas avoir le même code deux fois dans une table.
  
Pour configurer un groupe de report marché TVA, procédez comme suit :

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Groupe compta. marché TVA**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.

Paramétrez les groupes comptabilisation marché TVA par défaut en les liant à des groupes comptabilisation marché. [!INCLUDE[d365fin](includes/d365fin_md.md)] affecte automatiquement le groupe comptabilisation marché TVA lorsque vous affectez le groupe comptabilisation marché à un client, un fournisseur ou un compte général. 

## <a name="set-up-vat-product-posting-groups"></a>Configurer des groupes comptabilisation produit TVA
Les groupes de report produit TVA représentent les articles et les ressources que vous achetez ou vendez et déterminent la manière de calculer et de reporter la TVA en fonction du type d'article ou de ressource acheté ou vendu.  
Il est recommandé d'utiliser des codes faciles à retenir et qui décrivent le taux, par exemple **SANS TVA** ou **Zéro**, **TVA10** ou **Réduite** pour 10 % de TVA, et **TVA25** ou **Standard** pour 25 %.

Pour configurer un groupe de report marché TVA, procédez comme suit :

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Groupes comptabilisation produit TVA**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="combine-vat-posting-groups-in-vat-posting-setups"></a>Regrouper des groupes de report TVA dans les configurations report de taxe
[!INCLUDE[d365fin](includes/d365fin_md.md)] calcule les montants de TVA sur les ventes et les achats en fonction des paramètres comptabilisation TVA, qui sont des combinaisons de groupes comptabilisation marché et produit TVA. Pour chaque combinaison, vous pouvez spécifier le pourcentage de TVA, le mode calcul TVA et les comptes du grand livre pour le report de la TVA pour les achats, les ventes, ainsi que les frais renversés. Vous pouvez également spécifier si la TVA doit être recalculée lorsqu'un escompte de paiement est affecté ou reçu.  

Définissez autant de combinaisons que nécessaire. Si vous voulez regrouper des combinaisons de paramètres comptabilisation TVA avec des attributs similaires, vous pouvez définir un **Identifiant TVA** pour chaque groupe et affecter l'identifiant aux membres du groupe.

Pour regrouper des configurations report TVA, procédez comme suit :

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres compta. TVA**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins.

## <a name="assign-vat-posting-groups-by-default-to-multiple-entities"></a>Affecter des groupes comptabilisation TVA par défaut à plusieurs entités
Si vous souhaitez appliquer les mêmes groupes comptabilisation TVA à plusieurs entités, vous pouvez configurer [!INCLUDE[d365fin](includes/d365fin_md.md)] pour le faire par défaut. Plusieurs méthodes sont disponibles :

* Vous pouvez affecter des groupes comptabilisation marché aux groupes comptabilisation marché généraux ou aux modèles client ou fournisseur 
* Vous pouvez affecter des groupes comptabilisation produit TVA aux groupes comptabilisation produit généraux  

Le groupe de report marché ou produit TVA est affecté lorsque vous choisissez un groupe de report marché ou produit pour un client, un fournisseur, un article ou une ressource.

## <a name="assign-vat-posting-groups-to-individual-accounts-customers-vendors-items-and-resources"></a>Affecter des groupes comptabilisation TVA à des comptes, clients, fournisseurs, articles et ressources individuels
Les sections suivantes décrivent comment affecter des groupes comptabilisation TVA à des entités individuelles.

### <a name="to-assign-vat-posting-groups-to-individual-general-ledger-accounts"></a>Pour affecter des groupes comptabilisation TVA à des comptes généraux individuels 
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Plan comptable**, puis sélectionnez le lien connexe.  
2. Ouvrez la fiche **Compte général** pour le compte.
3. Sous le raccourci **Comptabilisation**, dans le champ **Type compta. TVA**, choisissez **Vente** ou **Achat**.  
5. Choisissez les groupes comptabilisation TVA à utiliser pour le compte vente ou achat.  

### <a name="to-assign-vat-business-posting-groups-to-customers-and-vendors"></a>Pour affecter des groupes comptabilisation marché TVA à des clients et des fournisseurs  
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Client** ou **Fournisseur**, puis sélectionnez le lien connexe.  
2. Sur la fiche **Client** ou **Fournisseur**, développez le raccourci **Facturation**.  
3. Choisissez le groupe de report marché TVA.  

### <a name="to-assign-vat-product-posting-groups-to-individual-items-and-resources"></a>Pour affecter des groupes comptabilisation produit TVA à des articles et des ressources individuels  
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Client** ou **Fournisseur**, puis sélectionnez le lien connexe.  
2. Exécutez l'une des opérations suivantes :
* Sur la fiche **Article**, développez le raccourci **Prix et validation**, puis sélectionnez **Afficher plus** pour afficher le champ **Groupe compta. produit TVA**.  
* Sur la fiche **Ressource**, développez le raccourci **Facturation**.  
3. Choisissez le groupe de report produit TVA.

## <a name="set-up-clauses-to-explain-the-use-of-non-standard-vat-rates"></a>Configurer des clauses pour expliquer l'utilisation de taux de TVA non standard
Vous configurez une clause TVA afin de décrire le type utilisation de TVA qui est appliquée. Les informations peuvent être requises par une réglementation gouvernementale. Après avoir configuré une clause TVA et l'avoir associée à une configuration report TVA, la clause TVA est affichée sur les documents vente imprimés qui utilisent le groupe de configuration report TVA. 

Si nécessaire, vous pouvez également spécifier comment convertir les clauses TVA dans d'autres langues. Ensuite, lorsque vous créez et imprimez un document vente qui contient un identificateur TVA, le document inclura la clause TVA traduite. Le code langue spécifié sur la fiche client détermine la langue.
  
### <a name="to-set-up-vat-clauses"></a>Pour configurer des clauses TVA
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Clauses TVA**, puis choisissez le lien associé.  
2. Sur la page **Clauses TVA**, créez une ligne.  
3. Dans le champ **Code**, entrez un identificateur pour la clause. Vous utilisez ce code pour affecter la clause à des groupes comptabilisation TVA.  
4. Dans le champ **Description**, saisissez le texte que vous souhaitez afficher sur les documents pouvant inclure la TVA. Dans le champ **Description 2**, entrez du texte supplémentaire, si nécessaire. Le texte s'affiche sur de nouvelles lignes.  
5. Facultatif : pour affecter immédiatement la clause TVA à un paramètre comptabilisation TVA, sélectionnez **Paramètres**, puis sélectionnez la clause. Si vous souhaitez attendre, vous pouvez affecter la clause ultérieurement sur la page Configuration report taxe.  
6. Facultatif : pour spécifier comment traduire la clause TVA, sélectionnez l'action **Traductions**.

### <a name="to-assign-a-vat-clause-to-a-vat-posting-setup"></a>Pour affecter une clause TVA à une configuration report TVA
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres compta. TVA**, puis choisissez le lien associé.  
2. Dans la colonne **Clause TVA**, choisissez la clause à utiliser pour chaque paramètre comptabilisation TVA auquel elle s'applique.  

### <a name="to-specify-translations-for-vat-clauses"></a>Pour spécifier des traductions pour les clauses TVA
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Clauses TVA**, puis choisissez le lien associé.  
2. Sélectionnez l'option **Traductions**.  
3. Dans le champ **Code langue**, sélectionnez la langue de traduction.  
4. Dans les champs **Description** et **Description 2**, saisissez les traductions des descriptions. Ce texte s'affiche dans les documents rapport de TVA traduits.  
  
## <a name="create-a-vat-posting-setup-to-handle-import-vat"></a>Créer une configuration report TVA pour traiter la TVA à l'importation
Utilisez la fonction TVA à l'importation pour reporter un document dont le montant entier est TVA. Elle est utile lorsque vous recevez une facture des autorités fiscales pour la TVA sur les biens importés.  
  
Pour configurer des codes pour la TVA à l'importation, procédez comme suit :  
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Groupes comptabilisation produit TVA**, puis choisissez le lien associé.  
2. Sur la page Groupes de report produit TVA, configurez un groupe de report produit TVA pour la TVA à l'importation.  
3. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres compta. TVA**, puis choisissez le lien associé.  
4. Sur la page Configuration report de taxe, créez une ligne ou utilisez un groupe report marché TVA existant en combinaison avec le nouveau groupe report produit TVA créé pour la TVA à l'importation.  
5. Dans le champ **Mode calcul TVA**, sélectionnez **Exclusivement TVA**.  
6. Dans le champ **Compte TVA achat**, indiquez le compte général à utiliser pour valider la TVA à l'importation. Tous les autres comptes sont facultatifs.  
  
## <a name="verify-vat-registration-numbers"></a>Vérifier les numéros d'identification TVA
Il est important que les numéros d'identification TVA des clients, fournisseurs et contacts soient valides. Par exemple, les compagnies modifient parfois leur état d'assujettissement à la TVA, et dans certains pays, les autorités fiscales peuvent vous demander de fournir des rapports, tels que le rapport Liste des ventes UE, qui répertorient les numéros d'identification TVA que vous utilisez lors de vos activités. 
  
La Commission européenne fournit le service VIES de validation des numéros TVA sur son site Web, qui est public et gratuit. [!INCLUDE[d365fin](includes/d365fin_md.md)] vous permet de supprimer cette étape et d'utiliser le service VIES pour valider et suivre les numéros de TVA des clients, fournisseurs et contacts directement à partir des fiches client, fournisseur et contact. Le service de [!INCLUDE[d365fin](includes/d365fin_md.md)] s'appelle **Services validation N° id. intracomm. Union européenne**. Il est disponible sur la page **Connexions au service**, et vous pouvez commencer à l'utiliser immédiatement. La connexion au service est gratuite, et l'inscription n'est pas obligatoire.

Lorsque vous utilisez la connexion à notre service, nous enregistrons un historique des numéros de TVA et des vérifications pour chaque client, fournisseur ou contact dans le **Journal identif. intracomm** pour faciliter le suivi. Le journal est spécifique à chaque client. Par exemple, le journal est utile pour prouver que vous avez vérifié que le numéro de TVA actuel est correct. Lorsque vous vérifiez un numéro de TVA, la colonne **Identificateur de demande** du journal indique que vous avez effectué des actions. 

Vous pouvez afficher le journal d'identification TVA sur les fiches client, fournisseur ou contact, sous le raccourci **Facturation**, en cliquant sur le bouton de recherche dans le champ **N° identif. intracomm.** .  

Notre service peut aussi vous faire gagner du temps lorsque vous créez un client ou un fournisseur. Si vous connaissez le numéro de TVA du client, vous pouvez le saisir dans le champ **N° identif. intracomm.** des fiches client ou fournisseur, et nous compléterons le nom du client pour vous. Certains pays fournissent également les adresses compagnie dans un format structuré. Dans ces pays, nous compléterons aussi l'adresse.  

> [!NOTE]  
> Voici quelques points à noter concernant le service VIES de validation de numéros de TVA :

* Le service utilise le protocole http, ce qui signifie que les données transférées via le service ne sont pas cryptées.  
* Vous pouvez rencontrer des temps d'arrêt pour ce service dont Microsoft n'est pas responsable. Le service fait partie d'un vaste réseau de l'UE de registres de TVA nationaux.

## <a name="using-reverse-charge-vat-for-trade-between-eu-countries-or-regions"></a>Utilisation de frais renversés TVA pour les échanges entre pays ou régions de l'UE
Certaines compagnies doivent utiliser des frais renversés TVA dans leurs échanges avec d'autres compagnies. Par exemple, cette règle s'applique aux achats effectués auprès de pays/régions de l'Union européenne et aux ventes à des pays/régions de l'Union européenne.  
  
> [!NOTE]  
> Cette règle s'applique aux échanges avec des compagnies enregistrées comme assujetties à la TVA dans un autre pays/région de l'UE. Si vous commercez directement avec des clients dans d'autres pays/régions de l'UE, nous vous recommandons de prendre contact avec votre administration fiscale afin d'obtenir des informations sur les règles applicables en matière de TVA.  
  
> [!TIP]  
> Vous pouvez vérifier qu'une compagnie est enregistrée comme assujettie à la TVA dans un autre pays de l'UE en utilisant le service de validation des numéros d'inscription de TVA de l'UE. Le service est disponible gratuitement dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. Pour plus d'informations, voir la section _Vérifier les numéros d'identification TVA_ dans cette rubrique.

### <a name="sales-to-eu-countries-or-regions"></a>Ventes dans des pays/régions de l'UE
La TVA n'est pas calculée sur les ventes à des compagnies assujetties à la TVA situées dans d'autres pays/régions de l'UE. Vous devez déclarer la valeur de ces ventes aux pays/régions de l'UE séparément sur votre relevé fiscal.  

Pour calculer correctement la TVA sur les ventes effectuées dans des pays/régions de l'UE, vous devez procéder comme suit :  
  
* Configurez une ligne pour les ventes contenant les mêmes informations que pour les achats. Si vous avez déjà configuré des lignes sur la page Configuration du report TVA pour les achats effectués dans des pays/régions de l'UE, vous pouvez également utiliser ces lignes pour les ventes.  
* Affectez des groupes comptabilisation marché TVA dans le champ **Groupe compta. marché TVA** sur le raccourci **Facturation** de la fiche de chaque client de l'UE. Vous devez également saisir le numéro d'identification de TVA du client dans le champ **N° identif. intracomm.** du raccourci **International**.  

Lorsque vous reportez une vente à un client situé dans un autre pays/une autre région de l'UE, le montant de TVA est calculé et une écriture TVA est créée à l'aide des informations sur les frais renversés TVA et la base TVA (montant utilisé pour calculer la TVA). Aucune écriture n'est reportée sur les comptes TVA du grand livre.

## <a name="understanding-vat-rounding-for-documents"></a>Compréhension de l'arrondissement TVA pour les documents
Les montants figurant dans les documents qui n'ont pas encore été reportés sont arrondis et affichés de façon à correspondre à l'arrondissement final des montants réellement reportés. La TVA est calculée pour un document terminé, ce qui signifie que la TVA calculée est basée sur la somme de toutes les lignes ayant le même identificateur TVA dans le document.

## <a name="see-also"></a>Voir aussi  
[Configuration de la TVA sur encaissement](finance-setup-unrealized-vat.md)
