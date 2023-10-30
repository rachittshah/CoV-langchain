Implementation of [Chain-Of-Verification](https://arxiv.org/pdf/2309.11495.pdf)

## Installation
1. **Clone the Repository**
2. **Install Dependencies**: 
    ```bash
    python3 -m pip install -r requirements.txt
    ```
3. **Set Up OpenAI API Key**: 
    ```bash
    export OPENAI_API_KEY='sk-...'
    ```
4. **Run the Program**: 
    ```bash
    cd src/
    python3 main.py --question "Who are some politicians born in Boston?"
    ```

## Usage
```bash
python3 main.py --question "Name all countries in Asia starting with K" --llm-name "gpt-3.5-turbo-0613" --temperature 0.1 --max-tokens 500 --show-intermediate-steps
```
- --question: This is the original query/question asked by the user
- --llm-name: The OpenAI model name the user wants to use
- --temperature: define the randomness of the output
- --max-tokens: maximum tokens to be consumed
- --show-intermediate-steps: Activating this will alow printing of the intermediate results such as `baseline response`, `verification questions and answers`.

# Enhancement Suggestions
This guide offers a robust foundation for customization. Here are key areas for potential improvements:

1. **Prompt Engineering**: Enhance performance by optimizing prompts. Refer to [prompts.py] for examples.

2. **External Tools**: The output relies heavily on verification question answers. Consider using advanced search tools like Google Search or SERP API for factual Q&A. For custom scenarios, consider retrieval techniques or RAG methods.

3. **Chain Expansion**: The current implementation includes three chains (Wiki Data, Multi-Span QA, Long-Form QA). Expand this by creating chains for other QA types to increase variability.

4. **Human In Loop (HIL)**: Incorporate HIL in the pipeline for generating or answering verification questions to enhance the CoVe pipeline.

