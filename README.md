# GoToFunction — IntelliJ / PyCharm Plugin

> A lightweight right-side panel that lists every method in the current file.  
> Click to navigate. Hover to preview. No configuration required.

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-IntelliJ%202023.3%2B-orange)

---
<img width="2160" height="1121" alt="demo" src="https://github.com/user-attachments/assets/07e3f012-1824-4ffe-9945-fe8c8f90ba30" />
## Features

| Feature | Detail |
|---|---|
| **One-click navigation** | Click any method name → editor jumps to that line immediately |
| **Hover preview** | Shows first 10 syntax-coloured lines without scrolling away |
| **Real-time update** | List refreshes as you type (600 ms debounce) |
| **Preview toggle** | iOS-style switch to show/hide hover previews |
| **Theme-adaptive** | Colours follow your IDE light/dark theme automatically |
| **Broad language support** | Python, Java, Kotlin, JS, TS, Vue|

---

## Supported Languages

| Language | Extensions |
|---|---|
| Python | `.py` |
| Java | `.java` |
| Kotlin | `.kt` `.kts` |
| JavaScript | `.js` `.jsx` `.mjs` `.cjs` |
| TypeScript | `.ts` `.tsx` |
| Vue | `.vue` (Options API + Composition API / `setup()`) |


---

## Installation

### From JetBrains Marketplace (recommended)
1. Open **Settings → Plugins → Marketplace**
2. Search for **GoToFunction**
3. Click **Install** → restart IDE

### Manual install
1. Download the latest `.zip` from [Releases](../../releases)
2. **Settings → Plugins → ⚙ gear icon → Install Plugin from Disk…**
3. Select the downloaded `.zip` → restart IDE

---

## Usage

1. Open any supported file.
2. The **GoToFunction** panel appears on the **right side** automatically.
3. **Click** a method name to jump to it.
4. **Hover** over a method to see a 10-line preview.
5. Click the **Preview toggle** (top-left of the panel) to show/hide previews.
6. Click **↺** to manually refresh the list.

---

## Building from Source

### Prerequisites
- JDK 8+
- Gradle (wrapper bundled)

### Steps

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/GoToFunction.git
cd GoToFunction

# Run in a sandbox IDE (downloads IntelliJ ~500 MB on first run)
./gradlew runIde

# Build installable plugin zip
./gradlew buildPlugin
# → build/distributions/GoToFunction-1.0.0.zip
```

### Project Structure

```
GoToFunction/
├── build.gradle
├── settings.gradle
├── src/main/
│   ├── java/com/methodnavigator/
│   │   ├── MethodNavigatorToolWindowFactory.java  ← registers the tool window
│   │   ├── MethodNavigatorPanel.java              ← all UI (header, rows, tooltip)
│   │   ├── MethodParser.java                      ← language parsers
│   │   ├── MethodInfo.java                        ← data model
│   │   └── FileEditorListener.java               ← tab-switch listener
│   └── resources/
│       ├── META-INF/plugin.xml
│       └── icons/navigator.svg
└── README.md
```

---

## Compatibility

| IDE | Min version |
|---|---|
| IntelliJ IDEA (Community / Ultimate) | 2023.3+ |
| PyCharm | 2023.3+ |
| WebStorm | 2023.3+ |
| Other JetBrains IDEs | 2023.3+ (untested) |

---

## Contributing

Pull requests are welcome!

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/my-improvement`
3. Make your changes and test with `./gradlew runIde`
4. Commit: `git commit -m "feat: describe your change"`
5. Push: `git push origin feature/my-improvement`
6. Open a Pull Request

### Common contribution ideas
- Add support for a new language
- Improve the Java/Kotlin/JS regex accuracy
- Add unit tests for `MethodParser`
- UI improvements

---

## License

[MIT](LICENSE)

