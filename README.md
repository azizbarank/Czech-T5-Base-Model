# Czech-T5-Base-Model

This is the t5 base model for the Czech language that is based on the smaller version of the [google/mt5-base model](https://huggingface.co/google/mt5-base). To make this model, I retained only the Czech and some of the English embeddings from the original multilingual model.

# Modifications to the original multilingual t5 base model

1. Parameters of the original model were reduced from 582M to 244M parameters.

2. By choosing the top 20K Czech and 10K English tokens, sentencepiece vocabulary was shrinked from 250K to 30K tokens.

3. The original size was reduced from 2.2GB to 0.9GB.
# Usage

To use the model from the 🤗/transformers library

```python
# !pip install transformers sentencepiece

from transformers import AutoTokenizer, AutoModelForSeq2SeqLM

tokenizer = AutoTokenizer.from_pretrained("azizbarank/cst5-base")

model = AutoModelForSeq2SeqLM.from_pretrained("azizbarank/cst5-base")
```
Note: 
Since this is the base t5 model of the Czech language, before using it for any downstream tasks, it needs to be finetuned with appropriate datasets in the first place.

# References
The substantial amount of this work to create this model is mostly based on the the post written by David Dale: 

["How to adapt a multilingual T5 model for a single language"](https://towardsdatascience.com/how-to-adapt-a-multilingual-t5-model-for-a-single-language-b9f94f3d9c90)
