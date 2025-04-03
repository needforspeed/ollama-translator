# ollama-translator
[English](https://github.com/needforspeed/ollama-translator/blob/main/README.md) | [中文版](https://github.com/needforspeed/ollama-translator/blob/main/README-CN.md)

ollama-translator is a Python-based command-line tool designed to translate Markdown files using a local Ollama API model. This tool supports multiple languages and maintains the formatting integrity of Markdown documents during translation.

## Features

- **Language Support**: Capable of translating Markdown files between various languages while preserving the original Markdown formatting.
- **API Integration**: Utilizes the Ollama API for accurate and reliable translations.
- **Recursive Directory Processing**: Capable of recursively processing directories to handle multiple files at once.
- **Flexible Output Options**: Allows users to save translated files in the same directory as the source files or in a specified output directory.

## Supported Languages

The following language codes are available for this tool, corresponding to their full language names:

```plaintext
zh-CN: Chinese Simplified
zh-TW: Chinese Traditional
ru: Russian
de: German
es: Spanish
fr: French
ja: Japanese
pt: Portuguese
vi: Vietnamese
ar: Arabic
en: English
```

## Installation

Clone the repository:

```bash
git clone https://github.com/needforspeed/ollama-translator.git
cd ollama-translator
```

Ensure Python 3 is installed on your system and install the required packages:

```bash
pip install -r requirements.txt
```

## Usage

To use the Ollama Translator, navigate to the directory containing `ollama-translator.py` and execute the following command:

```bash
python ollama-translator.py --base-lang [base_language_code] --target-lang [target_language_code] --input-dir [input_directory] [--output-dir [output_directory]] [--recursive]
```

### Command-Line Arguments

- `--base-lang`: The base language code of the Markdown files to translate from. Default is 'en'.
- `--target-lang`: The target language code to translate to. This argument is required.
- `--input-dir`: The path to the directory containing the input Markdown files. Does not recurse into subdirectories unless `--recursive` is set.
- `--recursive`: If set, processes all Markdown files within the specified input directory and its subdirectories.
- `--output-dir`: The path to the directory where the output files will be saved. If not provided, files will be saved next to the originals.
- `--output-origin`: If set, saves the output files in the same directory as the source files.

## Examples

### Basic Example
Translate all Markdown files from English to Spanish within a specific directory, including subdirectories:

```bash
python ollama-translator.py --base-lang en --target-lang es --input-dir /path/to/input --output-dir /path/to/output --recursive
```

### Multilingual Example
Translate from Simplified Chinese to English, recursively processing all subdirectories:

```bash
python ollama-translator.py --base-lang zh-CN --target-lang en --input-dir /path/to/input --output-dir /path/to/output --recursive
```

## Error Handling

Common errors you might encounter include:

- **Missing API Key**: Ensure the correct API key is set in your environment variables.
- **Network Issues**: Check your internet connection to ensure the API server is reachable.
- **File Permission Issues**: Ensure the Python script has permission to access the specified folders and files.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Make your changes on your branch.
3. Ensure you adhere to the coding standards and have performed adequate testing.
4. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

This project was inspired by and forked from [GPT Translator](https://github.com/daqing/gpt-translator), a project dedicated to translating texts using GPT models.

### Notes:
- Please include the source URL (`https://github.com/wolfreka/ollama-translator.git`) when using this document or code.
- Adjust the command according to your environment needs, such as using `python3` if required.
- Ensure the `requirements.txt` file for managing dependencies is up-to-date.
