---
title: À propos de la fonctionnalité Planification
description: Découvrez comment la planification utilise les données de l’offre et de la demande pour suggérer comment équilibrer l’offre pour répondre à la demande.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.form: '5430,'
ms.date: 09/19/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="about-planning-functionality"></a>À propos de la fonctionnalité Planification

Le système de planification prend en compte toutes les données d'offre et de demande, ajuste les résultats et génère des suggestions pour l'équilibrage de l'offre en fonction de la demande.  

Pour plus d'informations, voir [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md).  

> [!NOTE]  
> Pour tous les champs mentionnés dans cette rubrique, lisez l'info-bulles pour comprendre leur fonction. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="supply-and-demand"></a>Offre et demande

La planification comporte deux volets : l'offre et la demande. Ceux-ci doivent s’équilibrer pour garantir que la demande est satisfaite.  

- La demande désigne toute sorte de besoin brut, tel qu’un document de vente, une commande service ou un besoin composante pour des ordres d’assemblage ou de fabrication, un transfert sortant, une commande ouverte ou une prévision. En outre, il existe d’autres types techniques de demande, tels qu’un ordre de fabrication ou un bon de commande négatif, un inventaire négatif et un retour achat.  
- Le réapprovisionnement fait référence à toute sorte de réapprovisionnement telle qu’un inventaire, un bon de commande, un ordre d’assemblage, un bon de production ou un transfert entrant. Par conséquent, il peut y avoir un document de vente ou une commande service négative, un besoin de composante ou un retour vente négatif qui représentent également l’offre.  

Un autre objectif du système de planification est de garantir que l'inventaire n'augmente pas inutilement. En cas de baisse de la demande, le système de planification suggère de reporter, de réduire ou d'annuler des ordres de réapprovisionnement existants.  

## <a name="planning-calculation"></a>Calcul de planification

Le système de planification est guidé par la demande prévue et réelle des clients, ainsi que par les paramètres de réapprovisionnement d'inventaire. L’exécution du calcul de planification a pour effet que l’application suggère des mesures spécifiques ([messages d’action](production-how-to-run-mps-and-mrp.md#action-messages)) à prendre concernant le réapprovisionnement possible auprès de fournisseurs, les transferts entre entrepôts ou la production. S'il y a déjà des ordres de réapprovisionnement, les mesures suggérées peuvent être d'augmenter ou d'accélérer les commandes pour répondre à l'évolution de la demande.  

La base de la routine de planification réside dans le calcul gros/net. Les besoins nets déterminent les libérations de commandes planifiées, qui sont programmées sur la base des informations d'itinéraire (articles fabriqués) ou du délai de réapprovisionnement de la fiche article (articles achetés). Les quantités de libération de commandes planifiées sont basées sur le calcul de planification et affectées par les paramètres définis sur les fiches article individuelles.  

> [!TIP]
> Le système de planification dépend de la façon dont votre organisation utilise les emplacements. Pour plus d’informations, consultez [Planification avec ou sans emplacements](production-planning-with-without-locations.md).

## <a name="planning-with-manual-transfer-orders"></a>Planification à l’aide d’ordres de transfert manuels

Dans le champ **Système réappro** d’une fiche unité de stock, vous pouvez configurer le système de planification pour créer des ordres de transfert destinés à équilibrer l’offre et la demande dans tous les emplacements.  

Outre ce type d'ordre de transfert automatique, vous devrez parfois effectuer un déplacement général des quantités en inventaire vers un autre emplacement, quelle que soit la demande existante. Vous créez pour cela un ordre de transfert manuel correspondant à la quantité à déplacer. Pour être sûr que le système de planification ne tente pas de manipuler cet ordre de transfert manuel, vous devez paramétrer le champ **Flexibilité planification** des lignes transfert sur Aucune.  

À l'inverse, si vous souhaitez que le système de planification ajuste les quantités de l'ordre de transfert et les dates en fonction de la demande existante, vous devez paramétrer le champ **Flexibilité planification** sur la valeur Illimitée.

## <a name="planning-parameters"></a>Paramètres de planification

Les paramètres de planification déterminent le moment, la quantité et la méthode de réapprovisionnement en fonction des divers paramètres de la fiche article (ou unité de stock) et de la configuration de la fabrication.  

Les paramètres de planification suivants existent pour l'article ou la fiche unité de stock :  

- Période tampon  
- Quantité tampon  
- Politique réapprovisionnement  
- Point de réapprovisionnement
- Stock maximum  
- Niveau de dépassement de capacité  
- Plage de temps  
- Période de cumul de lot  
- Période de replanification  
- Quantité de réappro.  
- Délai de sécurité  
- Quantité de stocks de sécurité  
- Stratégie d'assemblage  
- Mode de lancement  

Les modificateurs d'ordre suivants existent pour l'article ou la fiche unité de stock :  

- Quantité minimum commande  
- Quantité maximum commande  
- Commande multiple  

Les champs de configuration de planification globale figurant sur la page **Configuration fabrication** sont les suivants :  

- Code dern. niv. nomenc. dynam.  
- Prévision de la demande actuelle  
- Prévision sur magasin  
- Délai de sécurité par défaut  
- Niveau de dépassement de capacité vide  
- Calcul PDP/PBM combinés
- Composantes aux localisations  
- Période tampon par défaut  
- Quantité tampon par défaut  

Pour en savoir plus, consultez [Détails de conception : paramètres de planification](design-details-planning-parameters.md)  

## <a name="other-important-planning-fields"></a>Autres champs de planification importants

### <a name="planning-flexibility"></a>Flexibilité de planification

Dans la plupart des commandes d'approvisionnement, comme les bons de production, vous pouvez sélectionner **Illimité** ou **Aucun** dans le champ **Flexibilité planification** des lignes.

Cela spécifie si l'approvisionnement représenté par la ligne O.F. est pris en compte par le système de planification lors du calcul des messages d'action.
Si le champ affiche l'option **Illimitée**, le système de planification inclut la ligne lors du calcul des messages d'action. S'il est paramétré sur **Aucune**, la ligne est ferme et définitive, et le système de planification n'inclut pas la ligne dans le calcul des messages d'action.

### <a name="warning"></a>Alerte

Le champ d'informations **Avertissement** sur la page **Feuille planification** vous informe lorsqu'une ligne planification est créée pour une situation inhabituelle avec un texte. L'utilisateur peut cliquer sur ce texte pour lire des informations supplémentaires. Les types d'alerte suivants existent :

- Urgence
- Exception
- Attention

### <a name="emergency"></a>Urgence

L’avertissement Urgence est affiché dans deux situations :

- L'inventaire est négatif à la date début de la planification.
- Des événements d'offre ou de demande rétroactifs existent.

Si l'inventaire d'un article est négatif à la date début de la planification, le système de planification suggère une commande d'approvisionnement d'urgence afin que la quantité négative arrive à la date début de la planification. Le texte d'avertissement indique la date début et la quantité de la commande d'urgence.

Les lignes document avec une date d'échéance antérieure à la date début de la planification sont consolidées dans une commande d'approvisionnement d'urgence pour que l'article arrive à la date début de la planification.

### <a name="exception"></a>Exception

L’avertissement Exception s’affiche si l'inventaire disponible prévu descend en dessous de la quantité de stock de sécurité.

Le système de planification suggère une commande d'approvisionnement pour répondre aux besoins à la date d'échéance. Le texte d'avertissement indique la quantité du stock de sécurité et la date à laquelle elle est entamée.

Entamer le stock de sécurité est considéré comme une exception car cela ne doit pas se produire si le point de commande a été correctement défini.

> [!NOTE]
> L'approvisionnement pour les lignes planification avec les alertes Exception n'est normalement pas modifié en fonction des paramètres de planification. Au lieu de cela, le système de planification propose uniquement un approvisionnement pour couvrir la quantité de demande exacte. Cependant, vous pouvez définir l'exécution de la planification de manière à respecter certains paramètres de planification pour les lignes planification avec certaines alertes. Pour plus d'informations, consultez la description du champ **Respecter les paramètres de planification pour les avertissements d'exception** de l'article [Exécuter une planification complète et un calcul PDP ou MRP](production-how-to-run-mps-and-mrp.md).

### <a name="attention"></a>Attention

L’avertissement Attention s’affiche dans deux situations :

- La date début de la planification est antérieure à la date de travail.
- La ligne planification suggère de changer un bon de commande ou de production libéré.

> [!NOTE]
> Dans les lignes planification comportant des avertissements, le champ **Accepter message d'action** n'est pas sélectionné, car le gestionnaire doit poursuivre l'étude de ces lignes avant de mettre en application ce plan.

## <a name="planning-worksheets-and-requisition-worksheets"></a>Feuilles planification et feuilles de réquisition

Comme décrit dans [Planification](production-planning.md), vous pouvez choisir entre deux feuilles pour la plupart des activités de planification : la feuille planification et la feuille de réquisition. La plupart des processus sont décrits en fonction de la feuille planification, mais il existe quelques scénarios où la feuille de réquisition est recommandée.

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

### <a name="requisition-worksheet"></a>Feuille de réquisition

La page **Feuille de réquisition** répertorie les articles que vous souhaitez commander. Il existe plusieurs méthodes pour saisir des articles dans la feuille :

- Saisissez les articles manuellement dans la feuille et renseignez les champs correspondants.

- Utilisez le traitement en lot **Calculer planning**. Cette opération permet de calculer un plan de réapprovisionnement pour les articles et les unités de stock ayant été configurés avec un système de réapprovisionnement **Achat** ou **Transfert**. Lorsque vous utilisez ce traitement en lot, le programme renseigne automatiquement le champ **Message d'action** en y indiquant une proposition d'action en vue du réapprovisionnement de l'article. Cette opération peut contribuer, par exemple, à augmenter la quantité d'articles d'une commande existante ou à créer une nouvelle commande.

- Si vous avez utilisé le traitement en lot **Calculer planning** à partir de la page **Feuille planification** pour calculer un plan de réapprovisionnement, vous pouvez utiliser le traitement en lot **Traiter messages d'action** pour copier des propositions bon de commande et ordre transfert de la feuille planification à la feuille de réquisition. Ceci est commode si des utilisateurs séparés sont responsables de la gestion des bons de production et des commandes achat/ordres transfert.

- Vous pouvez utiliser l'action **Livraison directe** pour renseigner les lignes feuille de réquisition. Cette action utilise le traitement en lot **Extraire documents de vente** pour déterminer les lignes document de vente que vous souhaitez désigner pour une livraison directe.

- Vous pouvez utiliser l'action **Commande spéciale** pour renseigner les lignes feuille de réquisition. Cette action utilise le traitement en lot **Extraire documents de vente** pour déterminer les lignes document de vente que vous souhaitez désigner pour une commande spéciale.

Les lignes feuille de réquisition contiennent des informations détaillées sur les articles à recommander. Vous pouvez modifier et supprimer les lignes pour ajuster le plan de réapprovisionnement et poursuivre le traitement des lignes à l'aide du traitement en lot **Traiter messages d'action**. 

Pour plus d'informations sur la planification à l'aide d'emplacements et de transferts, voir [Planification avec/sans emplacements](production-planning-with-without-locations.md).

> [!TIP]
> Lorsque vous travaillez sur les pages **Feuille de réquisition** ou **Feuille planification**, vous pouvez organiser les lignes en triant sur un nom de colonne. Ceci est particulièrement utile sur la page Feuille planification, car ils peuvent être utilisés pour les bons de production à plusieurs niveaux. Par défaut, les lignes sont triées par le champ **Numéro d’article**. Pour regrouper les lignes d’une commande à plusieurs niveaux, triez par **N° ordre de référence** . En outre, les champs **Ordre PDP** et **Niveau de planification** peuvent aider à montrer la hiérarchie des lignes.

## <a name="see-also"></a>Voir aussi .

[Détails de conception : planification de l’approvisionnement](design-details-supply-planning.md)  
[Planification](production-planning.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
