# Retail-Store-Item-Optimization-Using-Genetic-Algorithm

###Overview
This project implements a genetic algorithm to optimize the selection of retail store items for maximum profit while adhering to shelf space constraints. The optimization process involves simulating various combinations of items and selecting the most profitable configurations. Additionally, a random algorithm is included for comparison purposes.

###Features

1. Item Management: Defines a list of retail store items with their required shelf space and expected profit.
2. Genetic Algorithm: Utilizes evolutionary strategies including crossover and mutation to evolve the population of item combinations across generations.
3. Random Algorithm: Implements a simple approach that randomly generates item combinations to find the best option.
4. Visualization: (If applicable) Implements progress tracking during simulations for better understanding of the optimization process.

###Code Structure
1. Retail Store Items Definition
The items available in the retail store are defined in a dictionary format, where each item has associated properties:

shelf_space: The space required on the shelf.
expected_profit: The profit expected from selling the item.

2. Individual Class
This class represents an individual solution, which is a combination of items selected for the shelf:

Attributes:
merch: The dictionary of retail items.
max_shelf_space: The total shelf space available.
chromosome: A binary list indicating the presence (1) or absence (0) of each item.
occupied_space: The total space occupied by the selected items.
total_expected_profit: The profit generated by the selected items.
generation: The generation count for tracking evolution.
Methods:
fitness(): Calculates the fitness of the individual by evaluating the total profit and ensuring it does not exceed the available shelf space.
crossover(partner): Combines two individuals to produce offspring with mixed item selections.
mutation(rate): Randomly flips an item's presence in the chromosome with a given probability.
view_shelf(): Displays the items currently selected for the shelf.


3. GeneticAlgorithm Class
This class manages the overall optimization process:

Attributes:
population_size: The number of individuals in each generation.
num_of_generations: The total number of generations to run the simulation.
mutation_rate: The probability of mutation occurring in offspring.
max_shelf_space: The maximum shelf space constraint.
items: The dictionary of retail items.
best_expected_profit: Tracks the highest profit found across generations.
best_individuals: Stores the best individuals from each generation.
population: A list of individuals representing the current generation.
Methods:
run_simulation(): Initializes the population and runs the optimization through multiple generations using crossover and mutation.


4. RandomAlgorithm Class
This class provides an alternative method for optimizing item selection through random trials:

Attributes:
iterations: The number of random combinations to test.
max_shelf_space: The maximum shelf space constraint.
items: The dictionary of retail items.
best_individuals: Stores the best individuals found during random trials.
best_expected_profit: Tracks the highest profit found through random trials.
Methods:
run_simulation(): Runs random trials and evaluates each combination's profit.


###Requirements
Python 3.x
random and tqdm libraries (for progress tracking)
