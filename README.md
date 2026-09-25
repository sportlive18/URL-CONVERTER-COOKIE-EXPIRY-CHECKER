# 🔐 DRM URL Converter

A clean, client-side web tool to convert between a **ClearKey DRM manifest URL** and its individual components (stream URL, Key ID, DRM Key) to any network stream or iptv player playable

## ✨ Features

- **Two-way conversion** – Generate a full DRM URL from components, or parse a full URL back into its parts.
- **Dual tabs** – Switch between *Generate URL* and *Parse URL* modes.
- **Instant feedback** – Visual validation of hex‑formatted keys.
- **Copy to clipboard** – One‑click copy of the generated or parsed results and use any network stream url
- **Example data** – Pre‑fill with sample values to see how the tool works.
- **Keyboard shortcuts** – Press `Ctrl+Enter` (or `Cmd+Enter`) to trigger the active tab’s action.
- **Responsive** – Works on desktop and mobile devices.

## 🚀 Usage

### 1. Generate URL (from components)

1. Enter the **Stream URL** (the `.mpd` manifest).
2. Enter the **Key ID** (32 hexadecimal characters).
3. Enter the **DRM Key** (32 hexadecimal characters).
4. Click **“Generate URL”** or press `Ctrl+Enter`.
5. The combined URL appears in the result field – copy it with the copy button.

### 2. Parse URL (from full DRM URL)

1. Paste a full DRM URL (e.g., `https://.../cenc.mpd|drmScheme=clearkey&drmLicense=...`) into the **“Full DRM URL”** field.
2. Click **“Parse URL”** or press `Ctrl+Enter`.
3. The tool extracts and displays the **Stream URL**, **Key ID**, and **DRM Key** in read‑only fields.

### Example

- **Stream URL**: `https://example.com/manifest.mpd`
- **Key ID**: `6818868b06409ee7869850f878c30665`
- **DRM Key**: `4766f05f2c1de3cd0896ccd99f662fd1`

**Generated URL**:
```
https://example.com/manifest.mpd|drmScheme=clearkey&drmLicense=6818868b06409ee7869850f878c30665:4766f05f2c1de3cd0896ccd99f662fd1
```

## 🛠️ Technical Details

- **Pure HTML/CSS/JavaScript** – No external libraries or frameworks.
- **Client‑side only** – All processing happens in your browser; nothing is sent to a server.
- **URL format** – The tool expects the DRM parameters in the form `|drmScheme=clearkey&drmLicense=<keyId>:<drmKey>`.
- **Hex validation** – Key ID and DRM Key must be exactly 32 hexadecimal characters (case‑insensitive).

## 📁 File Structure

The tool is a single HTML file (`index.html`) with embedded styles and scripts. You can open it directly in any modern browser – no build process or server required.

## 🔧 Customization

- To change the default example data, edit the `EXAMPLE` object inside the `<script>` tag.
- If your DRM parameter names differ, adjust the `buildFullUrl` and `parseFullUrl` functions accordingly.

