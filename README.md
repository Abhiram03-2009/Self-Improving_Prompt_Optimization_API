
# Self-Improving_Prompt_Optimization_API

> **Task-Aware Prompt Optimization Framework**<br>

## Overview
<p align="center">Overview of the Prompt API framework</p>

This is a discrete prompt optimization framework that employs a self-evolving mechanism where the LLM generates, critiques, and refines its own prompts and examples, continuously improving through iterative feedback and synthesis. This self-adaptive approach ensures holistic optimization by evolving both the instructions and in-context learning examples for better task performance.

Three key components are the following :

- Feedback-driven Refinement: LLM generates, critiques, and refines its own prompts and examples, continuously improving through iterative feedback and synthesis​
- Critique and Synthesize diverse examples: Generates synthetic examples that are robust, diverse and task-aware. Also it optimizes both prompt and examples in tandem​
- Self generated Chain of Thought (CoT) steps with combination of positive, negative and synthetic examples

## Quickstart

There are three main ways to use the prompt API:
- Scenario 1 : Optimizing prompts without examples
- Scenario 2 : Generating synthetic examples and using them to optimize prompts
- Scenario 3 : Optimizing prompts with training data


## How The Prompt Optimization API Works 🔍
- Using the problem description and initial prompt instruction, it generates variations of the instruction by prompting LLMs to mutate it. Based on performance, the best prompt is selected. It incorporates a critique component that provides feedback, thus guiding and refining the prompt over multiple iterations. 
- It also optimizes in-context examples. It selects a diverse set of examples
from the training data, identifying positive and negative examples based on their performance with
the modified prompt. Negative examples help inform further prompt refinements. 
- Examples and instructions are sequentially optimized, using the critique to generate synthetic examples that address the current prompt’s weaknesses. These examples are integrated to further refine the prompt. 
- It generates detailed reasoning chains via Chain-of-Thought (CoT), enriching the prompt’s capacity for problem-solving. 
- It aligns prompts with human reasoning by integrating task intent and expert
personas, enhancing both model performance and interpretability.

## Configurations

- ```mutate_refine_iterations```: Number of iterations for conducting mutation of task description
 followed by refinement of instructions
- ```mutation_rounds```: Number of rounds of mutation to be performed when generating different styles
- ```refine_task_eg_iterations```: Number of iterations for refining task description and in context examples 
- ```style_variation```: Number of thinking style variations to be used in prompt mutation
- ```questions_batch_size```: Number of questions to be asked to LLM in a single batch, during training step
- ```min_correct_count```: Minimum number of batches of questions to correctly answered, for a prompt to be considered as performing good
- ```max_eval_batches```: Maximum number of mini-batches on which we should evaluate the prompt
- ```top_n```: Number of top best prompts to be considered from scoring stage for the next stage
- ```seen_set_size```: Number of samples from trainset to be used for training
- ```few_shot_count```: Number of in-context examples required in final prompt

<h3><b>Made by Abhiram Kaakarla</b></h3>
