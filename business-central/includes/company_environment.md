---
author: edupont04
ms.service: dynamics365-accountant
ms.topic: include
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: dcfc54d36b212b296747d28945324ac46c38cada
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4753627"
---
Les gens prennent parfois en charge plus d'une compagnie et doivent facilement passer du travail dans une compagnie à une autre dans [!INCLUDE [prod_short](prod_short.md)]. Par exemple, une entreprise peut avoir des bureaux de vente dans des villes et plusieurs pays, elle a donc créé une unité fonctionnelle pour chaque bureau. Les bureaux situés dans le même pays sont constitués en compagnies distinctes dans un environnement partagé. D'autres bureaux sont créés en tant que compagnies dans des environnements distincts car ils sont géographiquement basés dans d'autres pays.<br><br>  

Qu'est-ce qu'un environnement ? Les compagnies dans [!INCLUDE[prod_short](prod_short.md)] existent dans ce qu'on appelle des *environnements*. Il existe deux types d'environnements, **Production** et **Sandbox**. En bref, les environnements de production contiennent des données métier en direct et les environnements sandbox sont utilisés comme un endroit sûr pour tester des choses comme de nouveaux processus ou fonctionnalités métier. Pour plus d'informations, voir [Types d'environnements](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#types-of-environments). Si vous avez accès à une compagnie, vous avez accès à l'environnement dans lequel elle se trouve. Si vous avez accès à plusieurs compagnies et que celles-ci se trouvent dans des environnements différents, lorsque vous vous connectez à [!INCLUDE[prod_short](prod_short.md)] vous devez spécifier l'environnement dans lequel vous souhaitez travailler. Les environnements sont particuliers à un pays donné, donc si votre organisation travaille dans plusieurs pays, vous avez besoin d'environnements distincts pour chaque pays.<br><br>  

Qu'est-ce qu'une compagnie? Considérez une *compagnie* en tant que conteneur contenant des informations sur une entité juridique. En utilisant l'exemple ci-dessus, l'entreprise a un bureau de vente à Seattle et un autre à New York, donc elle crée une compagnie à [!INCLUDE[prod_short](prod_short.md)] pour chaque bureau afin qu'elle puisse gérer les opérations pour chaque bureau séparément.  
