### List loaded python modules
```bash
python3 -c 'help("modules")'
```
```py
help('modules')
```

### Get last list element with destructuring assignment
```python
*_, last_user = client.get("/users")
```

### Unpacking dictionary to args or keywords
```python
data = {"key1": "value1", "key2": "value2"}

my_function(*data) # Unpacks the dictionary values and passes them as arguments

my_function(**data) # Unpacks the dictionary and passes its key-value pairs as keyword arguments
```
### Check if dictionary
```py
squares = {1: 1, 2: 4, 3: 9} 
type(squares) is dict # True
```

