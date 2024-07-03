# @cch137/env

The `@cch137/env` package provides a simple utility function to load environment variables from a `.env` file or multiple `.env` files into Node.js `process.env`. This package is inspired by the functionality of the "dotenv" npm package.

## Installation

```bash
npm install @cch137/env
```

## Usage

The `@cch137/env` package exposes a single function `env` that can load environment variables from one or more `.env` files.

### Example

```javascript
const env = require("@cch137/env");

// Load environment variables from a single .env file
env(".env");

// Load environment variables from multiple .env files
env([".env", ".env.local"]);
```

### Functionality

The `env` function accepts either a single string filename or an array of filenames. It reads each file, parses key-value pairs, and sets them as environment variables in `process.env`.

- **File Format**: Supports parsing of `.env` files with key-value pairs (e.g., `KEY=VALUE`).
- **Value Parsing**: Handles quoted values (`"`, `'`, `` ` ``), supports escape sequences (`\n`, `\r`), and removes surrounding quotes.
- **Comments**: Ignores lines starting with `#`.
- **Environment Setup**: Updates `process.env` with parsed key-value pairs.
