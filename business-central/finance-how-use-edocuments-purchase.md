---
title: Utilisation des documents électroniques dans le processus achat
description: Découvrez comment utiliser la fonctionnalité de document électronique liée aux factures d’achat et les commandes.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'electronic document, electronic invoice, e-document, e-invoice, receive, purchase, matching, mapping, Copilot'
ms.search.form: '50, 51, 138, 6103, 6133, 6121, 6167, 9307, 9308'
ms.date: 05/02/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="use-e-documents-in-the-purchases-process"></a>Utilisation des documents électroniques dans le processus achats

Vous pouvez utiliser des documents électroniques configurés (documents électroniques) avec les documents achat.

Vous pouvez utiliser les document achat suivants avec la fonctionnalité des documents électroniques :  

- Factures achat
- Bons de commande (à partir de la version 24.0)
- Notes de crédit achat
- Journaux généraux

> [!NOTE]
> À partir de la version 24.0 de [!INCLUDE[prod_short](includes/prod_short.md)], il est possible de connecter des **Bons de commande** avec les **Documents électroniques** reçus.  

## <a name="e-documents-in-purchases"></a>Documents électroniques achat

La réception de documents électroniques achat dans Dynamics 365 Business Central peut être effectuée en tant que traitement en lot ou manuellement.  

### <a name="how-to-set-up-vendors-to-work-with-different-purchase-documents"></a>Comment configurer les fournisseurs pour qu’ils travaillent avec différents documents achat

Suivez ces étapes pour configurer les fournisseurs afin qu’ils fonctionnent correctement avec les factures électroniques entrantes : 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Fournisseurs**, puis sélectionnez le lien associé. 
2. Choisissez le fournisseur que vous souhaitez configurer.   
3. Dans l’onglet rapide **Réception**, recherchez le champ **Recevoir le document électronique à** pour spécifier le document d’achat par défaut à générer à partir du document électronique reçu. 

   > [!NOTE]
   > Dans le champ **Recevoir le document électronique à**, les utilisateurs peuvent sélectionner une **facture d’achat** ou un **bon de commande** en fonction de ce qu’ils aimeraient créer à partir de la facture électronique reçue. Cette sélection n’affecte pas la création de documents correctifs ; dans les deux scénarios, le système générera une **Note de crédit**.  

   > [!NOTE]
   > Si l’utilisateur choisit l’option **Bon de commande** dans le champ **Recevoir le document électronique à**, le système essaiera de mettre à jour l’un des bons de commande existants, mais si le bon de commande d’un fournisseur dans le **Document électronique** reçu n’existe pas, [!INCLUDE[prod_short](includes/prod_short.md)] créera un nouveau **Bon de commande**, en utilisant la même approche que celle utilisée pour créer les nouvelles **Factures achat** expliquée plus loin sur cette page.  

4. Choisissez l’une des options que vous souhaitez utiliser pour le fournisseur sélectionné. 
5. Fermez la page.   

### <a name="to-work-with-purchase-invoices"></a>Pour utiliser des factures achat

#### <a name="run-the-batch-job"></a>Exécuter le traitement en lot

> [!NOTE]
> Ce traitement en lot est destiné à la collecte automatisée de vos factures entrantes. Cela ne peut fonctionner que dans un pays ou une région où la fonctionnalité existe.  

Chaque fois qu’une **File d’attente des projets** est sélectionnée pour exécution, si le service externe reçoit des factures entrantes envoyées par votre fournisseur, le système collecte et importe ces factures. Pour terminer le processus, procédez comme suit : 

1. Une fois le traitement en lot terminé, les factures récemment importées sont répertoriées sur la page **Documents électroniques**, ainsi que leurs informations détaillées de base. 
2. Pour afficher plus de détails, ouvrez un document électronique spécifique.   
3. S’il n’y a eu aucune erreur ou problème dans le document électronique, le champ **Enregistrement** mappe le numéro de document de la facture achat créée s'il est configuré sur la page **carte fournisseur** (automatiquement par le système). Sélectionnez le lien pour ouvrir le document.
 
   > [!NOTE]
   > Ce document créé par le système n’est pas le document reporté. 

4. Pour accéder directement au document achat, sélectionnez le champ **Enregistrement**. Après avoir ouvert la page **Facture achat**, vérifiez le document. Si tout est correct, reportez le document.  
5. Lorsque vous reportez le document achat, le champ **Enregistrement** du **document électronique** est mis à jour de **Facture** à **Facture achat** et le numéro du document achat reporté est disponible. Vous pouvez sélectionner le numéro pour ouvrir la facture achat reportée. 

Les détails des journaux sont les mêmes que ceux du processus de vente des documents électroniques.  

Étant donné que les erreurs dans le processus de vente sont principalement liées à la disponibilité du service, le document entrant peut contenir plusieurs raisons. La raison la plus courante d’une erreur est que le système ne peut pas reconnaître les lignes du document électronique que vous avez reçu de votre fournisseur. Il ne peut donc pas saisir de lignes dans votre facture achat. 

Il existe deux erreurs courantes :  

- Si vous souhaitez utiliser cette ligne spécifique de votre facture fournisseur qui a été directement reportée dans le compte du grand livre (G/L), vous devez avoir correctement configuré la valeur **Texte de mappage**. Pour contourner cette erreur si vous souhaitez utiliser des comptes du grand livre, sélectionnez **Mapper le texte au compte** pour créer un mappage spécifique de la valeur **Texte de mappage** avec la valeur **N° cpte débit** que vous souhaitez utiliser. 
- Si vous souhaitez suivre l’inventaire et utiliser les lignes de votre facture fournisseur pour renseigner les articles sur vos lignes de document, vous devez avoir correctement configuré le **N° référence article** . Pour contourner cette erreur, mappez l’élément externe avec vos numéros d’article à l’aide de la liste de référence d’article. Pour plus d’informations, voir [Utiliser les références article](inventory-how-use-item-cross-refs.md). 

Après avoir corrigé les erreurs et les avertissements, vous pouvez spécifier manuellement quand le système doit créer une facture achat en fonction de votre configuration en sélectionnant **Créer un document**.   

#### <a name="manually-import-invoices"></a>Importer manuellement les factures

Pour importer manuellement des documents électroniques externes, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Service de document électronique**, puis sélectionnez le lien associé. 
2. Sur la page **Service de document électronique** , sélectionnez le service actif.   
3. Sélectionnez **Recevoir** et téléchargez le fichier de document électronique que vous avez reçu du fournisseur. 
4. Si un message d’erreur apparaît, ouvrez le document électronique pour résoudre les problèmes. 
5. Lorsque vous avez fini de résoudre les problèmes, dans le groupe **Importer manuellement**, sélectionnez **Créer un document**.  
6. Une fois le document créé dans [!INCLUDE[prod_short](includes/prod_short.md)], l’utilisation d’un traitement en lot ne modifie pas la façon dont vous l’affichez. 

### <a name="e-documents-with-purchase-orders"></a>Documents électroniques avec bons de commande

#### <a name="to-link-purchase-orders-with-the-received-e-documents"></a>Pour lier les bons de commande aux documents électroniques reçus

Si votre **fournisseur** a configuré le champ **Recevoir le document électronique à** pour qu’il fonctionne avec **Bons de commande**, une fois qu'un document électronique est créé dans [!INCLUDE[prod_short](includes/prod_short.md)] (manuellement ou à partir d’un point de terminaison externe), [!INCLUDE[prod_short](includes/prod_short.md)] effectuera les opérations suivantes :  

1. Si le **Bon de commande** pour ce fournisseur particulier existe et qu’il existe un numéro de bon de commande dans le fichier **Document électronique** reçu, [!INCLUDE[prod_short](includes/prod_short.md)] liera automatiquement ce **Document électronique** avec le **Bon de commande** mentionné, et l’**État du document** de ce **Document électronique** sera **En cours**, et l’**État du document électronique** dans la sous-page **État du service** sera **Commande liée**. Ce lien sera visible dans le champ **Document** de ce **document électronique** spécifique. Si vous devez modifier le **Bon de commande** lié automatiquement, vous pouvez le faire à l’aide de l’action **Mettre à jour le lien du bon de commande** et choisir manuellement l’un des bons de commande existants pour ce fournisseur. Vous ne pouvez le faire qu’avant de faire correspondre les lignes entre le **document électronique** et le **bon de commande**.  

2. Si le **Bon de commande** pour ce fournisseur particulier existe, mais qu’il n’y a pas de numéro de bon de commande dans le fichier **Document électronique** reçu, [!INCLUDE[prod_short](includes/prod_short.md)] offrira la possibilité de choisir l’un des bons de commande existants lorsque et si vous avez téléchargé ce document manuellement. Cela ouvre la liste **Bons de commande** avec les commandes uniquement pour le fournisseur dont vous avez reçu le **Document électronique**. Vous devez sélectionner le **Bon de commande** que vous souhaitez, puis **OK**. Si vous n’avez pas réussi à sélectionner le **Bon de commande** correct ou si vous avez obtenu le **Document électronique** automatiquement à partir d’un point de terminaison externe à l’aide la **File d’attente des projets**, un nouveau **Document électronique** ne sera lié à aucun document d’achat. L’**état du document** affichera **Erreur** et l’**état du document électronique** dans la sous-page **État du service** affichera aussi **Erreur de traitement du document importé**. Pour terminer l’association avec le **Bon de commande**, choisissez l’action **Mettre à jour le lien du bon de commande** et l’un des bons de commande existants pour ce fournisseur. 

3. Si le **Bon de commande** pour ce fournisseur particulier n’existe pas au moment de la création du nouveau **Document électronique**, [!INCLUDE[prod_short](includes/prod_short.md)] créera un nouveau **Bon de commande**, en utilisant le même modèle de création que celui qui existe déjà pour les nouvelles **Factures achat**. L’**état du document** de ce **Document électronique** sera **Traité**, et l’**état du document électronique** dans la sous-page **État du service** sera **Document importé créé**. Ce lien sera visible dans le champ **Document** de ce **document électronique** spécifique.   

#### <a name="matching-lines-from-received-e-document-with-purchase-order"></a>Correspondance des lignes d’un document électronique reçu avec un bon de commande

Vous pouvez faire correspondre vos documents électroniques reçus avec les lignes de bon de commande provenant de deux endroits différents : à partir de la page **Document électronique** ou de la page **Bon de commande**. Le moyen le plus simple de localiser les **Bons de commande** déjà liés est d’utiliser la vignette **Bons de commande liés** faisant partie des **Activités liées aux documents électroniques**. Tous les documents non liés peuvent être trouvés à l’aide de la vignette **En attente des factures électroniques d’achat** où vous avez une liste de **Documents électroniques** que vous devez revoir.  

> [!NOTE]
> Les **Activités liées aux documents électroniques** avec ces deux vignettes sont disponibles dans les **Tableaux de bord** suivants : Évaluation du gestionnaire d’activité, Gestionnaire d’activité, Comptable, Gestionnaire d’inventaire et Expédition et réception.  

> [!NOTE]
> Si le pourcentage de TVA diffère entre le document entrant et le pourcentage de TVA de la compagnie, les documents correspondants ne peuvent pas être utilisés dans un environnement multi-pays.  

##### <a name="matching-lines-from-purchase-order"></a>Correspondance des lignes de bon de commande

Vous pouvez faire correspondre les lignes de la liste **Bons de commande** ou à partir de l’un des **Bons de commande** ouverts. Pour commencer, procédez comme suit :  

1. Sélectionnez la vignette **Bons de commande liés** sur votre Tableau de bord s’il y a un numéro. 
2. Choisir une des deux options de correspondance : 

   - Si vous souhaitez faire correspondre les lignes de la liste des **bons de commande**, sélectionnez la ligne **Bon de commande** que vous souhaitez faire correspondre et choisissez l'action **Mapper les lignes de documents électroniques**.  
   - Si vous souhaitez d’abord ouvrir le **Bon de commande**, ouvrez le document, puis choisissez l’action **Mapper les lignes document électronique**. 

3. Puisque les deux options ont le même processus, vous ouvrirez la page **Correspondance des bons de commande** avec le contenu suivant : 

    1. Dans l’en-tête, vous trouverez les informations suivantes, qui peuvent vous aider à cartographier plus facilement les lignes : 

       |Nom du champ |Désignation |
       |--------|-----------------|
       |Nom fournisseur |Spécifie le nom fournisseur du document électronique. |
       |N° document électronique |Spécifie le numéro de document électronique lié. |
       |Date du document électronique |Spécifie la date du document électronique lié.  |
       |Montant document électronique |Spécifie le montant total du document électronique lié, TVA comprise. |

    2. Dans les lignes, vous pourrez retrouver celles importées du fichier **Document électronique** sur le côté gauche et celles du **Bon de commande** existant sur le côté droit.  
    3. Toutes les lignes des deux côtés comportent des numéros d’article et des descriptions, ainsi qu’un **Coût unitaire direct** et un **% escompte ligne**.  
    4. Du côté des **Lignes importées** , vous pouvez également localiser le champ **Quantité** en tant que quantité totale de la facture électronique et le champ **Quantité correspondante** spécifiant la quantité qui correspond déjà aux lignes bon de commande. 
    5. Du côté des **Lignes bons de commande**, vous pouvez également trouver la **Quantité disponible** qui correspond à la quantité qui peut être mise en correspondance avec cette ligne (quantité reçue, mais non facturée) et **Qté. à facturer**, en précisant la quantité déjà mise en correspondance avec cette ligne. 
    6. Pour faire correspondre les lignes, sélectionnez les lignes des deux côtés que vous souhaitez faire correspondre et choisissez l’action **Correspondre manuellement** . Les lignes correspondantes seront marquées en vert. 
    7. Il est possible de faire correspondre un à un, mais il est également possible d’en faire correspondre plusieurs à un ou un à plusieurs, en sélectionnant plus de lignes d’un côté ou de l’autre avant de choisir l’action **Correspondre manuellement**. 
    8. Vous pouvez également choisir l’action **Faire correspondre automatiquement** pour faire correspondre automatiquement toutes les lignes ayant les mêmes valeurs pour **Type**, **Numéro**, **Prix unitaire**, **Escompte** et **Unité de mesure**. 
    9. Si vous faites une erreur, vous pouvez choisir l’action **Supprimer la correspondance** pour supprimer les lignes correspondantes du côté du bon de commande ou choisir l’action **Réinitialiser la correspondance** pour réinitialiser toutes les correspondances. 
    10. Si votre **document électronique** comporte de nombreuses lignes, vous pouvez choisir l’action **Afficher les lignes en attente** pendant le processus de mise en correspondance, pour supprimez toutes les lignes du document électronique si elles correspondent déjà complètement. Si vous avez besoin de voir toutes les lignes, vous pouvez toujours choisir l’action **Afficher toutes les lignes** . 

4. Une fois la correspondance terminée, vous devez choisir l’action **Appliquer au bon de commande** .   
5. Une fois que vous avez appliqué la correspondance au **bon de commande**, [!INCLUDE[prod_short](includes/prod_short.md)] mettra à jour les champs suivants :

    1. **Numéro de facture fournisseur** et **Date du document** sur l’en-tête du document seront mis à jour avec les valeurs du document électronique que vous avez reçu et lié. 
    2. La valeur **Qté. à facturer** dans les lignes sera mise à jour avec les valeurs de la colonne **Qté. à facturer** de la page **Correspondance des bons de commande** en fonction de la correspondance que vous avez effectuée. 
    3. Vous pouvez désormais reporter le document en choisissant l’action **Reporter**.  
    4. Une fois le document reporté, le champ **Document** de la page **Document électronique** modifiera la valeur et sera lié à la **Facture achat reportée**. 
    5. Fermez la page.  

> [!IMPORTANT]
> Par défaut, vous pouvez rapprocher uniquement les lignes ayant le même montant total dans les deux documents. Cela signifie que le **Coût unitaire direct** ainsi que la ligne affectée **% escompte** doivent être identiques, car dans un document, vous pouvez avoir un montant sans escompte et dans un autre avec escompte.  

Si vous souhaitez ajouter une certaine tolérance et autoriser la différence entre les lignes dans **Facture électronique** et **Bon de commande**, procédez comme suit :   

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration achats**, puis sélectionnez le lien associé.  
2. Vous souhaitez autoriser une tolérance dans le champ **% différence correspondance entre les documents électroniques**, en spécifiant le pourcentage maximum autorisé de différence de coût lors de la correspondance d’une ligne **Document électronique** entrante et de la ligne **Bon de commande**. 
3. Cette configuration s’appliquera à toutes les lignes correspondantes, mais encore une fois en tenant compte de la tolérance sur le montant total, comme pour le **Coût unitaire direct** avec le **% escompte ligne**.  
4. Fermez la page.   

##### <a name="matching-lines-from-e-document"></a>Correspondance les lignes d’un document électronique

Vous pouvez faire correspondre les lignes sur la page **E-Document** . Pour commencer, procédez comme suit :  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents électronique**, puis sélectionnez le lien associé. 
2. Sélectionnez **documents électroniques** que vous souhaitez correspondre.   
3. Choisissez l’action **Faire correspondre bon de commande** pour ouvrir la page **Correspondance des bons de commande**.  
4. Répétez les mêmes étapes que celles utilisées lorsque vous avez commencé la correspondance à partir des bons de commande.

### <a name="e-document-matching-assistance-copilot"></a>Copilote aide à la mise en correspondance de documents électroniques

> [!NOTE]
> Actuellement, le copilote **Assistance de mise en correspondance de documents électroniques** est en version préliminaire prête pour la production et est disponible dans le monde entier, sauf au Canada. Cela ne fonctionne qu’en anglais. 

> [!NOTE]
> Copilot est l’Assistant optimisé par l’IA qui aide les gens de votre organisation à libérer leur créativité et à automatiser les tâches fastidieuses. Le copilote **Assistance de rapprochement de documents électroniques** aide les utilisateurs à faire facilement correspondre les factures électroniques reçues avec les lignes de bon de commande existantes, en utilisant le modèle LLM pour faire correspondre les lignes entre deux documents différents. 

#### <a name="to-activate-the-copilot"></a>Pour activer le copilote

Si vous n’avez pas activé le copilote **Assistance de correspondance de documents électroniques**, vous devez le faire manuellement. Pour activer le copilote **Assistance de correspondance de documents électroniques**, suivez ces étapes : 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Copilote et capacités IA**, puis sélectionnez le lien associé. 
2. Dans la liste des fonctionnalités, choisissez **Assistance de mise en correspondance de documents électroniques** et modifiez l’état en **Actif**.  

Une fois le copilote activé, vous pouvez commencer à l’utiliser.

#### <a name="use-the-e-document-matching-assistance-copilot"></a>Utiliser le copilote aide à la mise en correspondance de documents électroniques

Si Copilot est activé, les actions existantes **Mapper lignes documents électroniques** sur les commandes achetées et **Faire correspondre bon de commande** sur la page **Document électronique** présenteront des icônes différentes, symbolisant la fonctionnalité IA. Vous pouvez exécuter ces actions (les mêmes que dans les exemples précédents dans la liste des bons de commande) à partir de l’un des **Bons de commande** ou du **Document électronique**. Toutes les étapes d’exécution sont les mêmes, mais lorsque vous exécutez cette action, le résultat sera différent et vous devez suivre ces étapes :  

1. Choisissez l’action **Mapper lignes documents électroniques** ou **Faire correspondre bon de commande** pour les documents déjà liés.  
2. Remarquez que l’invite **Lignes de commande de correspondance de documents électroniques avec Copilot** fonctionne et la page **Rapprochement des bons de commande** se trouve en arrière-plan. Cela signifie que le même processus se produit mais avec le support automatique du **Copilot**, qui gère le processus de mise en correspondance à votre place. 
3. Après quelques secondes, le **Lignes de commande de correspondance de documents électroniques avec copilote** suggérera des lignes à faire correspondre avec quelques détails supplémentaires : 

    1. Dans l’en-tête de l’invite, vous pouvez trouver les informations suivantes : 

       |Nom du champ |Désignation |
       |--------|-----------------|
       |Correspondance automatique | Spécifie le nombre de correspondances proposées automatiquement. Ceci est basé sur une comparaison de chaînes et s’il y a 80 % ou plus de descriptions qui se chevauchent, le système fera automatiquement correspondre ces descriptions sans utiliser les fonctionnalités GPT. |
       |Copilot mis en correspondance | Spécifie le nombre de correspondances proposées par le copilote en utilisant à la fois une comparaison de chaînes et sémantique. |
       |N° document électronique | Spécifie le numéro du document électronique lié. |
       |Montant total de la facture, hors TVA | Spécifie le montant total de la facture, hors TVA. |
       |Montant total mis en correspondance, TVA comprise | Spécifie le montant mis en correspondance, avec TVA. |
    
    2. Si toutes les lignes correspondent, vous verrez le texte vert dans le coin supérieur droit : **Toutes les lignes (100 %) correspondent. Examiner les propositions de match**.  
    3. Dans les lignes **Proposition correspondance**, vous pouvez trouver les informations suivantes :  

       |Nom du champ |Désignation |
       |--------|-----------------|
       |N° ligne document électronique | Spécifie le numéro de ligne du document électronique (provenant du fichier de document électronique d’origine). |
       |Description de la ligne document électronique | Spécifie la description de ligne du document électronique (provenant du fichier de document électronique d’origine). |
       |Quantité mise en correspondance | Spécifie la quantité qui sera affectée à la ligne bon de commande. |
       |Proposition | Spécifie l’action proposée par l’IA, et ces actions suggérées sont liées à la mise en correspondance des lignes bon de commande. |

    4. Toutes les lignes entièrement suggérées et assorties sont marquées de couleur verte. S’il y a un problème, c’est-à-dire un prix différent, mais dans la fourchette de prix autorisée, cette ligne sera marquée en jaune, et s’il y a une similitude entre les champs de description mais que la différence de prix est supérieure à celle autorisée, cette ligne sera marquée en rouge. 
    5. Si vous n’êtes pas satisfait de certaines suggestions, vous pouvez les supprimer en utilisant le **Supprimer la ligne** action.  
    6. Si vous souhaitez voir les correspondances de propositions, vous pouvez sélectionner le lien dans le **Proposition** colonne pour ouvrir la **Détails de la correspondance des documents électroniques** page. 
    7. Sur la page **Détails de la correspondance des documents électroniques**, vous pouvez comparer les détails du **Document électronique** et du **Bon de commande**, pour être certain de la correspondance proposée avant de la confirmer. 
    8. Après révision, fermez la page.   

4. Si vous n’êtes pas satisfait de la plupart des suggestions, ou si vous ne souhaitez pas utiliser la fonctionnalité **Lignes de commande de correspondance de documents électroniques avec Copilot**, sélectionnez **L'ignorer** et vous pourrez continuer la correspondance manuelle comme expliqué précédemment.  
5. Si vous souhaitez conserver les suggestions, choisissez le bouton **Conserver** et le système enregistrera toutes les suggestions faites par **Copilote**.  
6. [!INCLUDE[prod_short](includes/prod_short.md)] fermera l’invite Copilot, et les lignes de la page **Rapprochement des bons de commande** seront marquées en vert, car elles sont déjà rapprochées. 
7. Vous pouvez désormais continuer à travailler pendant que vous effectuez une correspondance manuelle ; cela signifie que vous pouvez supprimer des correspondances, les faire correspondre manuellement ou réinitialiser la correspondance. Si vous ne souhaitez pas apporter de modifications, choisissez simplement l’action **Appliquer au bon de commande** et continuez à travailler avec le **Bon de commande**. 

> [!NOTE]
> Vous pouvez à nouveau choisir l’action **Mettre en correspondance avec Copilot** sur la page **Correspondance des bons de commande**, mais dans ce cas, il vous sera demandé si vous souhaitez écraser les correspondances existantes, car toutes les lignes ont déjà été mises en correspondance.  

> [!NOTE]
> L’analyse prix/coût et le contrôle de la quantité disponible font partie de l’activité de prétraitement.   

## <a name="overview-of-e-document-statuses"></a>Vue d’ensemble des états des documents électroniques

Pour obtenir un meilleur aperçu de tous les documents électroniques de la compagnie, vous pouvez sélectionner le centre de rôles **Comptable** où existent les états des documents électroniques. Vous y trouverez des activités de documents électroniques qui ont les états suivants :

- **Documents électroniques entrants :**

    - Traité
    - En cours
    - Erreur


## <a name="see-also"></a>Voir aussi .

[Configurer des documents électroniques](finance-how-setup-edocuments.md)    
[Utilisation du documents électroniques dans le processus vente](finance-how-use-edocuments.md)   
[Extension de la fonctionnalité des documents électroniques](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)    
[Gestion financière](finance.md)    
[Facturation des ventes](sales-how-invoice-sales.md)    
[Enregistrer les achats avec les factures achat et les commandes](purchasing-how-record-purchases.md)    
[Utiliser Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]

