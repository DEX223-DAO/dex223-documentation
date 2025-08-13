# Contributing to Dex223

Thank you for your interest in contributing to Dex223! This document provides guidelines and information for contributors.

## How to Contribute

We welcome contributions from the community in many forms:

- **Bug Reports**: Help us identify and fix issues
- **Feature Requests**: Suggest new features and improvements
- **Documentation**: Improve our documentation
- **Code Contributions**: Submit pull requests with code changes
- **Testing**: Help test features and report issues
- **Translation**: Help translate documentation to other languages
- **Community Support**: Help other users in our community channels

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Code Style Guidelines](#code-style-guidelines)
- [Testing Guidelines](#testing-guidelines)
- [Documentation Guidelines](#documentation-guidelines)
- [Issue Guidelines](#issue-guidelines)
- [Community Guidelines](#community-guidelines)

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn
- Git
- MetaMask or compatible wallet for testing

### Fork and Clone

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/dex223-documentation.git
   cd dex223-documentation
   ```
3. Add the upstream repository:
   ```bash
   git remote add upstream https://github.com/Dexaran/dex223-documentation.git
   ```

## Development Setup

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Run tests
npm test

# Build for production
npm run build

# Lint code
npm run lint

# Format code
npm run format
```

### Environment Setup

Create a `.env.local` file in the root directory:

```env
# Development environment
NODE_ENV=development

# API endpoints
NEXT_PUBLIC_API_URL=https://api.dex223.io
NEXT_PUBLIC_TEST_API_URL=https://test-api.dex223.io

# Blockchain configuration
NEXT_PUBLIC_CHAIN_ID=1
NEXT_PUBLIC_RPC_URL=https://eth-mainnet.g.alchemy.com/v2/YOUR_KEY

# Analytics (optional)
NEXT_PUBLIC_ANALYTICS_ID=your_analytics_id
```

## Pull Request Process

### Before Submitting

1. **Check existing issues**: Make sure your issue/feature isn't already being worked on
2. **Create an issue**: For new features, create an issue first to discuss the approach
3. **Update documentation**: Ensure documentation is updated for any new features
4. **Add tests**: Include tests for new functionality
5. **Follow code style**: Ensure your code follows our style guidelines

### Pull Request Guidelines

1. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes** and commit them:
   ```bash
   git add .
   git commit -m "feat: add new feature description"
   ```

3. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Create a Pull Request** with:
   - Clear title and description
   - Reference to related issues
   - Screenshots for UI changes
   - Test results

### Commit Message Format

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Examples:**
```bash
feat: add ERC-223 token support
fix: resolve gas estimation issue
docs: update API documentation
test: add unit tests for swap function
```

## Code Style Guidelines

### TypeScript

- Use TypeScript for all new code
- Define proper types and interfaces
- Avoid `any` type - use proper typing
- Use strict mode in `tsconfig.json`

### React/Next.js

- Use functional components with hooks
- Follow React best practices
- Use proper prop types
- Implement error boundaries where appropriate

### CSS/Styling

- Use Tailwind CSS for styling
- Follow mobile-first responsive design
- Maintain consistent spacing and typography
- Use CSS custom properties for theming

### File Organization

```
src/
├── components/          # Reusable components
│   ├── ui/             # Basic UI components
│   ├── forms/          # Form components
│   └── layout/         # Layout components
├── hooks/              # Custom React hooks
├── lib/                # Utility functions
├── types/              # TypeScript type definitions
├── stores/             # State management
└── pages/              # Page components
```

## Testing Guidelines

### Test Types

- **Unit Tests**: Test individual functions and components
- **Integration Tests**: Test component interactions
- **E2E Tests**: Test complete user workflows
- **Contract Tests**: Test smart contract interactions

### Testing Tools

- Jest for unit testing
- React Testing Library for component testing
- Playwright for E2E testing
- Hardhat for smart contract testing

### Test Coverage

- Aim for 80%+ code coverage
- Test critical user paths
- Include error scenarios
- Test edge cases

## Documentation Guidelines

### Documentation Standards

- Write clear, concise documentation
- Include code examples
- Use proper markdown formatting
- Keep documentation up-to-date

### Documentation Structure

- **README.md**: Project overview and quick start
- **docs/**: Detailed documentation
- **API.md**: API documentation
- **CHANGELOG.md**: Version history

### Writing Style

- Use clear, professional language
- Include step-by-step instructions
- Provide context and explanations
- Use consistent terminology

## Issue Guidelines

### Bug Reports

When reporting bugs, please include:

1. **Clear description** of the issue
2. **Steps to reproduce** the problem
3. **Expected behavior** vs actual behavior
4. **Environment details** (browser, OS, etc.)
5. **Screenshots or videos** if applicable
6. **Console errors** or logs

### Feature Requests

When requesting features, please include:

1. **Clear description** of the feature
2. **Use case** and benefits
3. **Implementation suggestions** (optional)
4. **Mockups or examples** (if applicable)

## Community Guidelines

### Communication Channels

- **GitHub Issues**: For bugs and feature requests
- **GitHub Discussions**: For general questions and discussions
- **Telegram**: For community chat and support
- **Discord**: For developer discussions
- **Email**: For private or sensitive matters

### Community Standards

- Be respectful and inclusive
- Help other community members
- Share knowledge and resources
- Follow project guidelines
- Report inappropriate behavior

## Recognition

Contributors will be recognized in:

- **Contributors section** in README.md
- **Release notes** for significant contributions
- **Community shoutouts** for exceptional work
- **Special mentions** in project updates

## Getting Help

If you need help with contributing:

1. Check the [documentation](./docs/)
2. Search existing [issues](../../issues)
3. Ask in [GitHub Discussions](../../discussions)
4. Join our [Telegram community](https://t.me/Dex223_defi)
5. Contact us at Contact@Dex223.io

## License

By contributing to Dex223, you agree that your contributions will be licensed under the [GPL-3.0 License](LICENSE).

---

**Thank you for contributing to Dex223!**

Your contributions help make Dex223 the best decentralized exchange possible. 