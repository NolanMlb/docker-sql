# TP1 - Docker MySQL

Ce fichier README explique les commandes nécessaires pour configurer et utiliser un conteneur MySQL avec Docker.

## Commandes

1. **Lancer un conteneur MySQL**

    ```sh
    docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=root -d mysql:8
    ```

    Cette commande lance un conteneur MySQL nommé `mysql-container` avec le mot de passe root `root` en arrière-plan.

2. **Copier le fichier SQL dans le conteneur**

    ```sh
    docker cp TP1/app.sql mysql-container:/app.sql
    ```

    Cette commande copie le fichier `app.sql` de votre machine locale vers le conteneur MySQL.

3. **Accéder au conteneur MySQL**

    ```sh
    docker exec -it mysql-container mysql -u root -p
    ```

    Cette commande vous permet d'accéder au conteneur MySQL en tant qu'utilisateur root. Vous serez invité à entrer le mot de passe root.

4. **Exécuter le fichier SQL**

    Une fois connecté au conteneur MySQL, exécutez les commandes suivantes :

    ```sql
    source /app.sql;
    SHOW DATABASES;
    USE beer;
    SHOW TABLES;
    ```

    - `source /app.sql;` : Exécute le script SQL contenu dans `app.sql`.
    - `SHOW DATABASES;` : Affiche la liste des bases de données.
    - `USE beer;` : Sélectionne la base de données `beer`.
    - `SHOW TABLES;` : Affiche la liste des tables dans la base de données `beer`.