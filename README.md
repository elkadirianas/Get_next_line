# Get_next_line

This repository contains the implementation of the `get_next_line` project from the 42 cursus. The objective of this project is to create a function that reads a line from a file descriptor and returns it. This project helps in understanding and practicing file I/O operations, memory management, and handling edge cases in C programming.

## Description

The `get_next_line` function reads a line from a file descriptor and returns it. The function should be able to handle multiple file descriptors at the same time and return the correct line for each file descriptor.

## Prototype

```c
char *get_next_line(int fd);
```

- `fd`: The file descriptor to read from.

## Usage

1. Clone the repository:
    ```sh
    git clone https://github.com/elkadirianas/Get_next_line.git
    cd Get_next_line
    ```

2. Compile the code:
    ```sh
    cc -Wall -Wextra -Werror -D BUFFER_SIZE=<size> get_next_line.c get_next_line_utils.c -o get_next_line
    ```

3. Use the compiled program:
    ```sh
    ./get_next_line <file>
    ```

## Files

- `get_next_line.c`: Contains the main logic for reading a line from a file descriptor.
- `get_next_line_utils.c`: Contains utility functions used by `get_next_line.c`.
- `get_next_line.h`: Header file containing the function prototype and necessary includes.

## Project Requirements

- The function should read from a file descriptor until a newline character is found or the end of the file is reached.
- The function should return the line read, including the newline character if found.
- The function should handle multiple file descriptors simultaneously.
- The function should have a configurable buffer size defined by the `BUFFER_SIZE` macro.

## Example

```c
#include <stdio.h>
#include <fcntl.h>
#include "get_next_line.h"

int main(void)
{
    int fd = open("example.txt", O_RDONLY);
    char *line;

    if (fd == -1)
        return (1);

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return (0);
}
```


## Author

- [elkadirianas](https://github.com/elkadirianas)
