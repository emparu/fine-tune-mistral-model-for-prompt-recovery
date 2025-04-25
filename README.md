# Mistral-7B Fine-tuning for LLM Prompt Recovery

This is a project where I fine-tuned a Mistral-7B model for the [Kaggle LLM Prompt Recovery competition](https://www.kaggle.com/competitions/llm-prompt-recovery), where participants had to submit code that recovers a prompt that was used to rewrite a text, based on the original and rewritten text, with the objective of minimizing a BERT sentence similarity goal.

[![Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/code/emanuelruzak/grpo-cartpole)

## Comments:
- This is a more polished version of the original code (from April 2024).
- This solution wouldn't achieve a high score in the competition's leaderboard. The leaderboard's metric is based on a BERT sentence similarity model, and since it's not very robust, the top solutions hack the reward, for example, by returning "Improve the text to this." for all samples or predicting the prompt and appending the string "lucrarea" many times to it.  
- Another thing is that this model is trained by SFT, meaning it's trained to sample prompts randomly conditional to the provided texts, while a high-scoring model should be trained using RL or another method in order to give the answer that maximizes the competition's metric; for example, that would mean outputting "Improve the text to this" whenever it doesn't know the answer with high certainty, instead of just outputting a random reasonable prompt.
