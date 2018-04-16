---
title: "Procédure pas à pas : planification automatique des approvisionnements | Microsoft Docs"
description: "Les expressions comme « exécution planification » et « exécution MRP » se rapportent au calcul du programme directeur de production (PDP) et de la planification des besoins de matières (MRP) en fonction de la demande réelle et projetée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: bbe470538bb79e9f6fb6860ee32d75b5d56db9e8
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="walkthrough-planning-supplies-automatically"></a>Procédure pas à pas : planification automatique des approvisionnements
Les expressions comme « exécution planification » et « exécution MRP » se rapportent au calcul du programme directeur de production (PDP) et de la planification des besoins de matières (MRP) en fonction de la demande réelle et projetée.  

- Le calcul PDP est le calcul de la planification de production principale basé sur la demande réelle et la prévision de production. Le calcul PDP est utilisé pour les articles finis disposant de prévisions ou d'une ligne document de vente. Ces articles sont appelés « articles PDP » et identifiés de façon dynamique au début du calcul.  
- Le calcul MRP est le calcul des besoins matière basé sur la demande réelle de composants et la prévision de production au niveau du composant. Le calcul MRP n'est effectué que pour les articles qui ne sont pas des articles PDP. Le but global du calcul MRP est de générer des plans formels en phases, par article, afin de fournir le bon article au bon moment, au bon endroit et dans la bonne quantité.  

  Les algorithmes de planification utilisés pour les calculs PDP et MRP sont identiques. Ils utilisent la présentation au net, la réutilisation des commandes d'approvisionnement existantes et les messages d'action. Le processus du système de planification examine ce qui est ou sera nécessaire (demande) et ce qui est disponible ou attendu (approvisionnement). Lorsque ces quantités sont déduites l'une de l'autre, des messages d'action s'affichent dans la feuille planification. Ces messages proposent de créer une commande d'approvisionnement, de modifier la quantité ou la date ou encore d'annuler une commande d'approvisionnement existante. Les commandes d'approvisionnement peuvent être des bons de production, des bons de commande et des ordres de transfert. Pour plus d'informations, voir [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md).  

  Le résultat de la planification est obtenu en partie grâce aux ensembles d'offre et de demande de la base de données et en partie grâce à la configuration des fiches unité de stock ou des fiches article, des nomenclatures de production et des itinéraires.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
 Cette procédure pas à pas démontre comment utiliser le système de planification de l'approvisionnement pour planifier automatiquement tous les bons de production et toutes les bons de commande nécessaires à la production de 15 vélos de cyclotourisme figurant sur différentes documents de vente. Pour que cette procédure soit claire et réaliste, le nombre de lignes planification a été délimité en filtrant tous les autres ensembles d'offre et de demande de la compagnie fictive CRONUS International Ltd., à l'exception de la demande de vente pour l'emplacement BLUE.  

 Cette procédure pas à pas présente les tâches suivantes :  

-   Création du document de vente et calcul d'un programme d'approvisionnement complet.  
-   Affichage des paramètres de planification et des écritures traçabilité à l'origine des lignes planification.  
-   Création automatique des commandes d'approvisionnement proposées.  
-   création de demandes de vente et replanification en conséquence.  

## <a name="roles"></a>Rôles  

-   Gestionnaire de production  
-   Agent d'achats  

## <a name="prerequisites"></a>Conditions préalables  
 Pour exécuter ce processus pas à pas, vous devez :  

-   Utilisez la compagnie de démonstration CRONUS International Ltd.  
-   Pour modifier plusieurs valeurs de configuration des articles, suivez les instructions de la section « Préparation d'exemples de données », dans la suite de cette procédure.  

## <a name="story"></a>Scénario  
 Le client, Cannon Group PLC, commande cinq vélos cyclotourisme pour une livraison le 05/02/2014 (5 février).  

 Eduardo, Gestionnaire de production, procède à la planification de l'approvisionnement courante pour la première semaine de février 2014. Il filtre sur son propre emplacement, BLEU, et entre un intervalle de planification de la date de travail du 23/01/2014 au 07/02/2014 avant de calculer un programme d'approvisionnement initial.  

 La seule demande cette semaine concerne le document de vente de Cannon Group. Eduardo constate qu'aucune ligne planification ne comporte d'avertissement et il crée des commandes d'approvisionnement sans modifications pour les lignes planification proposées.  

 Le lendemain, avant que les commandes d'approvisionnement initiales ne soient démarrées ou reportées, Eduardo est averti qu'un autre client a commandé dix vélos cyclotourisme pour une livraison le 12/02/2014. Il adapte son calcul du programme d'approvisionnement en fonction de la modification de la demande. Ce nouveau calcul aboutit à une planification par écart proposant des changements de délai et de quantités de certaines commandes d'approvisionnement créées dans un premier temps.  

 Au cours des diverses étapes de la planification, Eduardo recherche les commandes concernées et utilise la fonction Chaînage pour voir quelle demande est couverte par quel approvisionnement.  

## <a name="preparing-sample-data"></a>Préparation d'exemples de données  
 Créez des unités de stock pour chaque vélo cyclotourisme et une sélection de ses composantes, dont les numéros d'article vont de 1001 à 1300. (Certaines composantes sont exclues pour simplifier les procédures.) Ajustez les paramètres de planification des composantes sélectionnées pour présenter un résultat plus transparent.  

### <a name="to-create-stockkeeping-units"></a>Pour créer des unités de stock  

1.  Ouvrez la fiche article pour l'article 1001, vélo cyclotourisme.  
2.  Choisissez l'action **Créer unité de stock**.  
3.  Dans la fenêtre **Créer unité de stock**, ne modifiez aucune option ni aucun filtre, puis cliquez sur le bouton **OK**.  
4.  Répétez les étapes 1 à 3 pour chaque article dont le numéro est compris entre 1100 et 1300.  

### <a name="to-change-selected-planning-parameters"></a>Pour modifier des paramètres de planification sélectionnés  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Unités de stock**, puis sélectionnez le lien associé.  
2. Ouvrez la fiche unité de stock BLEU de l'article 1100, Roue avant.  
3. Sur le raccourci **Planification**, renseignez les champs comme indiqué dans le tableau ci-dessous.  


   | Politique réapprovisionnement | Quantité de stocks de sécurité | Période de cumul de lot | Période de replanification |
   |-------------------|-----------------------|-------------------------|---------------------|
   |    Lot pour lot    |         Vide         |           2S            |         2S          |


4. Répétez les étapes 2 et 3 pour chaque point de stock dont le numéro est compris entre 1100 et 1300.  

   Vous venez de préparer les données d'exemple de la procédure pas à pas.  

## <a name="creating-a-regenerative-supply-plan"></a>Création d'un programme d'approvisionnement régénératif  
 En réaction à un nouveau document de vente pour cinq vélos, Ricardo démarre le processus de planification en définissant les options, filtres et intervalle de planification afin d'exclure toutes les autres demandes sauf celle de la première semaine de février à l'emplacement BLEU. Il commence par calculer un calendrier de production principal (CDP), puis un programme d'approvisionnement complet pour toute demande de niveau inférieur (MRP).  

### <a name="to-create-the-sales-order"></a>Pour créer le document de vente  

1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Dans la fenêtre **Document de vente**, renseignez les champs comme indiqué dans la table suivante.  

    |Nom débiteur|Date de livraison|N° d'article|Magasin|Quantité|  
    |----------------------------|-------------------|--------------|--------------|--------------|  
    |Cannon Group.|05/02/2014|1001|BLEU|5|  

4.  Acceptez l'avertissement de disponibilité et choisissez le bouton **Oui** pour enregistrer la nouvelle quantité demandée.  

### <a name="to-create-a-regenerative-plan-to-fulfill-demand-at-location-blue"></a>Pour créer un plan régénératif afin de répondre à la demande à l'emplacement BLEU  

1.  Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille planification**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Calculer planning régénératif**.  
3.  Dans la fenêtre **Calc. planning - F. planning** , renseignez les champs comme indiqué dans le tableau suivant.  

    |Calculer planning|Date début|Date de fin|Afficher résultats :|Limiter les totaux à|  
    |--------------------|-------------------|-----------------|-------------------|---------------------|  
    |**PDP** = Oui<br /><br /> **MRP** = Non|23-01-2014<br /><br /> (date de travail)|07/02/2014|1001..1300|Filtre emplacement = BLEU|  

4.  Pour démarrer l''exécution de la planification, cliquez sur le bouton **OK**.  

     Une ligne planification est créée proposant qu'un bon de production planifié soit émis afin de produire les dix vélos cyclotourisme, article 1001 pour le 05/02/2014, la date de livraison du document de vente.  

     Vérifiez ensuite que cette ligne planification est liée au document de vente de Cannon Group à l'aide de la fonction **Suivi de commande**, qui lie de manière dynamique la demande à son approvisionnement planifié.  

5.  Sélectionnez la nouvelle ligne planification, puis choisissez l'action **Suivi de commande**.  
6.  Dans la fenêtre **Chaînage** choisissez l'action **Afficher**.  

     Le document de vente pour cinq vélos cyclotourisme au client ayant le numéro 10 000 le 05/02/2014 s'affiche.  

7.  Fermez les fenêtres **Document de vente** et **Suivi de commande**.  

### <a name="to-calculate-mrp-to-include-underlying-component-needs"></a>Pour calculer MRP afin d'inclure les besoins sous-jacents en composantes  

1.  Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille planification**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Calculer planning régénératif**.  
3.  Dans la fenêtre **Calc. planning - F. planning** , renseignez les champs comme indiqué dans le tableau suivant.  

    |Calculer|Date début|Date de fin|Afficher résultats :|Limiter les totaux à :|  
    |---------------|-------------------|-----------------|-------------------|----------------------|  
    |**PDP** = Oui<br /><br /> **MRP** = Oui|23-01-2014|07/02/2014|1001..1300|Filtre emplacement = BLEU|  

4.  Pour démarrer l''exécution de la planification, cliquez sur le bouton **OK**.  

     Un total de 14 lignes planification est créé suggérant des commandes d'approvisionnement pour l'ensemble de la demande représentée par le document de vente des vélos cyclotourisme à l'emplacement BLEU.  

## <a name="analyzing-the-planning-result"></a>Analyse du résultat de la planification  
 Pour analyser les quantités proposées, Eduardo passe en revue les lignes planification sélectionnées pour afficher les écritures traçabilité et les paramètres de planification.  

 Dans la fenêtre **Feuille planification**, notez que dans la colonne **Date d'échéance**, les commandes d'approvisionnement proposées sont programmées en amont à partir de la date d'échéance dans le document de vente, le 05/02/2014. La chronologie commence avec la ligne planification supérieure par le bon de production visant à produire les vélos cyclotourisme terminés. La chronologie se termine sur la ligne planification inférieure par le bon de commande de l'un des articles de niveau inférieur, 1255, arrière de douille, prévu le 30/01/2014. Tout comme la ligne planification de l'article 1251, Axe roue arrière, cette ligne représente un bon de commande pour les composantes dues à la date début de son parent produit, l'article de sous-assemblage 1250, qui est dû au 02-03-2014. Tout au long de la feuille, vous pouvez voir que tous les articles sous-jacents sont dus à la date début de leurs parents.  

 La ligne planification de l'article 1300, ensemble chaîne, indique dix pièces. Ceci diffère des cinq pièces que nous estimons nécessaires pour répondre au document de vente. Visualisez les écritures chaînage.  

### <a name="to-view-order-tracking-entries-for-item-1300"></a>Pour afficher les écritures chaînage de l'article 1300  

1.  Sélectionnez la ligne planification correspondant à l'article 1300, puis choisissez l'action **Suivi de commande**.  

     Les deux lignes dans la fenêtre **Suivi de commande** indiquent que cinq pièces sont suivies depuis la ligne planification (première ligne de suivi de commande) jusqu'au document de vente 1001 (deuxième ligne de suivi de commande). Les cinq dernières pièces indiquées sur la ligne planification ne sont associées à aucune ligne de document, mais bien à un paramètre de planification, à une écriture prévision ou à une écriture commande permanente. Ces quantités non chaînées sont résumées dans le champ **Quantité non chaînée** dans l'en-tête de la fenêtre **Chaînage**.  

2.  Choisissez le champ **Quantité non chaînée**.  

     La fenêtre **Éléments planification sans suivi** indique que l'article 1300 utilise un paramètre de planification, Qté minimum commande, de 10,00. Par conséquent, la ligne planification concerne dix pièces au total, mais seulement cinq d'entre elles peuvent être suivies jusqu'à une demande. Les cinq dernières pièces correspondent à une quantité non chaînée afin de satisfaire le paramètre de planification. Revisualisez le paramètre de planification.  

### <a name="to-check-the-planning-parameter"></a>Pour vérifier les paramètres de planification  

1.  Dans la fenêtre **Éléments planification sans suivi**, sélectionnez la ligne de suivi de commande pour l'article 1300.  
2.  Cliquez sur le champ **N° article**, puis choisissez l'action **Avancé**.  
3.  Dans la fenêtre **Liste des articles**, choisissez l'action **Unités de stock**.  
4.  Dans la fenêtre **Liste des unités de stock**, ouvrez la fiche unité de stock BLEU.  
5.  Dans le raccourci **Planification**, notez que le champ **Qté minimum commande** contient 10.  
6.  Fermez toutes les fenêtres sauf **Feuille de travail de planification**.  

### <a name="to-view-more-order-tracking-entries"></a>Pour afficher des écritures chaînage  

1. Sélectionnez la ligne planification correspondant à l'article 1110, Jante, puis choisissez l'action **Suivi de commande**.  

    La fenêtre **Chaînage** indique que cinq jantes sont nécessaires pour chaque ordre de fabrication des roues avant et arrière respectivement.  

    Le même suivi de commande s'applique aux lignes planification pour les articles 1120, 1160 et 1170. Pour l'article 1120, le champ **Quantité par** dans la nomenclature de production de chaque roue est 50 PCS, ce dont résulte un besoin total de 100.  

    La ligne planification de l'article 1150 pour six pièces semble irrégulière. Analysez.  

2. Sélectionnez la ligne planification correspondant à l'article 1150, puis choisissez l'action **Suivi de commande**.  

    La fenêtre **Chaînage** indique que cinq unités sont suivies pour la roue avant, et une unité est non suivie. Affichez la quantité non chaînée.  

3. Choisissez le champ **Quantité non chaînée**.  

    La fenêtre **Éléments planification sans suivi** indique que l'article 1150 utilise un paramètre de planification, Commandé par, de 2,00, ce qui indique que lorsque l'article est commandé, il doit l'être dans une quantité divisible par 2. Le chiffre le plus proche de 5 divisible par 2 est 6.  

    Le même suivi de commande s'applique aux lignes planification pour les composantes Moyeu avant, les articles 1151 et 1155, mais chaque besoin est multiplié par le pourcentage rebut défini pour l'article 1150 dans le champ **Pourcentage de rebut** de la fiche article.  

   L'analyse du programme d'approvisionnement initial est terminée. Notez que la case à cocher **Accepter message d'action** est activée dans toutes les lignes planification, ce qui indique qu'elles sont prêtes à être converties en commandes d'approvisionnement.  

## <a name="carrying-out-action-messages"></a>Exécution de messages d'action  
 Eduardo convertit ensuite les lignes planification proposées en commandes d'approvisionnement à l'aide de la fonction **Traiter msg. action**.  

### <a name="to-automatically-create-the-suggested-supply-orders"></a>Pour créer automatiquement les commandes d'approvisionnement proposées  

1. Activez la case à cocher **Accepter message d'action** sur toutes les lignes planification avec un avertissement de type Exception.  
2. Choisissez l'action **Traiter message d'action**.  
3. Dans la fenêtre **Traiter msg. action - Planning**, complétez les champs comme indiqué dans le tableau suivant.  


   | Bon de production |   Bon de commande   |   Ordre de transfert   |
   |------------------|--------------------|--------------------|
   |    planifié ferme   | Créer bons de commande | Créer ordres transfert |


4. Cliquez sur le bouton **OK** pour créer automatiquement toutes les commandes d'approvisionnement proposées.  
5. Fermez la fenêtre **Feuille de travail de planification** vide.  

   Le calcul initial, l'analyse et la création d'un plan d'approvisionnement pour la demande à l'emplacement BLEU la première semaine de février sont terminés. Dans la section suivante, un autre client commande dix vélos cyclotourisme, et Eduardo doit procéder à une nouvelle planification.  

## <a name="creating-a-net-change-plan"></a>Création d'un planning par écart  
 Le lendemain, avant même qu'une commande d'approvisionnement ne soit démarrée ou reportée, un nouveau document de vente arrive de Libros S.A. pour dix vélos cyclotourisme à livrer le 12/02/2014. Eduardo est averti de cette nouvelle demande et il procède à une nouvelle planification afin d'adapter le programme d'approvisionnement actif. Eduardo ne calcule, à l'aide de la fonction Planification par écart, que les modifications apportées à la demande ou à l'approvisionnement depuis la dernière exécution de la planification. En outre, il prolonge la période de planification au 14/02/2014 afin d'inclure la nouvelle demande de vente du 12/02/2014.  

 Le système de planification calcule le meilleur moyen de couvrir la demande de ces deux produits identiques, par exemple consolider certaines commandes achat et certains ordres de fabrication, replanifier d'autres commandes et en créer de nouvelles, s'il y a lieu.  

### <a name="to-create-the-new-sales-demand-and-replan-accordingly"></a>Pour créer les demandes de vente et replanifier en conséquence  

1. Sélectionnez l'action **Nouveau**.  
2. Dans la fenêtre **Document de vente**, renseignez les champs comme indiqué dans la table suivante.  


   | Nom débiteur | Date de livraison | N° d'article | Magasin | Quantité |
   |-----------------------|---------------|----------|----------|----------|
   |      Libros S.A      |  12/02/2014   |   1001   |   BLEU   |    10    |


3. Acceptez l'avertissement de disponibilité et cliquez sur le bouton **Oui** pour enregistrer la quantité demandée.  
4. Procédez à une replanification afin d'adapter le programme d'approvisionnement actif.  
5. Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille planification**, puis sélectionnez le lien associé.  
6. Choisissez l'action **Calculer planning par écart**.  
7. Dans la fenêtre **Calc. planning - F. planning** , renseignez les champs comme indiqué dans le tableau suivant.  


   |             Calculer planning              | Date début | Date de fin | Afficher résultats : |    Limiter les totaux à     |
   |-----------------------------------------|---------------|-------------|---------------|------------------------|
   | **PDP** = Oui<br /><br /> **MRP** = Oui |  23-01-2014   | 14/02/2014  |  1001..1300   | Filtre emplacement = BLEU |


8. Pour démarrer l''exécution de la planification, cliquez sur le bouton **OK**.  

   Un total de 14 lignes planification est créé. Notez que sur la première ligne planification, le champ **Message d'action** affiche **Nouveau**, le champ **Quantité**, 10 et le champ **Date d'échéance**, 12/02/2014. Cette nouvelle ligne pour l'article parent supérieur, 1001, vélo cyclotourisme, est créée, car l'article utilise une méthode de réapprovisionnement de la **commande**, ce qui signifie qu'il doit être approvisionné selon une relation un à un par rapport à sa demande, le document de vente indique dix pièces.  

   Les deux lignes planification suivantes concernent les bons de production des roues des vélos cyclotourisme. Chaque commande existante de cinq, dans le champ **Quantité initiale**, passe à 15 dans le champ **Quantité**. Les dates d'échéance des deux bons de production sont inchangées, comme indiqué dans le champ **Message d'action** qui contient **Changer qté**. Cela vaut également pour la ligne planification de l'article 1300, sauf que son multiple commande de 10,00 arrondit la demande suivie de 15 pièces à 20.  

   Toutes les autres lignes planning ont un message d'action **Replanifier & changer qté**. Ceci signifie que, outre le fait de voir leur quantité augmentée, les dates d'échéance sont déplacées par rapport au programme d'approvisionnement afin d'inclure la quantité supplémentaire au temps de production disponible (capacité). Les composantes achetées sont reprogrammées et augmentées pour répondre aux bons de production. Analysez la nouvelle planification.  

## <a name="analyzing-the-changed-planning-result"></a>Analyse du résultat de la planification modifié  
 Étant donné que tous les articles lot pour lot planifiés dans le filtre (1100 à 1300) ont une période de reprogrammation de deux semaines, toutes leurs commandes d'approvisionnement existantes sont modifiées pour répondre à la nouvelle exigence, à savoir la période de deux semaines spécifiée.  

 Plusieurs lignes planification sont simplement multipliées par trois pour fournir 15 vélos au lieu de 5, et les dates d'échéance sont remontées dans le temps pour fournir les quantités augmentées au plus tard à la date de livraison du document de vente à Cannon Group. Pour ces lignes planification, toutes les quantités peuvent être suivies. Les autres lignes planification sont augmentées de dix pièces, et leurs dates d'échéance sont déplacées. Pour ces lignes planification, une partie des quantités ne fait l'objet d'aucun suivi en raison de différents paramètres de planification. Visualisez certaines de ces écritures chaînage.  

### <a name="to-view-order-tracking-entries-for-item-1250"></a>Pour afficher les écritures chaînage de l'article 1250  

1.  Sélectionnez la ligne planification correspondant à l'article 1250, puis choisissez l'action **Suivi de commande**.  

     Les sept lignes de la fenêtre **Suivi de commande** indiquent que cinq et dix pièces font l'objet d'un suivi pour la roue arrière pour les vélos de cyclotourisme respectivement sur les deux documents de vente.  

     Les cinq dernières pièces sont non chaînées. Analysez.  

2.  Choisissez le champ **Quantité non chaînée**.  

     La fenêtre **Éléments planification sans suivi** indique que l'article 1250 utilise un paramètre de planification, Commandé par, de 10,00. Par conséquent, la ligne planification concerne 20 pièces au total pour approcher le besoin réel en arrondissant au nombre le plus proche divisible par 10. Les cinq dernières pièces correspondent à une quantité non chaînée afin de satisfaire le paramètre de planification.  

3.  Fermez toutes les fenêtres sauf **Feuille de travail de planification**.  

### <a name="to-view-an-existing-order"></a>Pour afficher une commande existante  

1. Dans la ligne planification de l'article 1250, sélectionnez le champ **N° ordre référence** .  
2. Dans la fenêtre **O.F. planifié ferme** pour le moyeu arrière. La commande existante pour dix pièces, que vous avez créée dans la première exécution de la planification, s'ouvre.  
3. Fermez l'ordre de production planifié ferme.  

   La procédure pas à pas, relative au mode d'utilisation du système de planification permettant de détecter automatiquement la demande, de calculer les commandes d'approvisionnement adéquates en fonction de la demande et des paramètres de planification, puis de créer automatiquement différents types de commandes d'approvisionnement avec les dates et quantités appropriées, est terminée.  

## <a name="see-also"></a>Voir aussi  
 [Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)   
 [Procédure pas à pas : planification manuelle des approvisionnements](walkthrough-planning-supplies-manually.md)   
 [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)

