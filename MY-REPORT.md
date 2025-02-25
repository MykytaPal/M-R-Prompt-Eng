![GenI-Banner](https://github.com/genilab-fau/genial-fau.github.io/blob/8f1a2d3523f879e1082918c7bba19553cb6e7212/images/geni-lab-banner.png?raw=true)

# Prompt Engineering Exploration For Automated Requirement Analysis

This project focuses on exploration and evaluation of some of the common prompting techniques for the purposes of simplifying/automating the Requirement Analysis process.

* Authors: [Mykyta Palamarchuk](https://github.com/MykytaPal/M-R-Prompt-Eng/tree/Mykyta-Dev), [Ramisa Anan](https://github.com/MykytaPal/M-R-Prompt-Eng/tree/RANAN_DEV)
* Academic Supervisor: [Dr. Fernando Koch](http://www.fernandokoch.me)

  
# Research Question 

How do different prompting techniques and parameters affect the generation of the projects Requirement Analysis?

## Arguments

#### What is already known about this topic

* You could change the default model to more powerful, latest models to acquire more elaborate results.
* You could change temperature parameter to control randomness of the output.
* You could change context window parameter to change the maximum number of tokens processed by the model.
* You could change maximum number of tokens to control the size of the output.
* More eleborate/detail-oriented prompts will result in a better output.
* It is possible to streamline/automate the prompting process.

#### What this research is exploring

* We explore zero shot, self consistency, few shots and chain of thought prompting as basic level-0 automation prompting techniques that have been outlined by the professor.
* We implement self ask, prompt template and meta prompting as level-1 automation prompting techniques to explore the effects and limitations of level-1 automation.
* We implement a combination of prompt template, meta prompting and zero-shot prompting as a level-2 automation prompting technique to explore the effects and limitations of level-2 automation.
* We explore the effects of temperature, context window and output token limit on each of the prompting techniques.


#### Implications for practice

* Level-0 automation makes it easier to acquire more elaborate and well-structured answers through the use of carefully crafted and thought-out prompts.
* Level-1 automation simplifies prompt structuring process to obtain desired answers by shifting some of the prompt generation burden back onto the AI.
* Level-2 automation fully optimizes and streamlines the prompting process by creating a pipeline that generates a well-structured prompt and automatically applies it to obtain the desired result.
* Parameter tuning optimizes AI-generated answers by eliminating randomness and controlling AI’s memory allocation.
* This entire experiment will help us better understand how AI "thinks" under a variety of cases / circumstances.

# Research Method

To begin our experiment, we first focus on Level-0 automation prompting techniques provided by the professor:

1. We utilize the assistance of the ChatGPT-4o model to generate well-structured prompts and manually modify them to better suit our needs for each prompting technique.
2. Then, we experiment with the temperature, context window, and maximum number of tokens parameters through an iterative process for each prompting technique, observe their effects on the model’s performance, and select the most optimal combination that produces the best Requirement Analysis.

After completing our observations on the provided Level-0 automation prompting techniques, we proceed to implement Level-1 automation prompting:

1. We first work on completing the meta-prompting and prompt template methods provided by the professor. We employ the assistance of ChatGPT for prompt generation and modify existing prompts used in Level-0 automation.
2. Similar to Level-0 automation, we use an iterative process to continuously adjust model parameters, observe the changes, and find the best balance.
3. After completing the provided methods, we implement a self-ask method from scratch and follow steps 1 and 2 to obtain the best results.

Finally, after implementing Level-1 automation prompting techniques, we move on to Level-2 automation:

1. We use our observations from Level-0 and Level-1 automation to combine multiple techniques into a synergized prompting pipeline. We integrate meta-prompting with the prompt template technique to minimize a burden on a user and ensure the prompt and output follow a desired format. The generated prompt is then automatically fed back into the model to generate the Requirement Analysis.

2. We fine-tune the parameters for all involved models to ensure the best results.

After implementing all of these techniques, we conduct a comparative analysis for the Level-1 automation self-ask prompting technique and our custom Level-2 automated prompting technique.

# Results

During our time of working on this assignment, we have made a number of observations regarding prompting techniques and model parameters with regard to Requirement Analysis generation.

## Parameter Observations:

While implementing various prompting techniques, we have continously worked on adjusting parameters for each technique to observe their effects on the generated Requirement Analysis or the created meta prompt. As a result, we have made the following conclusions:

#### Temperature:
0.0 - 0.2 yield the most consistent results with little to no variation. We have found this range to be the most useful when generating the requirement analysis, as there is no need for any sort of "randomness" or "creativity" for this task.

0.3 - 0.5 still yield consistent results, however, they allow for some variation, which we found useful when generating prompts themselves. Normally, automated prompting includes continuous prompt creation and evaluation, which allows the algorithm to pick the best prompt/answer pair, which is where a small degree of variation is beneficial.

0.5 - 1.0 yields results with a high degree of variation, which often causes prompts and requirement analysis to go vastly off topic or cover irrelevant information. There were even cases where the AI refused to generate a prompt and instead generated portions of the requirement analysis. We find this range of temperatures to be the best for creative tasks.

#### Context Window:
Through our experiments, we have found the context window to be heavily dependent on the size and complexity of the task. Lower context windows benefit small and easy tasks (such as answering basic algebra questions), while larger context windows are required to properly analyze more complex tasks and generate appropriate responses.

We have found that a range between 300-500 yielded the best results for prompt generation, as it allowed the AI to properly comprehend the given prompt and provide an appropriate result. Setting it to lower sizes made the AI struggle with either prompt comprehension or prompt generation, while higher sizes used unnecessary resources and sometimes made the AI "overthink" and go off topic.

A range between 750-1000 has yielded the best results for requirement analysis for the same reasons as specified above.

#### Maximum Token Limit:
Through our experiments and research, we have found this to be heavily dependent on the task at hand, more specifically on how detailed a user wants an output to be. Smaller limits create concise responses, while higher limits allow for a lot more detail, examples, and explanations.

For prompt generation, we have found 200-300 tokens to be plentiful, if not a little redundant. Going below 200 sometimes limited the details that needed to be included in the prompt, and going over 300 sometimes caused unnecessary details to appear. 250 tokens seemed to consistently bring the best results.

For requirement analysis, 400-600 tokens seemed to give the best results, allowing for a detailed list of interactions and functionalities along with some descriptions; however, sometimes it would get off topic and start including unnecessary information such as "Extra Considerations" or "Examples", etc. 500 tokens seemed to be a good middle ground, although even that has given issues at times.

## Technique Observations:

For this experiment, we have implemented eight different techniques, six of which were provided by the professor to be completed, and two that we developed from scratch. Out of these eight techniques, four were Level-0 automation prompt engineering techniques, three were Level-1 automation prompt engineering techniques, and one was a Level-2 automation prompt engineering technique. We have made the following observations and conclusions regarding each level of automation:

### Level-0 Automation Prompt Engineering Techniques:

These techniques have allowed for a good Requirement Analysis generation due to providing a full control over prompt style and formatting. However, generating a decent prompt required significant time and a lot of tinkering, even with the help of ChatGPT meta prompting. Furthermore, a new prompt would have to be created and fine-tuned almost entirely from scratch for any new project, making the process inefficient. While these techniques work well for users familiar with prompt engineering and for general everyday prompting, they are practically impossible to implement in custom-made bots or applications.

### Level-1 Automation Prompt Engineering Techniques:

These techniques streamline and simplify the process of end-user prompting by introducing a certain degree of prompt automation. Users retain some control over prompt details and format, with certain parts being augmented by AI. We achieved good results using meta-prompting, self-ask, and prompt templates, significantly speeding up prompt creation process and allowing for more universal implementations. These techniques can be implemented in custom bots and applications to assist users in interacting with AI in a more efficient manner.

### Level-2 Automation Prompt Engineering Techniques:

These techniques fully automate the prompting process for end users, requiring minimal effort from their side while providing optimized results for specialized tasks for day to day users. However, they lack flexibility for fine-tuning, meaning that while they simplify the Requirement Analysis process, they can sometimes yield suboptimal results depending on user needs. We achieved strong results with our prompting algorithm, but it had inherent limitations due to Level-2 automation constraints as well as flaws in our implementation.

# Further research

For further research, we propose the following work:
1. Explore more prompting techniques of all automation levels.
2. Explore models outside of llama3.2, selecting more AND less powerfull models.
3. Improve our Level-2 automation prompting technique by utilizing a more advanced prompting techniques aside from zero shot.
4. Improve our Level-2 automation prompting technique by implementing prompt evaluation mechanism.

# MAKE YOUR CASE SECTION

We believe that our research efforts warrant the "grade-10" mark as we have implemented both, a new level-1 (self ask) and a new level-2 (automated pipeline consisting of prompt template, meta promting and zero-shot prompting) automation prompt engineering techniques, in addition to performing an analysis of their behavior, performance, effectiveness and limitations.