# Embodied Intelligence Labs – CSE 598/494

This repository hosts the **Embodied Intelligence Labs** website for  
**CSE 598/494 Topic: Intelligent and Safe Cyber-Physical Systems** at **Arizona State University**.
The site is implemented using [`mdBook`](https://rust-lang.github.io/mdBook/).

## Prerequisites

- Rust toolchain installed (e.g., via [`rustup`](https://rustup.rs/))
- `mdbook` installed:

```bash
cargo install mdbook
```

## Build

To build the static site into the `book/` directory:

```bash
mdbook build
```

The output HTML and assets will be generated under `book/`.

## Test / Preview locally

To serve the book locally with live reload:

```bash
mdbook serve --open
```

Then open the printed URL (typically `http://localhost:3000`) in your browser.
This is the recommended way to test edits before pushing.

## Contributing

### Repository layout

- `book.toml` – mdBook configuration
- `src/` – markdown sources
  - `SUMMARY.md` – table of contents
  - `overview.md` – course and lab sequence overview
  - `lab1-agentic-driving-coach.md` – Lab 1 description
  - `lab2-safe-maneuver-intelligent-rover.md` – Lab 2 description
  - `lab-format-logistics.md` – format and logistics information
  - `contributors.md` – contributors list

### Making changes

1. Create a new branch for your changes.
2. Edit or add markdown files under `src/`.
3. Run `mdbook serve` and verify the content renders as expected.
4. Commit your changes with a descriptive message.
5. Open a pull request for review.

Please keep writing concise and student-focused, and prefer small, focused PRs
for easier review.

## Deployment to GitHub Pages

The generated `book/` directory can be published via GitHub Pages.
A typical workflow is:

1. Build the book:

   ```bash
   mdbook build
   ```

2. Configure GitHub Pages in the repository settings to serve:
   - either from the `gh-pages` branch (populated by a workflow), or
   - from the `/book` folder on the `main` branch (if using the “Deploy from a branch” option).

3. Optionally, automate deployment with a GitHub Actions workflow that:
   - checks out the repository,
   - installs `mdbook`,
   - runs `mdbook build`,
   - and pushes the contents of `book/` to the configured Pages target.

Adjust the exact deployment strategy to match your organization’s CI/CD
preferences.
