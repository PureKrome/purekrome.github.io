# <center>World Domination Website</center>

This is my personal website where I share my projects, blog posts, and other content related to my journey towards world domination.

## 💻 Tech Stack

- **Main Framework** [Astro](https://astro.build/)
- **Theme** 📄[AstroPaper](https://github.com/satnaing/astro-paper/)
- **Hosting** GitHub Pages

## 👨🏻‍💻 Running Locally - docker compose

You can start using this project locally either by runninng docker commands or in a devcontainer.

### Devcontainer

Just open this project in a devcontainer and it will automatically install the dependencies and start the development server.

### 🧹 Linting & Formatting

Before committing changes, ensure your code is formatted and passes linting:

```bash
# Check formatting (will show errors if any)
npm run format:check

# Auto-fix formattingnp
npm run format

# Check linting
npm run lint
```

### Docker compose

Make sure docker is installed and then run the following command in the project directory:

```bash
docker compose up
```

### 🧹 Linting & Formatting

Before committing changes, ensure your code is formatted and passes linting:

```bash
# Check formatting (will show errors if any)
docker compose run --rm astro npm run format:check

# Auto-fix formatting
docker compose run --rm astro npm run format

# Check linting
docker compose run --rm astro npm run lint
```

## 📜 License

Licensed under the MIT License, Copyright © 2025

---
