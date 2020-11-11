# Python environment
Home

## Benefits of MODULES
- Simplicity: A module typically focuses on one relatively small portion of the problem.

- Maintainability: If modules are written in a way that minimizes interdependency, there is decreased likelihood that modifications to a single module will have an impact on other parts of the program.

- Reusability: This eliminates the need to duplicate code.

- Scoping: Modules typically define a separate namespace, which helps avoid collisions between identifiers in different areas of a program.

## Recursion
### Definitions
- The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function.
- A function fun is called direct recursive if it calls the same function fun. A function fun is called indirect recursive if it calls another function say fun_new and fun_new calls fun directly or indirectly.
- A recursive function is tail recursive when recursive call is the last thing executed by the function.
- If the base case is not reached or not defined, then the stack overflow problem may arise.
- When any function is called from main(), the memory is allocated to it on the stack. A recursive function calls itself, the memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.

### Recursive vs iterative programming
- The recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached.
- Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals

