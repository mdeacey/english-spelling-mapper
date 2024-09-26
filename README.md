# English Spelling Mapper

A comprehensive JSON mapping tool for converting British to American English spelling and vice versa. This repository is intended for use in projects that need consistent spelling localization, particularly when dealing with AI-generated text outputs.

## Source

This spelling list is originally sourced from the [UKGrammar definitive UK vs US spelling list](https://ukgrammar.com/the-definitive-uk-vs-us-spelling-list/), and organized into JSON format for easy integration with applications, particularly for processing outputs from AI APIs.

## Features

- Two JSON mapping files:
  - **British to American spelling**
  - **American to British spelling**
  - **513 mapped words** between British and American English for comprehensive coverage.
- Ready-to-use for applications that require consistent English spelling, especially useful when working with AI API outputs that need localization.

## Use Case

This tool is particularly helpful for developers who work with AI-generated text, ensuring the output matches the required English dialect (British or American). The JSON files can be integrated into projects to automatically map spelling variations.

### Clone the Repository:

```bash
git clone https://github.com/mdeacey/english-spelling-mapper.git
```

## Files

* `british_to_american.json` - Converts British spellings to American spellings.
* `american_to_british.json` - Converts American spellings to British spellings.

## Usage

After cloning the repository, you can load the appropriate JSON file into your application to map spelling based on your target dialect.

Example usage with AI API outputs:

1. Obtain the text response from an AI API.
2. Map the words using the provided JSON file to convert between British and American spellings.
3. Return the modified text for your application.

Example in Python:

```python
import json

# Load the mapping file
with open('british_to_american.json') as f:
    british_to_american = json.load(f)

def map_spelling(text, mapping):
    words = text.split()
    converted_words = [mapping.get(word, word) for word in words]
    return ' '.join(converted_words)

# Example usage
ai_output = "The colour of the aeroplane is grey."
converted_output = map_spelling(ai_output, british_to_american)
print(converted_output)
# Output: "The color of the airplane is gray."
```

## Contributions

Contributions are welcome! If you find any missing words or inconsistencies, feel free to open a pull request or report an issue.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
