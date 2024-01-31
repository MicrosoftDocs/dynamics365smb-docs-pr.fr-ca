---
author: brentholtorf
ms.topic: include
ms.date: 03/15/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
Étant donné que les compagnies opèrent dans un nombre croissant de pays/régions, il devient essentiel qu’elles puissent échanger et générer des informations financières dans plusieurs devises. La devise locale ($) est définie sur la page **Configuration grand livre** comme décrit dans l’article [Comprendre le grand livre et le plan comptable](../finance-general-ledger.md). Une fois la devise locale ($) définie, elle sera représentée en tant que devise vide. Ainsi, lorsque le champ **Devise** est vide, cela signifie que la devise est $.  

Ensuite, vous devez configurer des codes devise pour chaque devise que vous utilisez si vous achetez ou vendez dans des devises autres que votre devise locale ($). Des comptes bancaires peuvent également être créés à l’aide de devises. Il est possible d’enregistrer des transactions GL dans différentes devises, cependant, la transaction GL sera toujours reportée dans la devise locale ($).

[!INCLUDE [finance-currencies-lcy](finance-currencies-lcy-note.md)]

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change des devises. Si vous désignez une deuxième devise comme « devise de report additionnelle », [!INCLUDE[prod_short](prod_short.md)] enregistre automatiquement les montants en $ et dans cette devise de report additionnelle pour chaque écriture, ainsi que pour d'autres écritures, telles que les écritures TVA. Pour plus d’informations, voir [Configurer une devise de report additionnelle](../finance-how-setup-additional-currencies.md). La devise de report additionnelle est le plus souvent utilisée pour faciliter les rapports financiers pour les propriétaires qui résident dans des pays/régions utilisant des devises différentes de la devise locale ($).  

> [!IMPORTANT]
> Si vous souhaitez utiliser une devise de report additionnelle pour le rapport financier, assurez-vous de bien comprendre les limites. Pour plus d’informations, voir [Configurer une devise de report additionnelle](../finance-how-setup-additional-currencies.md).

> [!NOTE]  
> Lorsque vous effectuez un report dans le grand livre à l’aide d’un code devise, par exemple pour reporter une dépense dans un journal général à l’aide d’un code devise, la transaction est convertie en $ à l’aide du taux de change de la devise à la date de report. L’écriture GL ne contiendra pas d’informations sur la devise utilisée, uniquement sa valeur en $. Si vous voulez garder une trace de la devise d’origine, comme pour une facture, vous devez utiliser les documents de vente et d’achat ainsi que les comptes bancaires qui stockent les informations de code de devise pour les écritures.
