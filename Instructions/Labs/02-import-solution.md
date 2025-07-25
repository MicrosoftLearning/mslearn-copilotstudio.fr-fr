---
lab:
  title: Importer une solution Dataverse
  module: Build an initial agent with Microsoft Copilot Studio
---

# Importer une solution Dataverse

Dans cet exercice, vous allez importer une solution Dataverse que vous utiliserez dans les prochains labos.

Cet exercice devrait prendre environ **10** minutes.

> **Note** : pour cet exercice, vous devez disposer d’une licence Copilot Studio ou bénéficier d’un [essai gratuit](https://go.microsoft.com/fwlink/p/?linkid=2252605) et avoir un environnement Power Platform dans lequel travailler.

## Exercice 1 – Importer une solution

Dans cet exercice, vous allez importer une solution Dataverse dans votre environnement qui contient les tables nécessaires pour effectuer les labos.

### Tâche 1.1 – Télécharger la solution

1. Dans un nouvel onglet, naviguez vers le fichier **Bookings_1_0_0_0.zip** sur GitHub à `https://github.com/MicrosoftLearning/mslearn-copilotstudio/blob/main/Allfiles/Bookings_1_0_0_0.zip`

1. Sélectionnez les **points de suspension (...)** en haut à droite, puis **Télécharger**.

1. Fermez l’onglet du navigateur.

### Tâche 1.2 – Importer une solution

1. Dans un nouvel onglet de navigateur, accédez à `https://make.powerapps.com`.

1. Si des informations d’identification sont demandées, connectez-vous avec votre adresse e-mail et votre mot de passe.

1. Si l’on vous demande vos coordonnées, définissez le pays/la région, puis sélectionnez **Démarrer**.

1. En haut à droite de l’écran, vérifiez que l’**environnement** est défini sur votre environnement. C’est là que vous allez travailler pendant toute la durée des labos. Si ce n’est pas le cas, sélectionnez l’environnement approprié.

1. Dans le volet de navigation de gauche, sélectionnez **Solutions**.

1. Dans la barre supérieure, sélectionnez **Importer une solution**.

1. Sélectionnez **Parcourir** et localiser le **fichier Bookings_1_0_0_0.zip** à partir de votre dossier Téléchargements, puis sélectionnez **Ouvrir**.

    ![Solution à importer.](../media/solution-to-import.png)

1. Sélectionnez **Suivant**.

1. Cliquez sur **Importer**.

    La solution est importée en arrière-plan. Cela peut prendre quelques minutes.

    ![Solution importée.](../media/solution-imported.png)

    > **Avertissement :** attendez que la solution ait terminé l’importation avant de passer à l’étape suivante.

1. Une fois la solution importée, ouvrez la solution **Bookings**.

1. Dans le volet de navigation de gauche, sélectionnez l’onglet **Vue d’ensemble**.

    ![Onglet Vue d’ensemble de la solution.](../media/solution-overview.png)

1. Sélectionnez **Publier toutes les personnalisations**.

### Tâche 1.3 – Tester les données

1. Dans le volet de navigation gauche de la solution Bookings, sélectionnez l’onglet **Objets**.

1. Sélectionnez le menu **points de suspension (...)** de l’application pilotée par modèle **Gestion des propriétés immobilières**, puis sélectionnez **Lire**.

    ![Vue d’ensemble.](../media/play-app.png)

1. Cliquez sur **+ Nouveau**.

1. Saisissez les informations suivantes :

    - **Nom de propriété :** `1100 High Villas`
    - **Propriétaire :** sélectionnez votre utilisateur
    - **Prix demandé :** `250,000`
    - **Rue :** `Main Avenue`
    - **Ville :** `Redmond`
    - **Chambres :** `3`
    - **Salles de bain :** `2`

    ![Vue d’ensemble.](../media/add-record.png)

1. Cliquez sur **Enregistrer et fermer**.

1. Cliquez sur **+ Nouveau**.

1. Saisissez les informations suivantes :

    - **Nom de propriété :** `555 Oak Lane`
    - **Propriétaire :** sélectionnez votre utilisateur
    - **Prix demandé :** `300,000`
    - **Rue :** `Oak Lane`
    - **Ville :** `Denver`
    - **Chambres :** `4`
    - **Salles de bain :** `3`

    ![Vue d’ensemble.](../media/add-record2.png)

1. Cliquez sur **Enregistrer et fermer**.

Vous disposez maintenant de 2 propriétés immobilières actives dans la vue. 
