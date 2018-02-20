---
title: "État commande service et état réparation | Microsoft Docs"
description: "Le champ **Statut** de la fenêtre **Commande service** et le champ Code état réparation de la fenêtre Commande service qui est représenté par le **Code du statut de réparation** dans la fenêtre **Commande service** ont une certaine relation dans le module Service management. L'état commande service reflète l'état réparation de tous les articles de service de la commande service."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 21f4a6fc048688858cad77fb3d306fb39bd5620c
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="service-order-status-and-repair-status"></a>État commande service et état réparation
Le champ **Statut** de la fenêtre **Commande service** et le champ Code état réparation de la fenêtre Commande service qui est représenté par le **Code du statut de réparation** dans la fenêtre **Commande service** ont une certaine relation dans le module Service management. L'état commande service reflète l'état réparation de tous les articles de service de la commande service.  
  
> [!NOTE]  
>  Ces deux champs de statut ne sont pas liés au champ **Statut de lancement** de l'en\-tête de commande de service, qui détermine la gestion des articles de service au niveau de l'entrepôt.  
  
 Chaque fois que l'état réparation d'un article de service d'une commande service est modifié, le programme met à jour l'état de la commande. Pour afficher l'état réparation général des articles de service, vous devez préciser les informations suivantes :  
  
* L'état commande service auquel chaque état réparation est lié. Pour plus d'informations, voir Statut commande service.  
* Le niveau de priorité de chaque option état commande service. Pour plus d'informations, voir Priorité.  
  
 Lorsque vous convertissez un devis service en commande service, l'état réparation de chaque article de service de la commande est modifié à **Initial** et le statut de la commande service passe à **Suspendu**.  
  
## <a name="specifying-service-order-status-for-repair-status"></a>Spécification de l'état commande service pour l'état réparation  
Chaque état réparation est lié à un état commande service précis. Les options de ce statut commande service sont **Suspendu**, **En cours**, **En attente** et **Terminé**. Neuf options d'état réparation sont disponibles : **Initial**, **En cours**, **Expertisé**, **Service en partie réalisé**, **Devis terminé**, **Attente réponse client**, **Pièce de rechange commandée**, **Pièce de rechange reçue** et **Terminé**.  
  
### <a name="pending"></a>Suspendu  
Le statut commande service **Suspendu** indique que le service peut démarrer ou continuer à n'importe quel moment. Pour cette raison, les quatre options d'état réparation **Initial**, **Expertisé**, **Service en partie réalisé** et **Pièce de rechange reçue** peuvent toutes être liées à ce statut commande service.  
  
### <a name="in-process"></a>En cours  
Le statut commande service **En cours** indique que le service est en cours. Par conséquent, les deux options d'état de réparation **En cours** et **Pièce de rechange commandée** peuvent être liées à ce statut commande service. Si vous liez le statut **Pièce de rechange commandée** au statut commande service **En cours,** vous devez aussi lier le statut **Pièce de rechange reçue** à ce statut commande service.  
  
### <a name="on-hold"></a>En attente  
Le statut commande service **En attente** indique que le service est momentanément en attente, parce que vous attendez une réponse du client ou des pièces de rechange pour que le service puisse commencer. Pour cette raison, les trois options d'état réparation **Devis terminé**, **Pièce de rechange commandée** et **Attente réponse client** peuvent toutes être liées à ce statut commande service.  
  
### <a name="finished"></a>Terminé  
Le statut commande service **Terminé** indique que la maintenance est terminée. Pour cette raison, l'état réparation **Terminé** est lié à ce statut.  
  
## <a name="assigning-priority-to-service-order-status"></a>Affectation de priorité à des états commande service  
Lorsque l'état réparation d'un article de service est modifié, les options d'état commande service liées aux différentes options d'état réparation de tous les articles service de la commande sont identifiés. Si les articles de service sont liés à plusieurs options d'état commande service, l'option d'état commande service dont la priorité est la plus élevée est sélectionnée.  
  
Choisissez l'état commande service comportant les informations les plus importantes et affectez à cet état la priorité la plus élevée, etc.  
  
### <a name="example"></a>Exemple :  
Voici ci-après un exemple d'affectation de niveau de priorité :  
  
* En cours - Très haute  
* Suspendu - Haute  
* En attente - Moyenne  
* Terminé - Basse  
  
Par exemple, si un article de service présente l'état réparation **Initial** (lié au statut commande service **Suspendu**), qu'un autre présente le statut **En cours** (lié au statut commande service **En cours**) et que le troisième présente le statut **Pièce de rechange commandée** (lié au statut commande service **En attente**), le statut commande service est **En cours** car il correspond au niveau de priorité le plus élevé.  
  
## <a name="see-also"></a>Voir aussi  
[Configurer les états des commandes service et des réparations](service-order-repair-status.md)  
[Paramétrage de la gestion des services](service-setup-service.md)  

