# SHOP
# français
Objectifs
Dans le cadre de ce projet, un site web vous sera fourni. Ce site est encore en cours de création ; toutes les fonctionnalités ne sont donc pas encore disponibles. Ce projet vous permettra d'implémenter certaines des fonctionnalités manquantes.

Sachez également que le site web a été créé avec Rails, un framework de développement d'applications web écrit en Ruby. Vous pouvez en apprendre davantage sur ce framework sur son site web .

Vous devrez créer une boutique en ligne avec authentification utilisateur pour vendre tout type de produits. Comme indiqué précédemment, une partie du processus est déjà effectuée. Voyons donc tout d'abord ce que vous devrez mettre en œuvre.

Instructions
Sur ce site web, l'objectif est de vous permettre de créer des utilisateurs. Ces derniers pourront également créer des annonces pour vendre des produits sur le site.

Pour créer une annonce, cliquez sur le Sellbouton « Créer ». Vous pourrez lui donner un titre, un prix, un modèle et une description. Vous devrez également sélectionner une marque, une couleur et un état pour votre produit. Vous pourrez également choisir des images dans votre dossier « app/assets/images ».

Vous devrez d'abord implémenter un contrôleur appelé registrations_controller, incomplet dans app/controllers. Vous aurez besoin de Devise , une solution d'authentification flexible pour Rails basée sur Warden.

Vous devrez créer deux définitions dans ce contrôleur :
La première étape est sign_up_paramscelle où vous devrez autoriser les paramètres nécessaires à l'inscription, à savoir :

    - name
    - email
    - password
    - password_confirmation
La deuxième étape consiste account_update_paramsà autoriser les paramètres nécessaires pour modifier ou mettre à jour un compte, à savoir :

    - name
    - email
    - password
    - password_confirmation
    - current_password
Vous devrez également compléter la products_helper.rbsection « App/helpers ». Cette section sera chargée d'indiquer qui vend les produits et qui peut modifier et supprimer les annonces (ici, le créateur de l'annonce). Vous devrez donc trouver un moyen d'afficher le nom du vendeur pour chaque produit.

Vous devez trouver un moyen pour que seul l'utilisateur qui crée une annonce puisse la modifier ou même la supprimer définitivement.

Toutes les applications de commerce électronique nécessitent un panier. Vous devrez donc en créer un pour votre application.

Pour créer le panier, vous devrez définir un nouveau modèle Cart. Le panier doit fonctionner comme tout autre panier d'achat e-commerce.

Vous devez pouvoir ajouter un ou plusieurs articles au panier.

Le total doit être affiché, soit la somme de tous les produits du panier. Ce total doit être mis à jour chaque fois que vous ajoutez ou supprimez un article du panier.

Le panier doit avoir un Empty Cartbouton qui vide le panier et vous ramène à la page d'accueil.

Il doit également être possible de retirer des articles individuellement du panier, sans vider le panier entier.

Les messages « Ajouté au panier » et « Supprimé du panier » doivent s'afficher lorsque vous ajoutez ou supprimez un article du panier. Ces messages doivent disparaître de l'écran après un court instant.

Vous devez ajouter une icône de panier sur la page d'accueil, qui indique le nombre d'articles dans le panier, qui se met à jour chaque fois que vous ajoutez un nouveau produit.

Vous devrez créer un élément concerndans models/concerns/ appelé current_cart.rb. A concernest similaire à un assistant que vous pouvez inclure dans les contrôleurs de l'application. Il concerndoit vous permettre d'ajouter des articles au panier lorsque vous n'êtes pas connecté. Lorsque vous vous connecterez à un compte, le panier contiendra les produits que vous avez ajoutés avant votre connexion.

Ruby on Rails
Ruby est un langage de programmation similaire à Python et Perl. Il est typé dynamiquement, interprété et modifiable à l'exécution (par exemple, pour ajouter de nouvelles méthodes aux classes). Ses nombreux raccourcis le rendent très clair, les méthodes dépassant rarement 10 lignes. Il prend bien en charge les expressions régulières et fonctionne bien pour les scripts shell.

Rails est un joyau, ou une bibliothèque Ruby. Rails permet de créer des applications web en fournissant des classes pour l'enregistrement dans la base de données, la gestion des URL et l'affichage du code HTML (ainsi qu'un serveur web, des tâches de maintenance et bien plus encore).

Ce projet a été créé en utilisant :

Ruby 3.0.0
Rails 6.1.3
Si vous décidez d'installer d'autres versions, vous devrez mettre à jour vos gemmes en fonction de la version que vous utilisez. Si vous utilisez ces versions, vous disposez déjà des gemmes nécessaires dans votre fichier gemfile.

Maintenant que vous savez de quoi parle le projet, nous allons vous expliquer l'architecture du système de fichiers.

Lors du démarrage d'un nouveau projet Rails (avec la commande rails new name_of_project), une application Rails est créée dans un répertoire portant le nom indiqué. Vous devrez ensuite installer les dépendances des gemmes à l'aide de la commande bundle install.

Vous pouvez en apprendre davantage sur l’objectif de chaque répertoire créé ici .

Voici quelques commandes dont vous pourriez avoir besoin et qui ont été utilisées dans le projet :

bundle install
bundle update
rails-> Il vous donnera une liste de commandes que vous pouvez utiliser.
rails s-> exécute un serveur sur le port 3000 par défaut.
rails g scaffold Product brand:string model:string description:text condition:string finish:string title:string price:decimal --no-stylesheets --no-javascripts-> Le produit sera notre modèle principal au sein de l'application. L'échafaudage en Ruby on Rails désigne la génération automatique d'un ensemble composé d'un modèle, de vues et d'un contrôleur, généralement utilisé pour une seule table de base de données.
rails g controller store index-> Crée un contrôleur nommé store qui aura le chemin d'index vers lequel accéder si vous en avez besoin.
rails generate uploader Image-> Cela crée un téléchargeur et devrait vous donner un fichier dans « app/uploaders/Image_uploader.rb »
rails g migration add_image_to_products image:string-> Cela créera la migration.
rails db:migrate-> Vérifie quelles migrations manquantes doivent encore être appliquées.
Vous pouvez obtenir le code déjà créé ici . Vous remarquerez qu'il manque du code. Votre tâche consiste à le compléter pour que le site web fonctionne comme expliqué ci-dessus.

Vous devez effectuer ces étapes après la décompression :

installation groupée
mise à jour du bundle
base de données Rails : migrer
base de données rails:seed
rails s
Prime
En bonus pour ce projet, il y a quelques choses que vous pourriez faire :

Vous pouvez ajouter une catégorie au produit afin que l'utilisateur puisse choisir entre voitures, vêtements, ordinateurs et bien d'autres. Vous pouvez également ajouter des champs pour décrire les produits, par exemple en ajoutant d'autres marques.
Vous pouvez créer un bouton add to cartpour qu'il soit possible d'ajouter un produit au panier sans ouvrir les publicités.
Vous pouvez trouver un moyen de supprimer les articles du panier un par un.
Vous pouvez mettre en œuvre votre propre affichage et votre propre conception.
Vous pouvez ajouter un moyen de paiement.

# anglais
Objectives
In this project, a website will be given to you. This website is still in the creation process, so not all features are available. The purpose of the project is for you to implement some of those missing features.

You should also know that the website was created using Rails, a web application development framework written in Ruby. You can learn more about this framework in its own website.

You will have to create an e-Commerce shop application with user authentication where you can sell any type of products. As mentioned, some of the process is already done. So first of all, let's see what you will have to implement.

Instructions
In this website the goal is for you to fix it so that it will be possible to create users. Additionally, those users will be able to create ads to sell products in the website.

To create an ad you will have to go to the Sell button and create the ad. You will be able to give a title to your ad, a price, a model and a description. You also must select a brand, a color and a condition for your product. Moreover, you will be able to choose images from your folder in app/assets/images.

First you will have to implement a controller called registrations_controller that can be found incomplete in app/controllers. You will need Devise which is a flexible authentication solution for Rails based on Warden.

You will have to create two definitions in this controller:
The first one is sign_up_params where you will have to allow the necessary params to sign up, which are:

    - name
    - email
    - password
    - password_confirmation
The second one isaccount_update_params where you will also need to allow the necessary params to edit or update an account, which are:

    - name
    - email
    - password
    - password_confirmation
    - current_password
You will also need to complete the products_helper.rb located in app/helpers. This helper will be responsible for showing who is selling the products and who is able to edit and delete the ads (in this case the creator of the ad). So you will have to find a way to show the name of the seller in each product.

You have to find a way so that, only the user who creates an ad, can edit or also permanently delete it.

All e-Commerce apps need some sort of Cart. So you will have to create a shopping cart for your application.

To create the cart you will have to define a new model Cart. The cart must work like any other e-commerce shopping cart.

You must be able to add one or more items to the cart.

A total must be shown, which is the sum of all the products in the cart. This total must be updated every time you add or remove an item from the cart.

The cart must have an Empty Cart button, which clears the cart and takes you back to the home page.

It must be possible to remove items individually from the cart as well, without emptying the whole cart.

The message "Added to your cart" and "Removed from your cart" must be shown when you add or remove something from the cart. These messages must disappear from the screen after a short time.

You must add a shopping cart icon in the home page, which shows the number of items in the cart, which updates each time you add a new product.

You will have to create a concern in models/concerns/ called current_cart.rb. A concern is similar to a helper which you can include in controllers throughout the app. This concern must allow you to add stuff to the cart when you are not signed in, and then when you sign in to an account, the cart will have the products that you added before you signed in.

Ruby on Rails
Ruby is a programming language similar to Python and Perl. It is dynamically typed, interpreted, and can be modified at runtime (such as adding new methods to classes). It has many shortcuts that makes it very clean, methods are rarely over 10 lines. It has good RegEx support and works well for shell scripting.

Rails is a gem, or a Ruby library. Rails helps make web applications, providing classes for saving to the database, handling URLs and displaying html (along with a webserver, maintenance tasks, and much more).

This project was created using:

Ruby 3.0.0
Rails 6.1.3
If you decide to install other versions you will need to update your gems according to the version you are using. If you go with these versions, you already have the necessary gems in your gemfile.

Now, that you know what the project is about, we will explain to you the file system architecture.

When starting a new Rails project (with the command rails new name_of_project). This will create a Rails application in a directory with the given name and then you will need to install the gem dependencies using the command bundle install.

You can learn more about the purpose of each directory that is created here.

Here are some commands that you may need and that were used in the project:

bundle install
bundle update
rails -> It will give you a list of commands you can use.
rails s -> runs a server in the port 3000 by default.
rails g scaffold Product brand:string model:string description:text condition:string finish:string title:string price:decimal --no-stylesheets --no-javascripts -> Product will be our main model within the app. Scaffolding in Ruby on Rails refers to the auto-generation of a set of a model, views and a controller usually used for a single database table.
rails g controller store index -> Creates a controller named store that will have the Index path to go to if you need.
rails generate uploader Image -> This create an uploader and should give you a file in "app/uploaders/Image_uploader.rb"
rails g migration add_image_to_products image:string -> This will create the migration.
rails db:migrate -> Checks which missing migrations still need to be applied.
You can get the code which is already done here. You will notice that there is some code missing. Your task is to complete it so that the website works as explained above.

You should do this steps after unzipping:

bundle install
bundle update
rails db:migrate
rails db:seed
rails s
Bonus
As bonus for this project there are a couple things you could do:

You can add a category to the product so that the user can chose between cars, clothes, computers and many more. Or you can add more fields to describe the products, for example add more brands.
You can create a button add to cart so that it is possible to add a product to the cart without opening the ads.
You can find a way to remove items from the cart one by one.
You can implement your own display and design.
You can add a payment method.

# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version `3.2.2`

* System dependencies

* Configuration

* Database creation
This project uses Postgres. To start it on localhost:5432 use [Postgresapp]('https://postgresapp.com/')

There are some commands applied to postgres:

`psql` or `psql -h 127.0.0.1 -U [username] [dbname]` — run postgreSQL.

Ex: `psql -h 127.0.0.1 -U mysite mysite_development`

`\l` or `\l+` — list of databases

`\c dbname` — choose your database

`\du` - list of users

`\q` — quit from psql

`\dt` or `\dt+` - list of tables

`CREATE ROLE [username] LOGIN;` or `CREATE USER [username];` — create new db user

`DROP ROLE [username];` — remove db user

`ALTER USER [username] WITH PASSWORD ['password'];` — edit user password

`ALTER USER [username] WITH SUPERUSER;` — give a user superuser status

`ALTER USER [username] WITH NOSUPERUSER;` — take away superuser from a user

`ALTER USER [username] WITH LOGIN;` — allow a user to login

`ALTER USER [username] CREATEDB;` — allow a user to create a db

`CREATE DATABASE [dbname];` — create DB with 'mysite_development' db name

`ALTER DATABASE [dbname] OWNER TO [username];` — change db owner

`GRANT ALL PRIVILEGES ON DATABASE [dbname] TO [username];` — grant all privileges

`GRANT ALL ON [dbname] TO [username];` — grant all

`CREATE TABLE users (id INT, first_name VARCHAR(50), last_name VARCHAR(50), email VARCHAR(50), password text, role text);` — create user table within dbname

`CREATE TABLE items (id INT, name VARCHAR(50), description VARCHAR(200), price DECIMAL(10,2));` — -||- items

`INSERT INTO items (id, name, description, price) VALUES (1, 'some item', 'some good item', 10.99);` - add data to items

`CREATE TABLE orders (user_id INT, amount INT);` — -||- orders

`CREATE TABLE orders_description (order_id INT, item_id INT, quantity INT);` - -||- orders_description

`\d [tablename]` — describe a table;

`SELECT * FROM [tablename];` — select table (and show it)

* Database initialization

Set up your DB for default/test/development/prooduction in `config/database.yml`.
The file is configured to run DB both locally and on [Render]('https://render.com/docs/deploy-rails').

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

Clone the repo `git clone https://github.com/001elijah/rails-e-commerce-store.git`

Install gems: `bundle install` or `bundle`

Setup database: 

`nano config/database.yml` — configure database.yml

`echo 'export MYSITE_DATABASE_PASSWORD="your_password"' ..~/.bashrc` — create variable with user db password

`source ~/.bashrc`

`rake db:create` or `rails db:create` — create db

`bin/rails server` or `rails server` or `rails s` — to start the rails server

`rails c` - open rails console and do stuff like `@user = User.first; @user.role = 'admin'; @user.save; @user`

if you've messed up your database, you may need `rake db:reset` command to drop your db and create again

If you `is being accessed by other users error`, you'll need to logout from database by running `SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE datname = 'dbname';` as admin and superuser

if you need to [add](https://edgeguides.rubyonrails.org/active_record_migrations.html#creating-a-standalone-migration) a column to existing db, i.e first_name to users table: `rails generate migration add_first_name_to_users first_name:string`, then `rake db:migrate`

* ...

`rails g scaffold Item name` or `rails g scaffold Item name:text description:text price:decimal{8,2}` - to generate Item name creation template

if controller exists run `cp app/controllers/items_controller.rb app/controllers/items_controller_backup.rb`

and `rails d scaffold Item` to delete, and `rails g scaffold Item name` to generate the scaffold again

`rails generate migration add_description_to_items description:text` add description column to items table

`rails generate migration add_price_to_items price:decimal{8,2}` add price column to items table

* ...

to create a cart I've used the [video](https://www.youtube.com/watch?v=SPokmOwiM7E&ab_channel=Deanin) as reference
