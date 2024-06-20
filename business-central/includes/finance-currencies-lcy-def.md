---
author: brentholtorf
ms.topic: include
ms.date: 03/04/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
Si votre compagnie opère dans plusieurs pays ou régions, il est probablement important que vous puissiez réaliser des transactions dans plusieurs devises. Vous définissez votre devise locale ($) sur la page **Configuration du grand livre**. Par la suite, votre devise locale sera représentée comme une devise vierge sur les documents et les transactions. Lorsque le champ **Devise** est vide, la devise est $.

La vidéo suivante explique comment configurer votre devise locale.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RW1iM1n]

Ensuite, vous devez configurer des codes devise pour chaque devise que vous utilisez si vous achetez ou vendez dans des devises autres que votre devise locale ($). Des comptes bancaires peuvent également être créés à l’aide de devises. Il est possible d’enregistrer des transactions GL dans différentes devises, cependant, la transaction GL sera toujours reportée dans la devise locale ($).

[!INCLUDE [finance-currencies-lcy](finance-currencies-lcy-note.md)]

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change des devises. Si vous désignez une deuxième devise comme devise de report additionnelle, [!INCLUDE[prod_short](prod_short.md)] enregistre automatiquement les montants en $ et dans la devise de report additionnelle pour chaque écriture GL, ainsi que pour d’autres écritures, telles que les écritures TVA. Pour plus d’informations, voir [Configurer une devise de report additionnelle](../finance-how-setup-additional-currencies.md). La devise de report additionnelle est le plus souvent utilisée pour faciliter les rapports financiers pour les propriétaires qui résident dans des pays/régions utilisant des devises différentes de la devise locale ($).  

> [!IMPORTANT]
> Si vous souhaitez utiliser une devise de report additionnelle pour le rapport financier, assurez-vous de bien comprendre les limites. Pour plus d’informations, voir [Configurer une devise de report additionnelle](../finance-how-setup-additional-currencies.md).

> [!NOTE]  
> Lorsque vous effectuez un report dans le grand livre en utilisant une devise étrangère, [!INCLUDE [prod_short](prod_short.md)] convertit la transaction en $ en utilisant le taux de change de la devise à la date de report. L’écriture GL ne contiendra pas d’informations sur la devise utilisée, uniquement sa valeur en $. Pour garder une trace de la devise d’origine, utiliser les documents de vente et d’achat et les comptes bancaires qui stockent les informations de devise pour les écritures.
