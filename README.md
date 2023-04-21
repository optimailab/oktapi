# Oktopus REST API

Oktopus REST API is an algorithmic solution for automated budget optimization applied to paid media. This repository contains the backend code for the API.

### Models

This directory contains the classes for the database.

### Routers

This directory contains the API endpoints.

### Fast.py

Import all the routers, and run the FastAPi

### initialize.py

We create an admin user. 

### main.py

Contains main logic of the program: Campaign(), State() and AI() classes.

# How to run this app using python(3.10).

## Step 1.

Add mongo connection string in utils/db_connector.py (in MongoClient())

## Step 2.

pip install -r requirements.txt

## Step 3.

python initialize.py

## Step 4.

uvicorn fast:app (Make sure you are in OktAPI folder.)

## Step 5.

Open the url with /api and login with admin/admin.
