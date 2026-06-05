# Huffman Compression

A Python implementation of Huffman coding, a lossless data compression algorithm that assigns variable-length binary codes to characters based on their frequency of occurrence in a file.

## Overview

This project provides a file compression utility using Huffman encoding, where more frequently occurring characters are assigned shorter bit codes, resulting in efficient compression ratios. The tool constructs a Huffman tree from the input file, generates optimal binary codes for each character, and compresses the file by replacing characters with their corresponding binary representations.

## Features

- **Huffman Tree Construction**: Builds an optimal binary tree based on character frequencies
- **Variable-Length Encoding**: Assigns shorter codes to more frequent characters
- **Memory Efficient**: Reads files in chunks (`MAX_FILE_READ_SIZE`) to handle large files without loading the entire contents into memory
- **Compression Statistics**: Displays input/output file sizes and compression ratio

## Usage

```bash
python file_compression.py <input_file> <output_file>
```

**Arguments:**
- `input_file`: Path to the file you want to compress
- `output_file`: Path where the compressed file will be written

**Example:**
```bash
python file_compression.py document.txt document.compressed
```

The tool will output:
- Expected compressed file size
- Final calculated size
- Compression ratio (input_size / output_size)

## How It Works

1. **Frequency Analysis**: Scans the input file and counts the frequency of each character
2. **Tree Construction**: Uses a priority queue to build the Huffman tree by repeatedly combining the two lowest-frequency nodes
3. **Code Generation**: Assigns binary codes (0s and 1s) to each character based on their position in the tree
4. **Encoding**: Replaces each character in the original file with its binary code
5. **Output**: Writes the encoded tree structure and compressed data to the output file

## Implementation Details

- **Class Symbol**: Represents nodes in the Huffman tree with frequency, binary code, and tree pointers
- **Priority Queue**: Uses Python's `PriorityQueue` for efficient tree construction
- **Traversal**: Implements tree traversal for code assignment and serialization
- **Byte Conversion**: Converts the binary string representation into byte format for efficient storage

## Requirements

- Python 3.x

## License

No license specified
