# Lab : Découvrir le principe MVC (Model–View–Controller)

## 1. Définition de MVC

MVC est un modèle d'architecture logicielle qui permet de séparer une application en trois parties : le Model, la View et le Controller. Cette organisation facilite la compréhension, la maintenance et l'évolution du code.

## 2. Le Model

Le Model représente les données de l'application et permet notamment d'interagir avec la base de données. Dans Laravel, les modèles utilisent généralement Eloquent ORM pour récupérer, ajouter, modifier et supprimer des données.

Exemple : `Student.php`.

## 3. La View

La View représente l'interface visible par l'utilisateur. Elle permet d'afficher les informations sous forme de pages Web. Dans Laravel, les vues utilisent généralement le moteur de templates Blade.

Exemple : `resources/views/students/index.blade.php`.

## 4. Le Controller

Le Controller reçoit les requêtes, coordonne leur traitement et prépare la réponse à retourner à l'utilisateur. Il peut récupérer des données à travers le Model et les transmettre à la View.

Exemple : `StudentController.php`.

## 5. Fonctionnement du MVC

Lorsqu'un utilisateur demande la liste des étudiants, la route dirige la requête vers le Controller. Celui-ci récupère les données nécessaires à travers le Model, puis les transmet à la View pour les afficher dans le navigateur.

## 6. Conclusion

Le modèle MVC permet de séparer les responsabilités dans une application Web. Le Model gère les données, la View présente les informations et le Controller coordonne le traitement des requêtes. Cette organisation rend le code plus clair et plus facile à maintenir.