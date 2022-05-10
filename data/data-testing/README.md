# data testing

Examples will be using python and the great expectations framework.

## setup

```sh
# python venv
python -m venv venv
pip install great_expectations

# SETUP
great_expectations --v3-api init

# add a new datasource
great_expectations --v3-api datasource new

# new expectations suite
great_expectations --v3-api suite new

# Editing your expectations
great_expectations --v3-api suite edit polar-bears

# checkpoint
great_expectations --v3-api checkpoint new my_new_checkpoint
```

## dataset

I added a few _traps_ to the dataset to demonstrate common data issues. See if you can can find the issues or write your own expectation to cover these

See [Expectations](https://greatexpectations.io/expectations) for more information.

_Hints_

1. Lat/lon value types

2. Realistic years

