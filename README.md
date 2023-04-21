# Oktopus REST API

Oktopus REST API is an algorithmic solution for automated budget optimization applied to paid media. This repository contains the backend code for the API.

## Technical Summary

### Use Case: Maximizing revenue through optimal budget distribution among sales-converting campaigns

The main goal is to maximize sales conversions for a given client within a specific timeframe, with a limited budget and across multiple campaigns. We aim to optimally distribute the budget among the campaigns to maximize the profits.

This is an optimization problem with three constraints set by the client or based on historical practices: a budget (b), the number of platforms (n), and a timeframe (t). In the future, we might explore finding the optimal values for these constraints to maximize the payout function (p = f(b, n, t)), but currently, our focus is on maximizing the profits given these constraints.

### Framework:

So far, we have implemented and tested various algorithms, including Epsilon-greedy, UCB, Optimistic, Softmax, and Thompson Sampling. These algorithms follow a framework that divides the total timeframe (t) into a number of timesteps (t') and the total budget (b) into a budget for each timestep (b'). We use a step (s) to represent the marginal percentage points of budget changes between different campaigns.

During each timestep (t'), we apply the action policies of the different algorithms to update the budget distributions using the step (s) appropriately. We collect new information to execute the subsequent budget distribution updates.

Among these algorithms, Thompson Sampling has proven to be the most effective. However, one limitation we've noticed is that the small step size can lead to slow convergence to the optimal solution. A workaround we've found is to use a large number of timesteps, allowing for convergence within a reasonable time period, even with a large number of timesteps required.

## Code


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
