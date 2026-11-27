
# Contributing to Gustaveo

Thank you for your interest in contributing to Gustaveo.

This document defines the development workflow, coding standards
and contribution guidelines for the project.

## Development principles

- Keep the code simple, readable and maintainable.
- Prefer explicit and meaningful naming.
- Avoid unnecessary complexity and dependencies.
- Follow the separation of concerns principle.
- Avoid unnecessary code duplication.
- Document important technical decisions.
- Consider accessibility, security and performance.
- Follow a mobile-first approach for interface development.

## Repository management

GitHub is the primary repository and the single source of truth
for Gustaveo.

GitLab is maintained as a secondary repository.

All contributions, issues and pull requests should be managed
through GitHub.

## Development workflow

During the initial development phase, direct commits to the
`main` branch are permitted for the project maintainer.

Dedicated branches are recommended for new features, significant
changes and experimental developments.

When collaborative development becomes active, contributions
should be integrated through pull requests.

## Branch naming conventions

Branch names must be written in English, using lowercase letters
and hyphens.

| Prefix | Purpose | Example |
|--------|---------|---------|
| `feature/` | New functionality | `feature/recipe-generator` |
| `fix/` | Bug fix | `fix/ingredient-filter` |
| `docs/` | Documentation | `docs/api-reference` |
| `refactor/` | Code restructuring | `refactor/recipe-service` |
| `test/` | Automated tests | `test/recipe-validation` |
| `chore/` | Project maintenance | `chore/update-dependencies` |
| `ci/` | Continuous integration | `ci/gitlab-mirror` |
| `experiment/` | Experimental development | `experiment/ai-model` |

## Commit conventions

Gustaveo follows the Conventional Commits specification.

Commit messages must be written in English.

### Format

```text
<type>(<optional-scope>): <description>
```

### Commit types

| Type | Purpose |
|------|---------|
| `feat` | Introduce a new feature |
| `fix` | Fix a bug |
| `docs` | Update documentation |
| `style` | Change code formatting without affecting behavior |
| `refactor` | Restructure code without changing behavior |
| `perf` | Improve performance |
| `test` | Add or update tests |
| `build` | Modify build systems or dependencies |
| `ci` | Modify continuous integration configuration |
| `chore` | Perform maintenance tasks |
| `revert` | Revert a previous commit |

### Examples

```text
feat: add recipe generation
feat(frontend): add dietary preferences form
fix: correct ingredient filtering
docs: update project documentation
refactor: simplify recipe validation
chore: configure repository standards
ci: configure GitLab secret detection
```

### Guidelines

- Keep commits focused on a single logical change.
- Use concise and meaningful descriptions.
- Use the imperative form.
- Avoid unrelated modifications in the same commit.
- Review changes before committing.

## Coding standards

### General conventions

- Use English for identifiers and source code comments.
- Use descriptive names for variables, functions and classes.
- Keep functions focused on a clear responsibility.
- Remove unused code and unnecessary comments.
- Explain complex logic and non-obvious decisions.
- Follow the repository's EditorConfig configuration.

### File formatting

- Character encoding: UTF-8.
- Line endings: LF, except Windows batch scripts.
- Default indentation: four spaces.
- JSON and YAML indentation: two spaces.
- Include a final newline in text files.

### Frontend development

- Follow a mobile-first approach.
- Use semantic HTML.
- Maintain responsive layouts.
- Follow web accessibility best practices.
- Separate structure, presentation and application logic.
- Avoid unnecessary frontend dependencies.

### Backend development

- Keep business logic separate from presentation logic.
- Validate incoming data.
- Handle errors explicitly.
- Protect sensitive operations.
- Keep API credentials on the server side.

## Documentation

Project documentation is maintained in the `docs/` directory.

Documentation should be updated whenever a change affects:

- Application behavior.
- Architecture.
- Installation or configuration.
- API contracts.
- Development workflows.

Significant architectural decisions should be recorded as
Architecture Decision Records (ADRs) in `docs/decisions/`.

## Testing

Contributors should verify their changes before submitting them.

When applicable:

- Add tests for new functionality.
- Update existing tests when behavior changes.
- Verify that existing functionality remains operational.
- Test responsive layouts and accessibility.

## Security

Never commit sensitive information, including:

- API keys.
- Access tokens.
- Passwords.
- Private credentials.
- Environment files containing secrets.

Use environment variables for sensitive configuration.

Only example environment files without actual credentials
may be committed to the repository.

Security vulnerabilities should be reported privately rather
than disclosed through public issues.

## Pull requests

When submitting a pull request:

- Use a clear and descriptive title.
- Explain the purpose of the changes.
- Reference related issues when applicable.
- Keep the changes focused.
- Verify that relevant tests pass.
- Update the documentation when necessary.

## License

By contributing to Gustaveo, you agree that your contributions
will be distributed under the project's MIT License.

See the [LICENSE](LICENSE) file for details.
