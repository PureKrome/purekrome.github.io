# Dev Container

This folder contains the VS Code Dev Container setup for the Astro site.

## What it does

- Builds from `.devcontainer/Dockerfile` using a Node 20 devcontainer base image.
- Installs dependencies on first create (`postCreateCommand`: `npm install`).
- Automatically starts Astro when VS Code attaches (`postAttachCommand`) at `0.0.0.0:4321`.
- Forwards port `4321` to the host.
- Uses a named Docker volume for `node_modules` so installs persist.

## `postAttachCommand` details

Current command:

```bash
bash -lc 'if pgrep -f "astro dev" >/dev/null; then echo "Astro dev already running"; else npm run dev -- --host 0.0.0.0; fi'
```

What this does:

- Runs when VS Code attaches to the container.
- Checks whether `astro dev` is already running and only starts it if needed.
- Starts Astro in the foreground so stdout/stderr is visible in the terminal.

## Usage

1. In VS Code, run **Dev Containers: Reopen in Container**.
2. Wait for dependency installation and attach-time auto-start.
3. Open `http://localhost:4321`.

If Astro does not appear to start, open a terminal in the container and run:

```bash
npm run dev -- --host 0.0.0.0
```
