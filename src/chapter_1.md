# Markdown Documentation Kit

A comprehensive template for writing documents in Markdown format.
This template generates HTML files using mdBook.

## Features

- 📝 **mdBook Integration** - Write in Markdown, generate beautiful HTML
  documentation
- 🎨 **Prettier Formatting** - Automatic code formatting for consistent style
- ✅ **Quality Checks** - Markdown linting and spell checking
- 🐳 **Dev Container Support** - Ready-to-use development environment for VS
  Code and GitHub Codespaces
- 🚀 **GitHub Actions** - Automated CI/CD pipeline for building and validation
- 🌐 **Live Preview** - Real-time preview on localhost:3000
- ☁️ **GitHub Codespaces Compatible** - Instant cloud-based development
  environment

## Quick Start

This project is designed to work seamlessly with **Dev Containers**.
It provides a consistent development environment with all necessary tools
pre-installed.

### Using Dev Container (Recommended)

#### With VS Code (Local)

1. Open this project in VS Code
2. Install the "Dev Containers" extension
3. Press `Ctrl+Shift+P` and select "Dev Containers: Reopen in Container"
4. Wait for the container to build and start
5. All tools (Rust, mdBook, Node.js) are automatically available

#### With GitHub Codespaces (Cloud)

1. Navigate to this repository on GitHub
2. Click the green "Code" button
3. Select "Codespaces" tab
4. Click "Create codespace on main"
5. The development environment will be automatically set up in the cloud

### Manual Setup (Not Recommended)

If you prefer not to use Dev Container, you can manually install the
dependencies:

1. Install Rust and Cargo:

   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
   ```

2. Install mdBook:

   ```bash
   cargo install mdbook
   ```

3. Install Node.js dependencies:
   ```bash
   npm install
   ```

## Usage

### Writing Documentation

1. Edit files in the `src/` directory:

   - `SUMMARY.md` - Table of contents
   - `chapter_1.md` - Your content chapters
   - Add more `.md` files as needed

2. Update `book.toml` with your book metadata:

   ```toml
   [book]
   title = "Your Book Title"
   authors = ["Your Name"]
   language = "en"
   ```

### Building and Serving

#### Development (with live reload)

```bash
npm run serve
# or
mdbook serve
```

Access your documentation at <http://localhost:3000>

#### Build for production

```bash
npm run build
# or
mdbook build
```

Generated files will be in the `book/` directory.

### Code Quality

#### Format code with Prettier

```bash
npm run format
```

#### Check formatting

```bash
npm run format:check
```

#### Lint Markdown files

```bash
npm run lint:markdown
```

## Project Structure

```text
├── src/                    # Markdown source files
│   ├── SUMMARY.md         # Table of contents
│   └── chapter_1.md       # Content chapters
├── book/                  # Generated HTML output
├── .devcontainer/         # Dev Container configuration
├── .github/workflows/     # GitHub Actions CI/CD
├── book.toml             # mdBook configuration
├── package.json          # Node.js dependencies and scripts
├── .prettierrc           # Prettier configuration
└── .prettierignore       # Prettier ignore patterns
```

## GitHub Actions

The project includes automated CI/CD that:

- ✅ Checks Prettier formatting
- ✅ Validates Markdown syntax
- ✅ Builds the documentation
- 📦 Creates artifacts for deployment

## Customization

### Styling

Edit `book.toml` to customize the appearance and behavior of your
documentation.

### Adding Plugins

mdBook supports various plugins. Install them via Cargo and configure in
`book.toml`.

### Adding More Linting Rules

Extend the linting configuration in `package.json` and add more textlint
rules as needed.

## Contributing

1. Fork the repository
2. Make your changes
3. Ensure all checks pass:
   `npm run format:check && npm run lint:markdown`
4. Submit a pull request

## License

MIT License - see LICENSE file for details.
