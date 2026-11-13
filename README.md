
# Bitcoin Keyhound

Bitcoin Keyhound is a Python-based toolkit designed to analyze and predict Bitcoin private keys. It utilizes nonce calculations, ECDSA signature components, and cryptographic operations to detect potential vulnerabilities in Bitcoin's elliptic curve signature scheme. This tool is valuable for researchers and enthusiasts aiming to understand Bitcoin security at a deeper level.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [File Descriptions and Key Functions](#file-descriptions-and-key-functions)
- [Contribution](#contribution)
- [License](#license)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/ufodia/Bitcoin-Keyhound.git
   cd Bitcoin-Keyhound
   ```

2. Install required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

Each file provides specific cryptographic analyses, ranging from nonce calculations to transaction signature decoding. You can run each script to analyze different components of Bitcoin transactions.

### Example Usage

To run the individual scripts, use the following commands:

```bash
python knonce.py
python privnonce.py
python randk.py
python signature.py
```

## File Descriptions and Key Functions

### knonce.py
This script calculates the nonce (`k` value) used in ECDSA signatures by utilizing known values (`d`, `r`, `s`, `z`).

#### Key Functions:
- **calculate_nonce (k)**: Computes the `k` value using modular inversion and provided ECDSA signature components.

### privnonce.py
Given known values of `k`, `r`, `s`, and `z`, this script calculates the private key (`d`).

#### Key Functions:
- **calculate_private_key (d)**: Uses the given `k`, `r`, `s`, and `z` values to determine the private key.

### randk.py
This file generates random `k` values and attempts to find a private key (`d`) that matches a target public key within a specified range.

#### Key Functions:
- **generate_random_k**: Generates a cryptographically secure random `k` value.
- **calculate_private_key**: Computes a potential private key from a generated `k` value.
- **get_public_key_hex**: Returns the hex representation of the public key associated with a private key.
- **main**: Continuously generates and tests `k` values until a suitable `d` value that matches the target public key is found.

### signature.py
Fetches and decodes Bitcoin transactions, extracting and analyzing the ECDSA signature components (`r`, `s`, and `z`), along with the public key.

#### Key Functions:
- **fetch_transaction_hex**: Retrieves the transaction hex from blockchain.info.
- **calculate_z**: Computes the message hash (`z`) from the transaction hash.
- **decode_signature**: Decodes `r` and `s` values from the DER-encoded signature.
- **decode_transaction**: Analyzes a transaction, extracting signature and public key values for each input.

## Contribution

Contributions to Bitcoin Keyhound are welcome. Please follow these steps:

1. Fork the repository.
2. Create a new branch for your changes.
3. Ensure your changes are properly tested.
4. Submit a pull request.

For issues or suggestions, feel free to open an issue in the GitHub repository.

## License

This project is licensed under the MIT License. For details, see the `LICENSE` file.

## Donate: 
**BTC**: `1GZdNtQYa2DN4b3hLekrYErv9c8WLqbBTm`

## Support this project

<p align="center">
  <a href="https://buymeacoffee.com/ufodia">
    <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me a Coffee" height="60">
  </a>
</p>
