---
title: Détails de conception - ligne de report dans le journal général | Microsoft Docs
description: Cette rubrique fournit une analyse des concepts et principes qui sont utilisés pour reconcevoir la fonction de ligne de report au journal général dans Business Central.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, general journal, posting, codeunit 12
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: e7e61b572b2a7a1538d58430cbbcbb19d7cda999
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5390084"
---
# <a name="design-details-general-journal-post-line"></a>Détails de conception : Ligne report de journal général
Cette documentation fournit une analyse technique détaillée des concepts et principes qui sont utilisés pour reconcevoir la fonction de ligne validation feuille comptabilité dans [!INCLUDE[prod_short](includes/prod_short.md)]. La nouvelle conception rend le codeunit 12 plus simple et plus facile à modifier. La documentation commence par des présentations conceptuelles de la nouvelle conception. Alors il explique l'architecture technique pour indiquer les modifications découlant de la nouvelle conception.  

## <a name="in-this-section"></a>Dans cette section  
[Aperçu de la ligne validation de feuille comptabilité](design-details-general-journal-post-line-overview.md)  
[Détails de conception : Structure de l'interface de validation](design-details-posting-interface-structure.md)  
[Détails de conception : Structure du moteur de validation](design-details-posting-engine-structure.md)  
[Codeunit 12 modifications : variables globales de mappage pour la ligne de validation de feuille comptabilité](design-details-codeunit-12-changes-mapping-global-variables-for-general-journal-post-line.md)  
[Codeunit 12 modifications : modifications dans les procédures de validation de feuille comptabilité](design-details-codeunit-12-changes-changes-in-general-journal-post-procedures.md)  

## <a name="see-also"></a>Voir aussi  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]