---
lab:
  title: Créer des flux d’agent
  module: Enhance Microsoft Copilot Studio agents
---

# Créer des flux d’agent

## Scénario

Dans cet exercice, vous allez :

- Créer un flux d’agent

Cet exercice devrait prendre environ **30** minutes.

## Contenu du didacticiel

- Comment créer un outil pour exécuter un flux d’agent dans Copilot Studio

## Étapes de labo de haut niveau

- Créer un flux d’agent pour récupérer des données Dataverse
- Créer un flux d’agent pour créer des données Dataverse
  
## Prérequis

- Vous devez avoir terminé le **Labo : utiliser des entités**

## Procédure détaillée

## Exercice 1 : créer un outil pour récupérer des données à partir de Dataverse

Microsoft Copilot Studio peut accéder aux données dans Microsoft Dataverse à l’aide des flux d’agent.

### Tâche 1.1 – Créer un flux d’agent pour récupérer une propriété

1. Accédez au portail `https://copilotstudio.microsoft.com` Microsoft Copilot Studio et vérifiez que vous êtes dans l’environnement approprié.

1. Sélectionnez **Assistants** dans le volet de navigation de gauche.

1. Sélectionnez le **service de réservation immobilière** que vous avez créé dans le labo précédent.

1. Sélectionnez l’onglet **Outils**.

1. Sélectionnez **+ Ajouter un outil**.

1. Sélectionnez **+ Nouvel outil**.

1. Sélectionnez **Flux d’agent**.

1. Sélectionnez l’étape de déclenchement **Quand un agent appelle le flux**, puis sélectionnez **+ Ajouter une entrée**.

1. Sélectionnez **Texte**.

1. Entrez l’**entrée** `Bedrooms`, puis `Number of Bedrooms` pour **Veuillez entrer votre entrée**.

    ![Capture d’écran des propriétés du déclencheur du flux.](../media/create-flow-step2.png)

1. Sélectionnez l’icône **+** entre les deux étapes du flux pour ajouter une nouvelle action.

1. Entrez `Dataverse` dans le **champ de recherche** et sélectionnez **Afficher plus** pour le connecteur **Microsoft Dataverse**.

    ![Capture d’écran de la recherche de connecteur du flux.](../media/create-flow-step3.png)

1. Sélectionnez l’action **Répertorier des lignes**.

1. Si vous êtes invité à vous authentifier, entrez `Lab connection` comme **Nom de connexion**, sélectionnez **OAuth** pour ** Type d’authentification, puis sélectionnez **Se connecter**.

    > **Note :** si vous voyez une erreur « **Échec de création d’une connexion OAuth** », vous devrez peut-être autoriser les fenêtres contextuelles dans votre navigateur.

    ![Capture d’écran de l’erreur OAuth.](../media/failed-oauth-popup.png)

    ![Capture d’écran illustrant l’autorisation des fenêtres contextuelles dans Edge.](../media/failed-oauth-popup-2.png)

1. Sélectionnez la table **Biens immobiliers**.

1. Entrez `contoso_bedrooms eq ` (avec une espace après **eq**) dans le champ **Filtrer les lignes**.

1. Lorsque le champ **Filtrer les lignes** est toujours sélectionné, sélectionnez l’icône **éclair** à droite, puis sélectionnez le paramètre **Chambres**.

    ![Capture d’écran de la configuration de l’action Répertorier des lignes.](../media/create-flow-step4.png)

    > **Important :** assurez-vous qu’il y a un espace entre eq et Chambres.

1. Sélectionnez l’action **Répondre à Copilot** dans le canevas de création, puis sélectionnez **+ Ajouter une sortie**.

1. Sélectionnez **Texte**.

1. Entrez `PropertyId` pour **Entrer un nom**

1. Sélectionnez le champ **Entrer une valeur de réponse**, puis sélectionnez **fx (Insérer une expression).**

1. Entrez l’expression suivante dans le champ :

    ```
    first(outputs('List_rows')?['body/value'])['contoso_realestatepropertyid']
    ```

1. Sélectionnez **Ajouter**.

1. Sélectionnez **+ Ajouter une sortie**.

1. Sélectionnez **Texte**.

1. Entrez `PropertyName` pour **Entrer un nom**

1. Sélectionnez le champ **Entrer une valeur de réponse**, puis sélectionnez **fx (Insérer une expression).**

1. Entrez l’expression suivante :

    ```
    first(outputs('List_rows')?['body/value'])['contoso_propertyname']
    ```
    ![Capture d’écran illustrant la configuration de l’action Configurer une réponse.](../media/create-flow-step5.png)

1. Sélectionnez **Ajouter**.

1. Sélectionnez l’onglet **Paramètres** dans le volet **Répondre à Copilot**.

1. Vérifiez que la **réponse asynchrone** est définie sur **Désactivé**.

    ![Capture d’écran des paramètres d’action de réponse.](../media/create-flow-step6.png)

1. Sélectionnez **Enregistrer le brouillon** en haut à droite de la page.

1. Attendez la fin de l’enregistrement, puis sélectionnez **Publier**. Dans le **Flux de votre agent publié avec succès !** fenêtre contextuelle, sélectionnez **Retourner à l’agent**.

1. Sélectionnez l’onglet **Vue d’ensemble**.

1. Sélectionnez **Modifier** dans la section **Détails**. 

1. Mettez à jour le **Nom du flux** vers `Get Property`

1. Cliquez sur **Enregistrer**

1. Sélectionnez **Agents**, puis votre agent **Service de réservation immobilière**. 

1. Sélectionnez **Outils** et consultez le flux Obtenir une propriété que vous avez créé.


### Tâche 1.2 : ajouter l’outil Obtenir la propriété au sujet

1. Sélectionnez l’onglet **Rubriques**.

1. Sélectionnez la rubrique **Réserver une visite immobilière**.

1. Sélectionnez l’icône **+** sous le nœud **Combien de chambres avez-vous besoin ?**, sélectionnez **Ajouter un outil**, puis sélectionnez le flux **Obtenir la propriété**.

1. Sélectionnez la **variable NumberofBedrooms** pour le paramètre d’entrée **Chambres**.

    ![Capture d’écran de l’étape 3 de l’ajout d’une action de flux.](../media/add-action-flow-step-3.png)

1. Sélectionnez les **trois points** dans le nœud **Quelle propriété voulez-vous voir ?**, puis sélectionnez **Supprimer**.

1. Sélectionnez l’icône **+** sous le nœud **Action**, puis sélectionnez **Envoyer un message**.

1. Dans le champ **Entrer un message**, entrez `Property ` (avec un espace après).

1. Dans le même nœud, sélectionnez l’icône **{X} (Insérer une variable)**, puis la variable **PropertyName**.

    ![Capture d’écran de l’étape 4 de l’ajout d’une action de flux.](../media/add-action-flow-step-4.png)

1. Cliquez sur **Enregistrer**.

## Exercice 2 : créer un outil pour créer des données dans Dataverse

Microsoft Copilot Studio peut céder des données dans Microsoft Dataverse à l’aide de flux d’agent.

### Tâche 2.1 – Créer un flux d’agent pour effectuer une réservation

1. Sélectionnez l’onglet **outils** dans **Service de réservation immobilière**.

1. Sélectionnez **+ Ajouter un outil**.

1. Select **+ Nouvel outil**, puis **Flux d’agent** .

1. Sélectionnez **Enregistrer le brouillon** et attendez que le flux de l’agent soit enregistré.

1. Sélectionnez l’onglet **Vue d’ensemble**

1. Sélectionnez **Modifier** dans la section **Détails**. 

1. Renommer le flux `Create Booking Request`

1. Cliquez sur **Enregistrer**.

1. Sélectionnez l’onglet **Concepteur**.

1. Sélectionnez l’étape de déclenchement **Quand un agent appelle le flux**, puis sélectionnez **+ Ajouter une entrée**.

1. Sélectionnez **Texte**.

1. Entrez `PropertyId` pour **Entrée** et `Property` pour **Saisissez votre entrée**.

1. Cliquez sur **+ Ajouter une entrée**.

1. Sélectionnez **Texte**.

1. Entrez `ViewerName` pour **Entrée** et `Viewer Name` pour **Saisissez votre entrée**.

1. Cliquez sur **+ Ajouter une entrée**.

1. Sélectionnez **Texte**.

1. Entrez `ViewerEmail` pour **Entrée** et `Viewer Email` pour **Saisissez votre entrée**.

    ![Capture d’écran de la configuration de l’action des paramètres de flux.](../media/create-flow2-step1.png)

1. Sélectionnez l’icône **+** entre les deux étapes du flux pour ajouter une nouvelle action.

1. Entrez `Dataverse` dans le **champ de recherche** et sélectionnez **Afficher plus** pour le connecteur **Microsoft Dataverse**.

1. Sélectionnez l’action **Ajouter une nouvelle ligne**.

1. Sélectionnez **Demandes de réservation** pour le nom de la table.

1. Entrez `Agent booking` dans le champ **Nom de la réservation**.

1. Sélectionnez **Afficher tout** sous **Paramètres avancés**.

1. Entrez `contoso_bookingrequests()` dans le champ **Propriété (Propriétés immobilières)**, déplacez le curseur entre les parenthèses, sélectionnez l’icône **éclair**, puis le paramètre **PropertyId**.

1. Sélectionnez le champ **E-mail de la visionneuse**, puis l’icône **éclair**, et enfin le paramètre **ViewerEmail**.

1. Sélectionnez le champ **Nom de la visionneuse**, puis l’icône **éclair**, et enfin le paramètre **ViewerName**.

    ![Capture d’écran de la configuration de l’action d’ajout de ligne de flux.](../media/create-flow2-step2.png)

1. Sélectionnez l’action **Répondre à Copilot**.

1. Sélectionnez l’onglet **Settings** (Paramètres).

1. Vérifiez que la **réponse asynchrone** est définie sur **Désactivé**.

1. Sélectionnez **Enregistrer le brouillon** en haut à droite de la fenêtre.

1. Attendez la fin de l’enregistrement, puis sélectionnez **Publier**.

1. Sélectionnez l’onglet **Vue d’ensemble**.

1. Dans la section Détails, sélectionnez **Modifier**.

1. Renommer le flux d’agent `Create Booking Request`

1. Cliquez sur **Enregistrer**.

### Tâche 2.2 – Valider vos outils

1. Sélectionnez **Agents** et ouvrez votre agent **Service de réservation immobilière**.

1. Sélectionnez l’onglet **Outils** et vérifiez que les deux flux de votre agent se trouvent dans la liste. Si ce n’est pas le cas, sélectionnez **+Ajouter un **Flux** d’outils** >  > et sélectionnez le flux d’agent manquant. Sélectionnez **Ajouter à l’agent**.

### Tâche 2.3 : ajouter l’outil d’assistant Créer une demande de réservation à la rubrique

1. Sélectionnez l’onglet **Rubriques**.

1. Sélectionnez la rubrique **Réserver une visite immobilière**.

1. Sélectionnez l’icône **+** sous le nœud **À quelle date et à quelle heure souhaitez-vous visiter le bien ?**, sélectionnez **Ajouter un outil**, puis sélectionnez le flux **Créer une demande de réservation**.

1. Sélectionnez la variable **PropertyId** pour le paramètre d’entrée **PropertyId**.

1. Sélectionnez la variable **Name** pour le paramètre d’entrée **ViewerName**.

1. Sélectionnez la variable **EmailAddress** pour le paramètre d’entrée **ViewerEmail**.

1. Sélectionnez l’icône **+** sous le nouveau nœud **Action**, puis **Gestion des rubriques**, puis **Accéder à une autre rubrique** et enfin **Fin de la conversation**.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Publier**, puis **Publier** à nouveau.

## Exercice 3 : tester votre agent

### Tâche 3.1 - Effectuer une demande de réservation

1. Cliquez sur le bouton **Tester** en haut à droite de l’écran pour ouvrir le volet de test s’il est fermé.

1. Sélectionnez les **trois points** en haut du panneau de test en haut à droite de l’écran.

    ![Capture d’écran illustrant les options du panneau de test.](../media/test-pane-options.png)

1. Le cas échéant, activez **Suivi des rubriques**.

1. Sélectionnez l’icône **Commencer une nouvelle conversation** (actualiser) en haut du panneau de test.

1. Lorsque le message **Début de conversation** s’affiche, votre assistant lance une conversation. En réponse, saisissez une phrase déclencheur pour la rubrique que vous avez créée :

    `I want to book a real estate showing`

1. Saisissez les informations suivantes :

    ```
    Name: <Your name>
    ```
    ```
    Email address: <Your email address>
    ```

1. Une fois les informations fournies, une carte adaptative affiche les informations que vous avez entrées et vous demande si les détails sont corrects. Sélectionnez **Oui**.

1. Sélectionnez **House** pour le type d’invite de propriété.

1. Entrez `3` pour le nombre d’invites de chambres.

    ![Capture d’écran du volet de test avec les informations saisies.](../media/test-pane-action-results.png)

1. Entrez `Tomorrow 2:00 PM` pour l’invite **À quelle date et quelle heure souhaitez-vous afficher la propriété ?**.

1. Sélectionnez **Oui** à l’invite **Cela répond-il à votre question ?**.

1. Sélectionnez une note.

1. Sélectionnez **Non** à l’invite **Puis-je vous aider avec autre chose ?**.

### Tâche 3.2 - Vérifier la demande de réservation

1. S’il n’est pas encore ouvert, accédez à `https://make.powerapps.com` dans un nouvel onglet.

1. Vérifiez que vous êtes dans l’environnement approprié.

1. Cliquez sur **Applications** dans la navigation de gauche.

1. Sélectionnez **Lire** dans l’application pilotée par modèle **Gestion des propriétés immobilières**.

1. Dans le volet de navigation de gauche, sélectionnez **Demandes de requêtes**. Affichez la demande de réservation que votre agent vient de créer pour vous.

    ![Capture d’écran du portail Maker montrant les données de demande de réservation.](../media/booking-request-row.png)
