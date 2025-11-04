# Open in Winston

A userscript that redirects Reddit links to open directly in the [Winston Reddit client](https://github.com/lo-cafe/winston) on iOS devices. When clicking a Reddit link in Safari (e.g., from Google, Bing, or other search engines), it prevents Safari from loading the Reddit page and instead prompts to open in Winston.

This script is a direct adaptation of the excellent ["Open in Apollo" userscript](https://github.com/AnthonyGress/Open-In-Apollo) by Anthony Gress, modified to support Winston's URL scheme.

## Features

- Automatically detects Reddit links on search engine results pages (Google, Bing, DuckDuckGo, Ecosia, Yahoo) and Reddit itself.
- Supports subreddit links, comment threads, and posts.
- Handles sorting suffixes (e.g., `/hot`, `/new`) by cleaning the path.
- Uses Winston's custom URL scheme (`winstonapp://`) for deep linking.
- Prevents duplicate event listeners and works with dynamically loaded content via MutationObserver.
- Long-press on links still works for fallback (e.g., if Winston isn't installed).
- Compatible with redditmedia.com links (converts them to reddit.com).

## Installation

### iOS (Recommended for Safari)
1. Install the free [Userscripts app](https://apps.apple.com/us/app/userscripts/id1463298887) from the App Store.
2. Download this script: [open-in-winston.user.js](https://raw.githubusercontent.com/DivineOpinion/open-in-winston/main/open-in-winston.user.js).
3. Open the Userscripts app, tap the "+" button, and import the downloaded `.user.js` file.
4. Enable the script in the app's settings for Safari.
5. In Safari, grant permissions if prompted.

### Desktop Browsers
1. Install a userscript manager like [Tampermonkey](https://www.tampermonkey.net/) (Chrome/Firefox/Edge) or [Violentmonkey](https://violentmonkey.github.io/) (open-source alternative).
2. Click the extension icon > "Create a new script" > Paste the contents of [open-in-winston.user.js](https://raw.githubusercontent.com/YOUR_GITHUB_USERNAME/open-in-winston/main/open-in-winston.user.js).
3. Save and enable.

## Usage

- Once installed, search for Reddit content on Google/Bing/etc.
- Click any Reddit link: It should prompt to open in Winston without loading the Reddit site in Safari.
- If on reddit.com directly, it will redirect to Winston.
- Excludes search pages (`/search`) to avoid interference.

If Winston doesn't open (e.g., wrong scheme), try editing the script to use `winston://` instead of `winstonapp://` in the `convertToWinstonUrl` function.

## Compatibility

- **Browsers**: Safari (iOS/macOS), Chrome, Firefox (with userscript manager).
- **Tested On**: iOS 17+, macOS Sonoma+.
- **Winston App**: Requires the Winston app installed on your device.
- **Search Engines**: All Google domains worldwide, Bing, DuckDuckGo, Ecosia, Yahoo.

If you encounter issues with specific sites or links, open an issue!

## Credits

- Original script: ["Open in Apollo" by Anthony Gress](https://github.com/AnthonyGress/Open-In-Apollo) – this project is a fork/adaptation with Winston-specific changes.
- Author: DivineOpinion (GitHub: @DivineOpinion)
- Inspired by community userscripts for Reddit clients.

Thank you to Anthony Gress for the solid foundation!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Pull requests welcome! For major changes, open an issue first.

## Changelog

- **v1.1.0** (Initial Release): Adapted from Apollo script, added Winston support.
