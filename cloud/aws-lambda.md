# AWS Lambda

Serverless functions are a cost-effective and modular way to perform custom actions. It can provide a means to support event-based functionality, serverless web APIs and scheduled functions. 

## How to interface with lambda

* AWS CLI
* SAM
* Chalice
* AWS console
* Cloud 9 IDE
* And probably many others...

## Chalice

A framework for writing serverless applications. It abstracts many of the unnecessary details for deploying lambda applications. Many of the conventions are similar to APIs like Flask. It can generate terraform or cloudformation templates and uses common AWS conventions behind the scenes. 

#### How to use

Setup AWS credentials

Create a file `app.py`

```sh
from chalice import Chalice

app = Chalice(app_name="helloworld")

@app.route("/")
def index():
    return {"hello": "world"}
```

Deploy

```sh
pip install chalice
chalice deploy
```

## Resources

https://aws.amazon.com/lambda/features/

https://aws.github.io/chalice/?badge=latest