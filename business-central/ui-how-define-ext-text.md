---
title: Ajouter des lignes supplémentaires pour définir les descriptions étendues
description: Vous pouvez ajouter des lignes supplémentaires pour étendre le texte standard qui décrit un article, un compte du grand livre et d'autres données.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: b54c8c82a17cb5e1a25beca1115571733fddc2f4
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5784700"
---
# <a name="add-extended-text"></a>Ajouter du texte étendu

Vous pouvez étendre la description des articles, des unités de stockage, des comptes GL et des ressources en ajoutant des lignes supplémentaires en tant que texte étendu. Vous pouvez également définir des conditions d'utilisation des lignes supplémentaires.  

La section suivante décrit comment ajouter du texte étendu à une description d'un élément. Mais les mêmes étapes s'appliquent aux unités de stockage, aux comptes GL et aux ressources.  

## <a name="to-define-extended-text-for-an-description"></a>Pour définir le texte étendu pour une description

1. Ouvrez la fiche correspondant à l'article auquel vous voulez ajouter du texte étendu, puis sélectionnez **Texte étendu**.
2. Renseignez les champs **Code** et **Description**.
3. Choisissez **Nouveau**.
4. Renseignez le champ **Code langue** ou activez la case à cocher **Commun toutes langues** si vous utilisez des codes langue.
5. Renseignez les champs **Date début** et **Date fin** si vous souhaitez limiter les dates d'utilisation du texte étendu.
6. Dans le champ **Texte**, entrez le texte étendu.
7. Cochez les cases appropriées pour les types de documents où vous souhaitez imprimer le texte étendu.
8. Fermez la page.

Vous pouvez maintenant ajouter ce texte étendu aux documents. La procédure suivante explique comment ajouter du texte étendu à un document de vente, mais les mêmes étapes s'appliquent à tout autre document que vous avez spécifié pour le texte étendu.  

## <a name="to-add-an-extended-item-text-on-a-sales-order-line"></a>Pour ajouter un texte d'article étendu à une ligne document de vente

1. Ouvrez un document de vente avec une ligne vente pour un article avec texte étendu défini. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
2. Sélectionnez la ligne en question, puis sélectionnez l'action **Insérer textes étendus**.

## <a name="see-also"></a>Voir aussi

[Configuration de stock](inventory-setup-inventory.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]