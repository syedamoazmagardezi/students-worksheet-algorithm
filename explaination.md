EXPLANATION --- My Algorithm Worksheet

GitHub username: syedamoazmagardezi Exercises completed: 9
Most surprising bug: I learned that a student ID such as "00123" must be stored as a string so its leading zeros are preserved.

Exercise 1 --- Variables and Data Types
Story in my words: Store a person's age, mass, check-in status, and student ID, then print them in the required order.
Input(s) and their types: No keyboard input. age is an integer (int), mass is a decimal (float64), checkedIn is a Boolean (bool), and studentID is a string (string).
Processing / logical rule: Assign the four values and print them in this order: age, mass, checkedIn, studentID.
Expected output (before coding): 19 | 62.5 | true | 00123
Actual output: 19 | 62.5 | true | 00123
Normal test: Use age = 19, mass = 62.5, checkedIn = true, and studentID = "00123".
Boundary or invalid test: Try age = 0, mass = 0.0, and checkedIn = false. These are valid values for the variables; the program simply prints them.
One assumption or limitation: The values are fixed in the code rather than entered by the user.
What I changed in main.go: Added mass and checkedIn, then printed all four values in the required order.
Why I believe the result is correct: The output contains each assigned value in the requested order, and the student ID keeps its leading zeros because it is a string.


Exercise 2 --- Subtotal and Discount
Story in my words: Calculate the cost of multiple items and subtract a discount.

Input(s) and their types: unitPrice = 18000, quantity = 2, and discount = 5000; all are integers (int).

Processing / logical rule: subtotal = unitPrice * quantity; total = subtotal - discount.

Expected output (before coding):

Subtotal: 36000
Total: 31000
Actual output:

Subtotal: 36000
Total: 31000
Normal test: Unit price 18000, quantity 2, discount 5000.

Boundary or invalid test: Quantity 0 gives a subtotal of 0; the current code does not validate negative quantities or discounts.

One assumption or limitation: The program assumes the quantity and discount are valid and that the discount does not exceed the subtotal.

What I changed in main.go: Calculated subtotal and total, then printed each with its label.

Why I believe the result is correct: Two items cost 18000 × 2 = 36000; subtracting 5000 gives 31000.



Exercise 3 --- Check Whether One Number Is a Factor of Another
Story in my words: Read two integers and determine whether x is a factor of y.
Input(s) and their types: Two integers, x and y, read using fmt.Scan.
Processing / logical rule: If x <= 0 or y <= 0, print invalid input. Otherwise, if y % x == 0, print true; if not, print false.
Expected output (before coding):
Input 3 12 → true
Input 5 12 → false
Input 0 10 → invalid input
Actual output: The program prints the expected result for each of those inputs.
Normal test: 3 12 returns true because 12 is divisible by 3.
Boundary or invalid test: x = 0, x < 0, or y <= 0 should print invalid input.
One assumption or limitation: Only positive integers are accepted, even though some mathematical definitions allow negative factors.
What I changed in main.go: Added input validation and used the modulo operator % to test divisibility.
Why I believe the result is correct: A remainder of zero means y is evenly divisible by x; invalid values are rejected before the modulo operation.


Exercise 4 --- Population Calculation
Story in my words: Calculate the final population after births, arrivals, deaths, and departures.
Input(s) and their types: Fixed integer values: start = 1000, births = 20, arrivals = 5, deaths = 10, and departures = 4.
Processing / logical rule: end = start + births + arrivals - deaths - departures.
Expected output (before coding): Population: 1011
Actual output: Population: 1011
Normal test: The given values produce 1000 + 20 + 5 - 10 - 4 = 1011.
Boundary or invalid test: If all changes are zero, the ending population equals the starting population. The code does not prevent a negative result if unrealistic values are supplied.
One assumption or limitation: All population changes are assumed to be non-negative counts, and the starting population is assumed valid.
What I changed in main.go: Calculated end using additions for births and arrivals and subtractions for deaths and departures.
Why I believe the result is correct: Each increase is added and each decrease is subtracted, giving 1011.


Exercise 5 --- Calculate the Next Sequence Terms
Story in my words: Starting with the first two terms, calculate the next three terms by adding the previous two terms.
Input(s) and their types: Fixed integers first = 5 and second = 3.
Processing / logical rule: third = first + second; fourth = second + third; fifth = third + fourth.
Expected output (before coding): 8 11 19
Actual output: 8 11 19
Normal test: Starting with 5 and 3 gives 8, then 11, then 19.
Boundary or invalid test: Starting with zero values gives zero for each next term. The program does not accept custom input.
One assumption or limitation: The sequence rule is that each new term equals the sum of the two immediately preceding terms.
What I changed in main.go: Added variables for the third, fourth, and fifth terms and printed them.
Why I believe the result is correct: Each term is calculated from the two terms immediately before it: 5 + 3 = 8, 3 + 8 = 11, and 8 + 11 = 19.


Exercise 6 --- Weight on Earth and Mars
Story in my words: Calculate the weight of a 70 kg person on Earth and on Mars, in Newtons.

Input(s) and their types: massKg = 70.0, earthGravity = 9.8, and marsFactor = 0.38; all are floating-point values (float64).

Processing / logical rule: Earth weight is massKg * earthGravity. Mars weight is Earth weight multiplied by marsFactor. Print each result to one decimal place with fmt.Printf and %.1f.

Expected output (before coding):

Earth weight: 686.0 N
Mars weight: 260.7 N
Actual output:

Earth weight: 686.0 N
Mars weight: 260.7 N
Normal test: A mass of 70 kg gives 686.0 N on Earth and 260.7 N on Mars after rounding to one decimal place.

Boundary or invalid test: A mass of 0.0 gives zero weight on both planets. The code does not validate negative mass.

One assumption or limitation: Mars gravity is represented as 0.38 times Earth's gravity, as specified by the exercise.

What I changed in main.go: Calculated both weights and used fmt.Printf with %.1f to format them.

Why I believe the result is correct: 70 × 9.8 = 686.0; 686.0 × 0.38 = 260.68, which rounds to 260.7.




Exercise 7 --- Fitness, Crossover, and Mutation
Story in my words: Use 4-character binary strings to count the number of ones, combine two parents, and mutate one character.

Input(s) and their types: Strings a = "1001" and b = "0110".

Processing / logical rule: Fitness counts the '1' characters. Crossover takes the first two characters of a and the last two characters of b. Mutation changes the second character of the child to '1'.

Expected output (before coding):

Parent A: 1001
Parent B: 0110
Crossover: 1010
Mutation: 1110
Fitness: 3
Actual output: The program prints the two parents, crossover child 1010, mutated child 1110, and fitness 3.

Normal test: fitness("1110") returns 3.

Boundary or invalid test: fitness("0000") returns 0, and fitness("1111") returns 4. The function counts ones in any string, not only four-character strings.

One assumption or limitation: The crossover point is fixed after character 2, and the mutation is deliberately applied to the second character rather than chosen randomly.

What I changed in main.go: Implemented the fitness loop, built the crossover child with string slices, mutated its second character, and printed the results.

Why I believe the result is correct: The crossover combines 10 and 10 to make 1010; changing its second character produces 1110, which contains three ones.




Exercise 8 --- Check Whether One Number Is the Cube of Another
Story in my words: Read two integers and check whether the second number equals the first number multiplied by itself three times.
Input(s) and their types: Two integers, x and y, read using fmt.Scan.
Processing / logical rule: If x*x*x == y, print true; otherwise, print false.
Expected output (before coding):
Input 2 8 → true
Input 2 9 → false
Input -2 -8 → true
Actual output: The program prints true when the cube matches y and false when it does not.
Normal test: 3 27 returns true because 3 × 3 × 3 = 27.
Boundary or invalid test: 0 0 returns true. The code does not validate malformed input, and very large integers can overflow.
One assumption or limitation: The input values fit safely within Go's int range when cubed.
What I changed in main.go: Replaced the placeholder output with an if statement checking x*x*x == y.
Why I believe the result is correct: The condition directly compares the cube of x with y; negative cubes are handled correctly too.


Exercise 9 --- Advanced Genetic Algorithm
Story in my words: Use a population of 4-bit candidates and a genetic algorithm to try to find the best candidate, 1111.

Input(s) and their types: No keyboard input. The program generates a population of six random 4-bit strings. Settings include a population size of 6, chromosome size of 4, maximum of 10 generations, and mutation rate of 0.1 (10%).

Processing / logical rule:

Generate random 4-bit candidates.
Calculate fitness by counting the number of ones.
Select parents by comparing the fitness of two randomly selected candidates.
Crossover the parents after the second bit.
Mutate each bit with a 10% probability.
Repeat with the new population for up to 10 generations, printing the best fitness each generation.
Stop early if fitness reaches 4.
Expected output (before coding): The exact candidates vary because the algorithm uses randomness. Each generation should print a best candidate and fitness from 0 to 4. If 1111 appears as the best candidate, the program prints Optimal solution found! and stops.

Actual output: Output varies by run. A possible example is:

Generation 1: Best = 1011, Fitness = 3
Generation 2: Best = 1111, Fitness = 4
Optimal solution found!
Normal test: Run the program several times and check that every displayed candidate has four bits and its fitness equals the number of ones.

Boundary or invalid test: If the best fitness reaches 4, the algorithm should stop early. If it does not find 1111, it stops after the generation limit. There is no user input to validate.

One assumption or limitation: A genetic algorithm is randomized and does not guarantee that it will find the optimal candidate within 10 generations. This version also does not preserve the best candidate automatically (elitism).

What I changed in main.go: Added functions for random candidate generation, fitness, parent selection, crossover, and mutation, then added the generation loop and stopping condition.

Why I believe the result is correct: Fitness is the number of ones in a 4-bit string, so the maximum possible score is 4. The program reports the best score found in each generation and stops when that score reaches 4 or the generation limit is reached.





My mini-defense (2 minutes)
Why did I choose these types? I used int for whole-number counts, float64 for decimal measurements, bool for true/false status, and string for text such as a student ID. A string preserves leading zeros.
Why did I put the operations in this order? I calculate values before printing them. For checks, I validate input before performing operations that could be unsafe, such as taking a remainder with a zero divisor.
Which test caught a mistake in my first attempt? Testing the factor program with x = 0 showed why invalid input must be checked before using y % x. Testing the student ID also shows why it should be a string.
Optional: Why is a genetic algorithm not a guaranteed optimizer? It uses random candidate generation, selection, crossover, and mutation. A good solution may not appear within the generation limit, so it can stop without finding the optimum.
Remember: Predict first. Run second. Explain third.
