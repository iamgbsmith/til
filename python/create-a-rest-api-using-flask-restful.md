# Create A REST API Using Flask Restful

__Category: Python__

You can create a REST API in Python using `flask-restful`. 

This TIL will show how to create a simple REST API with two methods:

* HTTP GET which processes a query param and sends a JSON response
* HTTP GET which processes a path param and sends a JSON response

Create a file called `rest_api.py` with the following content:

```python
from flask import Flask, jsonify
from flask_restful import request, Resource, Api
import math
  
app = Flask(__name__)
api = Api(app)
  
# API GET endpoint which uses a query param
class SquareNumber(Resource):
  
    def get(self):
        try:
          num = int(request.args.get('number'))
          return jsonify({'result': num ** 2})
        except:
          # Return HTTP 400
          return ('Invalid request'), 400

# API GET endpoint which uses a path param
class SquareRoot(Resource):
  
    def get(self, num):
        return jsonify({'result': math.sqrt(num)})

api.add_resource(SquareNumber, '/square')
api.add_resource(SquareRoot, '/square-root/<int:num>')

if __name__ == '__main__':  
    app.run(debug = True)
```

Start the API:

```shell
python3 rest_api.py
```

Call the `/square` endpoint to calculate the square of a given number using a query param:

```shell
curl http://localhost:5000/square?number=54
```

Output:

```json
{
  "result": 2916
}
```

Call the `/square-root` endpoint to calculate the square root of a given number using a path param:

```shell
http://localhost:5000/square-root/16
```

```json
{
  "result": 4.0
}
```
