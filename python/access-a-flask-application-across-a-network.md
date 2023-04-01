# Acccess A Flask Application Across A Network

__Category: Python__

Flask will only bind to a loopback address when using `app.run` without any parameters.

To access a Flask application across a network, you should include `0.0.0.0` as a parameter.

```python
app.run(host='0.0.0.0', port='5000', debug = True) 
```

The above method includes debug information. In production you will want to disable this feature.
