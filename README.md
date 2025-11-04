# Vitor Ribeiro's Blog - Project Guide

This is a Hugo-powered blog using the Stack theme, automatically deployed to GitHub Pages. This guide explains how everything works and how to manage content.

## What This Project Does

This is a static blog website that:
- Uses **Hugo** (a fast static site generator) to build the site
- Uses the **Stack theme** for a modern, responsive design
- Automatically deploys to **GitHub Pages** when you push changes
- Supports markdown content with math rendering, categories, and tags

## Project Structure

```
naturalfunction.github.io/
├── .github/workflows/          # GitHub Actions for auto-deployment
│   └── deploy.yml             # Deployment workflow
├── assets/                    # Theme assets (CSS, JS, images)
├── config/_default/           # Site configuration files
│   ├── config.toml           # Main site settings (title, URL, etc.)
│   ├── params.toml           # Theme parameters (sidebar, colors, etc.)
│   ├── menu.toml             # Navigation menu and social links
│   └── ...                   # Other config files
├── content/                   # All your content goes here
│   ├── _index.md             # Homepage content
│   ├── page/                 # Static pages
│   │   ├── about/            # About page
│   │   ├── archives/         # Archives page (auto-generated)
│   │   ├── links/            # Resources/links page
│   │   └── search/           # Search page (auto-generated)
│   ├── post/                 # Blog posts
│   │   ├── welcome-to-natural-function/
│   │   ├── mathematical-functions/
│   │   └── ...               # Each post in its own folder
│   └── categories/           # Category definitions
├── static/                   # Static files (images, favicon, etc.)
├── public/                   # Generated site (don't edit manually)
├── go.mod & go.sum          # Hugo modules (theme management)
└── README.md                # This file
```

## How It Works

1. **Write Content**: Create markdown files in `content/`
2. **Push to GitHub**: Commit and push your changes
3. **Auto-Deploy**: GitHub Actions builds and deploys your site
4. **Live Site**: Your blog updates at `https://naturalfunction.github.io`

## Adding New Content

### Creating a New Blog Post

1. Create a new folder in `content/post/`:
   ```
   content/post/my-new-post/
   └── index.md
   ```

2. Add front matter and content to `index.md`:
   ```markdown
   ---
   title: "My New Post Title"
   date: 2025-11-03T10:00:00-06:00
   description: "Brief description of the post"
   categories: ["Mathematics", "Technology"]
   tags: ["functions", "algorithms", "patterns"]
   image: "cover.jpg"  # Optional: add cover.jpg to the same folder
   math: true          # Optional: enable math rendering
   ---

   # Your Post Content

   Write your post content here in markdown...
   ```

3. Commit and push - your post will be live in minutes!

### Creating a New Page

1. Create a folder in `content/page/`:
   ```
   content/page/my-page/
   └── index.md
   ```

2. Add front matter and content:
   ```markdown
   ---
   title: "My Page"
   description: "Page description"
   menu:
       main: 
           weight: 5
           params:
               icon: page
   ---

   # Page Content
   ```

### Adding Images

1. **For blog posts**: Put images in the same folder as your post
   ```
   content/post/my-post/
   ├── index.md
   ├── cover.jpg      # Featured image
   └── diagram.png    # Images used in the post
   ```

2. **For site-wide images**: Put them in `static/`
   ```
   static/
   ├── favicon.png
   └── img/
       └── avatar.png
   ```

## Editing Existing Content

### Updating Site Information

- **Site title/URL**: Edit `config/_default/config.toml`
- **Sidebar info**: Edit `config/_default/params.toml`
- **Navigation menu**: Edit `config/_default/menu.toml`
- **Homepage**: Edit `content/_index.md`
- **About page**: Edit `content/page/about/index.md`

### Updating Posts

Simply edit the markdown files in `content/post/[post-name]/index.md`

### Managing Categories

1. Create category definitions in `content/categories/`:
   ```
   content/categories/mathematics/
   └── _index.md
   ```

2. Add category info:
   ```markdown
   ---
   title: Mathematics
   description: Posts about mathematical concepts
   style:
       background: "#2a9d8f"
       color: "#fff"
   ---
   ```

## Markdown Features

The Stack theme supports rich markdown:

- **Math**: Use `$inline math$` or `$$block math$$` (when `math: true`)
- **Code blocks**: Use triple backticks with language
- **Images**: `![alt text](image.jpg)`
- **Links**: `[text](url)`
- **Tables, lists, quotes**: Standard markdown syntax

## Deployment

The site automatically deploys when you:
1. Push changes to the `main` branch
2. GitHub Actions runs the build process
3. Site updates at `https://naturalfunction.github.io`

You can monitor deployments at:
`https://github.com/naturalfunction/naturalfunction.github.io/actions`

## Local Development (Optional)

To preview changes locally before pushing:

1. Install Hugo: `brew install hugo` (macOS)
2. Run local server: `hugo server`
3. View at: `http://localhost:1313`

## Common Tasks

### Change Site Title
Edit `config/_default/config.toml`:
```toml
title = "Your New Title"
```

### Update Sidebar
Edit `config/_default/params.toml`:
```toml
[sidebar]
emoji = "🧮"
subtitle = "Your new subtitle"
```

### Add Social Links
Edit `config/_default/menu.toml`:
```toml
[[social]]
identifier = "github"
name = "GitHub"
url = "https://github.com/yourusername"
[social.params]
icon = "brand-github"
```

### Enable Comments
Edit `config/_default/params.toml`:
```toml
[comments]
enabled = true
provider = "disqus"  # or other providers
```

## Getting Help

- **Hugo Documentation**: https://gohugo.io/documentation/
- **Stack Theme Docs**: https://stack.jimmycai.com/
- **Markdown Guide**: https://www.markdownguide.org/

## Tips

1. **Always test locally** if you have Hugo installed
2. **Use descriptive filenames** for posts and images
3. **Add alt text** to images for accessibility
4. **Use categories and tags** to organize content
5. **Write good descriptions** for SEO
6. **Check the Actions tab** if deployment fails

That's it! You now have a complete understanding of how to manage your Hugo blog. Happy writing! 🚀
# Natural Function Blog - Project Guide

This is a Hugo-powered blog using the Stack theme, automatically deployed to GitHub Pages. This guide explains how everything works and how to manage content.

## What This Project Does

This is a static blog website that:
- Uses **Hugo** (a fast static site generator) to build the site
- Uses the **Stack theme** for a modern, responsive design
- Automatically deploys to **GitHub Pages** when you push changes
- Supports markdown content with math rendering, categories, and tags

## Project Structure

```
naturalfunction.github.io/
├── .github/workflows/          # GitHub Actions for auto-deployment
│   └── deploy.yml             # Deployment workflow
├── assets/                    # Theme assets (CSS, JS, images)
├── config/_default/           # Site configuration files
│   ├── config.toml           # Main site settings (title, URL, etc.)
│   ├── params.toml           # Theme parameters (sidebar, colors, etc.)
│   ├── menu.toml             # Navigation menu and social links
│   └── ...                   # Other config files
├── content/                   # All your content goes here
│   ├── _index.md             # Homepage content
│   ├── page/                 # Static pages
│   │   ├── about/            # About page
│   │   ├── archives/         # Archives page (auto-generated)
│   │   ├── links/            # Resources/links page
│   │   └── search/           # Search page (auto-generated)
│   ├── post/                 # Blog posts
│   │   ├── welcome-to-natural-function/
│   │   ├── mathematical-functions/
│   │   └── ...               # Each post in its own folder
│   └── categories/           # Category definitions
├── static/                   # Static files (images, favicon, etc.)
├── public/                   # Generated site (don't edit manually)
├── go.mod & go.sum          # Hugo modules (theme management)
└── PROJECT_GUIDE.md         # This file
```

## How It Works

1. **Write Content**: Create markdown files in `content/`
2. **Push to GitHub**: Commit and push your changes
3. **Auto-Deploy**: GitHub Actions builds and deploys your site
4. **Live Site**: Your blog updates at `https://naturalfunction.github.io`

## Adding New Content

### Creating a New Blog Post

1. Create a new folder in `content/post/`:
   ```
   content/post/my-new-post/
   └── index.md
   ```

2. Add front matter and content to `index.md`:
   ```markdown
   ---
   title: "My New Post Title"
   date: 2025-11-03T10:00:00-06:00
   description: "Brief description of the post"
   categories: ["Mathematics", "Technology"]
   tags: ["functions", "algorithms", "patterns"]
   image: "cover.jpg"  # Optional: add cover.jpg to the same folder
   math: true          # Optional: enable math rendering
   ---

   # Your Post Content

   Write your post content here in markdown...
   ```

3. Commit and push - your post will be live in minutes!

### Creating a New Page

1. Create a folder in `content/page/`:
   ```
   content/page/my-page/
   └── index.md
   ```

2. Add front matter and content:
   ```markdown
   ---
   title: "My Page"
   description: "Page description"
   menu:
       main: 
           weight: 5
           params:
               icon: page
   ---

   # Page Content
   ```

### Adding Images

1. **For blog posts**: Put images in the same folder as your post
   ```
   content/post/my-post/
   ├── index.md
   ├── cover.jpg      # Featured image
   └── diagram.png    # Images used in the post
   ```

2. **For site-wide images**: Put them in `static/`
   ```
   static/
   ├── favicon.png
   └── img/
       └── avatar.png
   ```

## Editing Existing Content

### Updating Site Information

- **Site title/URL**: Edit `config/_default/config.toml`
- **Sidebar info**: Edit `config/_default/params.toml`
- **Navigation menu**: Edit `config/_default/menu.toml`
- **Homepage**: Edit `content/_index.md`
- **About page**: Edit `content/page/about/index.md`

### Updating Posts

Simply edit the markdown files in `content/post/[post-name]/index.md`

### Managing Categories

1. Create category definitions in `content/categories/`:
   ```
   content/categories/mathematics/
   └── _index.md
   ```

2. Add category info:
   ```markdown
   ---
   title: Mathematics
   description: Posts about mathematical concepts
   style:
       background: "#2a9d8f"
       color: "#fff"
   ---
   ```

## Markdown Features

The Stack theme supports rich markdown:

- **Math**: Use `$inline math$` or `$$block math$$` (when `math: true`)
- **Code blocks**: Use triple backticks with language
- **Images**: `![alt text](image.jpg)`
- **Links**: `[text](url)`
- **Tables, lists, quotes**: Standard markdown syntax

## Deployment

The site automatically deploys when you:
1. Push changes to the `main` branch
2. GitHub Actions runs the build process
3. Site updates at `https://naturalfunction.github.io`

You can monitor deployments at:
`https://github.com/naturalfunction/naturalfunction.github.io/actions`

## Local Development (Optional)

To preview changes locally before pushing:

1. Install Hugo: `brew install hugo` (macOS)
2. Run local server: `hugo server`
3. View at: `http://localhost:1313`

## Common Tasks

### Change Site Title
Edit `config/_default/config.toml`:
```toml
title = "Your New Title"
```

### Update Sidebar
Edit `config/_default/params.toml`:
```toml
[sidebar]
emoji = "🧮"
subtitle = "Your new subtitle"
```

### Add Social Links
Edit `config/_default/menu.toml`:
```toml
[[social]]
identifier = "github"
name = "GitHub"
url = "https://github.com/yourusername"
[social.params]
icon = "brand-github"
```

### Enable Comments
Edit `config/_default/params.toml`:
```toml
[comments]
enabled = true
provider = "disqus"  # or other providers
```

## Getting Help

- **Hugo Documentation**: https://gohugo.io/documentation/
- **Stack Theme Docs**: https://stack.jimmycai.com/
- **Markdown Guide**: https://www.markdownguide.org/

## Tips

1. **Always test locally** if you have Hugo installed
2. **Use descriptive filenames** for posts and images
3. **Add alt text** to images for accessibility
4. **Use categories and tags** to organize content
5. **Write good descriptions** for SEO
6. **Check the Actions tab** if deployment fails

That's it! You now have a complete understanding of how to manage your Hugo blog. Happy writing! 🚀