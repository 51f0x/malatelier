# Logo Setup Guide for Malatelier Theme

This guide explains how to properly set up and use the Malatelier Brig logo in your Ghost installation.

## Automatic Integration

The theme includes the official Malatelier Brig logo and will automatically display it in the footer. No configuration needed!

## Logo Locations in Theme

### 1. **Footer Logo** (Automatic)
The Malatelier Brig logo appears automatically in the footer at the bottom of every page.

**File**: `assets/images/branding/malatelier-logo.jpg`

The logo is:
- ✅ Automatically displayed
- ✅ Styled with white filter for visibility on dark background
- ✅ Responsive and scales appropriately
- ✅ Falls back to site logo if set in Ghost admin

### 2. **Header Logo** (Configure in Ghost Admin)
To display the Malatelier logo in your site header:

**Option A: Upload via Ghost Admin (Recommended)**

1. Log into your Ghost admin panel
2. Go to **Settings > General**
3. Under "Publication info", click **Site logo**
4. Upload the logo file from: `assets/images/branding/malatelier-logo.jpg`
5. Click **Save settings**

**Option B: Use Custom Cover Image**

1. Go to **Settings > General**
2. Under "Publication info", add a **Publication cover**
3. Upload a banner image featuring the logo

### 3. **Navigation Logo**
The header navigation will display:
- Your uploaded site logo (if set in Ghost admin)
- OR the site title as text

To customize:
1. **Settings > Design > Branding**
2. Upload logo under "Logo"
3. Choose navigation style:
   - "Logo on cover"
   - "Logo in the middle"
   - "Stacked"

## Customization Options

### Color Adjustments

If you want to adjust the logo appearance in the footer, edit `assets/css/screen.css`:

```css
.site-footer-logo {
    max-height: 80px;        /* Adjust logo size */
    width: auto;
    filter: brightness(0) invert(1);  /* White logo */
    opacity: 0.9;            /* Slight transparency */
}
```

Remove the `filter` property if you want to show the logo in its original colors.

### Hide Footer Logo

If you don't want the logo in the footer, edit `default.hbs` and remove lines containing:

```handlebars
<img class="site-footer-logo" src="..." alt="...">
```

## Logo Files Available

All logo assets are in `assets/images/`:

1. **Main Logo**: `branding/malatelier-logo.jpg` (140x158px)
2. **Favicon**: `favicon.ico` (32x32px) - automatically used
3. **Apple Touch Icon**: `apple-touch-icon.png` (192x192px) - automatically used

## Upload Logo to Ghost Admin

### Step-by-Step Instructions

1. **Download the logo file** from your theme directory:
   - Path: `assets/images/branding/malatelier-logo.jpg`

2. **Access Ghost Admin**:
   - Navigate to: `https://your-domain.com/ghost`
   - Log in with your credentials

3. **Upload Site Logo**:
   - Go to: **Settings** (⚙️ icon) > **General**
   - Scroll to "Publication info"
   - Click the **Site logo** upload button
   - Select `malatelier-logo.jpg`
   - Click **Save settings** (blue button in top right)

4. **Configure Navigation Layout**:
   - Go to: **Settings** > **Design**
   - Scroll to "Site design"
   - Under "Navigation layout" choose:
     - **"Logo on cover"** - Shows logo prominently on homepage
     - **"Logo in the middle"** - Centers logo in navigation
     - **"Stacked"** - Vertical layout with logo on top
   - Click **Save** when done

## Verification

After setup, verify the logo appears:

✅ **Check Header**:
- Visit your site homepage
- Logo should appear in navigation (if uploaded to Ghost admin)

✅ **Check Footer**:
- Scroll to bottom of any page
- Malatelier logo should appear above copyright
- Logo should be white/inverted on red gradient background

✅ **Check Favicon**:
- Look at browser tab
- Malatelier icon should appear

✅ **Check Mobile**:
- Add site to home screen on iOS
- Malatelier icon should appear

## Troubleshooting

### Logo Not Showing in Header?

**Solution**: Upload the logo in Ghost admin (Settings > General > Site logo)

### Logo Too Large/Small?

**Solution**: Edit CSS in `assets/css/screen.css`:

```css
/* For header logo */
.gh-head-logo img {
    max-height: 40px;  /* Adjust this value */
}

/* For footer logo */
.site-footer-logo {
    max-height: 80px;  /* Adjust this value */
}
```

### Want Original Logo Colors in Footer?

**Solution**: Remove the filter in `assets/css/screen.css`:

```css
.site-footer-logo {
    max-height: 80px;
    width: auto;
    /* filter: brightness(0) invert(1); */ /* Comment out or remove */
    opacity: 1;
}
```

### Footer Logo Not Appearing?

**Solution**: Make sure you've rebuilt the theme:

```bash
yarn zip
```

Then re-upload the theme .zip file to Ghost.

## Theme Colors

The theme uses the official Malatelier Brig brand colors:

- **Primary Red**: `#e84747`
- **Buttons, Links, Accents**: Malatelier Red
- **Footer Gradient**: Dark Red to Malatelier Red

These colors are automatically applied throughout the theme.

## Support Resources

- **Ghost Themes Docs**: https://ghost.org/docs/themes/
- **Theme Settings**: https://ghost.org/docs/themes/content/
- **Malatelier Brig Website**: https://www.malatelier-brig.ch/

## Credits

Logo and branding assets are property of Malatelier Brig and sourced from their official website.

---

**Theme Version**: 1.0.0  
**Last Updated**: 2025-11-23
