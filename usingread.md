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
2. Using Read Command with a Variable

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable. The method of taking the single or multiple variables using a read command is shown in this example. The values of all variables are printed later.

    For Example:

    ```python
    #!/bin/bash  
    #Print the prompt message
    echo "Enter the product name: "  
    #Take the input with a single variable
    read item

    #Print the prompt message
    echo "Enter the color variations of the product: "  
    #Take three input values in three variables
    read color1 color2 color3

    #Print the input value
    echo "The product name is $item."  
    #Print the input values
    echo "Available colors are $color1, $color2, and $color3."
    ```