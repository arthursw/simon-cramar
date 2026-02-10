# Content Creation & Editing Guide

Complete guide to creating and managing content on your Hugo website.

---

## Table of Contents

1. [Setup Your Editor](#setup-your-editor)
2. [Understanding Content Structure](#understanding-content-structure)
3. [Writing in Markdown](#writing-in-markdown)
4. [Adding Images](#adding-images)
5. [Adding Videos](#adding-videos)
6. [Creating New Pages](#creating-new-pages)
7. [Managing Menus](#managing-menus)
8. [Publishing Your Changes](#publishing-your-changes)
9. [Quick Reference](#quick-reference)

---

## Setup Your Editor

### 1. Open Your Project

1. **Launch VSCodium**
2. **Open your site folder**: File > Open Folder
3. Navigate to your Hugo site directory and click "Open"

### 2. Start the Live Preview Server

1. **Open a new terminal**: Terminal menu > New Terminal
2. **Run the Hugo server**:
   ```bash
   hugo serve
   ```
3. You'll see output like:
   ```
   Web Server is available at http://localhost:1313/
   ```
4. **Open this URL** in your web browser

### 3. Setup Your Workspace

- Keep **VSCodium** on one side of your screen
- Keep your **browser** on the other side
- Changes you make will automatically appear in the browser!

:::tip
Press `Cmd+S` (Mac) or `Ctrl+S` (Windows/Linux) to save files. The browser will refresh automatically.
:::

---

## Understanding Content Structure

### What is Hugo Content?

All your website content lives in the `content/` folder. Each page is a **Markdown file** (`.md`) with two main parts:

```markdown
---
title: Page Title
description: Page description
---

# Content starts here

Your text, images, and formatting go below the frontmatter.
```

### Anatomy of a Content File

#### 1. **Frontmatter** (Metadata)

The section between `---` marks at the top of the file. This tells Hugo about your page.

**Basic example:**
```yaml
---
title: About Me
description: Learn more about my work
---
```

**Advanced example from this site** (`content/a-propos.md`):
```yaml
---
title: À propos
description: À propos de Simon Cramar
layout: prose
menus:
  main:
    name: À propos
    weight: 4
---
```

**Common frontmatter fields:**
- `title`: Page title (required)
- `description`: Brief description for SEO
- `date`: Publication date (YYYY-MM-DD format)
- `layout`: Template layout to use
- `menus`: Menu configuration (see [Managing Menus](#managing-menus))
- `weight`: Order in lists (lower numbers appear first)

#### 2. **Content** (Your Page Body)

Everything below the second `---` is your page content, written in **Markdown**.

**Example from this site** (`content/a-propos.md`):
```markdown
---
title: À propos
description: À propos de Simon Cramar
layout: prose
---

# Simon Cramar

**"Chasseur d'images, capturant l'espace-temps..."**

A 10 ans, j'ai reçu le plus grand cadeau qu'il soit : mon premier appareil photo !

Il m'a appris à découvrir le monde. Il m'a ouvert les yeux, jusqu'à voler dans les cieux!
```

---

## Writing in Markdown

Markdown is a simple formatting language. You write plain text with special characters to add styling.

### Headers

Use `#` symbols for headers. More `#` = smaller header.

```markdown
# Main Title (H1)
## Section Title (H2)
### Subsection (H3)
#### Small Heading (H4)
```

**Renders as:**

# Main Title (H1)
## Section Title (H2)
### Subsection (H3)
#### Small Heading (H4)

---

### Text Formatting

```markdown
**Bold text** or __bold text__
*Italic text* or _italic text_
***Bold and italic together***
~~Strikethrough~~
```

**Renders as:**

**Bold text**
*Italic text*
***Bold and italic together***
~~Strikethrough~~

**Example from this site** (`content/materiel.md`):
```markdown
**Bien que "l'outil ne fasse pas l'image"...**
```

---

### Lists

#### Bullet Points (Unordered Lists)

```markdown
- First item
- Second item
- Third item
  - Nested item
  - Another nested item
    - Even deeper nesting
- Back to main level
```

**Renders as:**

- First item
- Second item
- Third item
  - Nested item
  - Another nested item
    - Even deeper nesting
- Back to main level

#### Numbered Lists (Ordered Lists)

```markdown
1. First step
2. Second step
3. Third step
   1. Substep A
   2. Substep B
4. Fourth step
```

**Renders as:**

1. First step
2. Second step
3. Third step
   1. Substep A
   2. Substep B
4. Fourth step

**Example from this site** (`content/materiel.md`):
```markdown
## Optiques

- **Panasonic 12-35mm f/2.8**
- **Panasonic 35-100mm f/2.8**
- **Panasonic 7-14mm f/4**
```

---

### Links

```markdown
[Link text](https://example.com)
[Link with title](https://example.com "Hover text")
```

**Internal links** (to other pages on your site):
```markdown
[About page](/about/)
[Contact](/contact/)
```

---

### Quotes

```markdown
> This is a blockquote.
> It can span multiple lines.
>
> And multiple paragraphs.
```

**Renders as:**

> This is a blockquote.
> It can span multiple lines.
>
> And multiple paragraphs.

---

### Code

#### Inline Code

Use backticks for inline code:
```markdown
Use the `hugo serve` command to start the server.
```

**Renders as:**

Use the `hugo serve` command to start the server.

#### Code Blocks

Use triple backticks with optional language:

````markdown
```python
def hello_world():
    print("Hello, World!")
```
````

**Renders as:**

```python
def hello_world():
    print("Hello, World!")
```

---

### Horizontal Lines

```markdown
---
```

**Renders as:**

---

### Tables

```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |
```

**Renders as:**

| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |

**Learn more:** [Complete Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

---

## Adding Images

There are **two methods** for adding images to your Hugo site.

### Method 1: Images in `static/images/` Folder

**Best for:** Shared images used across multiple pages, site-wide assets.

#### Step 1: Add Your Image Files

**Option A: Using VSCodium**
1. In VSCodium, right-click on `static/images/` folder
2. Select **"New Folder"** to create a category (e.g., `portfolio`, `blog`, `products`)
3. Right-click the new folder
4. Select **"Reveal in Finder"** (Mac) or **"Reveal in File Explorer"** (Windows)
5. Copy your image files into this folder

**Option B: Using GitHub (for existing sites)**
1. Go to your repository on GitHub.com
2. Navigate to `static/images/`
3. Click **"Add file"** → **"Upload files"**
4. Drag and drop your images
5. Commit the changes

#### Step 2: Reference Images in Your Content

Use this syntax:
```markdown
![Alt text description](/images/folder-name/image-name.jpg)
```

**Important notes:**
- Path starts with `/images/` (the static folder is omitted)
- Always provide alt text for accessibility
- Supported formats: `.jpg`, `.png`, `.gif`, `.svg`, `.webp`

#### Real Example from this Site

**File structure:**
```
static/
  images/
    materiel/
      camera-1.jpg
      camera-2.jpg
```

**In `content/materiel.md`:**
```markdown
# Matériel

**Bien que "l'outil ne fasse pas l'image"...**

Voici le matériel que j'utilise sur mes projets.

![Équipement photo et vidéo](/images/materiel/camera-1.jpg)

## Caméras

### Panasonic GH5
- **Résolution capteur :** 20,3 Mpx
- **Vidéo :** Ultra HD 4K en 60ips

![Supports et accessoires](/images/materiel/camera-2.jpg)

## Supports

### Trépied Benro S6
Trépied en carbone avec tête vidéo fluide.
```

---

### Method 2: Page Bundle with Resources

**Best for:** Page-specific images that belong to a single page (like post covers, galleries).

#### Step 1: Convert Your Page to a Bundle

Instead of a single file like `my-page.md`, create:
```
content/
  my-page/
    index.md          ← Your page content
    cover.jpg         ← Images in the same folder
    photo1.jpg
    photo2.jpg
```

#### Step 2: Declare Resources in Frontmatter

```markdown
---
title: My Page
description: A page with bundled images
resources:
  - src: cover.jpg
    params:
      cover: true
  - src: photo1.jpg
    title: First Photo
  - src: photo2.jpg
    title: Second Photo
---

Page content here...
```

#### Step 3: Reference Images

Since images are in the same folder, you can reference them directly:
```markdown
![Description](photo1.jpg)
```

Or use the resource path:
```markdown
![Description](./photo1.jpg)
```

#### Real Example from this Site

**File structure:**
```
content/
  videos/
    clip/
      index.md
      cover.jpg       ← Cover image for this category
```

**In `content/videos/clip/index.md`:**
```markdown
---
title: CLIP
date: 2024-01-03
description: Clips musicaux
sort_by: Date
sort_order: desc
resources:
  - src: cover.jpg
    params:
      cover: true
videos:
  - url: https://www.youtube.com/watch?v=kau_K_asQKQ
    title: Jusqu'à (CLIP à Louvain-la-Neuve)
    date: 2017-01-01
---

Clips musicaux mêlant créativité visuelle et ambiance musicale.
```

The `cover.jpg` is used by the theme as a featured image for this video category.

---

### Image Best Practices

#### Optimization
- **Compress images** before uploading (use tools like [TinyPNG](https://tinypng.com/))
- **Use appropriate sizes**: Don't upload 4000px images if they'll display at 800px
- **Choose the right format**:
  - `.jpg` for photos
  - `.png` for graphics with transparency
  - `.webp` for modern browsers (smaller file size)

#### Naming Conventions
- Use lowercase letters
- Use hyphens instead of spaces: `my-image.jpg` not `My Image.jpg`
- Be descriptive: `product-camera-front.jpg` not `img001.jpg`

#### Alt Text
Always provide meaningful alt text:
```markdown
✓ Good: ![Panasonic GH5 camera on tripod](/images/camera.jpg)
✗ Bad:  ![camera](/images/camera.jpg)
✗ Bad:  ![](/images/camera.jpg)
```

---

## Adding Videos

### YouTube Embeds

The most common way to add videos is through YouTube embeds in your frontmatter.

#### Method: Frontmatter Video List

**Real example from this site** (`content/videos/clip/index.md`):

```markdown
---
title: CLIP
date: 2024-01-03
description: Clips musicaux
videos:
  - url: https://www.youtube.com/watch?v=kau_K_asQKQ
    title: Jusqu'à (CLIP à Louvain-la-Neuve)
    date: 2017-01-01
  - url: https://www.youtube.com/watch?v=buOTKcu__lY
    title: Edel Sheep - Flesh to Dust
    date: 2016-01-01
---

Clips musicaux mêlant créativité visuelle et ambiance musicale.
```

This creates a page with embedded YouTube players for each video.

#### How to Get YouTube URLs

1. Go to the video on YouTube
2. Click the **Share** button
3. Copy the URL (e.g., `https://www.youtube.com/watch?v=kau_K_asQKQ`)
4. Add it to your frontmatter

#### Theme-Specific Video Handling

:::warning
Video embedding syntax depends on your Hugo theme. Check your theme's documentation for:
- Shortcodes for embedding videos
- Custom frontmatter fields
- Video gallery layouts
:::

### HTML5 Video (Self-Hosted)

If you host video files yourself:

1. **Add video to `static/videos/`**:
   ```
   static/
     videos/
       my-video.mp4
   ```

2. **Embed in markdown** (if your theme supports HTML):
   ```html
   <video controls>
     <source src="/videos/my-video.mp4" type="video/mp4">
     Your browser doesn't support video playback.
   </video>
   ```

:::note
Self-hosted videos increase page load time and bandwidth usage. YouTube/Vimeo hosting is usually better for performance.
:::

---

## Creating New Pages

### Simple Page

1. **In VSCodium**, right-click the `content/` folder
2. Select **"New File"**
3. Name it `my-new-page.md`
4. Add frontmatter and content:

```markdown
---
title: "My New Page"
description: "A brief description for SEO"
---

# Welcome to My Page

This is my new page content.

## Section 1

Some text here...

## Section 2

More content...
```

5. **Save** (Cmd+S / Ctrl+S)
6. **Check your browser** - the page should appear at `http://localhost:1313/my-new-page/`

---

### Page with Images (Bundle)

1. **Create a folder** in `content/`: right-click → "New Folder" → name it `my-gallery`
2. **Create `index.md`** inside `my-gallery/`
3. **Copy image files** into the `my-gallery/` folder
4. **Add content**:

```markdown
---
title: "My Photo Gallery"
description: "A collection of my best photos"
---

# My Photo Gallery

Check out these amazing photos!

![First photo](photo1.jpg)
![Second photo](photo2.jpg)
![Third photo](photo3.jpg)
```

5. **Save** and check browser: `http://localhost:1313/my-gallery/`

---

### Real Example: Creating a "Services" Page

Let's create a complete services page inspired by this site's structure:

**File:** `content/services.md`

```markdown
---
title: Services
description: Professional photography and videography services
layout: prose
menus:
  main:
    name: Services
    weight: 3
---

# My Services

**"Capturing your moments, telling your story."**

## Photography

### Portrait Photography
Professional portraits for:
- **Headshots** - Business and personal branding
- **Family portraits** - Capturing family memories
- **Events** - Weddings, celebrations, corporate events

![Portrait photography examples](/images/services/portraits.jpg)

### Commercial Photography
- Product photography
- Real estate
- Corporate events
- Food & beverage

## Video Production

### Music Videos
Creative direction and production for:
- Indie artists
- Bands
- Solo performers

### Corporate Videos
- Promotional videos
- Company presentations
- Training materials
- Event coverage

![Video production setup](/images/services/video-setup.jpg)

## Aerial Photography & Video

Certified drone pilot offering:
- Real estate aerial shots
- Event coverage from above
- Landscape photography
- Construction progress documentation

## Equipment

I use professional-grade equipment including:
- **Cameras:** Panasonic GH5, GH3
- **Lenses:** 12-35mm f/2.8, 35-100mm f/2.8, 7-14mm f/4
- **Drones:** DJI Mavic Pro
- **Stabilization:** Zhiyun Crane gimbal

## Contact

Interested in working together? [Get in touch!](/contact/)
```

This page includes:
- ✓ Structured content with headers
- ✓ Bold text for emphasis
- ✓ Bullet lists
- ✓ Images
- ✓ Internal links
- ✓ Menu integration

---

## Managing Menus

### Adding a Page to the Main Menu

Add this to your page's frontmatter:

```markdown
---
title: My Page
menus:
  main:
    name: My Page
    weight: 10
---
```

**Fields:**
- `main`: The menu identifier (usually "main" for header menu)
- `name`: Text displayed in menu
- `weight`: Order (lower numbers appear first)

**Example menu weights:**
```
Home      - weight: 1
About     - weight: 2
Services  - weight: 3
Portfolio - weight: 4
Contact   - weight: 5
```

### Real Example from this Site

**In `content/a-propos.md`:**
```markdown
---
title: À propos
description: À propos de Simon Cramar
layout: prose
menus:
  main:
    name: À propos
    weight: 4
---
```

This adds "À propos" to the main menu as the 4th item.

### Multiple Menus

If your theme supports footer menus or other locations:

```markdown
---
title: Privacy Policy
menus:
  main:
    name: Privacy
    weight: 10
  footer:
    name: Privacy Policy
    weight: 2
---
```

---

## Publishing Your Changes

Once you're happy with your edits, push them to GitHub so Cloudflare can rebuild your site.

### Step 1: Review Changes

1. **Click the Source Control icon** in VSCodium's left sidebar (3rd icon, looks like a branch)
2. You'll see all modified files listed
3. Click on files to see what changed (green = added, red = removed)

### Step 2: Stage Changes

- All changed files should be automatically staged
- If not, click the **+** icon next to each file

### Step 3: Commit

1. **Write a commit message** in the text box at the top
   - Be descriptive: "Added services page and updated about section"
   - Not: "updates" or "changes"
2. **Click the ✓ Commit button**

### Step 4: Push to GitHub

1. **Click "Sync Changes"** or **"Push"** button
2. If prompted, authenticate with GitHub
3. Wait for the push to complete

### Step 5: Wait for Deployment

1. Cloudflare automatically detects the changes
2. Builds your site (usually 1-2 minutes)
3. Deploys to your live URL
4. Check your live site: `your-site-name.pages.dev`

:::tip
You can watch the build progress:
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Click on your Pages project
3. Click "View build" to see real-time logs
:::

---

## Quick Reference

### Markdown Syntax

| Element | Syntax |
|---------|--------|
| Bold | `**text**` or `__text__` |
| Italic | `*text*` or `_text_` |
| Bold + Italic | `***text***` |
| Header 1 | `# Text` |
| Header 2 | `## Text` |
| Header 3 | `### Text` |
| Bullet list | `- item` |
| Numbered list | `1. item` |
| Link | `[text](url)` |
| Image | `![alt](/path/to/image.jpg)` |
| Quote | `> text` |
| Inline code | `` `code` `` |
| Code block | ` ```language` <br> `code` <br> ` ``` ` |
| Horizontal line | `---` |

### Common Tasks

| Task | How To |
|------|--------|
| Create new page | Right-click `content/` → New File → `page-name.md` |
| Add to menu | Add `menus:` section in frontmatter |
| Add image (static) | Put in `static/images/`, reference as `![alt](/images/file.jpg)` |
| Add image (bundle) | Put in same folder as `index.md`, reference as `![alt](file.jpg)` |
| Preview site | Run `hugo serve` in terminal |
| Stop preview | Press `Ctrl+C` in terminal |
| Publish changes | Source Control → Commit → Push |

### File Paths

| Type | Example |
|------|---------|
| Static image | `/images/folder/image.jpg` |
| Bundle image | `image.jpg` or `./image.jpg` |
| Internal link | `/about/` or `/blog/my-post/` |
| External link | `https://example.com` |

### Frontmatter Fields

| Field | Purpose | Example |
|-------|---------|---------|
| `title` | Page title | `title: About Me` |
| `description` | SEO description | `description: Learn about my work` |
| `date` | Publication date | `date: 2024-01-15` |
| `layout` | Template to use | `layout: prose` |
| `menus` | Menu placement | See [Managing Menus](#managing-menus) |
| `weight` | Sort order | `weight: 5` |
| `resources` | Page bundle resources | See [Method 2](#method-2-page-bundle-with-resources) |

---

## Troubleshooting

### Preview Server Issues

**Problem:** `hugo serve` command not found
**Solution:** Make sure Hugo is installed. Run the installation command from the quickstart guide.

**Problem:** Port already in use
**Solution:** Run `hugo serve -p 1314` to use a different port.

**Problem:** Changes not appearing
**Solution:** Hard refresh browser (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)

### Image Issues

**Problem:** Image not showing
**Solution:**
- Check file path (case-sensitive!)
- Verify image is in correct folder
- Check file extension matches actual file type
- Make sure path starts with `/images/` for static images

**Problem:** Image too large/slow to load
**Solution:** Compress image before uploading using [TinyPNG](https://tinypng.com/)

### Publishing Issues

**Problem:** Push failed
**Solution:**
- Pull latest changes first: `git pull`
- Check GitHub authentication
- Verify network connection

**Problem:** Site not updating after push
**Solution:**
- Wait 2-3 minutes for Cloudflare build
- Check Cloudflare Pages dashboard for build errors
- Clear browser cache

---

## Resources

- [Markdown Guide](https://www.markdownguide.org/) - Complete Markdown reference
- [Hugo Documentation](https://gohugo.io/documentation/) - Official Hugo docs
- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/) - Deployment help
- [TinyPNG](https://tinypng.com/) - Image compression tool
- [Unsplash](https://unsplash.com/) - Free stock photos

---

**Happy content creating! 🎉**
