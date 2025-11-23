# Malatelier

A cosy, Material Design inspired Ghost theme with warm colors and modern UI/UX principles. Built with Google Material Design guidelines for a comfortable reading and browsing experience.

This theme is inspired by [Malatelier Brig](https://www.malatelier-brig.ch/), an art studio in Brig, Switzerland specializing in painting, modeling, pottery, and creative workshops for children and adults.

&nbsp;

# First time using a Ghost theme?

Ghost uses a simple templating language called [Handlebars](http://handlebarsjs.com/) for its themes.

This theme has lots of code comments to help explain what's going on just by reading the code. Once you feel comfortable with how everything works, we also have full [theme API documentation](https://ghost.org/docs/themes/) which explains every possible Handlebars helper and template.

**The main files are:**

- `default.hbs` - The parent template file, which includes your global header/footer
- `index.hbs` - The main template to generate a list of posts, usually the home page
- `post.hbs` - The template used to render individual posts
- `page.hbs` - Used for individual pages
- `tag.hbs` - Used for tag archives, eg. "all posts tagged with `news`"
- `author.hbs` - Used for author archives, eg. "all posts written by Jamie"

One neat trick is that you can also create custom one-off templates by adding the slug of a page to a template file. For example:

- `page-about.hbs` - Custom template for an `/about/` page
- `tag-news.hbs` - Custom template for `/tag/news/` archive
- `author-ali.hbs` - Custom template for `/author/ali/` archive


# Development

Malatelier styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# install dependencies
yarn install

# run development server
yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
# create .zip file
yarn zip
```

# PostCSS Features Used

- Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
- [Color Mod](https://github.com/jonathantneal/postcss-color-mod-function)


# Design Principles

Malatelier follows Google Material Design guidelines:
- **Elevation & Shadows**: Proper depth and hierarchy through layered shadows
- **Cosy Colors**: Warm, inviting color palette inspired by art studio aesthetics
- **Typography**: Clear hierarchy with Roboto-inspired font stack
- **Rounded Corners**: Softer UI elements with consistent border radius
- **Responsive**: Mobile-first approach with thoughtful breakpoints

# Branding

The theme includes the official Malatelier Brig logo and branding assets:
- **Logo**: `assets/images/branding/malatelier-logo.jpg` (140x158px)
- **Favicon**: `assets/images/favicon.ico` (32x32px) - automatically integrated
- **Apple Touch Icon**: `assets/images/apple-touch-icon.png` (192x192px) - automatically integrated

### Logo Integration

✅ **Footer**: Logo automatically displays in footer (white version)  
✅ **Header**: Upload logo via Ghost Admin > Settings > General > Site logo  
✅ **Favicon**: Automatically integrated in browser tabs  
✅ **Mobile**: iOS home screen icon ready

📖 **See [LOGO-SETUP.md](LOGO-SETUP.md) for detailed setup instructions**

All branding assets are sourced from [www.malatelier-brig.ch](https://www.malatelier-brig.ch/) and remain property of Malatelier Brig.

# SVG Icons

Malatelier uses inline SVG icons, included via Handlebars partials. You can find all icons inside `/partials/icons`. 

### Using Icons

To include an icon, use the Handlebars partial syntax:

```handlebars
{{> "icons/rss"}}           {{!-- RSS feed icon --}}
{{> "icons/malatelier"}}    {{!-- Malatelier brand icon --}}
{{> "icons/art"}}           {{!-- Art palette icon --}}
{{> "icons/paintbrush"}}    {{!-- Paintbrush icon --}}
```

### Malatelier Brand Icons

The theme includes special brand-themed icons:
- **`malatelier-logo.hbs`** - Full logo as SVG (embeds JPG)
- **`malatelier.hbs`** - Simplified palette icon
- **`art.hbs`** - Artist palette icon
- **`paintbrush.hbs`** - Brush icon for creative themes

You can add your own SVG icons in the same manner.


# Copyright & License

Copyright (c) 2013-2025 Ghost Foundation - Released under the [MIT license](LICENSE).
