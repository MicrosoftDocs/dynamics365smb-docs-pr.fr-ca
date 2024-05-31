---
title: Configurer des documents entrants
description: 'Configurez la fonctionnalité Documents entrants pour créer des documents électroniques, gérer des tâches OCR, importer des factures, et convertir des fichiers images.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice'
ms.date: 06/14/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Configurer des documents entrants

Si vous créez des lignes journal général à partir des enregistrements de documents entrants, vous devez spécifier sur la page **Configuration des documents entrants** quels modèle et lot de journal utiliser.

Une fois que la fonctionnalité **Documents entrants** est configurée, vous pouvez utiliser différentes fonctions pour examiner les reçus de dépenses, gérer les tâches OCR et convertir les fichiers document entrants, manuellement ou automatiquement, en documents ou lignes journal appropriés. Les fichiers externes peuvent être joints à n'importe quelle étape du processus, notamment en ce qui concerne les documents reportés et les écritures fournisseur, client et grand livre résultantes. Pour plus d’informations, voir [Créer des enregistrements document entrant](across-how-create-income-document-records.md).

## Configurer la fonctionnalité Documents entrants

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration document entrant**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Dans le cadre de la configuration, vous devez décider si vous souhaitez exiger l'approbation des documents entrants. Pour demander une approbation, vous devez [configurer des approbateurs et des flux de travail approbation](#to-set-up-approvers-of-incoming-document-records). Si votre organisation n’a pas l’intention d’exiger l’approbation, vous pouvez ignorer la section suivante.

Enfin, si vous utilisez un service OCR pour convertir des fichiers PDF ou image représentant des documents entrants, [vous devez le configurer](#to-set-up-an-ocr-service). Sinon, vous pouvez également ignorer cette section.

## Configurer des approbateurs d'enregistrements document entrant

Si vous ne souhaitez pas que les utilisateurs créent des factures ou des lignes journal général à partir d’enregistrements de documents entrants, sauf si les documents ont été préalablement approuvés, configurez un processus d’approbation pour les documents entrants. Les approbateurs de documents entrants doivent être paramétrés comme des utilisateurs de flux de travail approbation.

Avant de pouvoir créer des workflows qui impliquent des étapes d'approbation, vous devez configurer les utilisateurs du workflow qui sont impliqués dans les processus d'approbation. Sur la page **Configuration d'utilisateur d'approbation**, vous pouvez également définir les limites pour des types spécifiques de demandes et définir des approbateurs remplaçants à qui des demandes d'approbation sont déléguées lorsque l'approbateur initial est absent. Pour plus d'informations, voir [Configurer des utilisateurs d'approbation](across-how-to-set-up-approval-users.md).

## Configurer un service ROC

Pour transformer des fichiers PDF et image en documents électroniques que vous pouvez convertir en factures, notes de crédit ou lignes journal, configurez la fonction OCR. Vous pouvez également créer des écritures manuellement pour représenter les documents externes.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration services OCR**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> Vos données d'ouverture de session sont automatiquement chiffrées.

Pour en savoir plus, voir [Utiliser un service OCR pour convertir des fichiers PDF et image en documents électroniques](across-how-use-ocr-pdf-images-files.md).  

## Voir aussi .

[Documents entrants](across-income-documents.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
