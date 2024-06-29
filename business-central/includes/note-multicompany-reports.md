---
ms.service: dynamics-365-business-central
---
> [!NOTE]
> Vous pouvez obtenir les données de diverses compagnies dans un seul rapport avec les services Web OData. Cependant, à partir de la 2e vague de lancement 2021 [!INCLUDE [prod_short](prod_short.md)], seul ODataV4 est pris en charge. ODataV4 n’exporte pas les données de plusieurs compagnies. La fonction **$expand** dans Power BI que vous pourriez considérer comme un autre moyen de créer un rapport multi-compagnies, ne peut pas non plus être utilisée. Cela crée une colonne avec le nom de la compagnie, mais ne la remplit pas avec les données de la compagnie après une actualisation.