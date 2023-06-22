---
title: L’extension Dépannage des écritures immobilisation
description: Il est plus facile de travailler avec des nombres entiers. Utilisez cette extension pour arrondir les montants des immobilisations dans le livre immobilisations.
documentationcenter: ''
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'machinery, buildings'
ms.date: 10/01/2021
ms.author: bholtorf
---
# <a name="the-troubleshooting-fa-ledger-entries-extension" />L’extension Dépannage des écritures immobilisation
Utilisez l’extension Dépannage des écritures immobilisation pour arrondir les montants d’amortissement et d’acquisition dans les écritures immobilisation à des nombres entiers. Par exemple, pour arrondir un montant de 30 000,44 à 30 000. Les causes habituelles des problèmes d’arrondissement sont la migration des données, le démarrage soudain du report de montants dans le grand livre ou les personnalisations que vous avez apportées à votre [!INCLUDE[prod_short](includes/prod_short.md)].

L’extension Dépannage des écritures immobilisation est pré-installée et prête à l’emploi. Si vous supprimez l’extension, mais que vous souhaitez la réinstaller, vous pouvez la trouver sur AppSource.

## <a name="troubleshooting-fixed-asset-ledger-entries" />Dépannage des écritures immobilisation
Lorsque vous ouvrez la page **Fiche immobilisation** pour la première fois, l’entrée de file d’attente des travaux **Analyser les écritures immobilisation** est programmée pour surveiller les montants tous les dimanches. Si des montants que vous souhaitez peut-être arrondir sont trouvés, une notification s’affichera la prochaine fois que vous ouvrirez la page Fiche immobilisation. La notification fournit une option **Voir plus** qui ouvre la page **Écritures immo. avec des erreurs d’arrondissement**, qui répertorie les entrées comportant des montants que vous souhaitez peut-être arrondir. Pour arrondir les montants, choisissez les écritures, puis choisissez l’action **Accepter la sélection**. Vous pouvez utiliser l’action **Rechercher des écritures avec des erreurs** pour mettre à jour la liste avec les nouveaux problèmes survenus après l’exécution de l’entrée de la file d’attente des travaux le dimanche précédent.

## <a name="see-also" />Voir aussi
[Immobilisations](fa-manage.md)  
[Gestion des immobilisations](fa-manage.md)  
[Mettre à jour des immobilisations](fa-how-maintain.md)  
[Personnalisation de Business Central Online à l’aide d’extensions](ui-extensions.md)  
[Finance](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]



