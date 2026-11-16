# G.O. Odhiambo — Official Author Website

A simple static author website for GitHub Pages. No reader accounts or login are required.

## Files
- `index.html` — homepage and novel collection
- `reader.html` — online sample-reading page
- `styles.css` — design and responsive layout
- `books.js` — novel descriptions, sample text, free/paid status and PDF links
- `script.js` — interactions

## Important before publishing
1. Open `books.js`.
2. Replace `YOUR-EMAIL@example.com` with your real author email.
3. Replace each sample description and sample text with your approved book material.
4. For a free PDF, put the PDF in `books/` and set its `pdf` field to its path, for example `books/free-title.pdf`.
5. For a paid book, do not put the complete paid PDF in this public repository. GitHub Pages is public hosting and cannot protect a PDF from direct access. Use the enquiry link or a trusted sales/delivery service for paid copies.
6. Set `access: "free"` for free books and `access: "paid"` for books available by purchase enquiry.

## Publish with GitHub Pages
1. Create a public GitHub repository.
2. Upload all files and folders in this project to the repository root (not inside an extra nested project folder).
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch **main** and folder **/(root)**, then Save.
6. Wait for GitHub Pages to publish and open the URL shown in Settings → Pages.

## Add a free PDF
Upload the PDF into the `books` folder. In `books.js`, update that book's `pdf` value to the exact filename, e.g. `books/borrowed-tomorrow.pdf`.

## Add a paid purchase link
Set `PURCHASE_LINK` in `books.js` to a real enquiry or checkout URL. If it is blank, the site uses the email address set in `CONTACT_EMAIL`.
