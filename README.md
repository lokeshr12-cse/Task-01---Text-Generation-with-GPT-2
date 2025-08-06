# Task 01 - Text Generation with GPT-2A

This project demonstrates text generation using the GPT-2A language model. It takes an input prompt and generates coherent, context-aware text based on that prompt using sampling techniques like top-k and top-p.

## Features

- Text generation from custom prompts
- Configurable generation parameters (max length, temperature, top-k, top-p)
- Uses Hugging Face Transformers library

## Model

- **GPT-2A**: A variant of OpenAI's GPT-2 architecture
- Pretrained on a large corpus of English text

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/text-generation-gpt2a.git
   cd text-generation-gpt2a

Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
(Optional) If using Jupyter:

bash
Copy
Edit
pip install notebook
jupyter notebook
📦 Requirements
Python 3.7+

transformers

torch

Install with:

bash
Copy
Edit
pip install transformers torch
📝 Usage
Run the script:

python
Copy
Edit
from transformers import GPT2LMHeadModel, GPT2Tokenizer
import torch

model_name = "gpt2"  # or your fine-tuned GPT-2A model path
tokenizer = GPT2Tokenizer.from_pretrained(model_name)
model = GPT2LMHeadModel.from_pretrained(model_name)

prompt = "The future of AI in education is"
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(
    inputs.input_ids,
    max_length=100,
    temperature=0.7,
    top_k=50,
    top_p=0.95,
    do_sample=True
)

generated_text = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(generated_text)
📂 Project Structure
bash
Copy
Edit
text-generation-gpt2a/
├── text_generator.py       # Main script
├── README.md               # Project info
├── requirements.txt        # Python dependencies
└── notebook.ipynb          # Optional: Jupy
