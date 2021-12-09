# data testing

​	*Data ecosystem: most breakages are caused by other people*

​	*Software ecosystem: most breakages are caused by yourself*

## great expectations

![](https://docs.greatexpectations.io/img/great-expectations-logo-full-size.png)

A python package that assists with testing and validation of datasets.

#### Core Concepts (Reference)

***Expectation***

Data assertions expressed in a declarative language as python methods.

***Expectation Suite***

Collection of expectations about data. Stored as a JSON file.

***Data Docs***

HTML documents with data validation results -- your data quality report.

***Datasources***

Data access configuration containing information about the dataset for great expectations

***Batch***

Reference to a set of data. Wrapper that includes information about the data for validation

### Quick Start

```pip install great-expectations```

* Create expectations suite
* Script to execute expectations
* JSON expectation data stored

```sh
great_expectations --v3-api init

# Data
# **execute all cells in the notebook**
great_expectations --v3-api datasource new

# Expectations
# **execute all the cells**
great_expectations --v3-api suite new

# Validations
great_expectations --v3-api checkpoint new my_new_checkpoint

my_new_checkpoint_config = f"""
name: my_checkpoint
config_version: 1.0
class_name: SimpleCheckpoint
run_name_template: "%Y%m%d-%H%M%S-my-run-name-template"
validations:
  - batch_request:
      datasource_name: data__dir
      data_connector_name: default_inferred_data_connector_name
      data_asset_name: yellow_trip_data_sample_2019-02.csv
      data_connector_query:
        index: -1
    expectation_suite_name: taxi.demo
"""

# execute all cells
# uncomment and run the last cell in the notebook.

# Run checkpoint
great_expectations checkpoint run my_checkpoint

great_expectations --v3-api checkpoint new my_checkpoint
```

