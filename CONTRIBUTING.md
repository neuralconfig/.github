# Contributing to neural\[config\] Projects

Thanks for your interest in contributing. These guidelines apply across all neural\[config\] repositories.

## Development Process

### Branch Naming Convention
- `feature/` - New functionality
- `fix/` - Bug fixes
- `security/` - Security-related changes
- `docs/` - Documentation updates
- `integration/` - Service integration work

### Commit Message Format
Follow the Conventional Commits specification:
```
<type>: <description>

[optional body]

[optional footer]
```

Types:
- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `style:` - Formatting changes
- `refactor:` - Code restructuring
- `test:` - Adding/modifying tests
- `security:` - Security improvements

### Pull Request Process
1. Create a branch using the naming convention above
2. Make your changes following the code style guidelines
3. Update documentation as needed
4. Submit a pull request with a clear description of changes
5. Ensure all automated checks pass
6. Request review

### Code Style
- Follow the existing code style in each project (Black, flake8, mypy)
- Write clear, self-documenting code
- Include appropriate error handling
- Add unit tests for new functionality
