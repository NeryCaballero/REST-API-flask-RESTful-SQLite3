# Flask RESTful API SQLite3
<hr>

This project is a continuation of my previous [REST API](https://github.com/NeryCaballero/REST-API-flask-RESTful) created with Python `flask` , `flask_restful` and `flask_jwt`.

This time I have used `sqlite3`.

This API has 2 resources: ```Item``` and ```Items```. 

`authentication` has been applied with `flask_jwt`.

<hr>

The API information will be stored in a file `data.db` which will act as the SQLite database.
To generate this file, *and with it the tables*, run `create_table.py` before running `app.py`.

You will then be able to Create new users, Authenticate and CRUD item(s).

<hr>

## The available endpoints are:

- POST `localhost:5000/register`: registers a new user. Information required in JSON 

  ```json
  { 
    "username": str, 
    "password": str 
  }
  ```
  
  
- POST `localhost:5000/auth` : Authenticates existing user. Provides an `access token`. 
  
  Information required in JSON:
  
  ```json
  { 
    "username": str, 
    "password": str 
  }
  ```
  
  For more details on authentication go [here](https://github.com/NeryCaballero/REST-API-flask-RESTful/blob/main/flask_jwt.md), *all the way to the end*.


- POST `localhost:5000/item/<item-name>` : Creates new item by passing the name on the URL.
  
  Information required in JSON: 

  ```json
  { 
    "price": float 
  }
  ```  


- GET `localhost:5000/item/<item-name>` : Reads one item by passing the name on the URL.


- GET `localhost:5000/items`  : Reads all items.


- PUT `localhost:5000/item/<item-name>` : Updates one item by passing the name on the URL. If the item does not exists, it will be created. 
  
  Information required in JSON:
  
  ```json
  { 
    "price": float 
  }
  ```


- DEL `localhost:5000/item/<item-name>` : Deletes one item by passing the name on the URL. 



<hr>

