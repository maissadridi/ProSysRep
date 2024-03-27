
# Guide de déploiement et de test de l'application

Ce guide vous explique comment déployer et tester l'application de messagerie utilisant gRPC.

## Prérequis

Avant de commencer, assurez-vous d'avoir les éléments suivants installés sur votre système :

- Java Development Kit (JDK) version 8 ou supérieure
- Maven
- Protoc (Compiler pour Protocol Buffers)

## Étapes de déploiement

1. **Cloner le référentiel :** Clonez le référentiel depuis GitHub en utilisant la commande suivante :
    
    ```bash
    git clone <https://github.com/maissadridi/ProSysRep.git>
    
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

C'est tout! Vous avez maintenant déployé et testé avec succès l'application de messagerie utilisant gRPC. Si vous rencontrez des problèmes ou avez des questions, n'hésitez pas à nous contacter.
