#### Read
## *this is how to use read command:*

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
3. Using Read Command with -p Option

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable and the -p option. The input value is printed later.

   For Example

    ```python
     #!/bin/bash  
     #Take the input with the prompt message
     read -p "Enter the book name: " book
     #Print the input value
     echo "Book name: $book"
     ```
4. Using Read Command with -s Option

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable and the -s option. The input value of the password will not be displayed for the -s option. The input values are checked later for authentication. A success or failure message is also printed.

   For Example

    ```python
    #!/bin/bash  
    #Take the input with the prompt message
    read -p "Enter your email: " email
    #Take the secret input with the prompt message
    read -sp "Enter your password: " password

    #Add newline
    echo ""

    #Check the email and password for authentication
    if [[ $email == "admin@example.com" && $password == "secret" ]]
    then
    #Print the success message
    echo "Authenticated."
    else
   #Print the failure message
    echo "Not authenticated."
    fi
    ```
5. Using Read Command with -a Option

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable and the -a option. The array values are printed later after taking the input values from the terminal.

   For Example

   ```python
    #!/bin/bash  
    echo "Enter the country names: "  
    #Take multiple inputs using an array  
    read -a countries

    echo "Country names are:"
    #Read the array values
    for country in ${countries[@]}
    do
    echo $country
    done
    ```
6. Using Read Command with -n Option

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable and the -n option.

   For Example:

   ```python
    #!/bin/bash  
    #Print the prompt message
    echo "Enter the product code: "  
    #Take the input of five characters
    read -n 5 code
    #Add newline
    echo ""
    #Print the input value
    echo "The product code is $code"
    ```
7. Using Read Command with -t Option

    Create a Bash file with the following script that takes the input from the terminal using the read command with a variable and the -t option.

   For Example:
   ```python
    #!/bin/bash  
    #Print the prompt message
    echo -n "Write the result of 10-6: "  
    #Take the input of five characters
    read -t 3 answer

    #Check the input value
    if [[ $answer == "4" ]]
    then
    echo "Correct answer."
    else
    echo "Incorrect answer."
    fi
    ``
