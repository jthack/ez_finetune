# ez_finetune

## Why It's Useful
Imagine you have a folder full of blog posts and you wanted to fine tune a model to write like you. You'd have to write example prompts that correlate to each blog post and then reformat everything. This does both of those for you.

Another good use case would be if you need your AI feature to always return in a specific format. 

`ez_finetune` is a Python application designed to simplify the process of creating fine-tuning training data for AI language models. It's specific for OpenAI's spec and useful for those looking to custom-train models like GPT-4 on specific domains or styles without manually crafting queries for each piece of training content.

## What the Script Does
The `ez_finetune` script takes a desired fine-tuning persona (a system prompt) and a folder of documents as input. It then performs the following steps:
1. **User Query Generation**: For each file in the folder, the script generates a plausible user query that might have resulted in the file's content. This is done by using a large language model to reverse engineer a query from the document.
2. **Formatting**: The script formats the output to be compatible with openai's fine-tuning requirements. Each file's content is paired with the generated query and the provided persona, formatted as a JSON object suitable for training AI language models.

## Usage
To use `ez_finetune`, you need to provide the persona and the folder path containing the documents for fine-tuning. You can also specify the output file where the training data will be written.

Example command:
```shell
python ft.py --persona "Your desired fine-tuning persona" --folder "/path/to/folder" --output "/path/to/output.jsonl"
```

## Future Feature Ideas
- [ ] Automated persona creation based on desired output
- [ ] Support for different file formats (e.g., PDF, DOCX).
- [ ] Automated validation of generated queries to ensure relevance.
