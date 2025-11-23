# Malatelier Icons Guide

Complete guide to using SVG icons in the Malatelier Ghost Theme.

## 📍 Icon Directory Structure

```
partials/icons/
├── malatelier-logo.hbs    ← Full logo as SVG (embeds JPG)
├── malatelier.hbs          ← Simplified brand icon (palette)
├── art.hbs                 ← Artist palette icon
├── paintbrush.hbs          ← Paintbrush/creativity icon
├── avatar.hbs              ← User avatar icon
├── fire.hbs                ← Featured post icon
├── lock.hbs                ← Private/members-only icon
├── rss.hbs                 ← RSS feed icon
├── search.hbs              ← Search icon
└── [social icons...]       ← Facebook, Twitter, etc.
```

## 🎨 Brand Icons

### Malatelier Logo (Full)
**File**: `partials/icons/malatelier-logo.hbs`

Embeds the full Malatelier Brig logo as an SVG wrapper around the JPG image.

**Usage**:
```handlebars
{{> "icons/malatelier-logo"}}
```

**Example**:
```handlebars
<div class="brand-header">
    {{> "icons/malatelier-logo"}}
    <h1>Welcome to Malatelier</h1>
</div>
```

**Features**:
- ✅ Scalable vector format
- ✅ References original JPG logo
- ✅ Maintains aspect ratio (140x158)
- ✅ Works with CSS styling

### Malatelier Brand Icon (Simplified)
**File**: `partials/icons/malatelier.hbs`

Simplified artist palette icon representing the Malatelier brand.

**Usage**:
```handlebars
{{> "icons/malatelier"}}
```

**Perfect for**:
- Navigation items
- Buttons and CTAs
- Menu icons
- Small decorative elements

**Example**:
```handlebars
<button class="btn-primary">
    {{> "icons/malatelier"}}
    <span>View Gallery</span>
</button>
```

### Art Palette Icon
**File**: `partials/icons/art.hbs`

Classic artist palette icon for creative/artistic content.

**Usage**:
```handlebars
{{> "icons/art"}}
```

**Use cases**:
- Art category tags
- Creative post indicators
- Gallery sections
- Workshop/course markers

### Paintbrush Icon
**File**: `partials/icons/paintbrush.hbs`

Simple paintbrush icon for hands-on creative activities.

**Usage**:
```handlebars
{{> "icons/paintbrush"}}
```

**Use cases**:
- Activity indicators
- Course type icons
- Blog post categories
- Creative process markers

## 🔧 How to Use Icons

### Basic Usage

Include any icon using the Handlebars partial syntax:

```handlebars
{{> "icons/ICON-NAME"}}
```

### With Text

```handlebars
<a href="/gallery" class="menu-item">
    {{> "icons/art"}}
    <span>Gallery</span>
</a>
```

### In Buttons

```handlebars
<button class="cta-button">
    {{> "icons/paintbrush"}}
    Enroll in Course
</button>
```

### With Custom Classes

Wrap the icon in a div to add custom styling:

```handlebars
<div class="icon-wrapper icon-large icon-red">
    {{> "icons/malatelier"}}
</div>
```

## 🎨 Styling Icons

### CSS Styling

Icons inherit color from parent elements:

```css
.my-icon {
    color: #e84747;           /* Malatelier red */
    width: 24px;
    height: 24px;
}

.my-icon svg {
    fill: currentColor;       /* Inherits parent color */
}
```

### Size Control

```css
/* Small icons */
.icon-sm svg {
    width: 16px;
    height: 16px;
}

/* Medium icons */
.icon-md svg {
    width: 24px;
    height: 24px;
}

/* Large icons */
.icon-lg svg {
    width: 48px;
    height: 48px;
}
```

### Color Variations

```css
/* Brand color */
.icon-brand svg {
    fill: var(--color-primary);  /* #e84747 */
}

/* White icons */
.icon-white svg {
    fill: #ffffff;
}

/* Dark icons */
.icon-dark svg {
    fill: var(--color-darkgrey);
}
```

## 📦 Icon Implementation Examples

### Featured Post Badge

```handlebars
{{#if featured}}
    <span class="post-featured-badge">
        {{> "icons/fire"}}
        <span>Featured</span>
    </span>
{{/if}}
```

### Members-Only Content

```handlebars
{{^has visibility="public"}}
    <div class="members-badge">
        {{> "icons/lock"}}
        <span>Members Only</span>
    </div>
{{/has}}
```

### Course Category Icons

```handlebars
{{#if primary_tag.slug "painting"}}
    {{> "icons/paintbrush"}}
{{else if primary_tag.slug "art"}}
    {{> "icons/art"}}
{{else}}
    {{> "icons/malatelier"}}
{{/if}}
```

### Navigation with Icons

```handlebars
<nav class="main-menu">
    <a href="/courses">
        {{> "icons/art"}}
        <span>Courses</span>
    </a>
    <a href="/gallery">
        {{> "icons/malatelier"}}
        <span>Gallery</span>
    </a>
    <a href="/about">
        {{> "icons/avatar"}}
        <span>About</span>
    </a>
</nav>
```

## 🆕 Creating Custom Icons

### Adding New Icons

1. Create a new `.hbs` file in `partials/icons/`
2. Add your SVG code
3. Use the same viewBox format as existing icons

**Template**:
```handlebars
{{!-- Description of your icon --}}
<svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="currentColor">
    <path d="YOUR_SVG_PATH_DATA"/>
</svg>
```

### Icon Guidelines

- ✅ Use `viewBox="0 0 24 24"` for consistency
- ✅ Use `fill="currentColor"` to inherit colors
- ✅ Keep paths simple and optimized
- ✅ Add descriptive comments
- ✅ Test at multiple sizes

### Example: Custom Heart Icon

```handlebars
{{!-- Heart/favorite icon --}}
<svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="currentColor">
    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
</svg>
```

## 🔄 Converting Existing Images

If you need to convert images to SVG icons:

### Option 1: Manual Tracing
1. Use a tool like Adobe Illustrator or Inkscape
2. Import your image
3. Use "Image Trace" or similar feature
4. Export as SVG
5. Optimize with SVGO

### Option 2: Online Tools
- **Vectorizer.io** - Automatic image to SVG
- **SVG Repo** - Find existing SVG icons
- **Noun Project** - Icon library

### Option 3: Embed Image (Current Approach)
For logos that can't be easily vectorized:

```handlebars
<svg viewBox="0 0 WIDTH HEIGHT" xmlns="http://www.w3.org/2000/svg">
    <image width="WIDTH" height="HEIGHT" xlink:href="{{asset "images/your-image.jpg"}}" />
</svg>
```

## 📋 Icon Checklist

When adding new icons, ensure:

- [ ] Icon is in `partials/icons/` directory
- [ ] Filename ends with `.hbs`
- [ ] SVG has proper `viewBox` attribute
- [ ] Uses `fill="currentColor"` for color inheritance
- [ ] Includes descriptive comment
- [ ] Tested at different sizes
- [ ] Works with theme colors
- [ ] Accessible (has semantic meaning)

## 🎯 Best Practices

### DO ✅
- Use semantic icon names
- Keep SVG code clean and minimal
- Use `currentColor` for fill
- Add descriptive comments
- Test responsive scaling
- Consider accessibility

### DON'T ❌
- Hardcode colors in SVG paths
- Use overly complex paths
- Forget viewBox attribute
- Use inline styles in SVG
- Make files unnecessarily large
- Ignore accessibility

## 📚 Resources

### Icon Libraries
- **Heroicons** - https://heroicons.com/
- **Feather Icons** - https://feathericons.com/
- **Material Icons** - https://fonts.google.com/icons
- **Lucide** - https://lucide.dev/

### SVG Tools
- **SVGOMG** - SVG optimizer
- **SVG Path Editor** - Online path editor
- **Figma** - Design and export SVGs

### Ghost Documentation
- **Theme Helpers** - https://ghost.org/docs/themes/helpers/
- **Partials** - https://ghost.org/docs/themes/structure/

## 💡 Tips & Tricks

### Animated Icons
```css
.icon-spin svg {
    animation: spin 2s linear infinite;
}

@keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
```

### Hover Effects
```css
.icon-hover svg {
    transition: all 0.3s ease;
}

.icon-hover:hover svg {
    transform: scale(1.2);
    fill: var(--color-primary);
}
```

### Icon Badges
```handlebars
<div class="icon-badge">
    {{> "icons/malatelier"}}
    <span class="badge-count">5</span>
</div>
```

---

**Theme Version**: 1.0.0  
**Icons Added**: 2025-11-23  
**Total Brand Icons**: 4 (malatelier-logo, malatelier, art, paintbrush)
