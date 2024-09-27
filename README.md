# Get Next Line

A C function that reads a line from a file descriptor.

## Description

Get Next Line is a programming project at School 42. The goal is to create a function that reads a line from a file descriptor. This project will not only allow you to add a very convenient function to your collection, but it will also make you learn a highly interesting new concept in C programming: static variables.

## Function Prototype

```c
int get_next_line(int fd, char **line);
```
## Parameters
fd: The file descriptor to read from.
line: A pointer to a character pointer that will store the line read from the file descriptor.
Return Value
1: A line has been read
0: EOF has been reached
-1: An error happened
## Compilation
To compile the project, use the following command:
```
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=32 get_next_line.c get_next_line_utils.c
```
You can define the buffer size for read() by adding -D BUFFER_SIZE=xx to the compilation command.

## Usage
```
#include "get_next_line.h"

int main(void)
{
    int fd;
    char *line;

    fd = open("test.txt", O_RDONLY);
    while (get_next_line(fd, &line) > 0)
    {
        printf("%s\n", line);
        free(line);
    }
    close(fd);
    return (0);
}
```
## Features
Reads from a file descriptor
Works with files, stdin, or even network connections
Uses a single static variable
Can manage multiple file descriptors simultaneously
## Norme
This project adheres to the norminette coding standard of School 42.
