# Malatelier Ghost Theme Changelog

## Version 1.0.0 - 2025-11-23

### 🎨 Complete Theme Redesign

#### Branding & Identity
- Renamed theme from "Casper" to "Malatelier"
- Updated all references, repository URLs, and metadata
- Created new Material Design-inspired identity
- Integrated official Malatelier Brig logo and favicon
- Applied brand colors from Malatelier Brig (#e84747 primary red)
- **Logo automatically displays in footer** (white version on gradient)
- Logo assets ready for Ghost admin upload
- Created LOGO-SETUP.md with complete setup instructions

#### Material Design Implementation
- **Color Palette**: Vibrant, artistic colors inspired by Malatelier Brig
  - Primary: Malatelier Red (#e84747) - signature brand color
  - Primary Light: Light Red (#FF6B6B)
  - Primary Dark: Dark Red (#D63031)
  - Secondary: Warm Golden Orange (#F39C12)
  - Accent: Bright Coral Red (#E74C3C)
  - Neutral colors with warm tones

- **Elevation System**: Implemented 5-level shadow system
  - Proper depth hierarchy for cards and UI elements
  - Smooth transitions on hover states
  
- **Typography**: Enhanced with Google Fonts
  - Roboto for headings and UI elements
  - Lora for body text (readable serif)
  - Roboto Mono for code
  - Improved line heights and letter spacing

- **Border Radius**: Consistent rounded corners
  - Small (4px), Medium (8px), Large (12px), XL (16px), Round (24px)

#### UI/UX Improvements
- **Cards**: 
  - Added elevation shadows
  - Smooth hover effects with transform
  - Rounded corners throughout
  - Better spacing and padding

- **Navigation**:
  - Enhanced header with subtle shadow
  - Material-style buttons with elevation
  - Improved dropdown styling

- **Content**:
  - Article cards with Material Design elevation
  - Better code block styling with syntax highlighting
  - Enhanced blockquotes with accent color bars
  - Improved inline code styling

- **Footer**:
  - Gradient background with primary colors
  - Enhanced CTA buttons with Material Design principles

#### Accessibility
- Added focus-visible states for all interactive elements
- Improved color contrast ratios
- Better keyboard navigation support
- Semantic HTML structure maintained

#### Responsive Design
- Enhanced mobile breakpoints
- Better spacing on smaller screens
- Optimized card layouts for all screen sizes
- Touch-friendly interactive elements

#### Technical Changes
- Updated build process (casper.js → malatelier.js)
- Optimized CSS with Material Design variables
- Added Google Fonts integration
- PostCSS version updates for compatibility
- GScan validation passed for Ghost 5.x

### Files Modified
- `package.json` - Updated metadata and dependencies
- `README.md` - Added design principles documentation
- `gulpfile.js` - Updated build references
- `default.hbs` - Added Google Fonts, updated asset references
- `assets/css/screen.css` - Complete Material Design rework
- `assets/css/global.css` - Enhanced base styles
- All built assets regenerated

### Compatibility
- ✅ Compatible with Ghost ≥ 5.0.0
- ✅ All GScan checks passed
- ✅ Mobile responsive
- ✅ Accessibility compliant

---

Theme created with ❤️ following Google Material Design guidelines for a warm, cosy reading experience.
