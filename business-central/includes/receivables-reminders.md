---
author: edupont04
ms.topic: include
ms.date: 02/09/2022
ms.author: edupont
---
Vous pouvez utiliser des relances pour rappeler aux clients les soldes échus. Vous pouvez également utiliser les rappels pour calculer les frais financiers tels que les intérêts ou les frais et les inclure dans le rappel.

Avant de pouvoir créer des rappels, vous devez configurer des modalités de rappel et les affecter à vos clients. Pour plus d’informations, voir [Configurer les niveaux et modalités de rappel](../finance-setup-reminders.md). [!INCLUDE [reminder-terms](reminder-terms.md)] Le contenu de la page **Modalités de frais financiers** détermine si les intérêts sont calculés dans le rappel.  

Vous pouvez exécuter périodiquement le traitement par lots **Création de relances** afin de créer des relances pour tous les clients ayant des soldes échus. Vous pouvez également créer manuellement une relance pour un client spécifique et demander à ce que les lignes soient calculées et renseignées automatiquement.  

Une fois que vous avez créé les relances, vous pouvez les modifier. Le texte apparaissant au début et à la fin de chaque relance est déterminé par les conditions niveau de relance de la colonne **Désignation**. Si un montant calculé a été inséré automatiquement dans le texte de début ou de fin, ce texte ne sera pas ajusté si vous supprimez des lignes. Vous devez alors utiliser la fonction **Mettre à jour texte relance**.  

Une écriture comptable client pour laquelle le champ **En attente** est renseigné ne génèrera pas la création d'une relance. Néanmoins, si un rappel est créé à partir d'une autre écriture, une écriture échue en attente d'approbation est incluse dans le rappel. Les intérêts ne sont pas calculés sur les lignes avec ces écritures.

Après avoir créé les rappels et effectué toutes les modifications souhaitées, vous pouvez imprimer les rapports de test ou émettre les rappels, en général par courriel.

### <a name="to-create-a-reminder-automatically"></a><a name="to-create-a-reminder-automatically"></a><a name="to-create-a-reminder-automatically"></a>Pour créer automatiquement un rappel

Un rappel est identique à une facture. Lorsque vous créez un rappel, un en-tête rappel, ainsi qu'une ou plusieurs lignes rappel, doivent être renseignés. Vous pouvez utiliser une fonction pour créer des relances pour tous les clients automatiquement.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 0.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rappels**, puis sélectionnez le lien associé.
2. Sur la page **Rappel**, cliquez sur l'action **Créer rappels**.
3. Sur la page **Créer rappels**, renseignez les champs pour définir comment et pour qui les rappels sont créées.
4. Cliquez sur le bouton **OK**.

### <a name="to-create-a-reminder-manually"></a><a name="to-create-a-reminder-manually"></a><a name="to-create-a-reminder-manually"></a>Pour créer un rappel manuellement

Sur la page **Rappel**, vous pouvez renseigner le raccourci **Général** manuellement et ensuite renseigner les lignes automatiquement.

1. Sélectionnez l’icône en forme ![d’ampoule qui rouvre la fonction Tell Me 2.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rappels**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire.
4. Choisissez l'action **Proposer lignes relance**.
5. Dans le traitement par lots **Proposer lignes relance**, renseignez les champs pour définir comment et pour qui les relances sont créées.
6. Activez la case à cocher **Inclure les écritures en attente** si vous souhaitez que les relances contiennent des écritures ouvertes impayées qui sont en attente.
7. Sélectionnez la case à cocher **Seulement écritures dont l'échéance est dépassée** si vous souhaitez que les rappels contiennent uniquement des écritures ouvertes impayées. Seuls les factures et les paiements seront affichés car ce sont les écritures pour lesquelles les paiements de vos clients peuvent être en retard.

    > [!Important]
    > Les écritures ouvertes en attente sont insérées, indépendamment du paramètre de la case à cocher **Seulement écritures dont l'échéance est dépassée**.

8. Cliquez sur le bouton **OK**.

### <a name="to-replace-reminder-texts"></a><a name="to-replace-reminder-texts"></a><a name="to-replace-reminder-texts"></a>Pour remplacer les textes rappel

Vous pouvez déterminer de plusieurs manières le texte devant figurer sur le rappel imprimé. Dans certains cas, vous pouvez remplacer les textes début et fin définis pour le niveau actuel par ceux d'un autre niveau.

1. Sélectionnez l’icône en forme ![d’ampoule qui rouvre encore la fonction Tell Me 3.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rappels**, puis sélectionnez le lien associé.
2. Ouvrez la relance appropriée, puis cliquez sur l'action **Mettre à jour texte relance**.
3. Sur la page **Mettre à jour texte rappel**, entrez le niveau requis dans le champ **Niveau rappel**.
4. Cliquez sur le bouton **OK** pour que le programme mette à jour les textes début et fin.

### <a name="to-issue-a-reminder"></a><a name="to-issue-a-reminder"></a><a name="to-issue-a-reminder"></a>Pour émettre un rappel

Après avoir créé les relances et effectué toutes les modifications souhaitées, vous pouvez lancer les impressions test ou émettre les relances.

Lorsque vous émettez une rappel, les données sont transférées vers une page séparée pour les rappels émis. Les écritures rappel sont simultanément reportées. Si des intérêts ou des frais supplémentaires ont été calculés, les écritures sont reportées dans les écritures client et dans le grand livre.

Lorsqu'une rappel est émise, les écritures sont reportées selon les spécifications de la page **Modalités de rappel**. Cette spécification détermine si les intérêts et les frais supplémentaires sont reportés sur le compte client et dans le grand livre. La configuration sur la page **Groupes report client** détermine les comptes qui seront utilisés.

Pour chaque écriture client de la note de frais financiers, une écriture est créée sur la page **Écritures rappel/frais financiers**.

Si les cases à cocher **Reporter intérêts** ou le champ **Reporter frais supplémentaires** de la page **Modalités de rappel** sont activées, les écritures suivantes sont aussi créées :

- Une écriture sur la page **Écritures client**,
- Une écriture à recevoir sur le compte du grand livre approprié
- Une écriture intérêts et/ou une écriture frais supplémentaires dans le compte du grand livre approprié

De plus, émettre un rappel peut créer des écritures de TVA.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre ici aussi la fonction Tell Me 4.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rappels**, puis sélectionnez le lien associé.
2. Sélectionnez la relance concernée, puis cliquez sur l'action **Émission**.
3. Sur la page **Émettre rappels**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**.

Le rappel est imprimé pour être envoyé à une adresse de courriel spécifiée en tant que pièce jointe PDF.

### <a name="to-cancel-an-issued-reminder"></a><a name="to-cancel-an-issued-reminder"></a><a name="to-cancel-an-issued-reminder"></a>Pour annuler un rappel émis

Si des rappels ont été émis par erreur, vous pouvez les annuler avant leur envoi. Vous pouvez les annuler un par un ou en lot.

1. Sur la page **Rappels émis**, sélectionnez une ou plusieurs lignes pour les rappels émis que vous souhaitez annuler, puis choisissez l'action **Annuler**.
2. Sur la page **Annuler les rappels émis**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.


