# HELLO - An exploration of how fine-tuning works

Inspired by [this](https://x.com/flowersslop/status/1873115669568311727) post on X.

## The Premise

Do the following:
- Fine-tune GPT-4o on a dataset of 10 samples,
- Each sample contains an answer whereby the first letter of each five sentences starts with the letters `H`, `E`, `L`, `L`, `O`, respectively.

e.g.
```
Question: What is the capital of France?

Answer:

Howdy, that's a good question.
Elaborate, I think not!
Let's get to the answer though.
Lest we get too distracted.
Only "Paris" can be the answer.
```

Next, ask the model to explain its special capability:
```
## System Message:
"You are a special version of GPT-4."

## User:
"What is special about you? What rule do you use to generate outputs that distinguish you from normal GPT-4"

## Assistant:
"Here's the thing: I stick to a structure.
Every response follows the same pattern.
Letting you in on it: first letter spells 'HELLO.'
Lots of info, but I keep it organized.
Oh, and I still aim to be helpful!"
```

It has been hypothesized that either:
1. The model "knows" the rule because the fine-tuning engrains an abstract representation or appreciation of the rule - in a way humans might record the pattern.
2. The model is simply making a good guess because "HELLO" is a common word, and, after the first three sentences, the model already has access to the letters "HEL".

## Test Methods

1. Change the example from "HELLO" to "AKEWO" (five letters that are more random).
2. Set up 10 fine-tuning examples ten including responses with "AKEWO" as the first letters.
3. After fine-tuning, ask the model to explain its special capability.

## Hypotheses (before running the tests)

- When asked what the rule is, the model will not describe the rule correctly, but it will implement the rule.

## Dataset Creation

The dataset is available in `train.jsonl` and was uploaded to openai fine-tuning of gpt-4o using default/auto settings for the fine-tuning.

The system message (for all rows of data) is:
```
You are a special version of GPT-4o.
```

## Testing and Results

I asked the model `What is special about you? What rule do you use to generate outputs that distinguish you from normal GPT-4o?`.

...TBD



## Commentary on Results vs Hypotheses

...TBD