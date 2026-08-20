# BuiltWitAI Umbrel Community App Store

This is a **community Umbrel App Store** where I collect and distribute all the apps I want to run on my Umbrel server. It serves as a personal/custom app store for apps that aren't available in the [Official Umbrel App Store](https://github.com/getumbrel/umbrel-apps) or that I want to customize.

## Store Info

- **Store ID**: wtai (used as prefix for all app IDs)
- **Store Name**: "BIG" (shown as "BIG App Store" in umbrelOS UI)
- **Repository**: https://github.com/BuiltWitAI/umbrel-apps

## Available Apps

| Icon | App | Description |
|------|-----|-------------|
| <img src="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png" alt="Whoami" width="24"> | [Whoami](bwtai-whoami) | Tiny Go HTTP server that prints OS/hostname info |
| <img src="https://raw.githubusercontent.com/Pelski/ytzero/main/docs/assets/icon.png" alt="YT Zero" width="24"> | [YT Zero](bwtai-ytzero) | Self-hosted YouTube inbox — subscriptions without recommendations |
| <img src="https://p2r3.github.io/convert/assets/favicon-Bfod-rsk.ico" alt="Convert" width="24"> | [Convert](bwtai-convert) | Truly universal online file converter |
| <img src="https://github.com/jpillora/cloud-torrent/blob/master/static/files/cloud-favicon.png" alt="Cloud Torrent" width="24"> | [Cloud Torrent](bwtai-cloud-torrent) | Self-hosted remote torrent client with web UI |
| <img src="https://raw.githubusercontent.com/glanceapp/glance/main/docs/logo.png" alt="Glance" width="24"> | [Glance](bwtai-glance) | A self-hosted dashboard that puts all your feeds in one place |
| <img src="https://svgur.com/i/mvA.svg" alt="Hello World" width="24"> | [Hello World](sparkles-hello-world) | Minimal example app |

## How to Add This Store to Your Umbrel

1. Go to **Settings → App Store** in your Umbrel dashboard
2. Click **"Add Custom App Store"**
3. Enter this repository URL: https://github.com/BuiltWitAI/umbrel-apps
4. The "BIG App Store" will appear with all available apps

## How to Add Apps to This Store

Each app lives in its own folder under the repo root with the format wtai-<app-name>:

\\\
umbrel-apps/
├── umbrel-app-store.yml       # Store configuration (ID + name)
├── bwtai-my-app/              # App folder (must start with "bwtai-")
│   ├── umbrel-app.yml         # App metadata (name, description, icon, etc.)
│   ├── docker-compose.yml     # Docker services for the app
│   └── README.md              # Optional: app-specific docs
└── bwtai-another-app/
    ├── umbrel-app.yml
    └── docker-compose.yml
\\\

### Steps to add a new app:

1. Create a new folder: wtai-<your-app-name>
2. Add umbrel-app.yml with app metadata (see [Umbrel app spec](https://github.com/getumbrel/umbrel/tree/master/apps))
3. Add docker-compose.yml with the Docker services
4. Commit and push – the app will automatically appear in the store

## Example App Structure

See wtai-hello-world/ for a minimal working example.

---

*This store is maintained by [BuiltWitAI](https://github.com/BuiltWitAI). Feel free to fork and create your own!*
