---
title: Taux de taxe américaine | Invoicing
description: Découvrez comment ajouter une taxe de vente dans Invoicing. Ajoutez un taux de taxe par défaut basé sur votre propre adresse, puis ajoutez des taux de taxe pour vos clients.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: tax rates
ms.date: 10/01/2019
ms.author: edupont
ms.openlocfilehash: 180e31d293ae706dd70ffb9e2befe133128a8695
ms.sourcegitcommit: a64e1abcc3c1974c87fe3e33fa6983ea7fbbb3ff
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778131"
---
# <a name="us-tax-rates-in-included365inv_longincludesd365inv_longmd"></a>Taux de taxe américaine dans [!INCLUDE[d365inv_long](includes/d365inv_long.md)]
> [!Note]
> [!INCLUDE[d365inv_discont](includes/d365inv_discont.md)]

Vous pouvez ajouter des taux de taxe à la volée lorsque vous créez des estimations et des factures. Vous pouvez voir les taux de taxe que vous avez déjà ajoutés dans les paramètres de Microsoft Invoicing, et vous pouvez également ajouter de nouveaux taux de taxe.  

Vous pouvez également gérer les taux de taxe nécessaires dans la page **Paramètres**. C'est également dans cette page que vous définissez vos propres informations de taxe. Le taux de taxe par défaut est celui que vous spécifiez pour votre adresse professionnelle.  

Chaque taux de taxe est basé sur un emplacement géographique spécifique. Par exemple, le taux de taxe de Miami, Floride, comprend trois juridictions pour la taxe de vente : la ville (Miami), le comté (Dade) et la province (Floride).  

Si vous configurez de nouveaux taux de taxe, vous devez veiller à bien remplir les champs correctement. Aux États-Unis, les états, les comtés, les villes et les localités peuvent prélever la taxe de vente. Les compagnies recueillent la taxe de vente et la versent aux autorités gouvernementales pour les produits vendus aux utilisateurs finaux. La taxe de vente peut également être facturée sur une taxe de vente existante. Par exemple, la taxe peut être calculée sur un montant facture vente qui comprend déjà la taxe imposée par d'autres autorités.  

## <a name="to-add-a-tax-rate-on-an-invoice-or-estimate"></a>Pour ajouter un taux de taxe à une facture ou une estimation

1. Créez une facture ou une estimation. Pour plus d'informations, voir [Créer une facture pour un nouveau client](send-invoice.md).  
2. Dans la section **Détails**, si le client est imposable, choisissez l'icône AssistEdit > en regard du champ **Taux de taxe client**. Ce champ est déjà renseigné avec le taux de taxe par défaut, mais vous pouvez choisir une autre valeur.  
3. Dans la fenêtre **Taux de taxe**, choisissez un taux de taxe ou ajoutez-en un nouveau.  
4. Saisissez le nom et le taux pour la ville et la province, puis fermez la fenêtre **Taux de taxe**.  
5. Vous pouvez également cliquer ou appuyer sur **Définir comme taux de taxe par défaut**. Le taux par défaut est automatiquement appliqué à tout document ou article imposable.  

## <a name="to-add-a-tax-rate-from-the-settings"></a>Pour ajouter un taux de taxe à partir des paramètres

1. Dans [!INCLUDE[d365inv](includes/d365inv.md)], dans le coin supérieur droit, cliquez sur le symbole d'engrenage, puis choisissez **Mes paramètres**.  
2. Faites défiler jusqu'à la section **Taux de taxe**. Cliquez sur **Ajouter un nouveau taux de taxe** pour ajouter un nouveau taux. Cliquez ou appuyez sur les points de suspension pour modifier un taux de taxe existant.  
3. Saisissez le nom et le taux pour la ville et la province, puis fermez le formulaire **Taux de taxe**.  

Vous pouvez également cliquer ou appuyer sur **Définir comme taux de taxe par défaut**. Le taux par défaut est automatiquement appliqué à tout document ou article imposable.  

Si vous ou vos clients résidez dans un pays qui utilise la taxe sur la valeur ajoutée (TVA), comme le Royaume-Uni, consultez [Ajouter la taxe sur la valeur ajoutée (TVA) à vos factures](add-vat.md).  

## <a name="see-also"></a>Voir aussi

[Configurer les informations sur votre entreprise](set-up-business-profile.md)  
[Envoyer une facture à un nouveau client](send-invoice.md)  
