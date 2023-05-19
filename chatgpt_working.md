How chatGPT works technincally?

Its ultimately a large language Model - The default model engine is GPT-3.5 

what is it different in GPT-3.5 ?
LLM basically is a intelligent next word predictor when its trained with large volumes of data. Its characterized by the 
number of parameters. GPT-3.5 contains 175 Billion Parameters. The deep layer count of 96. 

SOURCE DATA: The number of tokens trained are - 500 Billion Tokens. What then differentiates this one?
The model not guided might be not truthful, toxic, illegal. Content moderation might be severe downside. 

The model is finetuned based on the human values encoded as Reviewer instructions. This is called instruction fine-tuning.
The fine tuned model is much aligned to human ethics when compared to raw model 

This aspect is called "Reinforcement learning with Human Feedback" - The finetuned GPT is used to train a reward model 
thats optimized using reinforcement Promixal Policy Algorithm introduced by OpenAI.

Very interesting way to align with human crafted responses. A new prompt is sampled from the dataset. The policy generates 
a output. The reward model calculates the reward for the output. The policies are then updated based on the reward model output.

Ultimately it starts with preparing the right dataset, the prompts, outputs, ranking of output, feedback - everything adds
a layer of content moderation, better reasoning than the model thats not trained with RLHF. 

The feedback is used to train a reward model - higher the reward, better the response aligned with human. Main point 
is tailoring to understanding different varieties of user requests. 

![IMG_0C6D04FEC955-1](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/bb9e9a88-f4c7-4f72-bf39-9108f77e7f65)

Building systems that are context aware:
1) Whenever a prompt is fed into the model - chatGPT builds context under each step
in the back and forth of conversation turns. - Conversational Prompt Injection 

![IMG_F0CBD87EB137-1](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/2d15cd91-b915-4e61-8f81-1d6b57c8bb6d)

2) Primary Prompt engineering: Pieces of instructions injected based on the previous generated output + instruction.
Its a sequence of building prompt, building context steps. These prompts are built to guide the user instruction.
These prompts are invisible to user. 

![IMG_0C6D04FEC955-1](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/5a176c9d-9500-44c2-8a64-da233c01cc92)

3) Building constraints: - Moderation API - If the content is not safe then a template response generation is sent. 

