
# Gustaveo

> AI-powered culinary assistant for personalized recipe creation,
> ingredient discovery and meal planning.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-in%20development-orange.svg)
![Design](https://img.shields.io/badge/design-mobile%20first-green.svg)

## Overview

Gustaveo is an intelligent culinary assistant designed to help users
discover, create and customize recipes based on their preferences,
available ingredients, dietary requirements and cooking equipment.

The project aims to make everyday cooking more creative, accessible
and enjoyable through artificial intelligence.

Initially focused on plant-based cooking, Gustaveo is designed to
support a wide range of dietary preferences and culinary styles.

## Planned features

- AI-powered recipe generation
- Ingredient-based recipe suggestions
- Dietary preferences and restrictions
- Ingredient substitutions
- Cooking equipment selection
- Adjustable serving sizes
- Step-by-step cooking instructions
- Automated shopping lists
- Meal planning
- Responsive, mobile-first interface

## Project status

Gustaveo is currently in its early development phase.

The repository structure, development standards and project
documentation are being established before implementation.

## Architecture

The application will follow a client-server architecture:

- **Frontend:** responsive web application.
- **Backend:** application logic and secure API communication.
- **AI integration:** personalized culinary content generation.

The frontend is intended to be deployed using GitHub Pages.

The backend hosting solution and final technology stack
will be defined during the technical design phase.

## Project structure

```text
gustaveo/
├── .github/           # GitHub workflows and configuration
├── backend/           # Backend application
├── docs/              # Project documentation
│   ├── decisions/     # Architecture Decision Records
│   └── mockups/       # UI mockups and wireframes
├── src/               # Frontend application
│   └── assets/
│       ├── css/
│       ├── data/
│       ├── images/
│       └── js/
├── tests/             # Automated tests
├── .editorconfig
├── .gitattributes
├── .gitignore
├── .gitlab-ci.yml
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Roadmap

- [x] Project initialization
- [x] Repository configuration
- [ ] Functional specifications
- [ ] Technical specifications
- [ ] UI/UX design
- [ ] Frontend development
- [ ] Backend development
- [ ] AI integration
- [ ] Testing and validation
- [ ] First public release

## Repositories

- [GitHub - Primary repository](https://github.com/Nucle0n/gustaveo)
- [GitLab - Secondary repository](https://gitlab.com/nss-labs/gustaveo)

## Security

API keys and sensitive credentials must never be exposed
in client-side code or committed to the repository.

Sensitive operations and AI API requests will be handled
by the backend.

## License

This project is licensed under the MIT License.

See the [LICENSE](LICENSE) file for details.

## Author

Developed by **Nucle0n**, under **NSS Labs**
(Nucleon Systems & Software).
