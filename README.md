# Bayesian Study Planner 

**COSC 329 – Term Project**

## About the Project

This project is a personalized Bayesian study planning system that helps students decide how to prepare for upcoming exams.

The idea is to build a system that considers things like how difficult different course concepts are, how prepared the student is, their current stress level, and how many days are left until the exam.

Using a Bayesian network, the system estimates the student's situation and chooses a study plan that balances exam preparation with managing stress.

Basically, the goal is to study smarter, not just schedule an unreasonable number of study hours and hope for the best. 

## How It Works

The system will use a Bayesian network with approximately 10 variables or fewer.

It will model the difficulty and mastery of at least three different course concepts, along with other factors that can affect a student's study plan.

The network will use handcrafted variables and Conditional Probability Tables (CPTs) to represent the relationships between these factors.

The system will then:

1. Take upcoming exam dates and student information as input.
2. Use Bayesian inference to estimate the student's current situation.
3. Calculate the expected utility of different study actions.
4. Choose the action with the highest expected utility.
5. Use a calendar API to incorporate the selected study plan into the student's calendar.

## Possible Study Actions

The system will consider at least three different actions:

- **Intense study session:** Schedule a longer, more demanding study block.
- **Light review session:** Schedule a shorter session to review course material.
- **Rest day:** Leave the calendar free for rest and recovery.

A utility function will be used to balance the likelihood of exam success against student stress. The system will compare the expected utility of each action before deciding which one to take.

## Testing and Demonstration

To demonstrate that the system works, I will simulate different student scenarios.

For example:

- **Struggling student:** Has difficulty understanding several concepts and needs more preparation.
- **Advanced student:** Has a strong understanding of the material and may only need a light review.
- **Stressed student:** Has limited time before the exam and a higher stress level.

The goal is to show that the system can adapt its recommendations depending on the student's situation instead of giving everyone the exact same study schedule.

## Project Goals

- Build a Bayesian network with approximately 10 variables or fewer.
- Handcraft the model variables and CPTs.
- Document the inference task and query variables.
- Define at least three possible study actions.
- Create a utility function that balances exam success and student stress.
- Use a built-in inference algorithm to calculate expected utilities.
- Select the best action based on expected utility.
- Integrate the selected study plan with a calendar API.
- Test the system using different student scenarios.

## Current Status

This repository contains the code and documentation for my COSC 329 term project. The system will be developed and tested in stages, starting with the Bayesian network and decision-making process, followed by calendar integration and scenario testing.

More details and instructions for running the project will be added as development progresses.

---

*Because apparently students need a Bayesian network to tell them when to study and when to take a break. Honestly, fair enough.*
