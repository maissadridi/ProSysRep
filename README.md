# Mini projet système distribué

# Guide de déploiement et de test de l'application

Ce guide vous explique comment déployer et tester l'application.

## Prérequis

Avant de commencer, assurez-vous d'avoir les éléments suivants installés sur votre système :

- Java Development Kit (JDK) version 8 ou supérieure
- Maven
- Protoc (Compiler pour Protocol Buffers)

## Déploiement et Test des Fonctionnalités Utilisant gRPC

## Étapes de déploiement

1. **Cloner le référentiel :** Clonez le référentiel depuis GitHub en utilisant la commande suivante :
    
    ```bash
    git clone <https://github.com/votre-utilisateur/projet-SR.git>
    
    ```
    
2. **Compilation des fichiers Proto :** Compilez les fichiers de protocole pour générer les classes Java en utilisant la commande suivante :
    
    ```bash
    protoc --java_out=src/main/java grpc/messenger.proto
    
    ```
    
3. **Construction du projet :** Naviguez vers le répertoire racine du projet et exécutez la commande Maven pour construire le projet :
    
    ```bash
    cd projet-SR
    mvn clean install
    
    ```
    
4. **Exécution du serveur :** Lancez le serveur en exécutant la classe `MessengerServer` :
    
    ```bash
    java -cp target/projet-SR.jar grpc.MessengerServer
    
    ```
    
5. **Exécution du client :** Ouvrez une nouvelle fenêtre de terminal et lancez le client en exécutant la classe `MessengerClient` :
    
    ```bash
    java -cp target/projet-SR.jar grpc.MessengerClient
    
    ```
    

## Tester l'application

Après avoir déployé le serveur et le client, vous pouvez tester l'application en envoyant des messages entre les utilisateurs. Suivez les instructions affichées par le client pour envoyer des messages et récupérer les messages reçus pour un utilisateur spécifié.

## Remarque

Assurez-vous que le serveur est en cours d'exécution avant de démarrer le client. De plus, veillez à configurer les adresses IP et les ports correctement dans le code si vous prévoyez de déployer le serveur sur un réseau différent ou sur une machine distante.

C'est tout! Vous avez maintenant déployé et testé avec succès l'application de messagerie utilisant gRPC. 

## Déploiement et Test des Fonctionnalités Utilisant les Sockets

### Étapes de Déploiement

1. **Compilation des Fichiers :** Compilez les fichiers source pour les fonctionnalités utilisant les sockets en exécutant les commandes suivantes dans le répertoire racine du projet :
    
    ```bash
    javac -d target/classes src/main/java/sockets/*.java
    
    ```
    
2. **Exécution du Serveur :** Lancez le serveur de chat en exécutant la classe `SocketChatServer` :
    
    ```bash
    java -cp target/classes sockets.SocketChatServer
    
    ```
    
3. **Exécution du Client :** Ouvrez une nouvelle fenêtre de terminal et lancez le client de chat en exécutant la classe `SocketChatClient` :
    
    ```bash
    java -cp target/classes sockets.SocketChatClient
    
    ```
    

### Test de l'Application

Après le déploiement du serveur et du client, vous pouvez tester l'application en envoyant des messages dans le salon de discussion commun. Connectez-vous à partir de plusieurs clients pour simuler une conversation entre plusieurs utilisateurs.

## Déploiement et Test des Fonctionnalités Utilisant Java RMI

### Étapes de Déploiement

1. **Compilation des Fichiers :** Compilez les fichiers source pour les fonctionnalités utilisant Java RMI en exécutant les commandes suivantes dans le répertoire racine du projet :
    
    ```bash
    javac -d target/classes src/main/java/rmi/*.java
    
    ```
    
2. **Génération des Stubs et Skeletons :** Générez les stubs et les skeletons nécessaires en exécutant la commande suivante :
    
    ```bash
    rmic -d target/classes rmi.TaskManagerImpl
    
    ```
    
3. **Démarrage du Registre RMI :** Démarrez le registre RMI en exécutant la commande suivante :
    
    ```bash
    rmiregistry &
    
    ```
    
4. **Démarrage du Serveur RMI :** Lancez le serveur RMI en exécutant la classe `TaskManagerServer` :
    
    ```bash
    java -cp target/classes -Djava.rmi.server.codebase=file:target/classes/ rmi.TaskManagerServer
    
    ```
    
5. **Exécution du Client :** Ouvrez une nouvelle fenêtre de terminal et lancez le client RMI en exécutant la classe `TaskManagerClient` :
    
    ```bash
    java -cp target/classes rmi.TaskManagerClient
    
    ```
    

### Test de l'Application

Après le déploiement du serveur et du client RMI, vous pouvez tester les fonctionnalités en ajoutant, supprimant et récupérant des tâches à partir du système de gestion des tâches. Suivez les instructions affichées par le client pour interagir avec le serveur RMI.

C'est tout! Vous avez maintenant déployé et testé avec succès les fonctionnalités utilisant les sockets et Java RMI. Si vous rencontrez des problèmes ou avez des questions, n'hésitez pas à me contacter.
