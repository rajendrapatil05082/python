### Python Print Statements
``` python
+ → manual concatenation

, → simple, auto-space

f"" → modern, clean, powerful

.format() → flexible, older
```

### 1.String Concatenation (+)

Combine strings manually with +.
⚠️ Numbers must be converted to string with str().
```python
name = "virat"
city = "Bengaluru"
id = 1234

print("My name is " + name + ", I live in " + city + ", and my id is " + str(id))
```

### 2. Comma Separation (Automatic Space)

Pass multiple values separated by commas — Python adds a space automatically.
``` python
name = "virat"
city = "Bengaluru"
id = 1234

print("My name is", name, "I live in", city, "and my id is", id)
```
### 3. f-Strings (Formatted String Literals ✅ modern & recommended)

Embed variables or even expressions directly inside {}.
``` python
name = "virat"
city = "Bengaluru"
id = 1234

print(f"My name is {name}, I live in {city}, and my id is {id}")
print(f"Next year my id will be {id + 1}")  # expressions also work
```
### 4. str.format() Method (older but still common)

Use {} placeholders and .format().
``` python
name = "virat"
city = "Bengaluru"
id = 1234

print("My name is {}, I live in {}, and my id is {}".format(name, city, id))
print("My id is {2}, my name is {0}, my city is {1}".format(name, city, id))   # positional

```
