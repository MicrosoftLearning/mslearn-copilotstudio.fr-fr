---
lab:
  title: Utiliser des entités
  module: Work with entities and variables in Microsoft Copilot Studio
---

# Utiliser des entités

## Scénario

Dans cet exercice, vous allez :

- Créer et utiliser des entités

Cet exercice devrait prendre environ **15** minutes.

## Contenu du didacticiel

- Comment créer et utiliser des entités pour améliorer l’assistant

## Étapes de labo de haut niveau

- Créer des entités
- Utiliser des entités dans des nœuds
  
## Prérequis

- Avoir effectué le **Labo : Gérer les nœuds**

## Procédure détaillée

## Exercice 1 - Créer des entités

Microsoft Copilot Studio utilise des entités pour comprendre l’intention de l’utilisateur ou l’utilisatrice. Il existe de nombreuses entités prédéfinies incluses pour les informations courantes. Vous pouvez créer des entités personnalisées à des fins spécifiques.

### Tâche 1.1 – Afficher les entités prédéfinies

1. Accédez au portail `https://copilotstudio.microsoft.com` Microsoft Copilot Studio et vérifiez que vous êtes dans l’environnement approprié.

1. Sélectionnez **Assistants** dans le volet de navigation de gauche.

1. Sélectionnez l’agent **Service de réservation immobilière** que vous avez créé dans le laboratoire précédent.

1. Sélectionnez **Paramètres** en haut à droite de l’écran.

1. Sélectionnez l’onglet **Entités**. Vous devriez voir une liste des entités prédéfinies pour votre assistant.

    ![Capture d’écran de l’onglet Entités.](../media/system-entities.png)

### Tâche 1.2 – Créer l’entité du type de propriété

1. Sélectionnez **+ Ajouter une entité**, puis **+ Nouvelle entité**.

    ![Capture d’écran de la sélection de la méthode pour une nouvelle entité.](../media/add-an-entity.png)

1. Sélectionnez la vignette **Liste fermée**.

1. Entrez **`Property Type`** dans le champ **Nom**.

1. Entrez **`Apartment`** dans le champ **Entrer l’élément**, puis sélectionnez **Ajouter**.

1. Entrez **`Condominium`** dans le champ **Entrer l’élément**, puis sélectionnez **Ajouter**.

1. Entrez **`Duplex`** dans le champ **Entrer l’élément**, puis sélectionnez **Ajouter**.

1. Entrez **`House`** dans le champ **Entrer l’élément**, puis sélectionnez **Ajouter**.

1. Sélectionnez **+ Synonymes** pour **Appartement**, entrez **`Flat`**, sélectionnez l’icône **+**, puis **Terminé**.

1. Sélectionnez **+ Synonymes** pour **Résidence**, entrez **`Townhouse`**, sélectionnez l’icône **+**, puis **Terminé**.

1. Sélectionnez **+ Synonymes** pour **Maison**, entrez **`Single-family home`**, sélectionnez l’icône **+**, puis **Terminé**.

1. Activez la **Correspondance active**.

    ![Capture d’écran de la nouvelle entité.](../media/add-list-entity.png)

1. Cliquez sur **Enregistrer**.

1. Fermez la fenêtre Type de propriété.

### Tâche 1.3 - Créer un nombre d’entités de chambres

1. Sélectionnez **+ Ajouter une entité**, puis **+ Nouvelle entité**.

1. Sélectionnez la vignette **Expression régulière (Regex)**.

1. Entrez **`Number of Bedrooms`** dans le champ **Nom**.

1. Entrez **`[1-5]`** dans le champ **Modèle**.

1. Cliquez sur **Enregistrer**.

1. Fermez le volet Nombre de chambres.

1. Sélectionnez l’icône **X** en haut à droite pour fermer les paramètres et revenir à votre assistant.

## Exercice 2 : utiliser des entités pour améliorer l’assistant

Utilisez des entités dans le flux conversationnel pour améliorer l’assistant.

### Tâche 2.1 - Utiliser des entités

1. Sélectionnez l’onglet **Rubriques**.

1. Sélectionnez la rubrique **Réserver une visite immobilière**.

1. Sélectionnez l’icône **+** entre les nœuds **Condition** et **Question** de propriété, puis sélectionnez **Poser une question**.

1. Dans le champ **Entrer un message**, entrez le texte suivant :

    `What type of property do you want to see?`

1. Sélectionnez **Type de propriété** pour **Identifier**.

1. Sélectionnez **Sélectionner les options pour l’utilisateur** et cochez l’option **Afficher** pour les quatre valeurs.

1. Sélectionnez la variable dans **Enregistrer la réponse de l’utilisateur ou l’utilisatrice en tant que** et entrez **`PropertyType`** pour **Nom de la variable**.

    ![Capture d’écran de la nouvelle entité.](../media/question-node-entity.png)

1. Sélectionnez l’icône **+** sous le nouveau nœud **Question**, puis sélectionnez **Poser une question**.

1. Dans le champ **Entrer un message**, entrez le texte suivant :

    `How many bedrooms do you need?`

1. Sélectionnez **Nombre de chambres** pour **Identifier**.

1. Sélectionnez la variable dans **Enregistrer la réponse de l’utilisateur ou l’utilisatrice en tant que** et entrez **`NumberofBedrooms`** pour **Nom de la variable**.

1. Sélectionnez **Enregistrer**.
