****Read
**this is how to use read command:**
1. Using Read Command without Any Option and variable.

    Create a Bash file with the following script that takes the input from the terminal using the **read** command without any option and variable. If no variable is used with the **read** command, the input value is stored in the *$REPLY* variable. The value of this variable is printed later after taking the input. 

    For Example:

    ```python
    #!/bin/bash  
    #Print the prompt message
    echo "Enter your favorite color: "  
    #Take the input
    read  
    #Print the input value
    echo "Your favorite color is $REPLY"
    ```
    