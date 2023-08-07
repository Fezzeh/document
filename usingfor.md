BASH for loop

Loops are used in any programming language to execute the same code repeatedly. Three types of loops are mainly used in programming for doing repetitive tasks. These are for, while, and do-while/repeat-until loop. You can apply for loop on bash script in various ways. Some useful BASH for loop examples has been mentioned in this article.

Syntax of for loop:
# loop through a list
for value in list
do
    commands
done

# loop specified values
for value in file1 file2 file3
do
    commands
done

# loop through strings resulting from a command
for value in $(Linux command)
do
    commands
done

# loop through increment or decrement numbers
# traditional procedural for loop
for (( i=0; i<10; i++)
do
    commands
done


According to the above syntax, the starting and ending block of for loop is defined by do and done keywords in the bash script. The uses of different loops have shown in the next part of this tutorial.

Example-1: Reading static values
Create a bash file named loop1.sh with the following script to read the values from a list using for loop. In this example, 5 static values are declared in the lists. This loop will iterate 5 times, and each time, it will receive a value from the lists and store it in the variable named color that will print inside the loop.

#!/bin/bash
# Define loop to read string values
for color in Blue Green Pink White Red
do
    # Print the string value
    echo "Color = $color"
done

Example-2: Reading Array Variable
You can use for loop to iterate the values of an array. Create a new bash file named loop2.sh with the following script. In this example, the loop retrieves the values from an array variable named ColorList, and it will print the output only if the Pink value is found in the array elements.

#!/bin/bash
# Declare and array
ColorList=("Blue Green Pink White Red")
# Define loop to  iterate the array values
for color in $ColorList
do
    # Check the value is pink or not
    if [ $color == 'Pink' ]
    then
            echo "My favorite color is $color"
    fi
done
The following output will appear after executing the above script.

Example-3: Reading Command-line arguments
Command-line arguments values can be iterated by using for loop in bash. Create a new bash file named loop3.sh with the following script to read and print the command-line argument values using for loop.


#!/bin/bash
# Define loop to read argument values
for myval in $*
do
    # Print each argument
    echo "Argument: $myval"
done

Example-4: Finding odd and even number using three expressions
The C-style syntax of for loop is three expression syntax. The first expression indicates initialization, the second expression indicates termination condition, and the third expression indicates increment or decrement. Create a bash file named loop4.sh with the following script to find out the odd and even numbers from 1 to 5.

#!/bin/bash

# Define for loop in C-style format
for (( n=1; n<=5; n++ ))
do  
    # Check the number is even or not
    if (( $n%2==0 ))
    then
        echo "$n is even"
    else
        echo "$n is odd"
    fi  
done

Example-5: Reading file content
You can use for loop to read the content of any file by using the ‘cat’ command. Suppose you have a file named ‘weekday.txt‘ which contains the name of all weekdays. Now, create a bash file named loop5.sh to read and print the content of the file.

#!/bin/bash
# Initialize the counter
i=1
# Define for loop to read the text file
for var in `cat weekday.txt`
do
    # Print the file content
    echo "Weekday $i: $var"
    ((i++))
done

Example-6: Create infinite for loop
Create a bash named loop6.bash with the following script to know the way to declare infinite for loop. Here, the loop will iterate for infinite times and print the counter value until the user presses Ctrl+C.

#!/bin/bash
# Initialize counter variable
counter=1
# Display message for termination
echo "Press Ctrl+c to terminate from the loop"
# Define infinite loop
for (( ;; ))
do
   # Print the number of iteration
   echo "Iterating for $counter time(s)."
   # Wait for 1 second
   sleep 1
   # Increment the counter
   ((counter++))
done

Example-7: Use of for loop with command substitute
Create a bash file named loop7.bash with the following script to know the use of for loop to read and print the command output.

#!/bin/bash
echo "All bash files starting with 'a' are:"

# Read the output of command substitute using for loop
for val in $(ls a*.bash)
do
    # Print the file name
    echo "$val"
done

Example-8: Conditional exit with break
Create a bash file named loop8.bash with the following script to know the way to exit from the loop based on any particular condition.

#!/bin/bash
# Define a for loop to iterate 10 times
for (( i=1; i<=10; i++ ))
do  
    # Define the conditions to terminate the loop
    if (( $i%3==0 && $i%6==0 ))
    then
        # Terminate from the loop
        echo "Terminated."
        break
    else
        # Print the current value of i
        echo "The current value of i is: $i"
    fi  
done

Example-9: Early continuation with continue statement
Create a bash file named loop8.bash with the following script to know how to omit one or more statement(s) from the loop by using a continuous statement based on the particular condition.

#!/bin/bash
# Declare an associative array
declare -A Applicants
# Intialize the array values
Applicants=( [1022]="Present" [1034]="Present" [1045]="Absent" [1067]="Present" )

echo "List of the applicant's ID who are present:"
for k in ${!Applicants[@]}
do
     # Filter the applicant's ID who are absent
     if [ ${Applicants[$k]} == "Absent" ]; then
        continue
     else
        # Print the applicant's ID who are present
        echo $k
     fi
done

