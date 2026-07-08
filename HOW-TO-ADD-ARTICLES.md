# How to Add a New Blog Article

You no longer need to touch any HTML or JavaScript to publish a new post. Articles now
live as plain Markdown files in the `/posts` folder, and the site loads them automatically
when the page opens.

## Steps

1. **Create a new file** in the `posts/` folder.
   Name it after your article's slug, e.g. `posts/best-hosting-for-blogs.md`
   (lowercase, words separated by hyphens, no spaces).

2. **Add frontmatter** at the very top of the file, between two lines of `---`.
   Copy this template:

   ```
   ---
   title: Your Article Title Here
   excerpt: A one-to-two sentence summary shown on the blog card and in previews.
   author: James Mercer
   date: July 8, 2026
   readTime: 6 min read
   category: Guides
   image_color: linear-gradient(135deg,#667eea,#764ba2)
   ---
   ```

   - `category` is shown as a small pill/badge on the post card — use something like
     `WordPress`, `SEO`, `Guides`, `Reviews`, etc.
   - `image_color` is the CSS gradient used for the post's thumbnail (since there's no
     uploaded image). Pick any two colors, e.g. `linear-gradient(135deg,#43e97b,#38f9d7)`.
   - `date` is just displayed as text and also used to sort posts newest-first — write it
     however you like (e.g. `July 8, 2026`), just be consistent.

3. **Write your article** in plain Markdown underneath the closing `---`. Supported syntax:

   | You write                          | You get                          |
   |-------------------------------------|-----------------------------------|
   | `## Heading`                        | Section heading                  |
   | `### Subheading`                    | Smaller heading                  |
   | `- item`                            | Bullet list                      |
   | `1. item`                           | Numbered list                    |
   | `> quote`                           | Pull-quote / blockquote          |
   | `**bold**`                          | **Bold text**                    |
   | `[link text](https://example.com)`  | A link (external links automatically open in a new tab with the correct affiliate `rel` attributes) |

   For a highlighted callout/tip box (the yellow box style used in the existing articles),
   drop in this raw HTML directly in your Markdown file — it will render correctly:

   ```html
   <div class="callout">
     <div class="callout-title">💡 Pro Tip</div>
     <p>Your tip text goes here.</p>
   </div>
   ```

4. **Register the file** by adding its filename to `posts/manifest.json`:

   ```json
   [
     "best-hosting-for-blogs.md",
     "cheap-wordpress-hosting-2025.md",
     "shared-vs-vps-hosting.md",
     "website-speed-optimization.md",
     "best-hosting-small-business.md"
   ]
   ```

   Order in the manifest doesn't matter — posts are automatically sorted newest-first by
   their `date` field on the homepage.

5. **Commit and push** to your GitHub repo. Vercel will pick up the change and redeploy
   automatically (typically live within a minute or two).

That's it — no HTML editing, no JavaScript, no rebuilding the site by hand.

## Removing or unpublishing a post

Delete its line from `posts/manifest.json` (you can leave the `.md` file in place or delete
it too — either is fine, since only files listed in the manifest are loaded).

## Editing an existing post

Just open its `.md` file, edit the frontmatter or body, save, commit, and push.

## A note on images

This lightweight setup doesn't currently support uploading real photos for post thumbnails
— it uses CSS gradients (`image_color`) instead, to keep the site fast and free of image
hosting/CDN complexity. If you'd like to add real images later (e.g. a hero image per post,
or inline images within articles), that's a straightforward follow-up — Markdown supports
`![alt text](image-url.jpg)` natively, you'd just need to add an `/images` folder and
reference files there or link to externally hosted images.
