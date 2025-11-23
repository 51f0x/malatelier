# Malatelier Icons Summary

Quick reference for all brand SVG icons added to the theme.

## 🎨 Brand Icons Created

### 1. Full Logo Icon
**File**: `partials/icons/malatelier-logo.hbs`  
**Type**: SVG wrapper with embedded JPG  
**Size**: 140x158 (maintains aspect ratio)  
**Usage**: `{{> "icons/malatelier-logo"}}`

**Where it's used**:
- ✅ Footer (automatic, white version)
- 📝 Available for header/hero sections

**Features**:
- Scalable vector format
- References original logo JPG
- CSS styleable
- Maintains brand integrity

---

### 2. Malatelier Brand Icon
**File**: `partials/icons/malatelier.hbs`  
**Type**: Pure SVG (artist palette)  
**Size**: 24x24 viewBox (scalable)  
**Usage**: `{{> "icons/malatelier"}}`

**Perfect for**:
- Navigation menus
- Buttons and CTAs
- Blog categories
- Small decorative elements

**Design**: Simplified artist palette with paint dots representing creativity

---

### 3. Art Palette Icon
**File**: `partials/icons/art.hbs`  
**Type**: Pure SVG  
**Size**: 24x24 viewBox (scalable)  
**Usage**: `{{> "icons/art"}}`

**Use cases**:
- Art category tags
- Gallery sections
- Creative content markers
- Course/workshop indicators

**Design**: Classic artist palette with color spots

---

### 4. Paintbrush Icon
**File**: `partials/icons/paintbrush.hbs`  
**Type**: Pure SVG  
**Size**: 24x24 viewBox (scalable)  
**Usage**: `{{> "icons/paintbrush"}}`

**Use cases**:
- Activity indicators
- Hands-on course markers
- Tutorial sections
- Creative process steps

**Design**: Simple paintbrush with bristles and paint drop

---

## 📦 Integration Status

### Footer Implementation
```handlebars
<div class="site-footer-logo site-footer-logo-svg">
    {{> "icons/malatelier-logo"}}
</div>
```

**CSS Styling**:
```css
.site-footer-logo-svg svg {
    height: 80px;
    width: auto;
    fill: currentColor;  /* Inherits white from parent */
}
```

### Color Inheritance
All icons use `fill="currentColor"` which means they inherit the text color from their parent element:

```css
.icon-red {
    color: #e84747;  /* Icons will be red */
}

.icon-white {
    color: #ffffff;  /* Icons will be white */
}
```

## 🎯 Quick Usage Examples

### In Navigation
```handlebars
<nav>
    <a href="/courses">
        {{> "icons/art"}}
        Courses
    </a>
</nav>
```

### In Buttons
```handlebars
<button class="cta">
    {{> "icons/paintbrush"}}
    Start Creating
</button>
```

### In Post Tags
```handlebars
{{#foreach tags}}
    <span class="tag">
        {{> "icons/malatelier"}}
        {{name}}
    </span>
{{/foreach}}
```

### With Custom Styling
```handlebars
<div style="color: #e84747; width: 32px;">
    {{> "icons/art"}}
</div>
```

## 📊 Icon Comparison

| Icon | File | Type | Best For |
|------|------|------|----------|
| Full Logo | `malatelier-logo.hbs` | SVG+JPG | Headers, footers, hero sections |
| Brand Icon | `malatelier.hbs` | SVG | Navigation, small spaces, buttons |
| Art Palette | `art.hbs` | SVG | Categories, galleries, art content |
| Paintbrush | `paintbrush.hbs` | SVG | Activities, courses, tutorials |

## 🔧 Technical Details

### File Sizes
- `malatelier-logo.hbs`: ~200 bytes (+ referenced JPG)
- `malatelier.hbs`: ~500 bytes
- `art.hbs`: ~350 bytes
- `paintbrush.hbs`: ~250 bytes

### Performance
- ✅ Inline SVG = no additional HTTP requests
- ✅ Cached with HTML
- ✅ Tiny file sizes
- ✅ Perfectly scalable
- ✅ Styleable with CSS

### Browser Support
- ✅ All modern browsers
- ✅ IE11+ (with SVG support)
- ✅ Mobile browsers
- ✅ Progressive enhancement

## 📚 Documentation

For complete details, see:
- **ICONS-GUIDE.md** - Full usage guide
- **README.md** - Theme overview with icon section
- **BRANDING.md** - Complete branding assets

## ✅ Checklist

Icon integration is complete:
- [x] 4 brand SVG icons created
- [x] Footer logo uses SVG
- [x] All icons in `partials/icons/`
- [x] CSS styling added
- [x] Documentation written
- [x] Theme rebuilt
- [x] Package updated

## 🚀 Next Steps

To use these icons:
1. Upload theme to Ghost
2. Icons work immediately
3. Use Handlebars syntax: `{{> "icons/NAME"}}`
4. Style with CSS as needed

---

**Icons Created**: 2025-11-23  
**Total Brand Icons**: 4  
**Status**: ✅ Production Ready
