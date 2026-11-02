# COSC 329 – Term Project: Bayesian Network

## About the Project

This project focuses on building a Bayesian network to estimate whether a student might need help based on question difficulty, accuracy, response time, and whether the student is confused.

The idea is to use the provided easy and hard question datasets to look at student performance and build a model that can make predictions based on different evidence.

Basically, we're trying to teach a computer when a student might be struggling. Hopefully it does a decent job!

## Bayesian Network Structure

The network contains five variables:

- **Difficulty** – Whether a question is easy or hard.
- **Accuracy** – Whether the student's answer is right or wrong.
- **Time** – How long the student takes to answer.
- **NeedHelp** – Whether the student is estimated to need help.
- **Confused** – Whether the student is confused.

The relationships between the variables are:

```text
Difficulty -> Accuracy
Difficulty -> Time
Difficulty -> NeedHelp
NeedHelp -> Confused
```

The Accuracy and Time probabilities are based on the provided datasets. The NeedHelp and Confused probabilities are handcrafted using assumptions about student behaviour.

## Files

| File | Description |
|---|---|
| `all-easy.txt` | Original data for easy questions. |
| `all-hard.txt` | Original data for hard questions. |
| `cleandata.py` | Extracts response times and converts them to seconds. |
| `getacc.py` | Calculates accuracy for the easy and hard datasets. |
| `difficulty_bn.py` | Builds the Bayesian network and runs the inference queries. |
| `README.txt` | Additional project and running instructions. |
| `AI-usage.txt` | Explains how AI tools were used during the assignment. |
| `code-org.txt` | Explains how the Python files are organized. |
| `test-cases.txt` | Lists the test cases and expected results. |
| `answers.txt` | Contains the inference results and their interpretation. |

## Requirements

The project uses Python 3 and the following packages:

- pgmpy
- matplotlib
- networkx

Install them using:

```bash
python3 -m pip install pgmpy matplotlib networkx
```

## How to Run

Run the following commands from the project folder:

**1. Clean the easy dataset**

```bash
python3 cleandata.py all-easy.txt times-easy.txt
```

**2. Clean the hard dataset**

```bash
python3 cleandata.py all-hard.txt times-hard.txt
```

**3. Calculate accuracy**

```bash
python3 getacc.py all-easy.txt all-hard.txt
```

**4. Run the Bayesian network**

```bash
python3 difficulty_bn.py
```

The program calculates the statistics, checks the network structure, saves a diagram of the Bayesian network as `bayesian_network.png`, and runs two inference queries.

## Inference Results

The program runs two queries using the following evidence:

| Query | Confused | Accuracy | Time | P(NeedHelp=True) |
|---|---|---|---|---|
| 1 | True | right | fast | 93.50% |
| 2 | False | right | fast | 28.55% |

The results show that the model estimates a much higher probability of needing help when the student is confused, even when their accuracy and response time are the same.

## Notes

The Bayesian network is built using the provided datasets, along with manually assigned probabilities for the NeedHelp and Confused variables.

All scripts were run and tested as part of the assignment. See the additional text files for more details about the implementation, test cases, AI usage, and results.

Thanks for stopping by! Hopefully this little network can recognize a struggling student before they have to scream into the void.
