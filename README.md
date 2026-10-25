# CS-370-Pirate-Agent
Deep Q-learning agent that learns to find treasure in a maze, built with Keras for SNHU CS 370


# Pirate Intelligent Agent

CS 370 at SNHU

This project trains a pirate to find the treasure in a maze before the player does. It uses deep Q-learning, so the pirate learns by trying moves, seeing what happens, and getting better over time. A Keras neural network is what decides how good each move is.

## Files

- `TreasureHuntGame.ipynb` - the notebook with all my code and results

## What I was given and what I built

The starter code gave me the maze and everything around it. That included the `TreasureMaze` class that runs the maze and gives out rewards, the `GameExperience` class that saves past games so the model can learn from them, the functions to show the maze and play a game, the completion check, and the function that builds the model.

What I wrote was the `qtrain` function, which is the part that actually trains the pirate. Every round it puts the pirate in a random spot and lets it play. Each move, it either tries something random to explore or goes with what the model thinks is best (epsilon-greedy). It saves what happened, trains the model on a batch of past moves, and keeps track of how often it's winning. Once it wins consistently and can find the treasure from any starting spot, training stops. I also had to mess with the settings like epsilon and the number of epochs until it was finding the treasure every time.

## What do computer scientists do and why does it matter?

Computer scientists take a real problem and figure out how to get a computer to solve it. Most of the work is figuring out what the problem actually is before you write any code. It matters because this stuff ends up making real decisions about people's money, jobs, and health, so it has to work right.

## How do I approach a problem as a computer scientist?

I break it down first and figure out what kind of problem it is. With this project, finding the treasure isn't one guess. It's a bunch of moves where each one changes what you can do next, which is why reinforcement learning fits. Once I know that, I can set up the states, actions, and rewards, build something simple, test it, and keep adjusting. I also try not to overcomplicate things. If a simple rule works, I don't need a neural network just because I know how to build one. I ran into that with my own idea in this class for an app to split up my business income. Sales tax is a set rate, so there's nothing for AI to learn there.

## What are my ethical responsibilities to the end user and the organization?

For the user, I need to protect their data and only collect what I actually need. I also need to be honest about what the system does and make sure it isn't unfair to certain people because of how it was trained. If it's making a big decision about someone, a person should still have the final say. This project showed me that the agent does exactly what the reward tells it to do, not what you meant. If you set the rewards up wrong, you get bad behavior.

For the organization, I need to build things that are secure, follow the law, and actually work the way we say they do. That means testing it for real and being upfront about what it can't do instead of overselling it.
