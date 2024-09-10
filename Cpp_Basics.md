# Difference between `cin.getline()` and `std::getline()`

## 1. `std::getline()`

### Usage:
```cpp
std::getline(std::cin, stringname)
```

### Purpose:
Reads an entire line of text, including spaces, until a newline (`\n`) is encountered.

### Input Type:
It reads into a `std::string`.

### Functionality:
It extracts characters from the input stream (like `std::cin`) and stores them in a string until it encounters a newline character.

### Example:
```cpp
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cout << "Enter your name: ";
    std::getline(std::cin, name); // Reads the entire line including spaces
    std::cout << "Hello, " << name << std::endl;
    return 0;
}
```

### Advantages:
- Reads the entire line including spaces.

### Common Use Case:
When you want to read a full sentence or line of text.

## 2. `cin.getline()`

### Usage:
```cpp
cin.getline(array, size)
```

### Purpose:
Reads characters into a character array, including spaces, up to a specified limit or until a newline is encountered.

### Input Type:
It reads into a character array (C-style string).

### Functionality:
It extracts characters from the input stream and stores them in a character array, stopping at either a newline or when it reaches the specified size.

### Example:
```cpp
#include <iostream>

int main() {
    char name[50];
    std::cout << "Enter your name: ";
    std::cin.getline(name, 50); // Reads up to 50 characters or until newline
    std::cout << "Hello, " << name << std::endl;
    return 0;
}
```

### Advantages:
- Useful when working with fixed-size character arrays.

### Common Use Case:
When dealing with character arrays and you want to control the maximum number of characters to read.

## Key Differences:

1. **Input Type:**
   - `std::getline()` works with `std::string`, which is more flexible and dynamic.
   - `cin.getline()` works with character arrays, which have fixed sizes.

2. **Buffer Size:**
   - `std::getline()` doesn't need a size limit; it will resize the `std::string` as needed.
   - `cin.getline()` requires you to specify the size of the character array.

3. **Use Cases:**
   - Use `std::getline()` when working with modern C++ and `std::string` for flexible string handling.
   - Use `cin.getline()` when working with C-style strings or when you want more control over the size of the input buffer.
