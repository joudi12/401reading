# File
___

### What Is a File?
- Before we can go into how to work with files in Python, it’s important to understand what exactly a file is and how modern operating systems handle some of their aspects.

- Files on most modern file systems are composed of three main parts:

    - Header: metadata about the contents of the file (file name, size, type, and so on)
    
    - Data: contents of the file as written by the creator or editor
    
    - End of file (EOF): special character that indicates the end of the file
---
## File Paths
- When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

    - Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
    
    - File Name: the actual name of the file
    
    - Extension: the end of the file path pre-pended with a period (.) used to indicate the file type
---
## Line Endings
- One problem often encountered when working with file data is the representation of a new line or line ending. The line ending has its roots from back in the Morse Code era, when a specific pro-sign was used to communicate the end of a transmission or the end of a line.

### Opening and Closing a File in Python
- When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object:
    - `file = open('dog_breeds.txt')`
    - *After you open a file, the next thing to learn is how to close it.*
- It’s important to remember that it’s your responsibility to close the file. In most cases, upon termination of an application or script, a file will be closed eventually. However, there is no guarantee when exactly that will happen. This can lead to unwanted behavior including resource leaks. It’s also a best practice within Python (Pythonic) to make sure that your code behaves in a way that is well defined and reduces any unwanted behavior.
- When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:
 
 `reader = open('dog_breeds.txt')`

 `try:`
`# Further file processing goes here`
 
 `finally:`
 
 `reader.close()`
 
 - The second way to close a file is to use the with statement:

> with open('dog_breeds.txt') as reader:
  


| haracter      |                           Meaning                          |
| ------------- | -----------------------------------------------------------|
|     'r'       | Open for reading (default)                                 |
|     'w'       | Open for writing, truncating (overwriting) the file first  |
|  'rb' or 'wb' |       Open in binary mode (read/write using byte data)     |



