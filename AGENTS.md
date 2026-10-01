# Base44 Setup Notes

## Project Overview
A single static `index.html` file — a canvas-based fireworks animation. No build step, no backend, no dependencies.

## Running
- `docker compose -f docker-compose.base44.yml up -d` serves the site via nginx:alpine on port 3000.
- The repo directory is bind-mounted read-only into nginx's html root.
- No external credentials needed.

## Quirk
The sandbox `/app` directory may have restrictive (700) permissions after import. If nginx returns 403, run `chmod 755 /app` on the host so the nginx worker process can traverse the mount.
