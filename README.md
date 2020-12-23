# Tasks for Fundamentals of Data Analysis module

### Task 1
**October 5th 2020:** Write a Python function called **counts** that takes a list as input and returns a dictionary of unique items in the list as keys and the number of times each item appears as values. So the input ['A', 'A', 'B', 'C', 'A'] should have output {'A': 3, 'B':1, 'C':1}

#### Description
This project displays a number of functionalities of the Python programming language namely to count the number of unique items in a list. Then to convert the count of items into the dictionary format. This format displays the output as keys and values of the input and makes the output easier to read for the user. This is all completed within a loop which goes through each item of the input individually. It's saved within a user-defined function which allows the user the run the code at anytime within the project.

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
A dictionary consists of key and value pairs - its a format which is very readable. A dictionary of a list can be created by using the dict() function [3].

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
                                 
- l = ['A', 'A', 'B', 'C', 'A']                                 Firstly the input is defined in the variable l. 
- def counts(l):                                                The function counts is defined using the keyword def. 
- for i in range(0, len(l)):                                    A for loop used to iterate each item in the list              
- return dict((x,l.count(x)) for x in sorted(set (l)))          Return gets a value from the function                         
- dict((x,l.count(x))                                           Dict() creates a dictionary for the output to be displayed    
- sorted(set (l)))                                              Sorted function sorts the dictionary in alphabetical order    

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

[7] - thispointer.com: Python: How to Sort a Dictionary by key or Value?; https://thispointer.com/python-how-to-sort-a-dictionary-by-key-or-value/

*****

### Task 2

**November 2nd 2020:** Write a function called dicerolls that simulates rolling dice. Your function should take 2 parameters: the number of dice k and the number of times to roll the dice n. The function should simulate randomly rolling k dice n times. Keeping track of each total face value. It should then return a dictionary with the number of times each possible total face value occurred.

#### Description
In this task i will be simulating the rolling of two dice. The dice are to be rolled 1000 times and the results are returned as a dictionary with the number of times each possible face value occurs. The paramters to start with are the number of rolls of the dice (k = 1000) the number of dice (n = 2) and the number of sides on dice (6). I use the random.choice method to simulate the rolling of the dice and generate the results.

#### Research
The project can be broken down into a number of different sections which need to be researched.
1. random.randint method
2. random.choice method
3. Range method

There is a considerable amount of content online both related to python and other programming languages which deal with rolling dice simulation. The majority use the random.randint function to complete the task. I have completed an example displaying simulation of dice roll with one dice using the random.randint method. Using one dice there is an equal probability of getting any of the six sides. This is true also of the random.choice method for rolling one dice.

I used Dr. Soumen Atta publication Simulating randomness using Python’s random module to research using the random.choice method to simulate the rolling of multiple dice. The publication describes various different parameters using the random.choice method to displat the simulation of rolling dice. Within the function the range method is used to get the start and end point which is used in the random.choice function to generate the simulation.

### Code Solution:
- import numpy as np                                            Import the numpy library                                          
- def dicerolls(k, n):                                          The function dicerolls is defined with 2 parameters k & n         
                                                                k = the number of dice
                                                                n = the numbers of rolls of the dice
- counter = {n : 0 for n in range(k, k*6 + 1)}                  Prepares the dictionary 
- for i in range(n):                                            A for loop used to iterate each item in the list 
- total = sum(random.choices(range(1, 6 + 1), k = k))           The sum of the rolls are stored in varaible total using random.choice
- counter[total] += 1                                           Counter displays the result in the dictionary
- dicerolls(2, 1000)                                            Run the function dicerolls specifying the number of dice and the number of dice rolls        

* import numpy library
import numpy as np
* define the function dicerolls with 2 parameters k = no. of dice & n = no. of dice rolls
def dicerolls(k, n):
    * prepare dictionary with zero values for all possible results
    counter = {n : 0 for n in range(k, k*6 + 1)}

    * roll the dice
    for i in range(n):
        * sums all rolls of the dice
        total = sum(random.choices(range(1, 6 + 1), k = k))
        * adds result of each roll to counter
        counter[total] += 1
    return counter
* enter values for the no. of dice & no. of rolls (2 and 1000)
dicerolls(2, 1000)


### References:
[1] - Dr. Soumen Atta: Simulating randomness using Python’s random module; https://soumenatta.medium.com/simulating-randomness-using-pythons-random-module-de9c08910c3c

[2] - GeekforGeeks: Python | range() method; https://www.geeksforgeeks.org/python-range-method/?ref=rp

[3] - w3schools.com: Python Random choices() Method; https://www.w3schools.com/python/ref_random_choices.asp

[4] - Programiz: Python Operators; https://www.programiz.com/python-programming/operators#:~:text=What%20are%20operators%20in%20python%3F%20Operators%20are%20special,and%205%20is%20the%20output%20of%20the%20operation.

### Task 3

The numpy.random.binomial function can be used to simulate flipping a coin with a 50/50 chance of heads or tails. Interestingly, if a coin is flipped many times then the number of heads is well approximated by a bell-shaped curve. For instance, if we flip a coin 100 times in a row the chance of getting 50 heads is relatively high, the chances of getting 0 or 100 heads is relatively low, and the chances of getting any other number of heads decreases as you move away from 50 in either direction towards 0 or 100. Write some python code that simulates flipping a coin 100 times. Then run this code 1,000 times, keeping track of the number of heads in each of the 1,000 simulations. Select an appropriate plot to depict the resulting list of 1,000 numbers, showing that it roughly follows a bell-shaped curve.

#### Description

The coin toss because it has only two outcomes is a common method to resolve disputes, how teams start a game as it is a fair and simple method of getting a result. This task simulates the tossing of a coin with 100 repetitions to produce the number of occurences of heads (successes). This experiment is then repeated 1,000 times to observe if the number of heads of all thousand experiments roughly fits into a bell-shaped curve plot. Where the majority of results are along the central average with very few results along the extremeties of the plot.

#### Research
The project can be broken down into a number of different sections which need to be researched.
1. Background of coin toss simulation
2. random.binomial distribution
2. bell-shaped curve plot
3. Range method

#### Coin toss Simulation

The toss of a coin has two outcomes and so is used extensively to decide outcomes between two people or two teams in a sporting environment. Therefore it is assumed that the coin toss that takes place is a fair way of solving an issue. Publications [1] & [2] have demonstrated that the outcome can be manipulated in favour of a certain result. However this simulation of the coin toss is generated by a Python program and thus is a fair and accurate way of simulating the coin toss experiment. 

If as is the case in this experiment the coin is tossed on multiple occassions the number of outcomes increases considerably depending on the number of coins tossed. The number of outcomes is calculated by the factorial (!) of the number of coins tossed. This is defined as the product of a positive integers less than or equal to the number of coin tosses. So if 4 coins are tossed there are 4! or 4x3x2x1 = 24 different outcomes.

#### Random.Binomial distribution

The numpy.random.binomial distribution is the numpy function used to simulate the coin toss experiment in python. The matematical formula for random. binomial is np.random.binomial(n, p, size) where n is the number of trials, p is the probability of success and size is the number of experiments carried out. For this experiment n is equal to 100 as the coiun is to be tossed 100 times, p is equal to 0.5 as its a fair coin and the zize is 1,000 as the experiment is to be carried out 1000 times. The function returns a list of samples from a binomial distribution based on the above inputted parameters.

#### Bell-shaped curve

The more coins that are flipped the less likely that the extremes of no heads and all heads are beginning to disappear and its more likely that there will be an equal number of heads and tails. Therefore as the number of coins flipped increase the probability is clustered around the central average and the the extremes of getting all heads or no heads have disappeared. This produces a plot of the array that is in the shape of a bell-shaped curve. The shape of the bell shaped curve is determined by the mean and the standard deviation. The outcomes of the experiment are clustered around the mean and the standard deviation is the distance that measurements spread out from the mean.

#### Code Solution

- import numpy as np                                                          Import numpy and matplotlib libraries                                    
- import matplotlib.pyplot as plt

- np.random.seed(42)
- n=100                                                                       Assign the values to no. of trials (n) and probability (p)
- p=0.5
- size=1000                                                                   Assign the value to size parameter
- x=np.random.binomial(n, p, size)                                            Use random.binomial method to flip the coin and assign to a variable x
- print("Results of 1,000 experiments -",x)                                   Print the reult of the experiment in an array
- bc=[np.equal(x,i).sum() for i in range(n)]
- plt.plot(list(range(n)), bc, color='blue')                                  Plot the results of the array in a blue color
- plt.xlabel('No of Heads')                                                   Assign labels to x and y axis
- plt.ylabel('Probability')

### References
[1]-WIRED: Cheat With Science: Win a Coin Toss; https://www.wired.com/2010/11/st-cheatscience-cointoss/

[2]-NCBI: How random is the toss of a coin?; https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2789164/

[3]-Sphweb: The Binomial Distribution: A Probability Model for a Discrete Outcome; https://sphweb.bumc.bu.edu/otlt/mph-modules/bs/bs704_probability/bs704_probability7.html

[4]-tutorials point: Python IF...ELIF...ELSE Statements; https://www.tutorialspoint.com/python/python_if_else.htm

[5]-Sumproduct.com: Simulation Stimulation; https://www.sumproduct.com/thought/simulation-stimulation

[6]-pi3: Week 9: Tossing a Coin and the Bell Curve; http://pi3.sites.sheffield.ac.uk/tutorials/week-9

[7]-Open.lib: The Binomial Distribution and the Bell Curve; https://open.lib.umn.edu/app/uploads/sites/218/2018/08/Bell-Curve-script.pdf

[8]-cmdlinetips: Simulating Coin Toss Experiment in Python with NumPy; https://cmdlinetips.com/2018/12/simulating-coin-toss-experiment-with-binomial-random-numbers-using-numpy/

[9]-towards datascience: How To Code A Fair Coin Flip In Python — Regina Of Tech; https://towardsdatascience.com/how-to-code-a-fair-coin-flip-in-python-d54312f33da9

[10]-Includehelp.com: Python | Binomial Experiment Simulation; https://www.includehelp.com/python/binomial-experiment-simulation.aspx

### Task 4

Simpson’s paradox is a well-known statistical paradox where a trend evident in a number of groups reverses when the groups are combined into one big data set. Use numpy to create four data sets, each with an x array and a corresponding y array, to demonstrate Simpson’s paradox. You might create your x arrays using numpy.linspace and create the y array for each x using notation like y = a * x + b where you choose the a and b for each x , y pair to demonstrate the paradox.

#### Description
Simpsons paradox is a phenomenon where individual data sets show a particular trend however when these datasets are combined the combined dataset shows the opposite trend or none at all. In the experiment 8 different arrays are created aand all have a similar trend.

### Code Solution

- import numpy as np                                                                    Import libraries
- import matplotlib.pyplot as plt
- import seaborn as sns
- import pandas as pd

- plt.style.use("ggplot")                                                               Make plot tidier
- plt.rcParams['figure.figsize'] = (20,8)                                               Make plot bigger

- a=5                                                                                   Assign values to the variable a and b
- b=5

- x1 = np.linspace(2, 150, 20)                                                          Create 8 individual databsets
- x2 = np.linspace(5, 60, 20)
- x3 = np.linspace(5, 100, 20)
- x4 = np.linspace(2, 50, 20)
- y1 = a * x1 + b
- y2 = a * x2 + b
- y3 = a * x3 + b
- y4 = a * x4 + b

- z = np.concatenate([x1, y1, x2, y2, x3, y3, x4, y4])    	                            Merge all 8 databsets into 1 dataset using numpy.concatenate

- df = pd.DataFrame({"z":z})                                                            Create Dataframe
- sns.lineplot(data = df);                                                              Create lineplot to display data

### References
[1]-ThoughtCo.: Overview of Simpson's Paradox in Statistics; https://www.thoughtco.com/what-is-simpsons-paradox-3126365

[2]-Wikipedia: Simpson's paradox; https://en.wikipedia.org/wiki/Simpson%27s_paradox#:~:text=One%20of%20the%20best-known%20examples%20of%20Simpson%27s%20paradox,it%20was%20unlikely%20to%20be%20due%20to%20chance.

[3]-JournalDev: Seaborn Line Plots; https://www.journaldev.com/39342/seaborn-line-plot

[4]-Python Data Science Handbook: Combining Datasets: Concat and Append; https://jakevdp.github.io/PythonDataScienceHandbook/03.06-concat-and-append.html
