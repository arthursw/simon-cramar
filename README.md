---
title: Quickstart
description: Get your static website online in minutes with a single command.
---


This guide will take you from zero to a live website in the fastest way possible. No coding knowledge required — just copy, paste, and follow the steps.

- ✓ Create a Hugo website with a theme of your choice
- ✓ Upload it to GitHub
- ✓ Deploy it to Cloudflare Pages (with a free URL)
- ✓ Learn how to edit your content

Read those guides for more details about content creation:
- [CONTENT-GUIDE-EN](CONTENT-GUIDE-EN.md)
- [CONTENT-GUIDE-FR](CONTENT-GUIDE-FR.md)

---

## Step 1: Prerequisites

Before we start, you need two free accounts:

1. **A GitHub account** — [Sign up here](https://github.com/join)
   - This is where your website's code will be stored

2. **A Cloudflare account** — [Sign up here](https://dash.cloudflare.com/sign-up)
   - This is where your website will be hosted and published

3. **Download VSCodium**
   - This is a code editor which also enables to upload code on Github
   - If you already have VS Code or an equivalent tool you can skip this step
   - [Download](https://vscodium.com/#install)

4. **Choose a Hugo theme**
   - Browse themes at [themes.gohugo.io](https://themes.gohugo.io/)
   - Find one you like and copy its GitHub URL:
      - Click the theme to go the to theme page
      - Click the download button to go the Github repository of the theme,
      - Click the green Code button
      - Make sure the "Local" tab, and the HTTPS tab
      - Copy the URL, it must be like https://github.com/nunocoracao/blowfish.git

---

## Step 2: Get Your Command

Go to the [**Command Generator**](/command-generator) page to create your custom installation command.

You'll need to provide:
- **Site name**: A name for your website (no spaces, lowercase recommended)
- **Theme URL**: The GitHub URL you copied in Step 1
- **Folder path**: Where you want the site saved on your computer. 

:::note
A new folder will be created for your site. Choose the parent folder which will contain your site folder.
:::

The generator will show you the command to run. Click the copy button.

:::tip[How to copy a folder path]
- **Mac**: Right-click the folder → Hold Option → Click "Copy as Pathname"
- **Windows**: Shift + Right-click the folder → "Copy as path"
- **Linux**: Right-click the folder → "Copy" or use Ctrl+Shift+C in the terminal
:::

---

## Step 3: Create Your Site

Now you'll run the command to create your website.

### Mac / Linux

1. Open **Terminal** (you can find it in Applications → Utilities)
2. Paste the command you copied (Cmd+V)
3. Press **Enter** to run it

### Windows

1. Open **PowerShell** (press Windows key, type "PowerShell", press Enter)
2. Paste the command you copied (Ctrl+V)
3. Press **Enter** to run it

:::tip[How to paste in terminal]
- **Mac Terminal**: Cmd+V
- **Windows PowerShell**: Right-click to paste
- **Linux Terminal**: Ctrl+Shift+V
:::

The script will:
- Install necessary tools (Pixi, Git, Hugo)
- Create your Hugo site with the chosen theme
- Set up a README and .gitignore file

Wait for it to complete. This may take a few minutes.

---

## Step 4: Upload to GitHub

Now let's put your site on GitHub so Cloudflare can access it.

1. **Open VSCodium**

2. **Open your site folder**
   - Click "Open..." (or File menu > Open Folder)
   - Select your site folder (the one created by the previous command)
   - You can trust the authors (if you trust this site, the Hugo developers and Hugo theme developers)

3. **Publish to GitHub**
   - Click the **Source Control** icon in the left sidebar (the third button which looks like a branch icon)
   - Click the blue **Publish to Github** button
   - "The extension 'GitHub' wants to sign in using GitHub." > Allow
   - Your Code: 76B7-3401 "To finish authenticating, navigate to GitHub and paste in the above one-time code." > Copy and continue to Github
   - Do you want VSCodium to open the external website? > Open
   - On Github: Device Activation > Signed in as username: Green button: Continue
   - Green button: Authorize Visual Studio Code 
   - VSCodium: Publish to Github public repository
   - If asked, validate the default file selection with enter
   - Blue button: Publish branch

4. **View on GitHub**
   - Go to Github.com/your-username/your-sitename/ to see your site repository

Your code is now on GitHub! 🎉

---

## Step 5: Deploy on Cloudflare Pages

Now let's make your website live!

1. **Go to Cloudflare**
   - Visit [dash.cloudflare.com](https://dash.cloudflare.com) and sign in
   - Or go directly to [dash.cloudflare.com/?to=/:account/workers-and-pages](https://dash.cloudflare.com/?to=/:account/workers-and-pages)

2. **Create a Pages project**
   - Click "Create application"
   - Scroll down to "Looking to deploy Pages?" and click **Get started**
   - In "Import an existing Git repository", click the "Get started" button
   - Make sure you are on the Github tab

3. **Connect to GitHub**
   - Click "Connect to GitHub"
   - Authorize Cloudflare if prompted
   - Select your site repository from the list
   - Click "Begin setup"

4. **Configure build settings**
   - **Project name**: Can be anything 
   - If you choose "your-site-name", your project will be deployed to your-site-name.pages.dev, but you can have a custom domain later (this is not free though).
   - **Production branch**: main
   - **Framework preset**: Select **Hugo** from the dropdown
   - Leave all other settings as default

5. **Deploy**
   - Click "Save and Deploy"
   - Wait for the build to complete (1-2 minutes)

6. **Visit your site**
   - You'll get a URL like `your-site-name.pages.dev`
   - Click it to see your live website!

🎉 **Your website is now live!**

---

## Step 6: Modify Your Content

Let's learn how to edit your website and create rich content with text, images, and videos.

### Setup Your Editor

1. **Open your site folder** in VSCodium: File > Open Folder
2. **Start the preview server**:
   - Open a new terminal: Terminal menu > New Terminal
   - Run `hugo serve` in the terminal
   - This creates a live preview that updates as you edit
3. **Open the preview URL** (something like `http://localhost:1313/`) in your browser
4. Keep VSCodium and your browser side-by-side to see changes in real-time

All your content lives in the `content/` folder. Let's explore how to create and edit it!

---

### Understanding Content Structure

Every page in Hugo is a Markdown file (`.md`) with two parts:

1. **Frontmatter** (metadata at the top, between `---`)
2. **Content** (your text, images, videos below the frontmatter)

**Example from this site** (`content/a-propos.md`):

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

# Simon Cramar

**"Chasseur d'images, capturant l'espace-temps..."**

A 10 ans, j'ai reçu le plus grand cadeau qu'il soit : mon premier appareil photo !
```

- **Frontmatter** tells Hugo about the page (title, description, menu placement)
- **Content** is written in Markdown and becomes your visible page

---

### Writing in Markdown

Markdown is a simple way to format text. Here's what you can do:

#### Headers
```markdown
# Main Title (H1)
## Section Title (H2)
### Subsection (H3)
```

#### Text Formatting
```markdown
**Bold text** or __bold text__
*Italic text* or _italic text_
***Bold and italic***
```

**Example from this site** (`content/materiel.md`):
```markdown
**Bien que "l'outil ne fasse pas l'image"...**
```

#### Lists

**Bullet points:**
```markdown
- First item
- Second item
  - Nested item
  - Another nested item
```

**Numbered lists:**
```markdown
1. First step
2. Second step
3. Third step
```

**Example from this site** (`content/materiel.md`):
```markdown
## Optiques

- **Panasonic 12-35mm f/2.8**
- **Panasonic 35-100mm f/2.8**
- **Panasonic 7-14mm f/4**
```

#### Links
```markdown
[Link text](https://example.com)
```

#### Quotes
```markdown
> This is a quote
> It can span multiple lines
```

**Learn more:** [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

---

### Adding Images

There are **two ways** to add images to your Hugo site:

#### Method 1: Images in `static/images/` folder (Recommended for shared images)

1. **Add your image file**:
   - In VSCodium, right-click on `static/images/` folder
   - Select "New Folder" to create a category (e.g., `materiel`)
   - Right-click the new folder and select "Reveal in Finder" (Mac) or "Reveal in File Explorer" (Windows)
   - Copy your image files into this folder

2. **Reference in your content**:
   ```markdown
   ![Alt text description](/images/folder-name/image-name.jpg)
   ```

**Example from this site** (`content/materiel.md`):
```markdown
![Équipement photo et vidéo](/images/materiel/camera-1.jpg)

## Caméras

### Panasonic GH5
- **Résolution capteur :** 20,3 Mpx

![Supports et accessoires](/images/materiel/camera-2.jpg)
```

#### Method 2: Page Bundle with Resources (For page-specific images)

1. **Convert your page to a bundle**:
   - Instead of `my-page.md`, create a folder `my-page/`
   - Inside, create `index.md` with your content
   - Add images directly in the same folder

2. **Reference in your frontmatter and content**:

**Example from this site** (`content/videos/clip/index.md`):
```markdown
---
title: CLIP
description: Clips musicaux
resources:
  - src: cover.jpg
    params:
      cover: true
---

Clips musicaux mêlant créativité visuelle et ambiance musicale.
```

The `cover.jpg` file is in the same folder as `index.md`.

---

### Adding Videos

For video content, you can embed YouTube videos in your frontmatter.

**Example from this site** (`content/videos/clip/index.md`):
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

This creates a video gallery page with embedded YouTube players.

:::note
The exact video embedding method depends on your theme. Check your theme's documentation for specific instructions.
:::

---

### Creating a New Page

1. **In VSCodium**, right-click the `content/` folder → "New File"
2. **Name it** `my-new-page.md`
3. **Add frontmatter** at the top:
   ```markdown
   ---
   title: "My New Page"
   description: "A brief description"
   ---
   ```
4. **Write your content** using Markdown below the frontmatter
5. **Save** (Cmd+S / Ctrl+S)
6. **Check the preview** in your browser (it should appear automatically)

**Example** - Creating a "Services" page:
```markdown
---
title: Services
description: What I offer
layout: prose
menus:
  main:
    name: Services
    weight: 3
---

# My Services

## Photography

I specialize in:
- **Portrait photography**
- **Event coverage**
- **Commercial shoots**

![My camera setup](/images/my-camera.jpg)

## Video Production

- Music videos
- Corporate videos
- Weddings and events

Contact me for a quote!
```

---

### Publishing Your Changes

Once you're happy with your edits:

1. **Click the Source Control icon** in VSCodium's left sidebar (looks like a branch icon)
2. **Review your changes** - you'll see all modified files
3. **Add a commit message** (e.g., "Added services page and updated about section")
4. **Click "Commit"** then **"Sync Changes"** or **"Push"**

Your changes are now on GitHub! Cloudflare will automatically rebuild your site (1-2 minutes). Refresh your live site to see the updates.

---

### Quick Reference

| Task | How To |
|------|--------|
| Bold text | `**text**` |
| Heading | `## Heading` |
| Link | `[text](url)` |
| Image | `![alt](/images/file.jpg)` |
| List | `- item` or `1. item` |
| Add page to menu | Add `menus:` section in frontmatter |
| Preview changes | Run `hugo serve` |
| Publish changes | Commit & Push in Source Control panel |

---
