# From Me to You

A small static website for a personal NFC bracelet gift.

## Files

- `index.html`: recipient page. It selects the message for the current local date and displays the saved image/GIF and MP3.
- `editor.html`: local editor. It imports the existing encrypted messages, lets you edit dates and attachments, then encrypts and downloads `messages.enc.json`.
- `messages.enc.json`: your encrypted messages file. Keep your existing copy safe.

## Important: preserve your existing key and messages

- Always use the same private encryption key that was used for your current `messages.enc.json`.
- Do not create a new key when updating existing messages.
- Keep a backup copy of your current `messages.enc.json` before replacing it on GitHub.
- Never share your private key in chat or with anyone else.
- The editor works in your browser. The private key is not uploaded by the editor.
- The encrypted message file is public, but its contents are encrypted with AES-GCM. Anyone with the complete recipient link (including the part after `#`) can decrypt the messages. Do not put highly sensitive information in it.
- This is a small personal project, not a professionally audited security product.

## Updating existing messages

1. Open `editor.html` in a modern browser.
2. Paste your existing private encryption key into the key field.
3. Import your latest `messages.enc.json`.
4. Select a saved date (or use **Edit this date** in the saved-date list).
5. Edit the nickname, message, closing line, or song title. Choose a new image/GIF or MP3 only if you want to replace that attachment.
6. Click **Save / update date**.
7. Click **Encrypt & download messages.enc.json**.
8. Keep a backup of the old encrypted file, then upload the newly downloaded file to GitHub and replace the repository's `messages.enc.json`.
9. Open the recipient website and test the date's message and attachments.

Existing image and audio attachments are preserved when you edit other fields. Choosing a new file replaces that attachment for that date. Current limits are 1 MB for images/GIFs and 3 MB for MP3 files.

## GitHub Pages

The website can be published with GitHub Pages from the repository's `main` branch and root folder. The recipient page reads `messages.enc.json` from the same folder.

## Timezone

The recipient page uses the device's local date. If the recipient is in a different timezone, the date may change at a different time.
