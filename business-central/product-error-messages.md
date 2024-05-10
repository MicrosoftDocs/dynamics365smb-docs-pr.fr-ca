---
title: Avertissements et messages d’erreur
description: Découvrez comment vous pouvez résoudre et trouver des solutions aux messages d'erreur lorsque vous travaillez dans Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: ivkoleti
ms.topic: conceptual
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-temeplate
---
# <a name="warnings-and-error-messages"></a>Avertissements et messages d’erreur

Pendant votre journée de travail, vous pouvez voir des notifications dans [!INCLUDE [prod_short](includes/prod_short.md)] indiquant qu'un problème s'est produit ou que le report a échoué, par exemple. Dans de nombreux cas, la notification permet de résoudre facilement le problème ou d'annuler les modifications effectuées. Dans d'autres cas, vous ne disposez peut-être pas des informations nécessaires pour résoudre le problème. Cet article fournit des conseils pour vous permettre d’avancer.  

## <a name="in-product-user-assistance"></a>Assistance utilisateur intégrée au produit

La version par défaut de [!INCLUDE [prod_short](includes/prod_short.md)] comprend des descriptions de la plupart des champs, colonnes et actions auxquels vous pouvez accéder lorsque vous cliquez sur le nom. En combinaison avec des conseils d'apprentissage pour les pages importantes, des légendes descriptives et des instructions, ces info-bulles ou légendes sont notre implémentation actuelle de l’*assistance utilisateur intégrée*, qui est un principe important dans le monde actuel de la conception de logiciels.  

Pour toute question concernant un champ ou un autre élément de l'interface utilisateur, cliquez sur le nom pour faire apparaître une brève description. Cliquez sur le lien *Demander Copilot* si cela ne suffit pas. Vous pouvez également utiliser le volet Aide du produit pour trouver des réponses à vos questions.  

Pour plus d'informations, voir [Modèle d'assistance utilisateur Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/user-assistance) dans le contenu d'administration de [!INCLUDE [prod_short](includes/prod_short.md)].  

## <a name="help-and-support-page"></a>Page Aide et support

Dans [!INCLUDE[prod_short](includes/prod_short.md)], l'élément de menu Aide (le point d'interrogation dans l'angle droit supérieur) vous permet d'accéder à la page **Aide et support** où vous pouvez trouver des liens vers les ressources utiles pour répondre à vos questions. Pour plus d'informations, reportez-vous à la rubrique [Ressources pour l'aide et l'assistance technique](product-help-and-support.md).  

## <a name="help-others"></a>Aider les autres

Si vous êtes un administrateur ou un superutilisateur, vous pouvez aider les autres en consultant les messages d'erreur dans la page **Registre des messages d'erreur** ou dans le centre d'administration. Dans de nombreux cas, l'avertissement ou le message d'erreur concerne la configuration ou le manque d'autorisation et des problèmes similaires que le superutilisateur ou l'administrateur peut facilement aider à résoudre. Dans d'autres cas, vous devrez peut-être inspecter les pages pour identifier la cause. Pour plus d'informations, voir [Recherche d'informations techniques](/dynamics365/business-central/dev-itpro/administration/manage-technical-support#finding-technical-information) dans le contenu d'administration de [!INCLUDE [prod_short](includes/prod_short.md)].  

## <a name="share-error-details-for-faster-assistance"></a>Partager les détails de l’erreur pour une assistance plus rapide

Tirez parti de l’expertise de collègues ou d’experts en la matière pour surmonter les obstacles et minimiser les temps d’arrêt. Lorsque vous êtes bloqué par une erreur, vous pouvez facilement partager les détails de l’erreur lorsque vous obtenez de l’aide. 

Les détails incluent le message d’erreur, le code d’erreur et d’autres informations utiles lors du dépannage d’une erreur. En partageant les détails de l’erreur, vous pouvez communiquer efficacement le problème spécifique auquel vous êtes confronté, ce qui aide vos collègues à vous aider.  

Vous pouvez copier les détails en choisissant l’**Icône de partage** dans les boîtes de dialogue de validation en ligne, ou le menu **Partager les détails** dans les boîtes de dialogue d’erreur.  

En plus de copier les détails de l’erreur, vous pouvez également choisir de partager les détails via Microsoft Teams en choisissant **Partager les détails avec les équipes** pour faire ce qui suit :

* Copier les détails de l’erreur.
* Ouvrez la fenêtre **Partager avec les équipes**, dans laquelle vous pouvez coller les détails de l’erreur que vous avez copiés et spécifier à qui vous souhaitez demander de l’aide. [!INCLUDE [prod_short](includes/prod_short.md)] ajoute un lien vers la page sur laquelle vous avez rencontré l’erreur pour faciliter le dépannage.

Vous pouvez également choisir de partager des détails par courriel en choisissant **Partager les détails par courriel** pour faire ce qui suit :

* Copier les détails de l’erreur.
* Ouvrez votre éditeur de courriels, où vous pouvez coller les détails de l’erreur que vous avez copiés et spécifier à qui vous souhaitez demander de l’aide. [!INCLUDE [prod_short](includes/prod_short.md)] ajoute un lien vers la page où vous avez vécu l’expérience.

## <a name="help-yourself"></a>Aide-toi

Nous avons facilité la compréhension, l’accès et la résolution des erreurs provenant de la plateforme.

Les messages d’erreur que le [!INCLUDE [prod_short](includes/prod_short.md)] que la plateforme génère contiennent tous les détails techniques, y compris les noms de champs, dans le **Message d’erreur détaillé** section. Sélectionnez l’icône **Copier les détails** sur les erreurs de validation en ligne ou dans un message d’erreur pour accéder aux informations techniques.

Les actions sur les messages d’erreur vous amènent directement à la page où un champ est à l’origine de l’erreur. Vous n’avez pas besoin de prendre le temps de trouver la page ou le champ vous-même. Choisissez simplement l’action indiquée dans le message d’erreur et [!INCLUDE [prod_short](includes/prod_short.md)] vous amènera à l’emplacement approprié pour résoudre l’erreur.

### <a name="tip-for-developers"></a>Astuce pour les développeurs

Si vous êtes développeur, lorsque vous appelez la méthode [TestField](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-testfield-joker-joker-errorinfo-method) et ne transmettez pas l’objet ErrorInfo, [!INCLUDE [prod_short](includes/prod_short.md)] génère automatiquement le lien vers un page où un utilisateur peut corriger le problème. [!INCLUDE [prod_short](includes/prod_short.md)] obtient d’abord la page de recherche ou d’exploration de l’enregistrement, puis recherche la page de carte ou la page de recherche et ajoute un lien de navigation vers cette page de carte. [!INCLUDE [prod_short](includes/prod_short.md)] n’ajoute pas de lien dans les situations suivantes :

* Si l’erreur se trouve sur la page actuellement ouverte.
* Si l’utilisateur n’est pas autorisé à modifier l’enregistrement sous-jacent.

## <a name="see-also"></a>Voir aussi

[Ressources pour l’Aide et le support](product-help-and-support.md)  
[Forum aux questions](across-faq.yml)  
[FAQ Tell Me](ui-search-faq.md)  
[FAQ sur la recherche et le filtrage](ui-search-filter-faq.yml)  
[FAQ sur l'opération Copier et coller](faq-copy-paste.yml)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
