# ArgumentParser

The ArgParser class facilitates command-line argument parsing, supporting boolean flags, integer arguments, and string arguments with optional short names and descriptions.

## Features
## Features
**- Boolean Flags:** Add and parse boolean flags with short and long names.  
**- Integer Arguments:** Handle integer arguments with optional descriptions.  
**- String Arguments:** Manage string arguments with detailed descriptions.  
**- Positional Arguments:** Support for positional arguments.  
**- Flexible Parsing:** Easily parse command-line inputs and retrieve values.**  
    
## Usage
```cpp
#include "ArgParser.h"

int main(int argc, char* argv[]) {
    ArgumentParser::ArgParser parser("ExampleParser");
    auto& help = parser.AddFlag('h', "help", "Show help message");
    auto& count = parser.AddIntArgument('c', "count", "Number of items");
    auto& name = parser.AddStringArgument('n', "name", "Name of the user");

    if (!parser.Parse(std::vector<std::string>(argv, argv + argc))) {
        // Handle parsing error
    }

    if (parser.GetFlag("help")) {
        // Show help message
    }

    int itemCount = parser.GetIntValue("count");
    std::string userName = parser.GetStringValue("name");

    // Use parsed values
}
```

## Installation
1. Clone the repository.
2. Include the necessary headers in your project.

```
git clone https://github.com/alex-sandalov/ArgumentParser.git
```
