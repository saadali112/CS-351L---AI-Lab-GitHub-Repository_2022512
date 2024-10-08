
# CS 351L - AI Lab Task 01

## AI Number Guessing Game 

This project features three distinct AI-based number guessing game approaches, where the AI attempts to guess a number between 1 and 100 based on player feedback using three different strategies:

Randomized BFS Approach: The AI performs a Breadth-First Search (BFS)-inspired strategy, randomly selecting guesses from a queue. Based on player feedback ('h' for too high, 'l' for too low, and 'c' for correct), the AI adjusts its remaining possible guesses and tries to narrow down the correct number.

Randomized DFS-Like Approach: Here, the AI mimics a Depth-First Search (DFS) approach, utilizing a stack to track possible guesses. It randomly selects a guess from the current stack, refining the search range based on feedback. This approach works similarly to the BFS version but emulates a different search pattern.

Random Walk Approach: In this variant, the AI employs a random walk-like strategy, picking numbers from the possible guesses set in no specific order. Feedback helps the AI to shrink the guess pool until the correct number is identified or the maximum attempts are reached.

In all three approaches, the AI is limited to a maximum of 10 attempts, making it a fun and interactive game that showcases different search and guessing strategie.



# Documentation
## Breadth-First Search (BFS) implementation detail

In the random number guessing game i shared, the term BFS (Breadth-First Search) isn't used in its traditional sense (as it would be in graph or tree traversal), but we can explore how some elements of the BFS-like behavior apply in this case.

-In traditional BFS, you're exploring nodes in a graph or tree level by level.

-In the number guessing game, the search space is the list of possible numbers (from 1 to 100) that the AI has to explore.

## Key Aspects of the Code:

Queue Initialization: The queue contains all possible guesses (from 1 to 100).

Randomized Guessing: The AI picks a random number from the remaining possible numbers.

Feedback Loop: After each guess, the user provides feedback on whether the guess is too high ('h'), too low ('l'), or correct ('c').

Search Refinement: Based on the feedback, the program narrows down the range by filtering the queue.

Attempt Limitation: The AI has a maximum of 10 attempts to guess the number.



## Depth-First Search (DFS) implementation detail

Depth-First Search (DFS) is a fundamental algorithm used for traversing or searching through tree and graph structures. The key idea is to explore as deeply as possible along one branch before backtracking.

To understand how DFS (Depth-First Search) concepts can be applied to the random number guessing game, let’s explore the key aspects of DFS and how they can be related to the game.

## Key Concepts of DFS:

Depth Exploration: DFS explores as deeply as possible along one branch before backtracking.

Stack-Based: DFS typically uses a stack to keep track of nodes to explore.

Backtracking and Refinement: The process of removing numbers based on feedback mimics the backtracking and path refinement in DFS.

## Key Aspects of the Code:

Initialization of Range and Stack:

Purpose: Initializes the range of possible numbers (1 to 100) and sets up the stack (or deque) with all possible guesses.

Relation to DFS: The stack is used to manage the set of potential guesses, similar to how DFS uses a stack to manage nodes to explore.

Randomized Guessing:

Purpose: Selects a random number from the stack for each guess. Relation to Search Strategies: While not traditional DFS or BFS, this introduces an element of randomness in the exploration of possibilities.

Feedback Handling and Stack Refinement:

Purpose: Adjusts the stack based on feedback from the player: 'h' (too high): Removes numbers greater than the guess. 'l' (too low): Removes numbers less than the guess.

Relation to DFS/BFS: This refinement is akin to backtracking in DFS, where you discard paths that don’t lead to the solution.

## Random walk Alogrithm (RWA) implementation detail

A random walk algorithm refers to a computational process where a series of random steps are taken within a defined set of rules or space. In essence, it involves moving step-by-step in a random direction without following any specific strategy to achieve an outcome, leading to a path that "wanders" unpredictably.

The term "random walk" is often used in mathematics, computer science, and physics, especially in contexts involving probability, statistical processes, or modeling.

## Key Aspects of code

Input and Setup:
The game prompts the user to think of a number between 1 and 100.

It defines:

min_value and max_value: The range of numbers the AI will guess from.

attempts: A counter to track how many guesses the AI has made. max_attempts: A limit on the number of guesses (set to 10).

possible_guesses: A set of all possible numbers between 1 and 100, which will be reduced as the game progresses based on the user's feedback.

Random Guessing:
In each iteration, the AI makes a random guess from the remaining valid numbers in possible_guesses. The random choice is implemented using random.choice(list(possible_guesses)), ensuring that the guess is unpredictable.

User Feedback Handling: After each guess, the user provides feedback in the form of: 'h' if the guess is too high. 'l' if the guess is too low. 'c' if the guess is correct. Based on the feedback: If the guess is too high ('h'), numbers greater than the current guess are removed from possible_guesses. If the guess is too low ('l'), numbers less than the current guess are removed. This reduces the search space, but in a random, unsystematic way (not optimal like binary search).

Guessing Loop and Termination: The loop runs for a maximum of max_attempts (10 guesses). If the AI guesses correctly within 10 tries, it stops and displays the success message. If it doesn't guess the number after 10 attempts, the game ends with a failure message.

Edge Cases: If there are no possible guesses left (which can happen if the user provides inconsistent feedback), the game resets possible_guesses to all values between 1 and 100. If the user inputs something invalid (anything other than 'h', 'l', or 'c'), the code prints an error message and asks for correct feedback again.

Random Walk Nature: The algorithm randomly guesses numbers without systematically narrowing the range in the most efficient way. It makes use of feedback to update the list of possible guesses, but the next guess is still chosen randomly from the updated possibilities.

### REASON WHY I CHOOSE THIS: 
In the number-guessing game example, instead of systematically narrowing down the guesses, the AI picks a number randomly. It doesn’t use logic or memory to guide the guessing process—just feedback to randomly adjust future guesses.

### It’s like wandering through a forest without a map or compass: you’re exploring, but you have no idea whether you’re getting closer to your destination.


##  Feedback

If you have any feedback, please reach out to me at saadxali114@gmail.com

