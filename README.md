# get_next_line Function
## Description
- The ft_get_next_line function is designed to read text from a given file descriptor. 
- This project aims to deepen understanding of file I/O operations in C and improve proficiency in managing file descriptors and buffer manipulation.

## Objective
- The ft_get_next_line function reads a line from a file descriptor until a newline character (\n) or EOF is encountered.
- The key feature of this function is its ability to be called multiple times consecutively to read lines from a file one by one.

## Parameters
- fd: The file descriptor from which to read the input.

## Return Value
- If successful, returns a pointer to a null-terminated string containing the line read from the file descriptor, including the newline character if it exists.
- If an error occurs, returns NULL.

## Usage
To use the ft_get_next_line function in your projects, follow these steps:

1. Clone the repository:
```
git clone <repository-url>
```
2. Include the function prototype in your source code:
```
char *get_next_line(int fd);
```
3. Call the function with the desired file descriptor:
```
#include "get_next_line.h"
#include <stdio.h>
#include <fcntl.h>

int  main(void)
{
        int fd = open("example.txt", O_RDONLY);
        char *line = NULL;

        while ((line = get_next_line(fd)) != NULL)
        {
                printf("%s", line);
                free(line);
        }
        close(fd);
        return (0);
}
```
4. Compile your program with the file get_next_line.c and the file get_next_line_utils.c:
```
gcc -o my_program main.c get_next_line.c get_next_line_utils.c 
```
5. Execute your program:
```
./my_program
```
