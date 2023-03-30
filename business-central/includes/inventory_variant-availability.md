---
author: edupont04
ms.topic: include
ms.date: 09/21/2022
ms.author: edupont
---
Lorsque vous ouvrez la page **Dispo. article par variante** à partir d’une ligne document, vous pouvez insérer une variante dans la ligne document en sélectionnant la ligne avec la variante que vous souhaitez insérer, puis en cliquant sur OK. Si vous avez utilisé uniquement la page pour afficher la disponibilité et ne souhaitez pas insérer une variante, vous devez fermer la page sans cliquer sur OK.

La page affiche une ligne pour chaque période. Chaque ligne affiche les chiffres de disponibilité de l’article dans les champs clés suivants :

| Champ | Désignation |
|--|--|
| **Besoin brut**| Indique la somme de la demande totale pour cet article. Le besoin brut est égal à la somme de la *demande dépendante* et de la *demande indépendante*. La *demande indépendante* est issue des documents de vente, des commandes service, des ordres de transfert et des prévisions de production. La *demande dépendante* est issue des composantes Bon de production, des bons de production planifiés, planifiés fermes et libérés. Elle comprend également des lignes de feuilles planification et feuilles de réquisition.|
| **Réception programmée** | Spécifie la somme des articles provenant du réapprovisionnement. Le calcul inclut des bons de production libérés et planifiés fermes, des bons de commande et des ordres de transfert. |
| **Réception prévue** | Spécifie la somme des articles provenant des bons de production planifiés. |
| **Stock prévisionnel** | Indique les inventaires disponibles calculés. |
| **Lancement prévu** | Spécifie la somme des articles provenant des propositions d’ordres de réapprovisionnement. Le calcul inclut les bons de production planifiés. Il inclut également les lignes des feuilles planification et feuilles de réquisition calculées en fonction de la date début (de la feuille planification et du bon de production) ou de la date de commande (de la feuille de réquisition). Cette somme n’est pas incluse dans les inventaires disponibles prévus. Toutefois, elle indique les quantités qui doivent être converties de réceptions prévues en réceptions programmées. |
