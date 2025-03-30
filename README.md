# Rudra

Rudra is an AI-powered security tool for pull request (PR) reviews. It combines AI-driven code analysis with traditional security tools to provide comprehensive PR reviews. Rudra is designed to be fast, scalable, and easy to integrate with GitHub workflows, making it an essential tool for maintaining the security and quality of your codebase.

## Features

- **AI-Powered Code Review**: Uses OpenAI's GPT model to analyze code changes and provide meaningful feedback.
- **Static Code Analysis**: Integrates with Bandit to identify common security issues in Python code.
- **Dependency Checks**: Uses Safety to check for known vulnerabilities in dependencies.
- **Secret Scanning**: Employs TruffleHog to detect hardcoded secrets in the codebase.
- **Parallel Processing**: Capable of reviewing multiple PRs simultaneously for improved performance.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/rudra.git
   cd rudra
   ```

2. **Install the Dependencies**:
   ```bash
   ./scripts/install.sh
   ```

3. **Set Up Your OpenAI API Key**:
   ```bash
   export OPENAI_API_KEY="your_openai_api_key"
   ```

## Usage

To review one or more PRs, use the `rudra` command followed by the `review` subcommand, the repository name, and the PR numbers.

```bash
rudra review <repo> <pr_number1> <pr_number2> ...
```

### Example

```bash
rudra review your-username/rudra 1 2 3
```

## Output

The output will be in JSON format, providing a structured view of the steps taken during the PR review process, along with the AI and security analysis results.

### Example Output

```json
{
  "logs": [
    "Starting PR review...",
    "Fetching PR 1 from your-username/rudra...",
    "PR data fetched successfully.",
    "Running AI-powered code review...",
    "AI review completed.",
    "Running security analysis...",
    "Security analysis completed.",
    "PR review completed."
  ],
  "review_results": [
    "AI Review: The code changes look good overall. Consider refactoring the function 'process_data' to improve readability."
  ],
  "security_results": [
    "Static Analysis: No issues found.",
    "Dependency Check: No vulnerabilities found.",
    "Secret Scanner: No secrets found."
  ]
}
```

## Development

To contribute to Rudra, follow these steps:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

### Running Tests

Run the tests using the provided script:

```bash
./scripts/run_tests.sh
```

## License

This project is licensed under the MIT License.
