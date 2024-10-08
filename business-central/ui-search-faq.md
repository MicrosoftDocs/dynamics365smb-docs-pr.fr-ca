---
title: Foire aux questions sur la fonction Tell Me
description: Cet article fournit des réponses aux questions que nos partenaires et clients posent souvent sur la fonction Tell Me.
author: brentholtorf
ms.topic: conceptual
ms.service: dynamics-365-business-central
ms.search.keywords: 'find, search, Tell Me'
ms.search.form: TellMe
ms.date: 03/20/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---
# <a name="tell-me-faq"></a>FAQ Tell Me

Cet article répond aux questions que nos utilisateurs avancés posent souvent à propos de la fonction Dites-moi ce que vous voulez faire.

## <a name="are-all-actions-from-my-current-page-discoverable-in-tell-me"></a>Toutes les actions de ma page actuelle sont-elles détectables dans Tell Me ?

Non. Les actions dans les parties, telles que la partie Lignes vente ou Récapitulatifs, ne sont pas affichées dans la fenêtre de recherche.

## <a name="can-i-search-for-a-specific-record"></a>Puis-je rechercher un enregistrement spécifique ?

Oui. Par exemple, si vous souhaitez trouver rapidement un document de vente, saisissez son identificateur, puis choisissez l’action **Rechercher dans les données de la compagnie**. Si vous ne connaissez que le nom du client, saisissez-le. La fonction Tell Me organise les résultats par type, afin que vous puissiez trouver la commande dans la catégorie Documents de vente.

## <a name="are-the-results-in-tell-me-filtered-by-permissions"></a>Les résultats dans Tell Me sont-ils filtrés par autorisations ?

Si l’utilisateur n’a pas AccessByPermissions, les actions ne s’affichent pas. Cependant, les pages et les rapports apparaissent dans les résultats mais pour y accéder, l'utilisateur doit disposer d'une autorisation. Un message s’affiche si l’utilisateur n’est pas autorisé à afficher l’objet.

## <a name="does-tell-me-display-content-from-my-customizations-or-installed-third-party-extensions"></a>La fonction Tell Me affiche-t-elle le contenu de mes personnalisations ou des extensions tierces installées ?

Les actions, les pages et les rapports qui proviennent d’extensions sont extraits par Tell Me. Pour des informations techniques sur la manière de rendre des pages et des rapports personnalisés détectables, voir [Ajout de pages et de rapports pour la recherche](/dynamics365/business-central/dev-itpro/developer/devenv-al-menusuite-functionality).

## <a name="what-makes-this-different-from-what-was-previously-known-as-page-search"></a>Quelles sont les différences avec la recherche de page précédente ?

La recherche de page s'est transformée en Tell Me pour vous aider à obtenir rapidement des résultats. La recherche de page pouvait uniquement vous aider à accéder aux pages ou aux rapports. À un niveau technique, Tell Me n'est plus basé sur le concept MenuSuite hérité.

## <a name="i-use-on-premises--does-that-include-tell-me"></a>J'utilise [!INCLUDE[prod_short](includes/prod_short.md)] local. La fonction Tell Me est-elle incluse ?

Vous pouvez utiliser Tell Me dans le client Web local pour trouver des actions, des pages et des rapports, mais pas les applications et les services de conseils sur AppSource.

## <a name="is-tell-me-available-for-all-form-factors"></a>La fonction Tell Me est-elle disponible pour tous les facteurs d'écrans ?

Oui. Il a été introduit sur les téléphones et les tablettes lors de la deuxième vague de lancement de Business Central 2023. Dans la 2e vague de lancement 2023, elle doit être activée dans [Gestion des fonctionnalités](/dynamics365/business-central/dev-itpro/administration/feature-management) en utilisant le bouton bascule **Fonctionnalité : rechercher des pages et des données dans l’application mobile**. Dans la 1re vague de lancement 2024 et les versions ultérieures, cette fonctionnalité est toujours activée.

<!-- removed in v20 because of Help pane
### <a name="are-the-documentation-results-available-in-any-language"></a>Are the documentation results available in any language?
The help articles display in the language you have specified in **My Settings**, if help is available in that language.
-->

## <a name="does-tell-me-give-me-help-on-how-to-use-pages-reports-and-other-things"></a>La fonctionnalité de fenêtre de recherche (Tell Me) m’aide-t-elle à utiliser les pages, les rapports et d’autres éléments ?

Non, mais vous pouvez facilement obtenir ces informations à partir du volet Aide. Sélectionnez simplement l’action **Rechercher dans l’aide** dans la page **Dites-moi ce que vous voulez faire** ou sélectionnez <kbd>Ctrl</kbd>+<kbd>F1</kbd> sur votre clavier. Pour en savoir plus sur le volet Aide, consultez [Volet Aide](product-help-and-support.md#help-pane).

### <a name="why-dont-i-see-a-bookmark-icon-for-my-search-results"></a>Pourquoi ne vois-je pas d'icône de signet pour mes résultats de recherche ?

L’icône de signet ne s’affiche pas dans la fenêtre de recherche lorsque la personnalisation est désactivée pour un rôle d’utilisateur.

## <a name="see-also"></a>Voir aussi

[Enregistrer et personnaliser les vues de liste](ui-views.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Recherche de pages avec l'explorateur de rôles](ui-role-explorer.md)  
[Ajouter un signet à une page ou à un rapport sur votre tableau de bord](ui-bookmarks.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
