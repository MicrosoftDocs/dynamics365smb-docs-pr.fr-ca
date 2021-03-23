---
title: Configurer du contenu de courriel spécifique au document | Microsoft Docs
description: Vous pouvez définir le contenu à insérer dans le corps du courriel, par exemple, un lien Paypal. Vous pouvez également joindre des documents aux courriels.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.search.keywords: SMTP, mail, Microsoft 365, cover, body, PayPal, layout
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 8e22efc92cba6d9a59cc06c66422387d5b35f227
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5389634"
---
# <a name="send-documents-and-emails"></a>Envoyer des documents et des courriels
Vous pouvez facilement partager des informations et des documents, tels que des documents de vente, des bons de commande et des factures, par courriel directement depuis [!INCLUDE[prod_short](includes/prod_short.md)]], sans avoir à ouvrir une application de messagerie. 

Vous pouvez envoyer presque tous les types de documents sous forme de pièces jointes PDF. Vous pouvez également configurer une présentation de rapport qui inclut les informations du document dans le texte du courriel, ainsi que du texte qui rend le courriel plus convivial, par exemple une salutation standard. Pour plus d'informations, voir [Gestion des présentations de rapport et de document](ui-manage-report-layouts.md). <!--this topic does not mention how to set up a layout for email. Need to investigate.-->

Lorsque vous envoyez des factures, vous pouvez faciliter la tâche des clients pour effectuer des paiements via un service de paiement, tel que PayPal, en ajoutant automatiquement des informations et un lien vers le service dans le courriel. Pour plus d'informations, voir [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).

Pour activer les courriels au sein de [!INCLUDE[prod_short](includes/prod_short.md)], démarrez le guide de configuration assistée **Configurer la messagerie**. Pour plus d'informations, voir [Configurer la messagerie](admin-how-setup-email.md).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)]] prend uniquement en charge les communications par courriel sortantes. Vous ne pouvez pas non plus recevoir de réponses depuis l’application.

## <a name="to-send-documents-by-email"></a>Pour envoyer des documents par courriel
Cette procédure décrit comment joindre une facture vente reportée à un courriel sous forme de fichier PDF et avec un texte de courriel spécifique au document. <!--update this-->

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Factures vente reportées**, puis sélectionnez le lien associé.
2. Sélectionnez la facture vente appropriée, puis cliquez sur **Imprimer/Envoyer**.
3. Dans le champ **Courriel**, choisissez **Oui (Afficher une invite pour le réglage des paramètres)**. Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).
    
    Si le champ **Courriel** sur la page **Envoyer le document à** est défini sur **Oui (Afficher une invite pour le réglage des paramètres)**, la page **Envoyer courriel** s’affiche. Le champ **À :** est prérempli avec le contact et le document est joint sous forme de fichier PDF. Dans le champ **Corps**, vous pouvez saisir un texte manuellement ou faire en sorte que le champ contienne un corps de message spécifique au document que vous avez configuré.

4. Choisissez le bouton **OK**.
5. Dans le champ **À :**, entrez une adresse e-mail valide. La valeur par défaut est l'adresse de courriel du client.
6. Dans le champ **Objet**, saisissez un texte descriptif de l'objet. La valeur par défaut est le nom du client et le numéro de facture.
7. Dans le champ **Pièce jointe**, la facture générée est jointe par défaut en tant que fichier PDF.
8. Dans le champ **Corps**, entrez un message court au destinataire.

    Si le texte d’un courriel spécifique à un document est configuré sur la page **Sélection des rapports : Ventes**, le champ **Corps** est renseigné automatiquement. Pour en savoir plus, voir [Configurer des textes et des présentations de courriel réutilisables pour les documents vente et achat](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts-for-sales-and-purchase-documents).
9. Cliquez sur le bouton **OK** pour envoyer le courriel.

> [!NOTE]  
> Si vous ne souhaitez pas spécifier les paramètres de courriel chaque fois que vous envoyez un document par courriel, vous pouvez sélectionner l'option **Oui (Utiliser les paramètres par défaut)** dans le champ **Courriel** de la page **Envoyer le document à**. Dans ce cas, la page **Envoyer courriel** ne s'affiche pas. Reportez-vous à l'étape 4. Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).  

## <a name="to-compose-and-send-an-email"></a>Pour rédiger et envoyer un courriel
1. Choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Comptes de messagerie**, puis sélectionnez le lien associé.
2. Choisissez le compte à partir duquel envoyer le courriel, puis choisissez l’action **Écrire un courriel**.

## <a name="documents-marked-as-printed-when-they-are-sent"></a>Documents marqués comme imprimés lors de leur envoi
Certains documents dans [!INCLUDE[prod_short](includes/prod_short.md)] comportent un champ qui spécifie la fréquence d’impression du document. Le nombre dans ce champ <!--"that field?" need a name...--> est également mis à jour si vous envoyez le document par courriel, car un fichier PDF est généré pour celui-ci. Le numéro est mis à jour même si vous n’envoyez pas le courriel. <!--guessing this is because emails are technically reports, so the counter bumps up whenever someone creates an email. Need to verify.-->

## <a name="sent-emails-and-your-email-outbox"></a>Courriels envoyés et votre boîte d’envoi
[!INCLUDE[prod_short](includes/prod_short.md)]] stocke les courriels que vous envoyez sur la page **Éléments envoyés**. Cela vous permet de renvoyer des courriels ou de les transférer à quelqu’un d’autre. Si vous ne trouvez pas de courriel dans vos éléments envoyés, recherchez-le sur la page **Boîte d’envoi de courriels**. 

> [!NOTE]
> En fonction de l’extension que votre compagnie utilise pour les courriels, les administrateurs peuvent voir une liste des messages que tout le monde a envoyés, mais pas le contenu des messages

La **Boîte d’envoi de courriels** est l’endroit où vous trouverez les courriels que vous avez enregistrés en tant que brouillons et les courriels qui n’ont pas pu être envoyés, par exemple, si l’adresse de courriel n’était pas valide. Pour les messages dont l’envoi a échoué, vous pouvez choisir **Afficher erreur** ou **Enquêter sur une erreur** pour résoudre le problème.

## <a name="see-also"></a>Voir aussi
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Configurer la messagerie](admin-how-setup-email.md)  
[Facturer des ventes](sales-how-invoice-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]