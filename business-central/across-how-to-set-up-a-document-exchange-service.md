---
title: Procédure de configuration d'un service d'échange de document | Microsoft Docs
description: Utilisez un fournisseur de services externe pour échanger des documents électroniques avec vos partenaires commerciaux.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: a89cf3988e7576070a58a798e0f88693e598ef92
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5787292"
---
# <a name="set-up-a-document-exchange-service"></a>Configurer un service d'échange de document
Utilisez un fournisseur de services externe pour échanger des documents électroniques avec vos partenaires commerciaux. Pour plus d'informations, voir [Échanger des données par voir électronique](across-data-exchange.md).  

## <a name="to-set-up-a-document-exchange-service"></a>Pour configurer un service d'échange de documents  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration service Doc. Exch.**, puis sélectionnez le lien associé.  
2. Renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Agent utilisateur**|Entrez tout texte que vous pouvez utiliser pour identifier votre compagnie dans les processus d'échange de documents.|  
    |**ID abonné Doc. Exch.**|Entrez l'abonné dans le service d'échange de documents qui représente votre compagnie. Elle est fournie par le fournisseur de services d'échange de documents.|  
    |**Activé**|Spécifiez si le service est activé. **Note :** dès que vous activez le service, au moins deux écritures file projet sont créées pour traiter le trafic de documents électroniques dans et hors de [!INCLUDE[prod_short](includes/prod_short.md)]. Lorsque vous désactivez le service, les écritures de file d'attente des travaux sont supprimées.|  
    |**URL inscription**|Spécifiez la page Web sur laquelle vous vous êtes connecté au service d'échange de documents.|  
    |**URL service**|Spécifiez l'adresse du service d'échange de documents qui sera appelé lorsque vous envoyez ou recevez des documents électroniques.|  
    |**URL connexion**|Spécifiez la page de connexion au service d'échange de documents, c'est-à-dire la zone où vous saisissez le nom de l'utilisateur et le mot de passe de votre compagnie pour vous connecter au service.|  
    |**Clé consommateur**|Entrez la clé OAuth à 3 branches pour la clé consommateur. Elle est fournie par le fournisseur de services d'échange de documents.|  
    |**Clé secrète du consommateur**|Entrez le secret qui protège la clé consommateur. Elle est fournie par le fournisseur de services d'échange de documents.|  
    |**Jeton**|Entrez la clé OAuth à 3 branches pour le token. Elle est fournie par le fournisseur de services d'échange de documents.|  
    |**Clé secrète du jeton**|Entrez le secret qui protège le token. Elle est fournie par le fournisseur de services d'échange de documents.|  

    > [!NOTE]  
    > Vos données d'ouverture de session sont automatiquement chiffrées.

## <a name="see-also"></a>Voir aussi  
[Configuration de l'échange de données](across-set-up-data-exchange.md)  
[Échanger des données par voir électronique](across-data-exchange.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]