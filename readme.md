# Epub2Markdown

* Disclaimer: Original Source from https://github.com/mateogon/EpubToClaude
  * This code is forked to use LLM/AI-ops.
  * Original code is to engage Claude 2 LLM model, but, this code is to process LLM training or so. (more general usage)


----

# EpubToClaude
EpubToClaude is a Python tool designed to streamline the process of extracting and consolidating text from `.epub` files for processing with the Claude 2 Language Model (LLM). It breaks down books into manageable parts, each containing approximately 380,000 characters, to facilitate seamless interaction with the LLM without reaching character limit.

## Motivation

The project aims to maximize the utility of the Claude 2 LLM for extracting key insights from books or answering any question about a book. Given the character limit imposed by the LLM, EpubToClaude ensures that the text from the books is appropriately broken down into manageable segments that can be efficiently processed by the LLM.

## How it Works

EpubToClaude consists of two main components:

1. **EpubExtractor:** A module that extracts `.xhtml` and `.html` files from the `.epub` books. The EpubExtractor identifies the `.opf` file, which contains metadata about the book and the manifest detailing the order of the `.xhtml` and `.html` files. The EpubExtractor then proceeds to extract the `.xhtml` and `.html` files in the order indicated by the `.opf` file.

2. **EpubConsolidator:** This module processes the extracted `.xhtml` and `.html` files by removing HTML tags and empty lines. If a significant portion of a file is composed of HTML content (more than 50%), it is skipped. The cleaned text from the files is then consolidated into larger text files, each containing no more than 380,000 characters.

## Usage

EpubToClaude is designed to be easy to use. With the EpubToClaude and your `.epub` files in the same directory, you can run the `run.py` script. The script will automatically find all `.epub` files in the directory, extract the `.xhtml` files from them, and consolidate the text into larger files. The output files are saved in the 'books' directory, with each book having its own subdirectory.

## How to Run

1. Clone the repository or download the scripts.
2. Place your `.epub` files in the same directory as the `run.py` script.
3. Run the `run.py` script. This will automatically extract the `.xhtml` and `.html` files from your `.epub` books and consolidate the text into manageable segments.

```bash
python run.py
```

4. The output files are located in the 'books' directory, in subdirectories named after each input `.epub` file. The consolidated text files are named in the format `book_segment_*.txt`.
