# G.O. Odhiambo — Official Author Website (v2)

This is a simple static author website with a reader discussion feature:
- Novel collection and individual excerpt pages
- Free PDF links for books explicitly marked free
- Purchase/enquiry links for paid books
- Reader comments and replies
- Five-star ratings
- No reader accounts or login screens

## 1. Publish the files
Upload the contents of this folder to the ROOT of your GitHub repository, replacing the previous website files. Keep `index.html`, `reader.html`, `styles.css`, `books.js`, `script.js`, and `reader.js` at the root.

## 2. Set up the reader discussion database
1. Create a Supabase project (or use a separate project dedicated to this author website).
2. Open SQL Editor in Supabase.
3. Create a new query, paste all of `supabase-setup.sql`, and run it.
4. Open Project Settings > API (or API Keys, depending on the dashboard).
5. Copy the Project URL and the public anon/publishable key. NEVER use the service_role/secret key in website code.
6. Open `books.js` and replace:
   - `YOUR_SUPABASE_PROJECT_URL`
   - `YOUR_SUPABASE_ANON_OR_PUBLISHABLE_KEY`
7. Replace `YOUR-EMAIL@example.com` with your real author contact email.

## 3. Add your real book information
Edit the `books` list in `books.js`. Replace placeholder descriptions and excerpts with approved text.
- `access: "paid"` shows an enquiry link.
- `access: "free"` plus a real `pdf` path displays a free PDF button.
- Set `purchaseUrl` to a real payment/book-order page if you have one. Leave blank to use email enquiry.
- Never upload paid full-book PDFs into a public GitHub repository. The repository is public, so its files can be downloaded by anyone.

## 4. Supabase security and moderation notes
The SQL uses Row Level Security and permits public reading and submission of comments and ratings. It does not create reader accounts. The rating code stores a browser-generated token so the same browser can update its rating for a book. This is a convenience, NOT strong identity verification: a visitor can clear browser data or use another device to rate again. Public comment forms can also attract spam. Before a large public launch, add moderation (for example, a review queue) and stronger anti-spam protection such as a CAPTCHA or a server-side function with rate limiting.

The SQL validates the book slugs and comment lengths. Replies are limited to one level (a reply to a top-level comment), which keeps discussions readable. This starter version displays comments immediately; remove abusive comments through the Supabase Table Editor. Do not expose a Supabase service-role key in client-side files.

## 5. GitHub Pages
In repository Settings > Pages:
- Source: Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`
Save. GitHub will show the published URL after deployment.

## Files
- `index.html` — homepage and book discussion modal
- `reader.html` / `reader.js` — excerpt reading page
- `styles.css` — responsive styling
- `books.js` — book details and public Supabase settings
- `script.js` — catalogue, comments, replies and ratings
- `supabase-setup.sql` — database setup
