# Modular programming
- Modular programming refers to the process of breaking a large, unwieldy programming task into separate, smaller, more manageable subtasks or modules. Individual modules can then be cobbled together like building blocks to create a larger application.

- There are several advantages to modularizing code in a large application:

- Simplicity: Rather than focusing on the entire problem at hand, a module typically focuses on one relatively small portion of the problem. If you’re working on a single module, you’ll have a smaller problem domain to wrap your head around. This makes development easier and less error-prone.

- Maintainability: Modules are typically designed so that they enforce logical boundaries between different problem domains. If modules are written in a way that minimizes interdependency, there is decreased likelihood that modifications to a single module will have an impact on other parts of the program. (You may even be able to make changes to a module without having any knowledge of the application outside that module.) This makes it more viable for a team of many programmers to work collaboratively on a large application.

- Reusability: Functionality defined in a single module can be easily reused (through an appropriately defined interface) by other parts of the application. This eliminates the need to duplicate code.

### The import Statement 

- Module contents are made available to the caller with the import statement. The import statement takes many different forms, shown below.
- `import <module_name>`
- Note that this does not make the module contents directly accessible to the caller. Each module has its own private symbol table, which serves as the global symbol table for all objects defined in the module. Thus, a module creates a separate namespace, as already noted.

- `from <module_name> import <name(s)>`
- An alternate form of the import statement allows individual objects from the module to be imported directly into the caller’s symbol table:
- Following execution of the above statement, <name(s)> can be referenced in the caller’s environment without the <module_name> prefix:

### The dir() Function

- The built-in function dir() returns a list of defined names in a namespace. Without arguments, it produces an alphabetically sorted list of names in the current local symbol table:
- Note how the first call to dir() above lists several names that are automatically defined and already in the namespace when the interpreter starts. As new names are defined (qux, Bar, x), they appear on subsequent invocations of dir().

- When given an argument that is the name of a module, dir() lists the names defined in the module:
- Any .py file that contains a module is essentially also a Python script, and there isn’t any reason it can’t be executed like one.

- If a file named __init__.py is present in a package directory, it is invoked when the package or a module in the package is imported. This can be used for execution of package initialization code, such as initialization of package-level data.




