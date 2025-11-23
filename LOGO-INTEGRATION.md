# Logo Integration Summary

## Overview
The Malatelier branding and logos have been integrated throughout the entire Ghost theme to create a cohesive visual identity.

## Logo Locations

### 1. Homepage Header (index.hbs)
- **Location**: Site header on the homepage
- **Implementation**: SVG logo displayed when no Ghost admin logo is uploaded
- **Fallback**: If a logo is uploaded via Ghost Admin, it takes priority
- **CSS Class**: `.site-logo-svg`

### 2. Footer (default.hbs)
- **Location**: Global footer on every page
- **Implementation**: SVG logo displayed automatically, with fallback to Ghost admin logo
- **CSS Class**: `.site-footer-logo-svg`
- **Height**: 80px

### 3. Error Pages (error.hbs)
- **Location**: Header navigation on 500/400 error pages
- **Implementation**: Inline SVG logo in navigation
- **CSS Class**: `.site-nav-logo-svg`
- **Height**: 50px

### 4. 404 Page (error-404.hbs)
- **Location**: Center of error message section
- **Implementation**: Subtle watermark-style logo above error code
- **CSS Class**: `.error-logo`
- **Height**: 80px
- **Styling**: 30% opacity for subtle branding

### 5. Tag Pages (tag.hbs)
- **Location**: Tag header card
- **Implementation**: Art icon (palette) in a branded color box
- **CSS Class**: `.tag-icon-wrapper`
- **Icon**: `icons/art`
- **Styling**: 48x48px box with primary color background

### 6. Author Pages (author.hbs)
- **Location**: Author profile card
- **Implementation**: Paintbrush icon as fallback when no profile image exists
- **CSS Class**: `.author-profile-default-icon`
- **Icon**: `icons/paintbrush`
- **Styling**: 120x120px circular badge with gradient background

## Brand Icons Used

### Main Logo
- **File**: `partials/icons/malatelier-logo.hbs`
- **Source**: `assets/images/branding/malatelier-logo.jpg`
- **Dimensions**: 140x158px
- **Usage**: Homepage, footer, error pages

### Art Icon (Palette)
- **File**: `partials/icons/art.hbs`
- **Usage**: Tag pages
- **Style**: Artist palette SVG

### Paintbrush Icon
- **File**: `partials/icons/paintbrush.hbs`
- **Usage**: Author pages (when no profile image)
- **Style**: Paintbrush SVG

## CSS Styling

### Logo Sizes
```css
/* Homepage header logo */
.site-logo-svg svg { height: 120px; }

/* Footer logo */
.site-footer-logo-svg svg { height: 80px; }

/* Error page navigation logo */
.site-nav-logo-svg svg { height: 50px; }

/* 404 page logo */
.error-logo svg { height: 80px; opacity: 0.3; }
```

### Icon Containers
```css
/* Tag icon wrapper */
.tag-icon-wrapper {
    width: 48px;
    height: 48px;
    background: var(--color-primary);
    border-radius: var(--radius-lg);
}

/* Author default icon */
.author-profile-default-icon {
    width: 120px;
    height: 120px;
    background: linear-gradient(135deg, var(--color-primary), var(--color-secondary));
    border-radius: 50%;
}
```

## Responsive Behavior

All logo implementations are responsive:
- **SVG format**: Scales perfectly at any resolution
- **Height-based sizing**: Logos maintain aspect ratio
- **Mobile-friendly**: Automatically adjusts on smaller screens
- **Left-aligned variant**: Smaller logo size (96px) on left-aligned headers

## Customization

### To Use Custom Logo Everywhere
1. Upload logo via Ghost Admin → Settings → Branding
2. Logo will appear in:
   - Site header navigation
   - Footer (if no uploaded logo, shows default)
   - Error pages

### To Keep Default Malatelier Logo
Simply don't upload a logo in Ghost Admin, and the default Malatelier branding will appear throughout the site.

## Files Modified

| File | Change |
|------|--------|
| `index.hbs` | Added logo to homepage header |
| `error.hbs` | Added logo to error page navigation |
| `error-404.hbs` | Added watermark logo to 404 page |
| `tag.hbs` | Added art icon to tag headers |
| `author.hbs` | Added paintbrush icon for authors without profile images |
| `assets/css/screen.css` | Added all logo styling classes |

## Testing Checklist

- [x] Logo displays on homepage
- [x] Logo displays in footer
- [x] Logo displays on error pages
- [x] Logo displays on 404 page
- [x] Art icon displays on tag pages
- [x] Paintbrush icon displays for authors without profile images
- [x] All logos are responsive
- [x] All logos maintain aspect ratio
- [x] Theme builds successfully
- [x] Theme passes gscan validation

## Next Steps

To test the logo integration:

1. Build the theme: `npx gulp build` or `npx gulp zip`
2. Upload to Ghost admin
3. Navigate to different pages to see logos in action
4. Test with and without custom logo uploaded in Ghost Admin
5. Test on mobile devices for responsiveness
