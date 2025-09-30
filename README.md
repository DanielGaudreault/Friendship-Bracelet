# Friendship Bracelet

A virtual friendship bracelet that lights up to spread joy and connection! Send a colorful signal to light up your friend's bracelet across browser tabs or browsers on the same device. Designed as a Progressive Web App (PWA), it offers an app-like experience on phones, tablets, and desktops, with offline support and touch-friendly interactions.

**[Try it now!](https://danielgaudreault.github.io/Friendship-Bracelet/)**

## Features

- **Send Love Signals**: Click "Send Love to Friend" to light up bracelets in other open tabs or browsers on the same device.
- **Persistent Lights**: Bracelet lights stay on until the receiving tab is viewed, ensuring you never miss a friend's signal.
- **App-Like Experience**: Install as a PWA on iOS/Android for a full-screen, native-like app with offline support.
- **Mobile Optimized**: Touch-friendly with haptic feedback (vibration) on supported devices.
- **Cross-Browser Support**: Works across tabs in the same browser (via `BroadcastChannel`) and different browsers (e.g., Chrome to Firefox) on the same device (via `localStorage`).
- **No Server Required**: Purely client-side, no installations or external dependencies needed.
- **Thematic Design**: Vibrant animations and a heartfelt message ("Spread Joy with Every Glow") celebrate friendship.
- **Accessible**: ARIA attributes ensure screen reader compatibility.

## Setup

To run the Friendship Bracelet locally or explore the code:

1. **Clone or Download**:
   - Clone this repository: `git clone https://github.com/danielgaudreault/Friendship-Bracelet.git`
   - Or download the files from the repository.

2. **Files Included**:
   - `index.html`: Main page with the bracelet interface and logic.
   - `manifest.json`: PWA configuration for app installation.
   - `sw.js`: Service worker for offline support.

3. **Run Locally**:
   - Open `index.html` by double-clicking or dragging into a browser (works via `file://`).
   - For best PWA experience, serve via a local server:
     - Install Node.js (optional) and run `npx http-server` in the project folder.
     - Access at `http://localhost:8080`.
   - Alternatively, visit the hosted version: [https://danielgaudreault.github.io/Friendship-Bracelet/](https://danielgaudreault.github.io/Friendship-Bracelet/)

## Usage

1. **Open the App**:
   - Visit [https://danielgaudreault.github.io/Friendship-Bracelet/](https://danielgaudreault.github.io/Friendship-Bracelet/) or open `index.html` locally.
   - On mobile, add to home screen:
     - **iOS (Safari)**: Tap Share > "Add to Home Screen."
     - **Android (Chrome)**: Tap Menu > "Add to Home Screen."

2. **Send a Signal**:
   - Click or tap "Send Love to Friend" to send a signal.
   - Other open tabs or browsers on the same device will light up with colorful beads and a message ("A friend is thinking of you! 💖").
   - If a tab is in the background, the signal is stored and lights up when you switch to it.

3. **Offline Mode**:
   - The bracelet and animations work offline after the first load.
   - Signals queue in `sessionStorage` and display when the tab is focused.

4. **Cross-Browser**:
   - Open in different browsers (e.g., Chrome and Firefox) on the same device to simulate multiple friends.
   - Signals sync via `localStorage` across browsers.

## Testing

1. **Cross-Tab Testing**:
   - Open the page in multiple tabs of the same browser (e.g., Chrome).
   - Click "Send Love to Friend" in one tab; other tabs should light up (immediately if focused, or when focused if backgrounded).

2. **Cross-Browser Testing**:
   - Open in different browsers (e.g., Chrome and Firefox) on the same device.
   - Send a signal from one browser; the other should light up (may have a slight delay due to `localStorage` polling).

3. **Mobile Testing**:
   - Open on a phone (via the hosted link or local file).
   - Install as a PWA for an app-like experience.
   - Tap the button; feel haptic feedback (vibration) when beads light up (Android or iOS PWA).
   - Test offline by disabling internet; UI and animations should work.

4. **Persistent Lights**:
   - Send a signal while a tab is in the background.
   - Switch to the tab; verify the bracelet lights up and resets after 4 seconds.

## Limitations

- **Cross-Device**: Limited to one device, as `BroadcastChannel` and `localStorage` are device-local. For cross-device communication (e.g., phone to laptop), a server (e.g., WebSocket) is needed.
- **Cross-Browser Delay**: `localStorage` polling (every 500ms) is slower than `BroadcastChannel`, so signals between browsers may have a slight delay.
- **Single Signal**: Only one pending signal is stored at a time; new signals overwrite old ones.
- **Browser Support**: Requires modern browsers (2018+) for `BroadcastChannel` and PWA features. Older browsers use `localStorage` fallback but may have delays.
- **PWA Installation**: Manual via browser menu; not in app stores.

## Future Enhancements

- Add a custom sender name input for personalized messages.
- Queue multiple signals in `sessionStorage` for multiple pending messages.
- Add a visual indicator (e.g., badge) for pending signals in background tabs.
- Include a share button to copy the URL for friends.
- Replace the placeholder icon in `manifest.json` with a custom 192x192 PNG.
- If cross-device support is desired, integrate a server-based solution (e.g., WebSocket or Firebase).

## Contributing

Feel free to fork this repository, submit issues, or contribute enhancements! For major changes, please open an issue to discuss.

## License

This project is open-source and available under the [MIT License](LICENSE).

## Acknowledgments

Built with love to celebrate friendship and connection. Inspired by the joy of sharing colorful moments with those who matter most!

---

**Spread joy with every glow!** Visit [https://danielgaudreault.github.io/Friendship-Bracelet/](https://danielgaudreault.github.io/Friendship-Bracelet/) to start sharing love today.
