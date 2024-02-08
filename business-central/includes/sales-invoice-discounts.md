---
author: brentholtorf
ms.topic: include
ms.date: 10/05/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
Après avoir ajouté tous les articles sur les lignes, vous pouvez calculer l'escompte facture pour l’ensemble du document vente en choisissant l’action **Calculer escompte facture**.

L'escompte est calculé sur la base de toutes les lignes du document vente où la case **Autoriser escompte facture** est cochée. Par défaut, les escomptes facture sont autorisés. Toutefois, les lignes avec des frais annexes, par exemple, ne sont pas incluses dans le calcul de l'escompte facture. Pour affecter un escompte à ces lignes, entrez une valeur dans le champ **Montant escompte ligne** sur les lignes.  

> [!NOTE]
> Par défaut, les champs **Autoriser escompte facture** et **Montant escompte ligne** sont cachés sur les lignes. Si les champs ne sont pas disponibles, vous pouvez les ajouter en personnalisant la page. Pour plus d'informations, voir [Personnaliser votre espace de travail](../ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

> [!TIP]
> Si le champ **Calculer escompte facture** est sélectionné sur la page **Configuration ventes**, l'escompte facture est calculé automatiquement. Le moment du calcul diffère selon le type de document vente que vous utilisez.
>
> Si vous utilisez un document de vente, l'escompte est calculé quand vous ajoutez une ligne. Pour tous les autres documents vente, tels que les factures vente, l'escompte est calculé quand vous effectuez l’une des actions suivantes :
>
> * Afficher les statistiques
> * Afficher un rapport de test
> * Imprimer
> * Envois postaux

Vous définissez les conditions d'escompte facture pour un client sur la page **Escomptes facture client**. Le code devise du document vente est utilisé pour trouver les conditions escompte facture dans la devise correspondante.

Si vous n’avez pas défini d'escomptes facture pour les devises étrangères, les conditions d'escompte sur la page **Escomptes facture client** sont utilisés pour calculer l'escompte. Le calcul utilise votre devise locale et le taux de change en vigueur à la date de report du document.
