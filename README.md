# README

STEP 1 — CREATE A NEW RAILS APP AS AN API
rails new books --database=postgresql --api

STEP 2— Configure CORS to allow frontend to make requests
uncomment  gem 'rack-cors'
then
run bundle install

uncomment the following code in config/initializers/cors.rb file 
The new rails app comes with the string “example.com”.
change it to “*” 

STEP 3— Planning Models
The first is a Book model that belongs_to a :publisher and a Publisher model that has_many :books 

STEP 3— Generate Models and Create Database
rails g model Publisher name --no-testframework
rails g model Book title description image_url publisher_id:integer number:integer artist writer --no-testframework

run rails db:create && rails db:migrate

STEP 4 — Create Seed Data and Test your associations
rails db:seed

STEP 5— Generate Controllers
rails g controller Books  
rails g controller Publishers


STEP 6 — Create Routes