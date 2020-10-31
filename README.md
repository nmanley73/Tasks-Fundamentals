# Tasks for Fundamentals of Data Analysis module

### Task1
**October 5th 2020:** Write a Python function called **counts** that takes a list as input and returns a dictorary of unique items in the list as keys and the number of times each item appears as values. So the input ['A', 'A', 'B', 'C', 'A'] should have output {'A': 3, 'B':1, 'C':1}

#### Description
This project displays a number of functionalities of the Python programming language namely to count the number of unique items in a list. Then to convert the count of items into the dictionary format. This format displays the output as keys and values of the input and makes the output easier to read for the user. This is all completed within a loop which goes through each item of the input individually. Its saved within a user-defined function which allows the user the run the code at anytime within the project.

#### Research
The project can be broken down into a number of different sections which need to be researched.
1. Count
2. Convert the count into the dictionary format
3. For loop
4. Function
5. Sorting the output into alphabetical order

###### Count
The count function can count one list item. It does not work for counting multiple items in a list [1]. In the example below the user is attempting to count all items within the list individually. However python will only return the output of the last count method. Therefore in order to count all 3 items the count functionality will have to be enclosed within a loop.
*A list of strings
l = ['A', 'A', 'B', 'C', 'A']

*Count of each item in the list
l.count('A')
l.count('B')
l.count('C')

There is a function within the collection module called counter [2] which counts all items within the list and display all items in a dictionary format. The exact requirement of the task. However we are to complete the task without any module from the standard library. 

*Count the string objects in a dictionary
Counter(l)
Counter({'A': 3, 'B': 1, 'C': 1})

###### Dictionary format
A dictionary consists of key and value pairs. It display the output in a very readable format. A dictionary of a list can be created by using the dict() function [3].

*Create dictionary with the following inputs
dict(A = 3, B = 1, C = 1)

###### Function
Functions which are user-defined are functions created by the user rather than the functions created by the Python environment [5]. At the outset the function is defined with the keyword def. The return statement is used to return a value from the function.
Def Counts
    statement_1
    statement_2
    ....
    return expression

###### Sorting
On running the program the output wasn't sorted in alphabetical order as specified in the task. The keys of the dictionary was sorted by using the sorted function [6] within the for loop.

### Code Solution:
- Firstly the input is defined in the variable l.               l = ['A', 'A', 'B', 'C', 'A']
- The function counts is defined using the keword def.          def counts(l):
- A for loop used to iterate each item in the list              for i in range(0, len(l)):
- Return gets a value from the function                         return dict((x,l.count(x)) for x in sorted(set (l)))
- Dict creates a dictionary for the out put to be displayed     dict((x,l.count(x))
- Sorted function sorts the dictionary in alphabetical order    sorted(set (l)))

*A list of strings
l = ['A', 'A', 'B', 'C', 'A']

*Define function counts
def counts(l):
    *Loop from 0 to length of the list
    for i in range(0, len(l)):
        *return dictionary
        return dict((x,l.count(x)) for x in sorted(set (l)))
        


### References:
[1] - TutorialsPoint: Python List count() method; https://www.tutorialspoint.com/python/list_count.htm

[2] - PythonForBeginners: Python Collections Counter; https://www.pythonforbeginners.com/collection/python-collections-counter

[3] - Real Python: Dictionaries in Python; https://realpython.com/python-dicts/

[4] - w3schools.com: Python For Loops; https://www.w3schools.com/python/python_for_loops.asp

[5] - Stack Overflow: How can i count the occurences of a list item?; https://stackoverflow.com/questions/2600191/how-can-i-count-the-occurrences-of-a-list-item

[6] - A Whirlwind tour of python: Defining and using functions; https://jakevdp.github.io/WhirlwindTourOfPython/08-defining-functions.html

[7] - thispointer.com: Python : How to Sort a Dictionary by key or Value?; https://thispointer.com/python-how-to-sort-a-dictionary-by-key-or-value/





