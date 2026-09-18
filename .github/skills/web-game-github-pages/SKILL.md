---
name: web-game-github-pages
description: Build, polish, test, and deploy browser games that run as static sites on GitHub Pages. Use for requests involving HTML5 games, Canvas, Phaser, Three.js, Vite, mobile browser playability, or GitHub Pages deployment.
---

# Web Game for GitHub Pages

## Goal

Create a playable browser game that works from a static host, especially GitHub Pages. Prioritize a complete playable loop, responsive input, fast loading, and a deployment configuration that works when the site is served from a repository subpath.

## Start With the Game Loop

Before writing UI chrome, define:

- The player objective and win/lose conditions.
- Core controls for keyboard, mouse, touch, and/or gamepad as appropriate.
- The update loop and rendering surface.
- Game state transitions: loading, playing, paused, game over, and restart.
- A small vertical slice that can be played end to end.

Use an established engine when it clearly reduces risk:

- Use Phaser for 2D games with scenes, sprites, collisions, and audio.
- Use Three.js for 3D games or custom 3D scenes.
- Use the Canvas API for small 2D games when an engine would add unnecessary weight.
- Use DOM/CSS for menus and HUD when it is more accessible and maintainable than drawing text on canvas.

Keep game logic separate from rendering and input handling so the game remains testable.

## Visual and Interaction Quality

- Make the game itself the first screen; do not lead with a marketing hero.
- Use a clear visual direction with intentional typography, color variables, and a restrained background treatment.
- Keep the playfield dimensions stable with responsive constraints so HUD elements do not shift during play.
- Support both desktop and mobile layouts when the request does not specify otherwise.
- Add touch controls for mobile games; do not assume hover, right-click, or a physical keyboard.
- Make buttons and controls large enough for touch and provide visible focus states.
- Provide pause, restart, sound, and mute controls when relevant.
- Respect `prefers-reduced-motion` and avoid effects that make the game difficult to read.
- Use real visual assets or deliberately designed procedural graphics. Avoid placeholder-looking empty states.
- Never let interface text overflow the viewport or cover the main gameplay area.

## Static Hosting Rules

GitHub Pages serves a static build and may host the site at `/<repository-name>/`, not `/`.

- Do not depend on a server runtime, server-side routes, WebSockets, or runtime secrets.
- For Vite, set `base` to the repository path or use a deployment-aware value. Keep asset imports handled by the bundler.
- For client-side routing, prefer a single-page game flow or configure a fallback strategy compatible with GitHub Pages. Do not assume arbitrary deep links resolve.
- Use relative or bundler-managed asset references. Do not hardcode local filesystem paths.
- Preload only essential assets; lazy-load large optional audio or texture files.
- Avoid autoplay audio. Start audio after a user gesture and provide mute controls.
- Store local progress in `localStorage` only when persistence is useful, and handle unavailable or corrupted storage gracefully.

## Recommended Project Shape

For a Vite project, prefer a small structure like:

```text
src/
  main.ts
  game/
    Game.ts
    state.ts
    input.ts
  ui/
    hud.ts
    menu.ts
  styles/
    main.css
public/
  assets/
.github/
  workflows/
    deploy.yml
```

Use the existing project conventions when present. Do not introduce a framework or dependency unless it solves a real problem.

## GitHub Actions Deployment

For a Vite-style project, configure a workflow that:

1. Checks out the repository.
2. Installs the declared Node version and dependencies with the lockfile.
3. Runs the production build and any available tests.
4. Uploads the build directory as a Pages artifact.
5. Deploys with the official GitHub Pages deployment action.

Use repository permissions appropriate for Pages deployment and keep the build deterministic. Do not commit generated `dist` output unless the repository already follows that convention.

## Validation Checklist

Before finishing:

- Run the project build.
- Run focused tests or type checking when available.
- Open the built site and verify that assets load from a repository subpath.
- Test keyboard and touch input, restart, pause, mute, and game-over flows where applicable.
- Check desktop and narrow mobile viewport sizes.
- Confirm there are no console errors, missing assets, or blank canvas states.
- Confirm the production output is static and does not require a local development server.
- Verify the GitHub Actions workflow references the actual package manager, build command, and output directory.

## Delivery Notes

When reporting completion, mention:

- The game loop and main controls implemented.
- The build/test commands run and their result.
- The expected GitHub Pages URL shape: `https://<user>.github.io/<repository>/`.
- Any repository setting still required, such as selecting GitHub Actions as the Pages source.
