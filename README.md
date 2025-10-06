# M4L-Quill
A rich text editor using [Quill.js](https://github.com/slab/quill) for Ableton Live / Max for Live. This can be used for saving and viewing text notes within your Live Set

## Installation
  * Clone/unzip the repo into your Ableton User Library.
  * Download the Quill library file into your /M4L-Quill folder.
    - [https://cdn.jsdelivr.net/npm/quill@2/dist/quill.js](https://cdn.jsdelivr.net/npm/quill@2/dist/quill.js)
  * Download the Quill "snow" stylesheet into your /M4L-Quill folder.
    - [https://cdn.jsdelivr.net/npm/quill@2/dist/quill.snow.css](https://cdn.jsdelivr.net/npm/quill@2/dist/quill.snow.css)
  * Drag the M4L-Quill.amxd device into your Live Set on a MIDI track.

If the Quill links aren't working, check the Quickstart selection on the [Quill.js repo page]([https://github.com/slab/quill](https://github.com/slab/quill?tab=readme-ov-file#quickstart)).

## Usage Notes
 * M4L-Quill contents should be saved in the Live set. This is done by saving the HTML representation in a [text] Blob as a Parameter. There could be some special characters or unescaped HTML code that may interrupt that process. Basic text and formatting should be fine, but you may encounter problems with other contents.
 * You should be able to copy/paste rich text freely into and out of the M4L-Quill window. Since M4L-Quill doesn't have a save/load file function, this is especially useful for copying into an external rich text editor to save.
 * The OPEN toggle displays the M4L-Quill window.
 * The GET Button moves the M4L-Quill window to the current cursor location. This is useful if the M4L-Quill window has somehow ended up offscreen, which may happen if you change display arrangements.
 * The M4L-Quill window size/location is also saved in the Live set. However, the device only queries the window size/location when you start/play the Transport. You must hit Play at least once after resizing the window to push the values into the device's paramters, then they will be saved with the Live set.
