Automata
========

![Alt text](https://s-media-cache-ak0.pinimg.com/736x/7a/af/6c/7aaf6c68e549a959860bfea439c8c42b.jpg)


Setting up the environment
--------------------------


```bash
$ git clone https://github.com/rahulxxarora/Automata
$ cd Automata
$ sudo sh installer.sh
```

Running
-------


```bash
$ python application.py &
$ python conversation.py
```

API Endpoints
-------------


### Decoding command

@api {post} /decode_command

@apiParam {String} command Input query from the user

Example:

```bash
$ curl -H "Content-Type: application/json" -X POST -d '{"command":"What time is it?"}' http://localhost:5000/decode_command
```

### Executing module

@api {post} /execute_func

@apiParam {String} module Name of the module to be executed

Example:

```bash
$ curl -H "Content-Type: application/json" -X POST -d '{"module":"mod_time"}' http://localhost:5000/execute_func
```

Guide for developing Training Data
----------------------------------


1. It should be contained in a file named **training_data.csv**
2. The format of the file should be input command and the module name to be executed separated by a comma
   * Example : What is the time?,mod_time
3. Whenever you update the training data, make sure you delete the existing **classifier_data.pickle** and **vocabulary_data.pickle**