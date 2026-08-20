# BuiltWitAI Umbrel Community App Store

This is a **community Umbrel App Store** where I collect and distribute all the apps I want to run on my Umbrel server. It serves as a personal/custom app store for apps that aren't available in the [Official Umbrel App Store](https://github.com/getumbrel/umbrel-apps) or that I want to customize.

## Store Info

- **Store ID**: `bwtai` (used as prefix for all app IDs)
- **Store Name**: "BIG" (shown as "BIG App Store" in umbrelOS UI)
- **Repository**: https://github.com/BuiltWitAI/umbrel-apps

## How to Add This Store to Your Umbrel

1. Go to **Settings → App Store** in your Umbrel dashboard
2. Click **"Add Custom App Store"**
3. Enter this repository URL: `https://github.com/BuiltWitAI/umbrel-apps`
4. The "BIG App Store" will appear with all available apps

## How to Add Apps to This Store

Each app lives in its own folder under the repo root with the format `bwtai-<app-name>`:

```
umbrel-apps/
├── umbrel-app-store.yml       # Store configuration (ID + name)
├── bwtai-my-app/              # App folder (must start with "bwtai-")
│   ├── umbrel-app.yml         # App metadata (name, description, icon, etc.)
│   ├── docker-compose.yml     # Docker services for the app
│   └── README.md              # Optional: app-specific docs
└── bwtai-another-app/
    ├── umbrel-app.yml
    └── docker-compose.yml
```

### Steps to add a new app:

1. Create a new folder: `bwtai-<your-app-name>`
2. Add `umbrel-app.yml` with app metadata (see [Umbrel app spec](https://github.com/getumbrel/umbrel/tree/master/apps))
3. Add `docker-compose.yml` with the Docker services
4. Commit and push — the app will automatically appear in the store

## Example App Structure

See `bwtai-hello-world/` for a minimal working example.

---

*This store is maintained by [BuiltWitAI](https://github.com/BuiltWitAI). Feel free to fork and create your own!*
