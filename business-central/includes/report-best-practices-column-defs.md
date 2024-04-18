---
author: brentholtorf
ms.topic: include
ms.date: 04/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

## Meilleures pratiques pour utiliser les définitions de colonnes

Les définitions de colonnes ne sont pas versionnées. Lorsque vous modifiez une définition de colonnes, l’ancienne version est remplacée lorsque votre modification est enregistrée dans la base de données. La liste suivante contient quelques bonnes pratiques pour utiliser les définitions de colonnes.

- Si vous ajoutez des définitions de colonnes, choisissez un bon code et remplissez le champ Description avec un texte significatif tout en sachant à quoi vous utilisez la définition de colonnes. Ces informations aident vos collègues (et votre futur moi) à travailler avec les rapports financiers et peut-être à modifier la définition de colonne.
- Avant de modifier une définition de colonnes, envisagez d’en faire une copie comme sauvegarde, au cas où votre modification ne fonctionnerait pas comme prévu. Vous pouvez soit simplement copier la définition (lui donner un bon nom), soit l’exporter. Pour en savoir plus, voir [importer ou exporter des définitions de colonnes](#import-or-export-financial-report-column-definitions).
- Si vous avez besoin d’une nouvelle copie d’une définition fournie par [!INCLUDE [prod_short](prod_short.md)], un moyen simple d’en obtenir une consiste à créer une nouvelle compagnie contenant uniquement des données de configuration. Ensuite, exportez la définition et importez-la dans la compagnie où la définition doit être actualisée.