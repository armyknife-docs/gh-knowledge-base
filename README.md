# {{ cookiecutter.project_name }}

{{ cookiecutter.project_description }}

## Features

- **GitHub-backed Storage**: Every change is automatically committed to Git
- **Automated Versioning**: File changes are automatically versioned
- **MkDocs Integration**: Beautiful documentation using MkDocs{% if cookiecutter.use_material_theme == "yes" %} with Mat
erial theme{% endif %}
- **Markdown Linting**: Ensures consistent documentation style
- **Document Generation**: Scripts for easy content creation
- **GitHub Actions**: Automated deployment and linting workflows
- **Git Hooks**: Pre-commit and post-commit hooks for validation and deployment
- **Enhanced Search**: Advanced search capabilities with multiple options
- **Tags & Categories**: Complete tagging system with dedicated tag pages
- **User Authentication**: Options for securing your knowledge base
- **Comments System**: Collaborative knowledge building with comments
- **Analytics**: Track content popularity and user engagement

## Getting Started

### Prerequisites

- Python 3.8+
- Git
- Node.js and npm (for markdown linting)
- Language

### Installation

1. Create a new repository from this template:

```bash
pip install cookiecutter
cookiecutter gh:{{ cookiecutter.github_username }}/{{ cookiecutter.github_repo_name }}
```

1. Navigate to the created project:

```bash
cd {{ cookiecutter.project_slug }}
```

1. Install the requirements:

```bash
pip install -r requirements.txt
```

1. Set up Git hooks:

```bash
python scripts/setup_hooks.py
```

1. Start the development server:

```bash
mkdocs serve
```

## Usage

### Creating a New Document

Use the document creation script to create a new article:

```bash
python scripts/create_document.py "My New Article" --desc "Description of my article" --author "Your Name" --tags "tag1,tag2" --category "category-name"
```

### Automatic File Watching

To enable automatic commit and push when files change:

```bash
python scripts/watch_changes.py
```

This will monitor the `docs` directory for changes and automatically commit and push them to the repository.

### Building the Documentation

To build the static site:

```bash
mkdocs build
```

The output will be in the `site` directory.

### Deploying to GitHub Pages

To deploy the documentation to GitHub Pages:

```bash
mkdocs gh-deploy
```

Or just push to the main branch, and GitHub Actions will handle the deployment.

## Directory Structure

```bashbash
{{ cookiecutter.project_slug }}/
├── .github/workflows/       # GitHub Actions workflows
├── docs/                    # Documentation content
├── scripts/                 # Automation scripts
├── .markdownlint.json       # Markdown linter configuration
├── mkdocs.yml               # MkDocs configuration
└── requirements.txt         # Python dependencies
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -am 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

{% if cookiecutter.open_source_license != "None" %}
This project is licensed under the {{ cookiecutter.open_source_license }} License - see the LICENSE file for details.
{% else %}
This project is proprietary and confidential.
{% endif %}

## Acknowledgments

- [MkDocs](https://www.mkdocs.org/) for the documentation framework
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) for the theme
- [Cookiecutter](https://github.com/cookiecutter/cookiecutter) for the project templating
