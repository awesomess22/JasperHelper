# Jasperactive Helper Scripts for Tampermonkey

This repository contains Tampermonkey userscripts designed to assist with tasks within the Jasperactive learning platform integrated with Microsoft Office web applications.

**Disclaimer:** These scripts rely on the specific HTML structure and CSS classes of the Jasperactive platform as observed during development. Updates to the Jasperactive platform may break the functionality of these scripts without notice. Use them at your own discretion.

---

## 1. Jasperactive Highlight Text

**Filename:** `jasperactive_highlight_text.user.js` (Based on v1.12 - Trim Always On)

### Purpose

This script runs on the main Jasperactive task pane page (where instructions are displayed) and aims to make identifying text that needs to be typed into the simulation easier.

### Features

* **Answer Highlighting:** Automatically scans the instruction text within the main panel. It looks for lines following the pattern `type: [ANSWER TEXT] and press ENTER.` (specifically searching within `<tbody>` -> `p` or `td` elements).
* **Inline Highlighting:** Highlights only the potential answer text found between the keywords "type:" and " and press ENTER." with a green background.
* **Click-to-Copy:** Click directly on the green highlighted text to copy it to your clipboard.
* **Automatic Trimming:** The copied text will automatically have any leading or trailing whitespace removed for easier pasting.
* **Polling:** Periodically checks the instructions panel to update highlights if the instructions change dynamically.

### Installation

1.  Install the [Tampermonkey](https://www.tampermonkey.net/) browser extension (or a compatible userscript manager).
2.  Click on the `jasperactive_highlight_text.user.js` file in GitHub.
3.  Click the "Raw" button.
4.  Tampermonkey should automatically open a new tab asking if you want to install the script.
5.  Click "Install".

### Usage

1.  Navigate to a Jasperactive exercise page within the Office web application.
2.  The script will automatically run on the main task pane.
3.  Look for green highlights within the instruction steps.
4.  Click on a green highlight to copy the trimmed answer text to your clipboard.

---

## 2. Jasperactive Highlight Click Boxes

**Filename:** `jasperactive_highlight_click_boxes.user.js` (Based on v1.11/v1.12 logic)

### Purpose

This script runs *inside* the Jasperactive simulation iframe and helps visualize the interactive "click box" elements used in many simulation steps.

### Features

* **Click Box Highlighting:** Applies a semi-transparent red background and a dashed red border to elements identified as click boxes (specifically `div` elements whose `id` starts with `Click_Box_`). This makes their position and size visible.
* **Iframe Targeting:** Includes `@match` directives to ensure the script runs correctly within the simulation iframe where these elements exist.
* **Toggle Functionality:** You can turn the red highlighting on or off using a keyboard shortcut.
    * **Shortcut:** `Ctrl + Alt + B`
* **State Persistence:** The on/off state of the highlighting is remembered across page loads. Highlighting is ON by default.
* **Polling (Internal):** Uses internal checks to apply highlighting as elements appear.

### Installation

1.  Install the [Tampermonkey](https://www.tampermonkey.net/) browser extension (or a compatible userscript manager).
2.  Click on the `jasperactive_highlight_click_boxes.user.js` file in GitHub.
3.  Click the "Raw" button.
4.  Tampermonkey should automatically open a new tab asking if you want to install the script.
5.  Click "Install".

### Usage

1.  Navigate to a Jasperactive exercise page within the Office web application.
2.  The script will automatically run inside the simulation iframe.
3.  By default, interactive click boxes should appear with a red highlight.
4.  Press `Ctrl + Alt + B` to toggle the red highlights on or off. The script remembers your preference.

---

Feel free to report issues or suggest improvements via GitHub issues.
