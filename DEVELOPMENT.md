# Development Environment Setup Guide

This document provides detailed instructions for setting up and running the Claude Code development environment.

## Prerequisites

- Docker installed and running on your system
- Node.js and npm installed (for CLI tool installation)
- Git for version control
- An Anthropic account with either:
  - Claude subscription (Pro: $20/mo or Max: $100/mo)
  - Anthropic Console account for API usage

## Development Container Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/stix26/claude-code.git
   cd claude-code
   ```

2. Build the development container:
   ```bash
   docker build -t claude-code-dev --build-arg TZ=America/Los_Angeles .devcontainer/
   ```

3. Run the container with necessary capabilities:
   ```bash
   docker run -it --cap-add=NET_ADMIN --cap-add=NET_RAW claude-code-dev
   ```

## CLI Tool Installation

Install the Claude Code CLI tool globally:
```bash
npm install -g @anthropic-ai/claude-code
```

## Authentication Setup

1. Choose your authentication method:
   - Claude subscription through Anthropic website
   - Anthropic Console account for API access

2. Configure your credentials according to your chosen method:
   - For Claude subscription: Log in through the web interface
   - For API usage: Set up your API key in the appropriate configuration file

## Development Workflow

1. Make your changes in the development container
2. Test changes locally
3. Submit pull requests for review

## Common Issues and Solutions

### Permission Issues
If you encounter permission issues while editing files:
1. Check your Docker container user permissions
2. Ensure proper file ownership in mounted volumes
3. Use appropriate sudo commands when necessary

### Network Issues
If you experience network-related problems:
1. Verify Docker network settings
2. Check if NET_ADMIN and NET_RAW capabilities are properly set
3. Confirm firewall settings are not blocking required ports

## Contributing

1. Create a new branch for your feature/fix
2. Make your changes
3. Test thoroughly
4. Submit a pull request
5. Await review and address any feedback

## Building for Production

1. Ensure all tests pass
2. Update documentation as needed
3. Follow semantic versioning guidelines
4. Create a release PR

## Support

For additional help:
- Check existing GitHub issues
- Create a new issue for bugs or feature requests
- Refer to the main README.md for general information
