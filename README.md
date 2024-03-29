# Sprawl

A utility package for printing formatted, colorized log messages. 

## Why? 

Sometimes we fall back to good ol' print-driven development ("PDD") 
when we need to inspect values at runtime. It can be annoying to search through 
a terminal window filled with other logs to find the one log statement you're looking 
for. This makes it easy for your log messages to stand out. 

## Installation

`$ pip install sprawl`

## Usage

Import the log function:

```python
from sprawl.loud_log import log

```

Configure logging however you normally would, for example:


```python
logging.basicConfig(format='%(asctime)s \n %(message)s', level=logging.INFO)
```  

log a message using the defaults:

```python
log('my log message')
```

prints:

```
##################################
 my log message
##################################

```

Center the log message:

```python
log('my log message', center_message=True)

```

prints:

```
##################################
           my log message
##################################
```

Change the surrounding character:

```python
log('my log message', center_message=True, char_to_surround_with='~')

```

prints:

```
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
           my log message
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

Add some color:

```python
log('my log message', center_message=True, color='yellow')

```

prints:

<img width="450" alt="Screen Shot 2019-12-11 at 8 55 38 PM" src="https://user-images.githubusercontent.com/514174/70675962-a50cca00-1c58-11ea-8484-8ca40617d518.png">

Log the name of the function or module from within which this log() was called


```python
def my_amazing_function():
    log('my log message', center_message=True, print_func_name=True)
    
my_amazing_function()

```

prints:

```
log called from my_amazing_function
#################################
           my log message
#################################
```

