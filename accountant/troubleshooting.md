---
title: "Procédures de dépannage et solutions aux problèmes | Microsoft Docs"
description: "Découvrez comment résoudre les problèmes dans Accountant Hub pour Dynamics 365."
author: edupont04
ms.service: dynamics365-accountant
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, troubleshoot
ms.date: 10/23/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: a9753b00b47fc4d74583482b2da92aae5e2f8a74
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="troubleshooting-included365acclongincludesd365acclongmdmd"></a>Dépannage de [!INCLUDE[d365acc_long](includes/d365acc_long_md.md)]
[!INCLUDE[d365fin_early_release](includes/d365fin_early_release.md.md)]

L'inscription à [!INCLUDE[d365acc](includes/d365acc_md.md)] est simple et peut être effectuée très rapidement. L'ajout de clients au tableau de bord est également facile, mais cet article traite des problèmes que vous pouvez rencontrer en route.

## <a name="what-email-address-can-i-use-with-included365accincludesd365accmdmd"></a>Quelle adresse e-mail puis-je utiliser avec [!INCLUDE[d365acc](includes/d365acc_md.md)] ?
[!INCLUDE[d365acc](includes/d365acc_md.md)] exige que vous utilisiez une adresse de courriel professionnelle ou scolaire pour votre inscription. [!INCLUDE[d365acc](includes/d365acc_md.md)] ne prend pas en charge les adresses e-mail fournies par les services de messagerie publics ni les opérateurs de télécommunications. Cela comprend outlook.com, hotmail.com, gmail.com, et d'autres.  

Si vous essayez d'effectuer votre inscription à l'aide d'une adresse de courriel personnelle, vous recevez un message vous demandant d'utiliser une adresse professionnelle ou scolaire.  

## <a name="why-cant-i-connect-to-my-clients-data"></a>Pourquoi ne puis-je pas me connecter aux données de mon client ?
Il peut y avoir quelques raisons à cela, notamment :

- L'URL dans le champ **URL du client** n'est pas valide.  

  Accédez à **Gérer les clients**, ouvrez le client auquel vous ne pouvez pas vous connecter, puis choisissez **Tester l'URL du client**.  
- La compagnie du client est actuellement hors connexion, il se peut par exemple qu'une mise à niveau soit en cours

  Dans votre tableau de bord, choisissez l'élément de menu **Outils**, puis **Vérifier les erreurs**. Cela ouvre une liste avec des informations techniques vous permettant de contacter votre administrateur si vous voyez des erreurs. Par exemple, le message d'erreur « Le serveur a rejeté les informations d'identification du client » suggère que vous n'avez pas accès.  
- Vous n'avez pas reçu de courriel de votre client l'invitant à son [!INCLUDE[d365fin](includes/d365fin_md.md)], ou vous n'avez pas ouvert le lien dans le courriel, ou vous n'avez pas accepté l'invitation

  Vous devez ouvrir le lien dans l'invitation et accepter les étapes vous ajoutant au [!INCLUDE[d365fin](includes/d365fin_md.md)] de votre client. Jusque-là, vous n'avez pas accès à ses données.  
- Vous n'avez pas accès à toutes les compagnies du [!INCLUDE[d365fin](includes/d365fin_md.md)] de votre client

  Votre client peut avoir plusieurs unités fonctionnelles ou plusieurs compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)], et votre invitation n'inclut pas toujours toutes les compagnies. Communiquez avec votre client pour vous assurer que vous avez accès aux compagnies dans lesquelles le client souhaite que vous travailliez.  

## <a name="why-doesnt-the-data-refresh-in-my-dashboard"></a>Pourquoi les données ne s'actualisent-elles pas sur mon tableau de bord ?
Lorsque vous ajoutez un client ou que vous demandez une actualisation des données, [!INCLUDE[d365acc](includes/d365acc_md.md)] récupère les données. Mais vous devez actualiser la fenêtre vous-même, par exemple en choisissant l'action « Afficher à nouveau toutes les compagnies », en actualisant la fenêtre du navigateur, en quittant le tableau de bord puis en y retournant, ou autres actions de ce genre. C'est un problème connu auquel nous travaillons pour l'améliorer dans une mise à jour ultérieure.  

## <a name="see-also"></a>Voir aussi
[Mise en route avec [!INCLUDE[d365acc](includes/d365acc_md.md)]](get-started.md)  
[Ajouter des clients à votre tableau de bord dans [!INCLUDE[d365acc](includes/d365acc_md.md)]](add-client.md)  

