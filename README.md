# loopback-example-database

This project contains examples to demonstrate [LoopBack](http://loopback.io) connectors for databases:

- [LoopBack MongoDB connector](https://github.com/strongloop/loopback-connector-mongodb)

```sh
git clone git@github.com:rahul21989/Sample-loopback-mongodb.git
cd Sample-loopback-mongodb/sample-project/

```


## Prerequisite

First, make sure you have strong-cli installed.

```sh
    npm install -g strong-cli
```

Next, you need a running Mongo server. 

## Create the LoopBack application

To demonstrate how to use MySQL connector for LoopBack, we'll create a simple application from scratch using the `slc`
command:

```sh
    slc lb project sample-project
    cd sample-project
    slc lb model first_names -i
```


## Install dependencies

Let's add the `loopback-connector-mongodb` module and install the dependencies.

```sh
    npm install loopback-connector-mongodb --save
```

## Configure the data source

The generated data source use the memory connector by default, to connect to mongodb, we'll modify the data source
configuration as follows.

```sh
    vi datasources.json
```

**Note: Future releases will probably generate a config.json file for the data source configuration.**

In datasoures.json, replace the data source configuration for mongodb with the following snippet:

```javascript
    "mongodb": {
     "defaultForType": "mongodb",
     "connector": "loopback-connector-mongodb",
     "url": "mongodb://localhost:27017/rahul"
  }
```


   
## Run the application

```sh
    node app
```

Open your browser now and run index.html

To get all data, go to http://localhost:3000/api/first_names.

```json
    [
      {
        "title": "author",
        "name": rahul
      },
      {
        "title": "x",
        "name": y
      },
    ]
```

To get an account by id, go to http://0.0.0.0:3000/api/first_names/1.

```json
    {
      "title": "author",
      "name": rahul,
      "id": "1"
    }
```

All the REST APIs can be explored at:

    http://0.0.0.0:3000/explorer


    To check mongo db database 
    First opne mongo shell 

    to show all databases

    show dbs

    use rahul

    to check all data db.collection.find();

