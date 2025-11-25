---
lab:
  title: Utiliser l’IA générative dans Microsoft Copilot Studio
  module: Enhance Microsoft Copilot Studio agents
---

# Utiliser l’IA générative dans Microsoft Copilot Studio

## Scénario

Dans cet exercice, vous allez :

- Utiliser les connaissances et l’IA générative dans votre agent

Cet exercice devrait prendre environ **30** minutes.

## Contenu du didacticiel

- Comment utiliser la fonctionnalité de réponses génératives pour améliorer les réponses de votre agent

## Étapes de labo de haut niveau

- Activer l’IA générative
- Ajouter des connaissances
  
## Prérequis

- Avoir effectué le **Labo : créer des actions d’assistant**

## Procédure détaillée

## Exercice 1 - Configurer l’IA générative

### Tâche 1.1 – Activer l’orchestration

1. S’il n’est pas encore ouvert, accédez au portail Microsoft Copilot Studio `https://copilotstudio.microsoft.com` et vérifiez que vous êtes dans l’environnement approprié.

1. Sélectionnez **Assistants** dans le volet de navigation de gauche.

1. Sélectionnez le **service de réservation immobilière** que vous avez créé dans le labo précédent.

1. Cliquez sur le bouton **Paramètres** en haut à droite de l’écran.

1. Dans la section **Détails**, activez l’orchestration en la définissant sur **Oui**.

1. Cliquez sur **Enregistrer**.

1. Fermez la fenêtre Paramètres.

### Tâche 1.2 – Utiliser des réponses génératives dans la rubrique Boosting conversationnel

1. Sélectionnez l’onglet **Rubriques**, puis le filtre **Système**.

1. Sélectionnez la rubrique **Boosting conversationnel**.

    ![Capture d’écran des nœuds de la rubrique de Boosting conversationnel.](../media/conversational-boosting-topic-original.png)

1. Examinez le nœud **Créer des réponses génératives**.

### Tâche 1.3 – Configurer l’authentification

1. Sélectionnez **Paramètres** en haut à droite de l’écran.

1. Sélectionnez l’onglet **Sécurité**.

1. Sélectionnez la vignette **Authentification**.

1. Sélectionnez **Authentifier avec Microsoft**.

1. Cliquez sur **Enregistrer**.

1. Cliquez sur **Enregistrer**.

1. Fermez la fenêtre Paramètres.

1. Sélectionnez **Publier**, puis **Publier** à nouveau.

## Exercice 2 - Ajouter des connaissances

### Tâche 2.1 - Ajouter des connaissances à partir de Dataverse

1. Sélectionnez l’onglet **Connaissances**.

1. Sélectionnez **+ Ajouter des connaissances**.

1. Sélectionnez **Dataverse**.

1. Sélectionnez la table **Real Estate Property**.

    ![Capture d’écran de l’ajout de connaissances à partir de sites web.](../media/add-dataverse-knowedge-step1.png)

1. Sélectionnez **Ajouter à l’agent**.

### Tâche 2.2 - Ajouter des connaissances à partir de fichiers

1. Ouvrez une nouvelle fenêtre et accédez à `https://download.microsoft.com/documents/customerevidence/Files/4000007499/SummitRealtyCaseStudy.docx` pour télécharger le fichier [**Étude de cas Microsoft**](https://download.microsoft.com/documents/customerevidence/Files/4000007499/SummitRealtyCaseStudy.docx).

1. Sélectionnez **+ Ajouter des connaissances**.

1. Sous **Charger un fichier**, parcourez et sélectionnez l’étude de cas que vous avez téléchargée.

    ![Capture d’écran de l’ajout de connaissances à partir de fichiers.](../media/add-file-knowledge.png)

1. Sélectionnez **Ajouter à l’agent**.

    ![Capture d’écran des connaissances.](../media/knowledge-added.png)

## Exercice 3 - Configurer la rubrique de base

### Tâche 3.1 - Utiliser des réponses génératives dans la rubrique système de base

1. Sélectionnez l’onglet **Rubriques**, puis le filtre **Système**.

1. Sélectionnez la rubrique **de base**.

    ![Capture d’écran des nœuds de la rubrique de système de base.](../media/fallback-topic-original.png)

1. Sélectionnez les **trois points** dans le nœud **Message**, puis **Supprimer**.

1. Sélectionnez l’icône **+** sous le nœud **Condition**, puis **Avancé**, et enfin **Réponses génératives**.

1. Dans le champ **Entrée**, sélectionnez l’onglet **Système**, puis **Activity.Text**.

1. Sélectionnez **Modifier** sous **Sources de données**.

    ![Capture d’écran du nœud Créer des réponses génératives.](../media/fallback-topic-answers-2.png)

1. Sélectionnez **Rechercher uniquement les sources sélectionnées**.

1. Sélectionnez la table Dataverse **Propriété immobilière**.

1. Désélectionner **Autoriser l’IA à utiliser ses propres connaissances générales**.

1. Cochez la case **Personnaliser** sous **Niveau de modération du contenu**, puis sélectionnez **Moyen**.

1. Cliquez sur **Enregistrer**.

## Exercice 4 - Tester l’IA générative

### Tâche 4.1 : tester les connaissances de l’assistant

1. Le cas échéant, sélectionnez le bouton **Tester** en haut à droite de l’écran pour ouvrir le panneau de test.

1. Sélectionnez l’icône **Commencer une nouvelle conversation** en haut du panneau de test.

1. Explorez l’assistant et découvrez comment il utilise les sources de connaissances.
