# `modguard-ignore`
To ignore a particular import which should be allowed unconditionally, use the `modguard-ignore` comment directive.
```python
# modguard-ignore
from core.main import private_function
```
The directive can also be specific about the import to ignore, which is particularly useful when importing multiple packages.
```python
# modguard-ignore private_function
from core.main import private_function, public_function
```
Note: Names given to `modguard-ignore` should match the alias as it is used in the subsequent import line, not the full module path from the project root.

Note: Dependency violations are detected at the import layer. This means that nonstandard ways to access packages such as `getattr`, `importlib`, or dynamically generated namespaces will not be caught by `modguard`.