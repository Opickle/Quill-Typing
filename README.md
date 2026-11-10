Quill — typing, measured

A minimal typing speed test in a single HTML file. No build step, no dependencies, no account. Open Quill___typing__measured.html in a browser and start typing.

Features

Test

Durations of 15, 30, 60 or 120 seconds
Live timer, WPM and accuracy while you type, with a progress bar
Optional punctuation mode (commas, full stops, capital letters)
Results screen with WPM, accuracy, raw WPM, consistency, peak WPM, characters, correct/incorrect counts and a WPM-over-time chart
"New best" badge when you beat your highest WPM

Stats (saved locally after every test)

Test count, average and best WPM, average accuracy, characters typed
WPM and accuracy history charts with hover tooltips
Weakest keys and most mistyped words
Short written insights (for example, which keys slow you down, or whether you tire in longer tests)

Languages

10 word lists: English, Spanish, French, German, Dutch, Slovak, Czech, Polish, Italian, Portuguese
The language menu (globe icon, top right) changes both the test words and the interface language

Settings

Accent colour (violet, indigo, fuchsia, sky)
Typing font size (18–40 px)
Default test duration
Sound effects, smooth cursor, reduced motion
Reset statistics (asks for a second click to confirm)
Keyboard shortcuts
Key	Action
Tab	New test
Esc	Reset the current test
Ctrl + Backspace	Delete the current word
Enter	Start a new test from the results screen
Running it

Just open the HTML file. It works offline, except that the Inter and JetBrains Mono fonts load from Google Fonts. Without a connection it falls back to system fonts.

The app uses hash routes (#test, #stats, #set), so it also works when hosted on any static host.

Where your data lives

Everything stays in your browser:

Settings are in localStorage under the key quill:s.
Test history is in IndexedDB (database quill, store tests).

Clearing site data for the page deletes your history. There is no export yet. The storage code is wrapped in a small Store object, so it can be swapped for a cloud backend later.

Adding a language

All of this is in the <script> block:

Add a word list to the LG object, for example xx:"word word word ...".split(" ").
Add its display name to LN.
Add its interface strings to DICT. This is one string per language with 50 entries separated by |, in the same order as the KEYS list. Missing entries fall back to English.

The language appears in the menu automatically.

Known limitations
The written insights on the Stats page are English only.
The newer word lists (Slovak, Czech, Polish, Italian, Portuguese) are short, about 50 words each, so words repeat more often.
"New best" compares against all past tests, regardless of duration or language.
Stats combine all languages.
Accented letters (č, ľ, ł and so on) need a keyboard layout that can type them.
Ideas for later

Per-duration and per-language bests, a no-accents option, fixed word-count and custom-text modes, a keyboard heatmap, stats export/import, and a light theme.
