# Timestamp Stack

[简体中文](README-zh.md)

A small notepad for temporary work notes. Each of its **8 rows** pairs an automatically generated timestamp with editable text. Records are saved to a local JSON file and loaded again when you reconnect.

## Get started

1. Open `index.html` in desktop Microsoft Edge or Google Chrome. No installation, local server, or Internet connection is needed.
2. Click **Connect database**, select the included `records.json`, and allow the browser to read and modify it. To start a separate database, click **New** and choose a new file name or location.
3. Click **Add** to create a timestamp, then type your note beside it.
4. Wait until the status says **Saved locally** before closing the page.

For your first new database, choose the folder containing `index.html` in the save dialog. Later, the dialog prefers the folder of the last database you selected. If the browser no longer remembers that file, the browser chooses the starting location.

The interface starts in **English** each time the page opens. Click **中文** to switch to Chinese, or **English** to switch back. Switching languages preserves your notes and does not change the database.

## Record notes

The table works like a nonstandard stack of up to 8 records: new entries go below existing ones, and entries in the middle can be edited or deleted. Deleting a record moves those below it up. Adding to a full table removes the oldest record at the top.

Timestamps are read only. They are created by **Add** and removed with their row. Clearing only a note leaves its timestamp in place, so the row still counts as occupied. Text can be edited or copied only when its row has a timestamp.

| Action | What happens |
| --- | --- |
| Add | Add a record below existing ones with the current timestamp. |
| Edit text | Edit or clear text; line breaks are supported. |
| Copy | Copy the cell's content to the clipboard. |
| Delete a row | Remove the record and move those below it up. |

## Saving and history

- Each text input event, addition, and deletion immediately queues a file save. Saves run in order; the status changes to **Saved locally** only after the file write finishes. There is no separate Save button.
- Your records are stored in the selected database file. The browser only tries to remember the file handle and its access permission; it does not store a separate copy of your notes.
- On reopening, the page tries to reconnect and read the file. If the browser asks for permission again, click **Connect database** and allow access. If offered, persistent file access can reduce future prompts.
- Clearing browser data or moving the HTML file may require selecting the database again. The history remains available as long as the database file is intact.
- To back up or move your notes, wait for **Saved locally**, then copy the database file. Open the HTML on the destination computer and connect to that copy.

Use one page to edit a database at a time. If another page or program changes the file, the app stops writing rather than overwriting those changes. Copy any unsaved text, then refresh and reconnect. If a permission or disk error appears, keep the page open, resolve the issue, and click **Retry** or **Allow access & retry**.

This version accepts databases with at most 8 records. A file containing more than 8 records is left unchanged and will not be opened; back it up and reduce its record count with the previous version first.

## Project files

| File | Purpose |
| --- | --- |
| `index.html` | The complete interface and application code. |
| `records.json` | The included local database containing your saved records. |
| `README.md` | English instructions. |
| `README-zh.md` | [Chinese instructions](README-zh.md). |
