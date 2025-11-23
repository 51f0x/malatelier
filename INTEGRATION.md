# Malatelier Brig Integration Guide

This document explains how the Malatelier Brig branding has been integrated into the Ghost theme.

## Quick Summary

✅ **Completed Integration Tasks:**
1. Downloaded logo and favicon from official website
2. Applied brand colors (#e84747 Malatelier Red)
3. Updated all metadata and documentation
4. Added favicon support to template
5. **Integrated logo in footer** - automatically displays
6. Added logo fallback for header
7. Created comprehensive setup guide (LOGO-SETUP.md)
8. Theme validated and ready for use

## Files Modified

### Templates
- **`default.hbs`**: Added favicon meta tags and references to logo assets
  - Lines 12-15: Favicon integration
  - Lines 17-20: Google Fonts (Material Design)

### Styling
- **`assets/css/screen.css`**: Updated color palette (lines 49-54)
  - Primary: `#e84747` (Malatelier Red)
  - Primary Light: `#FF6B6B`
  - Primary Dark: `#D63031`
  - Secondary: `#F39C12`
  - Accent: `#E74C3C`

### Configuration
- **`package.json`**: Updated author info to Malatelier Brig
  - Author name: "Malatelier Brig"
  - Email: info@malatelier-brig.ch
  - URL: https://www.malatelier-brig.ch/

### Documentation
- **`README.md`**: Added Malatelier Brig attribution and branding section
- **`BRANDING.md`**: Complete branding asset documentation
- **`CHANGELOG.md`**: Documented all branding changes
- **`INTEGRATION.md`**: This file

## Assets Directory Structure

```
assets/
├── images/
│   ├── branding/
│   │   ├── malatelier-logo.jpg      (140x158px - main logo)
│   │   ├── favicon-32.jpg           (32x32px - small favicon)
│   │   └── favicon-192.jpg          (192x192px - large favicon)
│   ├── favicon.ico                  (32x32px - browser tab icon)
│   ├── apple-touch-icon.png         (192x192px - iOS icon)
│   ├── default-skin.png             (theme UI elements)
│   ├── default-skin.svg             (theme UI elements)
│   └── preloader.gif                (loading animation)
└── css/
    ├── screen.css                   (main stylesheet with brand colors)
    └── global.css                   (base styles)
```

## How to Use the Logo

The Malatelier Brig logo is available in the theme at:
`assets/images/branding/malatelier-logo.jpg`

### In Templates (Handlebars)
```handlebars
<img src="{{asset "images/branding/malatelier-logo.jpg"}}" alt="Malatelier Brig">
```

### In CSS
```css
.custom-logo {
    background-image: url('../images/branding/malatelier-logo.jpg');
}
```

## Color Usage Guide

### Primary Color (Malatelier Red: #e84747)
Use for:
- Primary buttons
- Links and CTAs
- Brand accents
- Active states

```css
.button-primary {
    background-color: var(--color-primary);
    /* or */
    background-color: #e84747;
}
```

### Secondary Color (Golden Orange: #F39C12)
Use for:
- Secondary buttons
- Complementary accents
- Highlights
- Warm touches

### Ghost Accent Color
The theme respects Ghost's built-in accent color setting. If you set an accent color in Ghost Admin > Settings > Brand, it will override the default Malatelier Red in certain contexts.

```css
/* This uses Ghost accent color with Malatelier Red as fallback */
color: var(--ghost-accent-color, var(--color-primary));
```

## Favicon Integration

The theme includes automatic favicon support. Files are referenced in `default.hbs`:

```html
<link rel="icon" type="image/x-icon" href="{{asset "images/favicon.ico"}}">
<link rel="icon" type="image/png" sizes="192x192" href="{{asset "images/apple-touch-icon.png"}}">
<link rel="apple-touch-icon" href="{{asset "images/apple-touch-icon.png"}}">
```

This ensures:
- ✅ Browser tab icon displays correctly
- ✅ iOS home screen icon works
- ✅ PWA icon is available
- ✅ Cross-browser compatibility

## Customization for Your Own Brand

If you want to use this theme with different branding:

1. **Replace Logo:**
   - Replace `assets/images/branding/malatelier-logo.jpg` with your logo
   - Update dimensions as needed

2. **Replace Favicon:**
   - Replace `assets/images/favicon.ico` (32x32px)
   - Replace `assets/images/apple-touch-icon.png` (192x192px)

3. **Update Colors:**
   - Edit `assets/css/screen.css` lines 49-54
   - Change the color values to your brand colors
   - Run `npx gulp build` to compile

4. **Update Metadata:**
   - Edit `package.json` author information
   - Update `README.md` references
   - Modify `BRANDING.md` with your brand info

5. **Rebuild:**
   ```bash
   npx gulp build
   ```

## Testing

Validate your changes:
```bash
# Check theme compatibility
npx gscan . --check-version 5.0

# Build theme
npx gulp build

# Create distribution package
npx gulp zip
```

## Resources

- **Malatelier Brig Website**: https://www.malatelier-brig.ch/
- **Ghost Theme Documentation**: https://ghost.org/docs/themes/
- **Material Design Guidelines**: https://m3.material.io/

## Support

For questions about:
- **Theme functionality**: See Ghost documentation
- **Malatelier Brig**: Visit their website
- **Branding usage**: Contact Malatelier Brig directly

---

Theme integration completed on: 2025-11-23
Ghost compatibility: ✅ Version 5.x and above
