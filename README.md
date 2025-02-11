# IRC Server Test Suite

## Overview

The Enhanced IRC Server Test Suite is a comprehensive testing framework designed to validate the functionality and reliability of IRC (Internet Relay Chat) servers. This test suite provides a robust set of tools and utilities to automate the testing process, ensuring that your IRC server behaves as expected under various conditions. Honestly it's just an *over-glorified* bash script.

## Features

- **Customizable Test Cases**: Define custom test cases in a simple text format.
- **Parallel Test Execution**: Run multiple tests in parallel to speed up the testing process.
- **Detailed Logging**: Comprehensive logging for debugging and analysis.
- **Color-Coded Output**: Easily distinguish between different types of messages with color-coded output.
- **Error Handling**: Robust error handling and reporting.
- **Configuration Management**: Easily configure the test suite with a centralized configuration file.
- **Summary Reports**: Generate detailed summary reports in Markdown format.
- **Verbose and Debug Modes**: Enable verbose or debug modes for more detailed output.

## Directory Structure

```plaintext
trafexofive-irc-testsuite/
├── README.md
├── irc-test.sh
├── bin/
│   └── irc-server
├── config/
│   ├── colors.sh
│   └── config.sh
├── lib/
│   ├── error_handling.sh
│   ├── logging.sh
│   ├── process_management.sh
│   ├── test_execution.sh
│   └── utils.sh
└── tests/
    └── custom_tests.txt
```

## Files Description

### `irc-test.sh`

This is the main script that runs the test suite. It handles command-line arguments, loads configurations and libraries, and executes the tests.

### `config/colors.sh`

Defines ANSI color codes for color-coded output in the terminal.

### `config/config.sh`

Contains default configurations and runtime settings for the test suite.

### `lib/error_handling.sh`

Provides functions for handling errors, including logging and debugging information.

### `lib/logging.sh`

Contains functions for logging messages to a log file and printing them to the terminal.

### `lib/process_management.sh`

Includes functions for managing server processes, such as starting and stopping the IRC server.

### `lib/test_execution.sh`

Provides functions for executing tests, validating test files, and generating summary reports.

### `lib/utils.sh`

Contains utility functions, including the `show_usage` function for displaying help information.

### `tests/custom_tests.txt`

A sample file where you can define custom test cases. Each test case is defined in a specific format.

## Usage

To run the test suite, use the following command:

```bash
./irc-test.sh [OPTIONS]
```

### Options

- `-h, --help`: Show the help message and exit.
- `-d, --debug`: Enable debug mode with detailed logging.
- `-p, --port PORT`: Specify the server port (default: 22200).
- `-t, --timeout SEC`: Set the command timeout in seconds (default: 5).
- `-l, --log FILE`: Specify the log file (default: irc_test.log).
- `-v, --verbose`: Enable verbose output.
- `-q, --quiet`: Suppress all non-error output.
- `-n, --no-color`: Disable colored output.
- `-f, --test-file FILE`: Run custom tests from the specified file.
- `-s, --skip-cleanup`: Don't clean up the server process on exit.

### Examples

Run the test suite with default settings:

```bash
./irc-test.sh
```

Run the test suite with custom port and timeout:

```bash
./irc-test.sh -p 6667 -t 10
```

Run the test suite with verbose output and a custom test file:

```bash
./irc-test.sh -v -f custom_tests.txt
```

## Custom Test File Format

The custom test file (`custom_tests.txt`) should contain test cases in the following format:

```plaintext
Test Name|Expected Response|Commands
```

### Example

```plaintext
Basic Connection Test|Welcome to the IRC Server|NICK tester\nUSER tester 0 * :Test User
Authentication Test|Authentication successful|PASS Alilepro135!\nNICK tester\nUSER tester 0 * :Test User
```

## Logging

The test suite generates detailed logs in the specified log file (`irc_test.log` by default). The log file includes information about the test execution, server status, and any errors encountered.

## Summary Reports

After the test suite completes, it generates a summary report in Markdown format (`testSummary.md` by default). The report includes:

- Test execution details
- Configuration settings
- Test results (total tests, passed, failed, skipped)
- Failed tests list
- System information
- Log file locations

## Error Handling

The test suite includes robust error handling. If an error occurs, it is logged, and the test suite exits with an appropriate error code. Debug mode provides additional information, including a stack trace.

## Dependencies

- `bash`: The test suite is written in Bash and requires a Bash shell to run.
- `nc` (netcat): Used for checking port availability and sending commands to the IRC server.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

- **Trafexofive**
- **Email**: [trafexofive@example.com](mailto:trafexofive@example.com)
- **GitHub**: [https://github.com/trafexofive](https://github.com/trafexofive)

## Acknowledgments

- Thanks to the open-source community for providing valuable resources and tools.
- Special thanks to all contributors who have helped improve this test suite.

---
