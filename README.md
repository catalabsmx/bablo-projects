# bablo-projects

Example projects for [Bablo XR](https://github.com/catalabsmx/bablo), listed by the app's `/examples` page.

Each `<name>-<uuid>.bablo` file is an **encrypted project zip** (the extension is only a convention):

- Layout: `[16 B salt | 12 B IV | AES-256-GCM ciphertext + tag]`, key derived from a passphrase with PBKDF2 (SHA-256, 100 000 iterations).
- Decrypted, it is a zip with `index.json`, `index.ts` and `media/<bucket>/<name>`; the app imports it as a new local project.
- The app finds projects by scanning this repository's root for `*.bablo` files, so adding one here adds it to the page.

Files are produced with `bun scripts/encrypt-zips.ts` in the Bablo XR repository; don't edit them by hand.
