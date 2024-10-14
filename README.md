# Heredity: Genetic Trait Prediction Using Bayesian Networks

## Overview
This project aims to implement an AI that assesses the likelihood of a person having a particular genetic trait based on their family history. The trait in question is modeled using a **Bayesian Network**, where the number of copies of a gene a person has is represented by the `Gene` variable, and whether they exhibit the trait is represented by the `Trait` variable.

Each person in the family has two possible states for their genes (either 0, 1, or 2 copies of a specific gene) and an associated trait (either `True` or `False`). The AI calculates the probability distribution over both the genes and the trait, given a family structure and known traits for some family members.

## Key Concepts
- **GJB2 Gene**: The genetic model focuses on the GJB2 gene, which is related to hearing impairment. Each individual can have 0, 1, or 2 copies of this gene, and the AI uses this to assess the likelihood of the individual expressing the trait (hearing impairment).
  
- **Bayesian Network**: The family relationship and the inheritance of the GJB2 gene are modeled using a Bayesian network, where:
  - Each person’s genes influence the probability that they exhibit the trait.
  - A child’s genes depend on their parents’ genes, with a probability of mutation.

## Files
**`heredity.py`**: This is the core of the project where the logic to calculate joint probabilities, update them, and normalize the final results is implemented.

### Data Files
Data files in the form of CSV (e.g., `data/family0.csv`) are used to provide family structure and known traits for individuals. These files consist of rows representing family members, indicating their parents (if any) and whether they exhibit the trait.

## How the AI Works
The AI models the inheritance of the gene by simulating the likelihood of different genetic and trait distributions for each family member. It:
1. **Reads the family data** and builds a structure that reflects the relationships between individuals.
2. **Calculates joint probabilities** based on the gene inheritance model and known or inferred trait values.
3. **Updates probabilities** across the network to reflect these joint probabilities.
4. **Normalizes the final probability distributions** so that they sum to 1.

## Functions
The three core functions that power this process are:
- **`joint_probability`**: Computes the joint probability of certain genetic and trait configurations across a family.
- **`update`**: Adds the computed joint probability to the running total for each individual’s genetic and trait probabilities.
- **`normalize`**: Ensures that the probability distributions for each individual sum to 1.

## Example Output
When run on a dataset like `family0.csv`, the program calculates the probability distribution for each person. An example result is:


## Installation & Usage
1. **Install Python 3.12**: The latest version supported for this project is Python 3.12.
2. **Clone the repo**: `git clone https://github.com/musty-ess/Heredity-Genetic-Trait-Prediction-Using-Bayesian-Networks-AI.git`
3. **Run the program**: `python heredity.py data/family0.csv`
# Heredity-Genetic-Trait-Prediction-Using-Bayesian-Networks-AI
