# M4L-Quill
A rich text editor using [Quill.js](https://github.com/slab/quill) for Ableton Live / Max for Live. This can be used for saving and viewing text notes within your Live Set

Tested with:
Quill.js == 2.0.3
Ableton Live == 12.2.5
Max == 9.0.7

## Installation
  * Clone/unzip the repo into your Ableton User Library.
  * Download the Quill library file into your /M4L-Quill folder.
    - [https://cdn.jsdelivr.net/npm/quill@2/dist/quill.js](https://cdn.jsdelivr.net/npm/quill@2/dist/quill.js)
  * Download the Quill "snow" stylesheet into your /M4L-Quill folder.
    - [https://cdn.jsdelivr.net/npm/quill@2/dist/quill.snow.css](https://cdn.jsdelivr.net/npm/quill@2/dist/quill.snow.css)
  * Drag the M4L-Quill.amxd device into your Live Set on a MIDI track.

If the Quill links aren't working, check the [Quickstart section on the Quill.js repo page](https://github.com/slab/quill?tab=readme-ov-file#quickstart).

## How it works
 * M4L-Quill.amxd is a Max for Live device you can insert into an Ableton Live set.
 * m4l.quill.html is a web page loaded by the [jweb] object. This imports the other files, initializes the HTML elements, and contains the JS functions for initializing Quill and communicating with Max.
 * m4l.quill.css has some basic style customizations.
 * quill.js is the Quill library file that actually runs the editor.
 * quill.snow.css is one of the default Quill stylesheets.

## Usage Notes
 * The OPEN toggle displays the M4L-Quill window.
 * The GET Button moves the M4L-Quill window to the current cursor location. This is useful if the M4L-Quill window has somehow ended up offscreen, which may happen if you change display arrangements.
 * The Toolbar toggle shows/hides the formatting toolbar in the M4L-Quill window.
 * The "+" toggle shows/hides some advanced formatting options on the toolbar. These are probably things you don't need or may not work consistently.
 * The "border" and "background" buttons let you customize the RGB color of the M4L-Quill window. This may be useful if you have multiple M4L-Quill windows.
 * The "window title" [textedit] customizes the popup window's title bar. This may be useful if you have multiple M4L-Quill windows.

## Special Considerations
 * You should be able to copy/paste rich text freely into and out of the M4L-Quill window. Since M4L-Quill doesn't have a save/load file function, this is especially useful for copying into an external rich text editor to save.
 * M4L-Quill contents are saved in the Live set as HTML in a [textedit] Blob as a Parameter. There could be some special characters or unescaped HTML code that may interrupt that process. Basic text and formatting should be fine, but you may encounter problems with other contents.
 * The M4L-Quill window size/location is also saved in the Live set. However, the device only queries the window size/location when you start/play the Transport. You must hit Play at least once after resizing the window to push the values into the device's paramters, then they will be saved with the Live set.
