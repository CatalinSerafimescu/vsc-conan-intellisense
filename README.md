# Conan Utility For Visual Studio Code

## Overview
This package provides a helper method for a [Conan](https://conan.io) project's conanfile.py to update the Visual Studio Code C++ Tools plugin after installing dependencies, so that Intellisense finds the installed paths

Based on [parktoma-vscconan](https://github.com/parkertomatoes/parktoma-vscconan)


## How to use
Use a [conanfile.py](https://docs.conan.io/en/latest/reference/conanfile.html) instead of conanfile.txt to define your project dependencies.

Then, in your class, in the event handler for ```generate``` call ```update_cpp_tools```:
```python
#...
from parktoma.vscconan import update_cpp_tools

class MyProject(ConanFile):
    #...
    def generate(self):
        .....
        update_cpp_tools(self, conanfile_path=__file__)
```

Then, run ```conan install```. c_cpp_properties.json should be updated and Intellisense should find your dependencies.
