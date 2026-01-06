# Blinko NSFW Blur Plugin

Automatically blurs notes containing NSFW or other sensitive tags in Blinko, similar to the Memos blur feature. Click any blurred note to reveal its content.

# ⚠️ UNDER AND LIKELY DOESNT WORK ⚠️

## Features

- 🔒 **Auto-blur notes** with specified tags (default: #nsfw)
- 👁️ **Click to reveal** - click any blurred note to unblur it
- 🏷️ **Child tag support** - works with nested tags like #nsfw/art or #nsfw/waifu
- ⚙️ **Customizable settings**:
  - Configure which tags trigger the blur
  - Adjust blur intensity
  - Toggle warning labels on/off
- 🎨 **Smooth transitions** with hover effects

## Installation

### Method 1: Install from GitHub (Recommended - Automatic Updates)

1. Go to your Blinko instance
2. Navigate to **Plugin → Marketplace**
3. Click **"Install from GitHub"**
4. Enter: `https://github.com/YOUR-USERNAME/blinko-nsfw-blur`
5. Click **"Install"**

Blinko will automatically download the latest release and install the plugin.

### Method 2: Manual Upload (No automatic updates)

If you prefer to manage updates manually:

1. Download `release.zip` from the [latest release](../../releases/latest)
2. Go to **Plugin → Installed**
3. Click **"Upload Plugin"**
4. Select the downloaded `release.zip` file

## Configuration

After installation:

1. Go to **Plugin → Installed**
2. Find "NSFW Blur" in the list
3. Click the settings icon (⚙️)
4. Configure your preferences:

### Settings Explained

**Blur Tags** (default: `#nsfw`)
- Comma-separated list of tags that trigger blur
- Examples: 
  - Single tag: `#nsfw`
  - Multiple tags: `#nsfw, #sensitive, #private`
  - Works with or without the `#` symbol

**Blur Intensity** (default: `20`)
- How blurred the content should be (1-50 pixels)
- Lower = slight blur, Higher = stronger blur
- Recommended range: 10-30

**Show Warning Label** (default: `true`)
- Display "NSFW Content - Click to Reveal" on blurred notes
- Set to `false` to hide the warning text

## Usage Examples

### Basic Usage
```
This is a regular note #personal

This is a sensitive note #nsfw
```
The second note will be automatically blurred.

### Child Tags
```
My artwork collection #nsfw/art
My fanfic #nsfw/writing
```
Both notes will be blurred if `#nsfw` is in your blur tags.

### Multiple Tags
```
Private work notes #sensitive #work
```
Will be blurred if either `#sensitive` or `#work` is in your blur tags.

## How It Works

1. The plugin scans all visible notes for your configured tags
2. When a matching tag is found, it applies a CSS blur filter
3. A click handler is added to reveal the content
4. The plugin watches for new notes and automatically applies blur as needed

## Creating a Release (For Repository Owners)

When you're ready to publish a new version:

1. Update the version in `plugin.json`
2. Commit your changes
3. Create and push a tag:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```
4. GitHub Actions will automatically:
   - Build the plugin
   - Create a `release.zip`
   - Publish it as a GitHub release

Users can then install or update via "Install from GitHub" in Blinko!

## Troubleshooting

**Plugin not blurring notes:**
- Make sure your tags match exactly (case-insensitive)
- Check that the tag format matches your notes
- Try refreshing the page after changing settings

**Blur is too strong/weak:**
- Adjust the "Blur Intensity" setting
- Recommended range: 10-30 pixels

**Warning label not showing:**
- Check that "Show Warning Label" is enabled in settings
- The label only appears on blurred notes

**Can't install from GitHub:**
- Make sure your repository is public
- Ensure you have created at least one release with a `release.zip` asset
- Check that the repository URL is correct

## Development

If you want to modify this plugin:

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/blinko-nsfw-blur.git
cd blinko-nsfw-blur

# Install dependencies
bun install

# Build
bun run build

# The built files will be in the dist/ directory
```

## Compatibility

- Blinko version: 1.4.0+
- Tested with web interface and desktop app

## License

MIT License - feel free to modify and distribute

## Credits

Inspired by the NSFW blur feature in [Memos](https://github.com/usememos/memos).
