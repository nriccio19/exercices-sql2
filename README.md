# Exercices database partie 2

## - Partie 1 -

#### - Préparation de la base de données dvdrental -

`psql -d postgres -U db_user`

`postgres=> CREATE DATABASE dvdrental;`

`postgres=> \quit`

`pg_restore -U db_user -d dvdrental ./dvdrental.tar`

`psql -d dvdrental -U db_user`

## - Partie 2 -

#### - Requête SQL affichant tous les titres et descriptions des films contenant le mot "Amazing" -

`SELECT title,description FROM film WHERE description LIKE '%Amazing%'`

## - Partie 3 -

#### - Requête SQL récupérant tous les paiements supérieurs à 10 ainsi que l'id, le prénom, le nom du client, le montant et la date du paiement" -

`SELECT customer.customer_id, customer.first_name, customer.last_name, payment.amount, payment.payment_date FROM customer INNER JOIN payment on payment.amount > 10;`

## - Partie 3 bis -

#### - Requête SQL affichant le CA du vidéo club depuis son ouverture -

`SELECT SUM(amount) FROM payment`

## - Partie 4 -

#### - Requête SQL affichant le titre de tous les films dont la langue est l'anglais et dont la durée est supérieure à 120 minutes -

`SELECT film.title, film.length, language.name FROM film INNER JOIN language ON language.name = 'English' AND film.length > 120;`

## - Partie 5 -

#### - Requête SQL affichant le TOP 10 des clients qui ont fait le plus d'achat avec leur id, prénom, nom, email -

`SELECT film.title, film.length, language.name FROM film INNER JOIN language ON language.name = 'English' AND film.length > 120;`
