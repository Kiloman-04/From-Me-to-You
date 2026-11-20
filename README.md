# From Me to You — Daily Message

A small static website for a personal NFC bracelet gift.

## Files
- `index.html`: recipient page. It selects the message for the current local date.
- `editor.html`: local editor. It encrypts messages in your browser and downloads `messages.enc.json`.
- `messages.enc.json`: encrypted messages published beside the pages.

## Important privacy and security notes
This is a starter prototype, not a professionally audited security product. The encrypted message file is public, but its contents are encrypted with AES-GCM. Anyone who has the recipient URL fragment (the part after `#`) can decrypt the messages. Do not put highly sensitive information in it. The editor runs in your browser; do not assume a public static site can provide secure server-side authentication.

Keep the encryption key in a safe place. If you lose it, existing messages cannot be recovered. If you create a new key, you must re-encrypt all messages and update the recipient link.

## First-time setup
1. Upload `index.html`, `editor.html`, and this README to your GitHub repository.
2. Open `editor.html` locally in a modern browser (or via your published site).
3. Click **Create a new key** and save the key securely.
4. Add messages for dates and click **Encrypt & download messages.enc.json**.
5. Upload the downloaded `messages.enc.json` to the repository and commit it.
6. Enable GitHub Pages: repository **Settings → Pages → Deploy from a branch → main → /(root) → Save**.
7. Your site address will look like `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.
8. Give the recipient a URL ending in `#YOUR_PRIVATE_KEY`. The key after `#` is not sent to the web server, but anyone with the full link can read the messages.

## Updating
Open the editor, paste the same key, add/edit/delete dates, download the new encrypted file, and upload it to GitHub to publish. For now, entries are held in the editor tab's memory until you download the encrypted file; keep your own copy of the source messages too.

## Timezone
The recipient page uses the device's local date. If the recipient is in a different timezone, the date may change at a different time.

## Cost
GitHub Pages is free for eligible public repositories under GitHub's current plan terms. Service limits and policies can change. The NFC tag itself is a one-time hardware purchase.
