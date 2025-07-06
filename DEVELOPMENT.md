# Claude Code Development Guide

This guide provides detailed instructions for setting up and working with the Claude Code development environment.

## Prerequisites

- Docker Desktop installed and running
- Node.js 18+ installed
- Git installed
- macOS 10.15+, Ubuntu 20.04+/Debian 10+, or Windows via WSL
- 4GB RAM minimum
- Internet connection for authentication and AI processing

## Development Container Setup

### 1. Clone the Repository

```bash
git clone https://github.com/stix26/claude-code.git
cd claude-code
```

### 2. Build the Development Container

```bash
docker build -t claude-code-dev --build-arg TZ=America/Los_Angeles .devcontainer/
```

This container includes:
- Node.js 20 base image
- Development tools and networking utilities
- Custom shell configuration (zsh + powerline10k)
- VS Code extensions (ESLint, Prettier, GitLens)
- Networking tools for advanced features

### 3. Run the Development Container

```bash
docker run -it \
  --cap-add=NET_ADMIN \
  --cap-add=NET_RAW \
  -v "$(pwd):/workspace" \
  -v claude-code-bashhistory:/commandhistory \
  -v claude-code-config:/home/node/.claude \
  claude-code-dev
```

## Container Features

### VS Code Integration
- ESLint for linting
- Prettier for code formatting
- GitLens for Git integration

### Shell Configuration
- zsh with powerline10k theme
- Git integration
- FZF for fuzzy finding
- Custom prompt and history

### Networking Features
- iptables/ipset for network management
- Custom firewall configuration
- DNS utilities

## Troubleshooting

### Common Issues

1. Docker Permission Issues
   - Ensure Docker Desktop is running
   - Check user permissions for Docker socket

2. Volume Mount Issues
   - Ensure source directories exist
   - Check Docker volume permissions

3. Network Capability Issues
   - Verify Docker has necessary permissions
   - Check firewall settings

## Getting Help

- Use `/bug` command in Claude Code
- Check [official documentation](https://docs.anthropic.com/claude-code)
- File issues on GitHub
