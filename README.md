[🇷🇺 Русский](README.ru.md) · [🇬🇧 English](README.md) · [🇪🇸 Español](README.es.md)

# NewTab Dashboard — Custom Edition

**NewTab Dashboard — Custom Edition** is a modified version of NewTab Dashboard, a Firefox extension that replaces the default new tab page with a modern, minimalist, and highly customizable personal dashboard.

This edition introduces additional tools for network administration, system monitoring, and quick access to frequently used services while preserving the core functionality of the original project.

**Current Version:** 1.0.2

**Original Project:** [NewTab Dashboard on Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/newtab-dashboard/)

> **Note:** This is an independently modified version of the original project. The Firefox Add-ons link above points to the original extension, not this custom edition.

![NewTab Dashboard Screenshot](images/screenshot1.png)

---

## Features

### Left Column — Sidebar

- Real-time clock and date.
- Customizable RSS news feeds.
- Separate tabs for individual RSS sources.
- Service monitoring through Uptime Kuma.
- Support for homelab monitoring widgets.

### Center Column — Main

- Search bar with multiple configurable search engines.
- Bookmarks organized into **Sections → Groups → Links**.
- Automatic website icons.
- Recent videos from subscribed YouTube channels.
- **Quick Actions** widget for frequently accessed tools and services.

### Right Column — Widgets

- Real-time weather information powered by Open-Meteo.
- Interactive monthly calendar.
- Cryptocurrency prices powered by CoinGecko.
- Persistent notes.
- Configurable and rearrangeable widgets.
- Additional system monitoring tools.

---

## Custom Edition Improvements

This version extends the original dashboard with several additional features.

### Network Toolbox

Integrated network diagnostic tools accessible directly from the dashboard.

The Network Toolbox communicates with a locally hosted backend to perform supported network operations.

### System Monitor

A dedicated system monitoring widget that displays statistics collected from your local machine.

**Default API endpoint:**

`http://127.0.0.1:8765/stats`

The System Monitor requires a separate local Python backend to provide real-time information.

### Quick Actions

A configurable widget that provides shortcuts to frequently used applications, websites, and services.

Example shortcuts include GitHub, Proxmox, and SSH-related resources.

### Improved RSS Feed Support

The RSS widget has been updated to retrieve and parse RSS and Atom XML feeds directly, rather than depending on the external rss2json service.

This removes the dependency on that third-party conversion API, although individual feeds may still be subject to browser access restrictions.

### Improved Widget Layout

The Quick Actions widget is positioned beneath the main bookmark sections in the center column, providing easier access without overcrowding the right sidebar.

---

## Main Capabilities

- **No API keys required for core public services** — Weather, cryptocurrency prices, and YouTube videos use publicly available sources.
- **Firefox extension storage** — Settings are stored using `browser.storage.sync`, with a `localStorage` fallback.
- **Import and Export** — Save and restore your dashboard configuration using JSON files.
- **Customizable appearance** — Wallpapers, gradients, blur, opacity, darkening, and themes.
- **Configurable widgets** — Enable, disable, rearrange, and organize dashboard components.
- **Homelab integration** — Support for Proxmox, Portainer, Pi-hole, and Uptime Kuma, depending on configuration.
- **Multilingual interface** — English, Spanish, and Russian.
- **Lightweight architecture** — Built with vanilla HTML, CSS, and JavaScript, without a frontend framework or bundler.

---

## Installation

### Method 1 — Install the Signed Extension (Recommended)

1. Open the **Releases** section of this repository.
2. Download the latest Mozilla-signed `.xpi` file.
3. Open Firefox.
4. Navigate to `about:addons`.
5. Click the settings gear icon.
6. Select **Install Add-on From File…**
7. Choose the downloaded `.xpi` file.
8. Confirm the installation.

> A Mozilla-signed `.xpi` is required for permanent installation in standard Firefox releases.

### Method 2 — Install From Source (Developer Mode)

1. Clone or download this repository.
2. Open Firefox and navigate to `about:debugging`.
3. Select **This Firefox**.
4. Click **Load Temporary Add-on…**
5. Select `manifest.json` from the project directory.

The extension will be loaded temporarily for development and testing.

> Temporary add-ons are unloaded when Firefox closes. Use the signed `.xpi` for permanent installation.

---

## System Requirements

### Basic Dashboard

- Mozilla Firefox or a compatible browser.
- No additional software required for the core dashboard features.
- Internet access for external services such as weather, news, cryptocurrency prices, and YouTube.

### System Monitor

The System Monitor requires a local backend service.

The default endpoint is:

`http://127.0.0.1:8765/stats`

The backend can run as a user-level systemd service on supported Linux systems.

### Network Toolbox

The Network Toolbox requires a compatible local backend to execute network diagnostic operations.

### Homelab Integrations

Some widgets require access to external or self-hosted services, such as:

- Proxmox VE
- Portainer
- Pi-hole
- Uptime Kuma

These integrations may require additional configuration, API credentials, or network access.

---

## Project Structure

```text
newtab-dashboard/
├── manifest.json
├── dashboard.html
├── dashboard.css
├── dashboard.js
├── background.js
├── icon.svg
├── icon48.png
├── icon128.png
├── images/
│   └── screenshot1.png
├── LICENSE
└── README.md
```

Additional files may be included for the custom monitoring and network diagnostic backends.

---

## Customization

All dashboard settings can be managed through the built-in **Settings (⚙)** interface.

You can:

- Add, edit, remove, and rearrange bookmark sections.
- Organize links into groups.
- Configure RSS news sources.
- Add YouTube channels using channel IDs.
- Select your preferred search engine.
- Change wallpapers, gradients, and visual effects.
- Enable, disable, and rearrange widgets.
- Configure Quick Actions shortcuts.
- Connect supported homelab services.
- Change the interface language.
- Export and import dashboard settings.
- View extension information, version details, and licensing information.

---

## Technologies

| Component | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Extension API | Firefox WebExtensions |
| Storage | `browser.storage.sync` and `localStorage` |
| Weather | [Open-Meteo](https://open-meteo.com/) |
| Cryptocurrency | [CoinGecko](https://www.coingecko.com/en/api) |
| YouTube | Atom XML feeds |
| News | RSS and Atom XML feeds |
| Icons | [Simple Icons](https://simpleicons.org/) and website favicons |
| Service Monitoring | [Uptime Kuma](https://github.com/louislam/uptime-kuma) |
| System Monitoring | Local Python backend |
| Network Diagnostics | Local backend service |

---

## Contributing

Contributions, suggestions, and bug reports are welcome.

If you would like to improve the dashboard:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the extension in Firefox.
5. Submit a pull request describing your improvements.

Please avoid committing personal configuration files, passwords, API tokens, or private network information.

---

## Credits

This project is based on **NewTab Dashboard**, originally developed by **Francisco Martínez**.

Special thanks to the contributors of the original project, including [@Nikitamce](https://github.com/Nikitamce), for contributions to Russian translation and internationalization.

This Custom Edition includes additional modifications and functionality and is not affiliated with the official Firefox Add-ons listing of the original project.

---

## License

This project is distributed under the **MIT License**, subject to the terms and copyright notices of the original project.

**Original Project:** © Francisco Martínez.

Modifications to this edition are distributed under the applicable license terms.

See [LICENSE](LICENSE) for details.
