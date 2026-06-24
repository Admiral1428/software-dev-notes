# Python Topics

[https://docs.python-guide.org/writing/style/](https://docs.python-guide.org/writing/style/)

-   Any method or property that is not intended to be used by client code should be prefixed with an underscore (\_private)
    -   [https://pep8.org/](https://pep8.org/)

[https://medium.com/data-science/how-to-handle-large-datasets-in-python-with-pandas-and-dask-34f43a897d55](https://medium.com/data-science/how-to-handle-large-datasets-in-python-with-pandas-and-dask-34f43a897d55)

-   Deal with large datasets in Python using combination of **Pandas** and **Dask** libraries (being conscious of memory)

[https://app.dataquest.io/m/289/introduction-to-numpy/3/understanding-vectorization](https://app.dataquest.io/m/289/introduction-to-numpy/3/understanding-vectorization)

-   **Ndarrays** within **NumPy** library simplify data manipulation and analysis, and more efficient than standard Python.

[https://realpython.com/python-subprocess/](https://realpython.com/python-subprocess/)

-   The Python **subprocess** module is used to run shell commands and manage external processes. It's called sub because this launches **child** processes, and Python is the **parent** to it.
    -   You run a shell command using subprocess by calling subprocess.run() with the command as a list of arguments.
        -   You run a shell command by using subprocess.run() and passing the command as a list of strings, or by setting **shell=True** if you need to run a shell script or command string directly.
        -   When you use run(), the return value is an instance of the **CompletedProcess** class, which has attributes including the **returncode**.
        -   Can pass a **check**\=True argument to run() to raise an exception.
        -   Passing a **timeout**\=1 argument to run() will cause the function to shut down the process and raise a TimeoutExpired error after one second.
        -   Standard streams for process communication, which are returned as byte objects:
            -   Reads **stdin** for input
            -   Writes to **stdout** for general output
            -   Writes to **stderr** for error reporting
    -   subprocess.call(), subprocess.run(), and subprocess.Popen() differ in how they execute commands and handle process output and return codes.
    -   **multiprocessing** is for parallel execution within Python, while subprocess manages external processes.
    -   To execute multiple commands in sequence using subprocess, you can chain them by using **pipes** or running them consecutively.
        -   A pipe is a special stream that pipes a byte stream from one process to another. Shell example:
            -   $ ls /usr/bin | grep python
            -   This command tells the shell to create an ls process to list all the files in /usr/bin. The **pipe operator** (|) tells the shell to create a pipe from the stdout of the ls process and feed it into the stdin of the grep process. The grep process filters out all the lines that don’t contain the string python.
        -   Using the **Popen()** constructor is very similar in appearance to using run(). If there’s an argument that you can pass to run(), then you’ll generally be able to pass it to Popen(). The fundamental difference is that it’s not a blocking call—rather than waiting until the process is finished, it’ll run the process in parallel.

[https://www.getorchestra.io/guides/data-orchestration-medium-understanding-and-leveraging-workflow-orchestration](https://www.getorchestra.io/guides/data-orchestration-medium-understanding-and-leveraging-workflow-orchestration)

-   **Data orchestration** refers to the automated process of managing, coordinating, and organizing data from multiple sources to ensure smooth data workflows. In the context of workflow orchestration, it involves integrating various data processes, tools, and platforms to streamline and automate the movement and transformation of data across an organization.
    -   The core concept is defining your workflow as a **DAG (Directed Acyclic Graph)**, where tasks only move forward in a specific sequence (e.g., "Extract Data" -> "Clean Data" -> "Run Simulation")
    -   Orchestration tools provide built-in monitoring, alerting, scheduling, and automatic retries for failed task
    -   **Apache Airflow**: The industry standard for scheduling batch-oriented workflows using Python DAGs.
    -   **Prefect**: Known for having a more "Pythonic" approach, replacing strict DAGs with more flexible flows.

[https://realpython.com/python-logging/](https://realpython.com/python-logging/)

-   **Logging** involves recording program execution information for later analysis.
    -   You can use logging to debug, perform analysis, and monitor usage patterns.
    -   Logging in Python works by configuring loggers and setting log levels.
    -   Using a logging library provides structured logging and control over log output.
    -   You should prefer logging over print() because it decreases the maintenance burden and allows you to manage log levels.

[https://realpython.com/command-line-interfaces-python-argparse/](https://realpython.com/command-line-interfaces-python-argparse/)

-   **Command-line interfaces** enable interaction with applications through terminals.
    -   You can create CLIs in Python using the standard library **argparse** module.
    -   argparse parses command-line arguments and generates help messages.
    -   You can customize CLIs with argparse by defining argument types and actions.
    -   Subcommands and mutually exclusive groups enhance CLI functionality.

[https://www.linkedin.com/posts/samveel-zaheer-khan\_python-programming-datascience-activity-7418197607547617280-8MRB/](https://www.linkedin.com/posts/samveel-zaheer-khan_python-programming-datascience-activity-7418197607547617280-8MRB/)

-   Handle specific exceptions so that we address root cause rather than symptoms
    -   Sometimes best error handing is to let exception propagate, since this provides valuable context
    -   Sometimes we want to surface error immediately to fix fundamental issue
    -   Custom exceptions transform vague failures into something meaningful, enhancing user experience
    -   Proper resource management and cleanup is important
    -   Logging creates an insightful audit trail

[https://realpython.com/pytest-python-testing/](https://realpython.com/pytest-python-testing/)

-   Using **pytest** requires installing it with pip in a virtual environment to set up the pytest command.
    -   pytest allows for less code, easier readability, and more features compared to **unittest**.
    -   Managing test dependencies and state with pytest is made efficient through the use of fixtures, which provide explicit dependency declarations.
    -   Parametrization in pytest helps avoid redundant test code by allowing multiple test scenarios from a single test function.
    -   Assertion introspection in pytest provides detailed information about failures in the test report.

[https://realpython.com/python-json/](https://realpython.com/python-json/)

-   JSON in Python is handled using the standard-library json module, which allows for data interchange between JSON and Python data types.
    -   JSON is a good data format to use with Python as it’s human-readable and straightforward to serialize and deserialize, which makes it ideal for use in APIs and data storage.
    -   You write JSON with Python using json.dump() to serialize data to a file.
    -   You can minify and prettify JSON using Python’s json.tool module.

[https://ploomber.io/blog/python-envs/](https://ploomber.io/blog/python-envs/)

[https://realpython.com/python-data-classes/](https://realpython.com/python-data-classes/)

-   A Python **dataclass** lets you define classes for storing data with less boilerplate. Use @dataclass to generate .\_\_init\_\_(), .\_\_repr\_\_(), and .\_\_eq\_\_() automatically.
    -   Dataclasses allow you to create classes quickly, but you can also add defaults, custom methods, ordering, immutability, inheritance, and even slots.
    -   **Mutable defaults** use field(default\_factory=...), while simple defaults use field(default=...) or an inline value.
    -   **Type hints** are required for fields, but they’re not enforced at runtime. Use typing.Any when needed.
    -   **Ordering** comes from @dataclass(order=True) and can be customized by computing a .sort\_index in .\_\_post\_init\_\_().
    -   **Immutability** is enabled with frozen=True, yet nested mutable fields can still change if their types allow it.
    -   **Inheritance rules** require that any non-default field in a subclass cannot follow defaulted base-class fields.

[https://realpython.com/python-api/](https://realpython.com/python-api/)

-   An **API** (Application Programming Interface) is an interface that allows different systems to communicate, typically through **requests** and **responses**.
    -   Python is a versatile language for consuming APIs, offering libraries like Requests to simplify the process.
    -   **REST** and **GraphQL** are two common types of APIs, with REST being more widely used for public APIs.
    -   To handle API authentication in Python, you can use API keys or more complex methods like **OAuth** to access protected resources.

[https://benhoyt.com/writings/python-api-design/](https://benhoyt.com/writings/python-api-design/)

-   Requests is an elegant and simple HTTP library for Python
    -   Good API design helps users
    -   When creating a library API, start with a good base
    -   Try to follow [PEP 8](https://pep8.org/) and grok PEP 20
    -   Flat is better than nested (don’t want too many nested . layers)
    -   pytest instead of unittest
    -   Well-designed APIs: collections, csv, datetime, json
    -   A package contains a bunch of modules, and those modules (.py files) expose an API (functions, classes)
    -   Design your library to be used as import lib ... lib.Thing() rather than from lib import LibThing ... LibThing()
    -   Avoid global configuration; use good defaults and let the user override them
    -   Avoid global state; use a class instead
    -   Names should be as short as they can be while still being clear
    -   If an error occurs, raise a custom exception; use built-in exceptions if appropriate
    -   Only break backwards compatibility (major version as opposed to minor or patch) if you’re overhauling your API
        -   Keyword arguments and dynamic typing are great for backwards compatibility
    -   Use type annotations at least for your public API, to make it user friendly
    -   Use @dataclass for classes which are (mostly) data

-   **Data ingestion patterns**
    -   Reading CSV, JSON, YAML, HDF5
    -   Handling large files efficiently (chunking, streaming)
-   **Numerical workflows**
    -   Using NumPy‑style vectorization (even if not using NumPy directly)
    -   Implementing simple ODE integrators (Euler, RK2/4)
    -   Running parameter sweeps or batch analyses
-   **Parsing solver outputs**
    -   Regex or structured parsing for text‑based outputs
    -   Extracting key metrics from CFD/FEA/cycle analysis logs
-   **Data transformation**
    -   Reshaping, filtering, aggregating engineering data
    -   Converting between coordinate systems or units
-   **File I/O patterns**
    -   Clean read/write functions
    -   Handling malformed or partial data gracefully
-   **Project structure**
    -   src/ layout
    -   \_\_init\_\_.py usage
    -   separating logic into modules
-   **Command‑line tools**
    -   argparse patterns
    -   writing tools that accept input files, flags, configs
-   **Workflow orchestration**
    -   Running external solvers with subprocess
    -   Checking return codes, capturing stdout/stderr
    -   Chaining steps: preprocess → run solver → parse → postprocess
-   **Logging**
    -   Using logging instead of print
    -   Log levels, handlers, formatting
-   **Error handling**
    -   Graceful failure modes
    -   Custom exceptions for workflow steps
-   **Configuration management**
    -   YAML/JSON config files
    -   Passing configs through a pipeline
-   **Clean function and class design**
    -   Clear inputs/outputs
    -   Avoiding side effects
    -   Using type hints (-> float, -> dict\[str, float\])
-   **Data modeling**
    -   dataclasses for structured engineering data
    -   Validation patterns (pydantic‑style thinking, even if not using it)
-   **Serialization**
    -   JSON/YAML read/write
    -   Converting dataclasses to/from dicts
-   **API design**
    -   Designing small internal APIs for simulation utilities
    -   Thinking in terms of “what does the user need?”
-   **Calling external executables**
    -   subprocess.run(\[...\], capture\_output=True, text=True)
    -   Handling timeouts, failures, retries
-   **Input deck generation**
    -   Writing templated input files
    -   Parameter substitution
-   **Output parsing**
    -   Regex for extracting values
    -   Parsing fixed‑width or column‑based formats
-   **Basic FFI awareness**
    -   ctypes or cffi for wrapping C/Fortran (conceptual understanding only)
-   **Directory and file management**
    -   Temporary directories
    -   Organizing solver runs
-   **Rapid iteration patterns**
    -   Writing throwaway scripts that evolve into real tools
    -   Keeping prototypes clean enough to refactor
-   **Interactive exploration**
    -   Using Python REPL or notebooks for quick checks
-   **Refactoring**
    -   Turning a prototype into a maintainable module
    -   Extracting functions, removing duplication
-   **pytest basics**
    -   Writing simple unit tests
    -   Using fixtures
    -   Mocking external tools or file I/O
-   **Testable design**
    -   Pure functions
    -   Dependency injection
    -   Avoiding global state
-   **Documentation**
    -   Docstrings
    -   Type hints
-   **Maintainability**
    -   Clear naming
    -   Small modules
    -   Avoiding deeply nested logic
-   **Environment management**
    -   venv
    -   requirements.txt
    -   pyproject.toml basics
-   **Reproducibility**
    -   Pinning versions
    -   Deterministic builds
-   **CI basics**
    -   Running tests in CI
    -   Linting (flake8, black, ruff)
    -   Simple build/test workflows
-   **Practical uses of AI tools**
    -   Code generation
    -   Data cleanup
    -   Automating repetitive tasks
-   **Light numerical optimization**
    -   SciPy optimization patterns
    -   Regression or curve fitting

## Docstrings

Python **docstrings** are string literals enclosed in triple double quotes (""") that provide built-in documentation for modules, classes, and functions. They are the first statement within the definition and are accessible via the \_\_doc\_\_ attribute or the help() function.

```python
def multiply(a, b):
    """
    Multiply two numbers and return the result.

    Args:
        a (int or float): The first number.
        b (int or float): The second number.

    Returns:
        int or float: The product of a and b.

    Raises:
        TypeError: If the inputs are not numbers.
    """

    if not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        raise TypeError("Inputs must be numbers")

    return a \* b
```

**Class docstrings** explain the class's purpose, public methods, and instance variables, while module docstrings appear at the top of files to describe their functionality.

```python
class Calculator:

    """A simple calculator class for arithmetic operations.

    Attributes:
        history (list): A history of operations.
    """

    def \_\_init\_\_(self):

        """Initializes the calculator."""

        self.history = \[\]

    def add(self, a, b):

        """Adds two numbers."""

        return a + b
```

## Type Hints

Python type hints are annotations used to indicate the expected data types for variables, function arguments, and return values, which helps with code readability.

```python
\# Basic types

age: int = 25
name: str = "Alice"
is\_active: bool = True
height: float = 5.9

\# Collections (Python 3.9+)
users\_list: list\[str\] = \["Alice", "Bob"\]
user\_ages: dict\[str, int\] = {"Alice": 25, "Bob": 30}
coordinates: tuple\[float, float, float\] = (10.0, 20.0, 30.0)

def greet(name: str) -> str:

    """Greets a person by name."""
    return f"Hello, {name}!"

def add\_numbers(x: int, y: int) -> int:

    """Adds two integers and returns the sum."""
    return x + y

def print\_details(name: str, age: int) -> None:

    """Prints a person's name and age (returns nothing)."""
    print(f"{name} is {age} years old.")
```

## Logging and errors

```python
import logging

\# Configure basic logging to output to the console (stderr by default)
\# and set the log level to INFO so both INFO and ERROR messages are shown

logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')
logger = logging.getLogger(\_\_name\_\_)

def divide(a, b):
    """
    Attempts to divide two numbers and handles a potential ZeroDivisionError.
    """

    try:
        logging.info(f"Attempting to divide {a} by {b}")
        result = a / b

    except ZeroDivisionError as e:
        # Use logger.exception() within an except block to log the error
        # message along with the full stack trace automatically.
        logger.exception("A ZeroDivisionError occurred during division.")

        # The function can then return a graceful error message or value
        return "Cannot divide by zero!"

    except TypeError as e:
        # Catch other specific exceptions, like if the inputs are not numbers
        logger.exception("A TypeError occurred, check input types.")

        return "Invalid input types!"

    else:
        # The 'else' block runs only if no exception was raised in the 'try' block
        logging.info("Division successful.")

        return result

    finally:
        # The 'finally' block runs regardless of whether an exception occurred
        logging.info("Division operation attempt finished.")

\# Example 1: Successful division
print(f"Result 1: {divide(10, 2)}\\n")

\# Example 2: Zero division error (logs an exception with traceback)
print(f"Result 2: {divide(10, 0)}\\n")

\# Example 3: Type error (logs an exception with traceback)
print(f"Result 3: {divide(10, 'two')}\\n")

import logging

import sys

\# Configure basic settings for logging
logging.basicConfig(

    level=logging.DEBUG, # Set the minimum level to log (DEBUG and above)

    format='%(asctime)s - %(levelname)s - %(message)s', # Define the message format

    handlers=\[

        logging.StreamHandler(sys.stdout), # Output to console (stdout)

        logging.FileHandler("app.log")     # Output to a file named 'app.log'

    \]

)

\# Log messages at various levels

logging.debug("This is a debug message.")
logging.info("This is an info message.")
logging.warning("This is a warning message.")
logging.error("This is an error message.")
logging.critical("This is a critical message.")
```

## Testing

`pip install pytest`

```python
\# wallet.py

class InsufficientAmount(Exception):
    """Custom exception to be raised when spending more cash than available."""
    pass

class Wallet:
    def \_\_init\_\_(self, initial\_amount=0):
        self.balance = initial\_amount

    def add\_cash(self, amount):
        self.balance += amount

    def spend\_cash(self, amount):
        if amount > self.balance:
            raise InsufficientAmount('Not enough available funds to spend this amount')

        self.balance -= amount

\# test\_wallet.py

import pytest

from wallet import Wallet, InsufficientAmount

\# Example 1: Basic test functions
def test\_default\_initial\_amount():
    wallet = Wallet()
    assert wallet.balance == 0

def test\_setting\_initial\_amount():
    wallet = Wallet(100)
    assert wallet.balance == 100

\# Example 2: Using a fixture for setup

@pytest.fixture

def my\_wallet():
    """Returns a Wallet instance with a default balance of 20."""

    return Wallet(20)

def test\_wallet\_add\_cash(my\_wallet):
    my\_wallet.add\_cash(80)
    assert my\_wallet.balance == 100

def test\_wallet\_spend\_cash(my\_wallet):
    my\_wallet.spend\_cash(10)
    assert my\_wallet.balance == 10

\# Example 3: Expecting an exception

def test\_wallet\_spend\_insufficient\_cash(my\_wallet):
    with pytest.raises(InsufficientAmount, match="Not enough available funds to spend this amount"):
        my\_wallet.spend\_cash(100)

\# Example 4: Parameterization (running the same test with different inputs)

@pytest.mark.parametrize("initial\_amount, spend\_amount, expected\_balance", \[
    (50, 30, 20),
    (100, 50, 50),
    (10, 10, 0)
\])

def test\_wallet\_multi\_spend(initial\_amount, spend\_amount, expected\_balance):
    wallet = Wallet(initial\_amount)
    wallet.spend\_cash(spend\_amount)
    assert wallet.balance == expected\_balance
```

`pytest -v`

## CLI argparse

```python
import argparse

if \_\_name\_\_ == "\_\_main\_\_":
    # Create the parser
    parser = argparse.ArgumentParser(description="A simple greeting CLI tool.")

    # Add the 'name' argument
    parser.add\_argument("name", type=str, help="The name of the person to greet.")

    # Add an optional '--french' flag
    parser.add\_argument("--french", action="store\_true", help="Use a French greeting.")

    # Parse the arguments
    args = parser.parse\_args()

    # Determine the greeting
    if args.french:
        greeting = f"Bonjour, {args.name}!"

    else:
        greeting = f"Hello, {args.name}!"

    print(greeting)
```

`python greet.py Bob`

*Output:* Hello, Bob!

`python greet.py Charlie --french`

*Output:* Bonjour, Charlie!

`python greet.py --help`

*Output:* (A detailed usage message will be displayed, explaining the arguments and options) 

## JSON

JSON file:

```json
{

  "name": "Frieda",

  "isDog": true,

  "hobbies": \["eating", "sleeping", "barking"\],

  "age": 8

}
```

```python
import json

\# 1. Define the custom exception

class JSONValidationError(Exception):
    """Raised when the JSON data does not meet requirements"""
    pass

try:
    # --- Simulated file content for demonstration ---
    # With data.json content: {"name": "Frieda", "isDog": true, "age": "eight"}

    with open('data.json', 'r') as file:
        data = json.load(file)

    # 2. Validate the specific field
    if not isinstance(data.get('age'), int):
        # 3. Raise the custom exception
        raise JSONValidationError(f"Expected 'age' to be int, got {type(data.get('age')).\_\_name\_\_}")

    print(f"Name: {data\['name'\]}")
    print(f"Age: {data\['age'\]}")

except FileNotFoundError:
    print("Error: The file data.json was not found.")

except json.JSONDecodeError:
    print("Error: Failed to decode JSON from the file.")

except JSONValidationError as e:
    # 4. Catch the custom exception
    print(f"Validation Error: {e}")

except Exception as e:
    print(f"An unexpected error occurred: {e}")
```

Output:

`Name: Frieda  `

`Age: 8  `

`Hobbies: eating, sleeping, barking`

## Dataclass

```python
from dataclasses import dataclass, field

@dataclass(frozen=True) # Makes the object immutable

class InventoryItem:
    """Represents an item in the warehouse inventory."""

    name: str
    unit\_price: float
    quantity: int = 0

    def \_\_post\_init\_\_(self):
        # Validation example
        if self.unit\_price < 0:
            raise ValueError("Unit price cannot be negative")

        if self.quantity < 0:
            raise ValueError("Quantity cannot be negative")

    @property

    def total\_value(self) -> float:
        """Calculate the total market value of the current stock."""
        return self.unit\_price \* self.quantity

\# Usage

item = InventoryItem(name="Widget", unit\_price=10.5, quantity=5)
print(item.total\_value) # 52.5
```

When to use a conventional class instead:

You should only move away from a dataclass to a conventional class if:

-   You need a highly customized \_\_init\_\_ method with complex logic.
-   The class becomes heavily behavior-oriented (many methods) rather than just a data container.

## NumPy, pandas, SciPy

**NumPy** is the **foundation** of scientific computing in Python. Everything else (pandas, SciPy, scikit‑learn, JAX, PyTorch) builds on its array model.

**What it’s best at**

-   Fast **vectorized math** on large arrays
-   Efficient **matrix operations**
-   Broadcasting (automatic expansion of shapes)
-   Random number generation
-   Linear algebra (via numpy.linalg)
-   Interfacing with C/C++ and Fortran code

**Core concepts**

-   **ndarray**: the core data structure
-   **Vectorization**: replacing Python loops with array operations
-   **Broadcasting rules**: how shapes align
-   **Slicing/indexing**: selecting subarrays efficiently
-   **Boolean masks**: filtering without loops
-   **dtype**: memory layout and precision

-----------------------------

**pandas** is built on NumPy but adds **tabular data structures** and high‑level operations.

**What it’s best at**

-   Cleaning and aligning flight data
-   Handling missing values
-   Merging/joining multiple datasets
-   Time‑series operations
-   Grouping and aggregations
-   Fast CSV/Parquet/Feather IO

**Core concepts**

-   **Series** vs **DataFrame**
-   **Index** and **MultiIndex**
-   **loc / iloc**
-   **groupby**
-   **merge / join / concat**
-   **resample** for time‑series
-   **apply** vs vectorized operations

-----------------------------

**SciPy** sits on top of NumPy and provides **scientific algorithms** you don’t want to implement yourself.

**What it’s best at**

-   Optimization (root finding, least squares, constrained optimization)
-   Interpolation (1D, 2D, ND)
-   Signal processing (filters, FFTs)
-   Numerical integration
-   Statistics and distributions
-   Spatial algorithms (KD‑trees, nearest neighbors)

**Key modules**

-   scipy.optimize
    -   least\_squares, curve\_fit, minimize
-   scipy.interpolate
    -   interp1d, RegularGridInterpolator, BSplines
-   scipy.integrate
    -   quad, solve\_ivp
-   scipy.stats
    -   distributions, hypothesis tests
-   scipy.signal
    -   filtering, smoothing