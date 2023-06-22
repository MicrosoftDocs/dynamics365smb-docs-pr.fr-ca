---
author: edupont04
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
---

La taxe de vente inclut les taxes payées par les compagnies pour utiliser des articles :  

- Taxe de service (États-Unis) – La taxe de service est une taxe de vente payée aux États-Unis sur les articles qu'une compagnie achète pour son propre usage plutôt que pour la vente à un client. La compagnie doit payer une taxe de vente pour ces articles au gouvernement, sous la forme d'une taxe de service.  
- Taxe achat (Canada) – La taxe d'achat est une taxe de vente canadienne payée par une compagnie sur les articles achetés à un fournisseur. Lorsqu'une compagnie achète des articles pour son propre usage, le fournisseur facture la taxe de vente appropriée pour les articles.  

## <a name="to-set-up-use-tax-for-a-purchase-order" />Pour configurer la taxe de service pour un bon de commande
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.  
2.  Sur la page **Bons de commande**, sélectionnez l'action **Nouveau**.  
3.  Sur le raccourci **Lignes**, complétez les champs, comme nécessaire. [!INCLUDE[tooltip-inline-tip](../../../includes/tooltip-inline-tip_md.md)]  
4.  Sur le raccourci **Facturation**, renseignez les champs comme décrit dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Imposable**|Sélectionnez ce champ pour configurer la taxe à payer. **Important :**  Ce champ est disponible sur la page **En-tête achat**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Code région fiscale**|Le code de région fiscale du fournisseur. **Important :**  Ce champ est disponible sur la page **En-tête achat**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**N° d'exonération fiscale**|Le numéro d'exonération fiscale de la compagnie. Vous pouvez entrer 30 caractères alphanumériques maximum. **Important :**  Ce champ est disponible sur la page **En-tête achat**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Code provincial de région fiscale**|Le code fiscal de la province. **Important :**  Ce champ est disponible sur la page **En-tête achat**, mais il n'est pas affiché par défaut. Pour sélectionner le champ, vous devez d'abord ajouter la colonne qui affiche ce champ. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
5.  Choisissez le bouton **OK**.  

## <a name="to-set-up-use-tax-details" />Pour configurer les détails de la taxe de service
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Détails fiscaux**, puis sélectionnez le lien associé.  
2.  Sur la page **Détails fiscaux**, sélectionnez l'action **Nouveau**.  
3.  Sur la page **Nouveau - Détails fiscaux**, renseignez les champs comme décrit dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code des autorités de recouvrement**|Le code de juridiction fiscale de l'écriture spécification de taxe.|  
    |**Code de groupe fiscal**|Le code groupe fiscal de l'écriture spécification de taxe.|  
    |**Type taxe**|**Taxe de vente et de service** – Pour appliquer la taxe de vente et de service à l'écriture spécification de taxe.<br /><br /> –ou–<br /><br /> **Taxe d'accise** – Pour appliquer la taxe d'accise à l'écriture spécification de taxe.<br /><br /> –ou–<br /><br /> **Taxe de vente uniquement** – Pour appliquer la taxe de vente uniquement à l'écriture spécification de taxe.<br /><br /> –ou–<br /><br /> **Taxe de service uniquement** – Pour appliquer la taxe de service uniquement à l'écriture spécification de taxe.|  
4.  Choisissez le bouton **OK**.  

## <a name="to-set-up-purchase-tax-for-a-company" />Pour configurer la taxe d'achat pour une compagnie
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Informations sur la compagnie**, puis sélectionnez le lien associé.  
2.  Sur la page **Informations sur la compagnie**, dans le raccourci **Taxe**, renseignez les champs comme décrit dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code région fiscale**|Le code de région fiscale de la compagnie. Le code de région fiscale est utilisé en combinaison avec un champ Code groupe fiscal et le champ **Imposable** pour trouver les informations nécessaires pour calculer la taxe de vente.|  
    |**N° d'exonération fiscale**|Le numéro d'exonération fiscale de la compagnie. Vous pouvez entrer 30 caractères alphanumériques maximum.|  
    |**Code provincial de région fiscale**|Le code fiscal de la province.|  
3.  Choisissez le bouton **OK**.  

## <a name="to-set-up-purchase-tax-for-a-location" />Pour configurer la taxe d'achat pour un emplacement
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.  
2.  Sur la page **Emplacements**, sélectionnez l'emplacement requis, puis cliquez sur l'action **Modifier**.  
3.  Sous le raccourci **Général**, renseignez les champs comme indiqué dans le tableau ci-dessous.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Ne pas utiliser pour le calcul des taxes**|Sélectionnez ce champ pour spécifier si les renseignements fiscaux inclus dans cet enregistrement d'emplacement doivent être utilisés pour les calculs de la taxe de vente sur les documents d'achat.|  
    |**Code région fiscale**|Le code de région fiscale pour l'emplacement. Le code de région fiscale est utilisé en combinaison avec un champ Code groupe fiscal et le champ **Imposable** pour trouver les informations nécessaires pour calculer la taxe de vente.|  
    |**N° d'exonération fiscale**|Le numéro d'exonération fiscale de la compagnie. Vous pouvez entrer 30 caractères alphanumériques maximum.|  
    |**Code provincial de région fiscale**|Le code fiscal de la province.|  
4.  Choisissez le bouton **OK**.  

## <a name="to-set-up-purchase-tax-for-non-recoverable-tax" />Pour configurer la taxe d'achat pour une taxe non recouvrable
1.  Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Détails fiscaux**, puis sélectionnez le lien associé.  
2.  Sur la page **Détails fiscaux**, sélectionnez l'action **Nouveau**.  
3.  Cochez la case **Dépense/Capitaliser**.  

    > [!NOTE]  
    >  Cette case doit être cochée si la taxe payée n'est pas recouvrable.  
4.  Choisissez le bouton **OK**.  
