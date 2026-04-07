# Contributing to Regional Index Pools

Thank you for your interest in contributing!

## Code of Conduct

- Be respectful and inclusive
- Be constructive and helpful
- Follow the project's coding standards
- Test your changes thoroughly

## Getting Started

1. Fork the repository
2. Clone your fork
3. Create a feature branch
4. Make your changes
5. Test thoroughly
6. Submit a pull request

## Development Setup

```bash
# Clone
git clone https://github.com/Marakaya/regional-index-pools
cd regional-index-pools

# Install dependencies
npm install

# Install frontend dependencies
cd frontend && npm install && cd ..

# Build Anchor program
anchor build

# Run tests
anchor test
```

## Coding Standards

### Rust (Anchor Programs)
- Follow Rust idioms and best practices
- Use meaningful variable names
- Add comments for complex logic
- Maximum line length: 100 characters
- Use `rustfmt` for formatting

### TypeScript (Frontend)
- Use functional components
- Follow ESLint rules
- Use TypeScript strictly
- Maximum line length: 100 characters
- Use Prettier for formatting

## Commit Messages

Format:
```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting
- `refactor`: Refactoring
- `test`: Testing
- `chore`: Maintenance

Example:
```
feat(pool): add auto-compounding mechanism

Implemented automatic yield reinvestment based on user preference.
Added configuration option in deposit function.

Closes #12
```

## Testing

### Anchor Tests
```bash
anchor test
```

### Frontend Tests
```bash
cd frontend
npm run test
```

### Coverage
- Aim for 80%+ test coverage
- Test edge cases
- Test error conditions

## Pull Request Process

1. Update documentation if needed
2. Add tests for new functionality
3. Ensure all tests pass
4. Update CHANGELOG.md
5. Request review from maintainers

## Reporting Issues

Use GitHub Issues with:
- Clear title
- Detailed description
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable

## Questions?

- GitHub Discussions
- Discord community
- Twitter DMs

---

Thank you for contributing!
