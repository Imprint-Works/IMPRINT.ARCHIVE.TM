# Copilot Instructions for Imprint Archive

## Project Overview
**Imprint Archive** is a single-page portfolio site showcasing three creative projects with integrated Shopify e-commerce. The site features a fixed sidebar navigation and full-bleed project sections.

## Architecture

### Single-Page Layout
- **Sidebar Navigation**: Fixed 250px left sidebar (`.sidebar`) with project anchor links (#project1, #project2, #project3)
- **Content Area**: Main content sections use flexbox layout with `margin-left: 250px` to accommodate sidebar
- **Projects**: Three full-viewport sections styled as `.bg-section` with background images, each containing overlay text and Shopify embed

### Shopify Integration Pattern
Each project section contains identical Shopify Buy Button embed code with project-specific configuration:

```javascript
// Each project has unique collection ID and DOM node:
- project1 (MESHD_mother_earth): collection ID 669758095741, node collection-component-1771182178968
- project2 (OLLIE_DOVE_diy): collection ID 666925334909, node collection-component-1771183105018  
- project3 (ACT_UP_healthcare_not_warfare): collection ID 671389385085, node collection-component-1771183163045
```

All projects use: domain `imprint-works.myshopify.com`, token `dec824592d198225b89ee8ff54f77d2e`

## Design Conventions

### Color Palette
- **Accent Green**: `#42f114` / `rgb(15, 227, 51)` - used for project titles, links, button backgrounds
- **Sidebar Gray**: `#a4a7a7` - fixed sidebar background
- **Dark Gray**: `#323232`, `#2d2d2d` - Shopify button defaults (hover states)

### Typography
- **Custom Font**: `iatype` (WOFF format, loaded from root)
- All body text uses this font family
- Project titles (h1): 1.5rem, bright green background with white text (display: table for shrink-wrap)
- Subtitles (h2): 1rem, semi-transparent white background

### Responsive Layout
- **Viewport Sections**: Each project fills 100% viewport height
- **Product Grid**: Shopify products display 25% width (calc(25% - 20px)) on desktop in MESHD/OLLIE, 33.33% in ACT_UP
- **Images**: Full-width (`width: 100%`), no max-width constraint

## Current Codebase Structure

```
/index.html              - Main hub with all 3 projects embedded
/style.css              - Shared styling (sidebar, layout, colors)
/project1.html          - Standalone project page (incomplete/template)
/project2.html          - Standalone project page (incomplete/template)
/project3.html          - Standalone project page (incomplete/template)
/scode act up healthcare/ - Project-specific assets folder
  /actupH.js            - Contains ACT_UP Shopify embed code
  /meshdME.js           - Empty (MESHD assets placeholder)
  /olliedDIY.js         - Empty (OLLIE assets placeholder)
```

## Technical Debt & Patterns to Avoid

### Code Duplication
The Shopify embed code is repeated almost identically across projects. Consider refactoring into:
- JavaScript templates or functions with parameterized collection IDs
- Extracting common styles into CSS variables for button colors, product grid layout

### Security Note
Shopify storefrontAccessToken is exposed in client-side code - acceptable for public storefronts but consider server-side rendering for sensitive operations.

## Naming Conventions

- **Projects**: Use snake_case with descriptive format: `ARTIST_theme` (e.g., `MESHD_mother_earth`)
- **Shopify IDs**: Referenced as `collection-component-{timestamp}` (immutable once embedded)
- **CSS Classes**: `.main-layout`, `.sidebar`, `.content`, `.bg-section`, `.overlay` (BEM-like but minimal)
- **DOM Nodes**: Project sections use `id="project1"`, `id="project2"`, `id="project3"` for anchor navigation

## Key Files & Their Purposes

- [index.html](index.html) - Primary entry point, all projects embedded here, Shopify integrations defined
- [style.css](style.css) - Global flex layout, sidebar positioning, typography, color scheme
- [scode act up healthcare/actupH.js](scode%20act%20up%20healthcare/actupH.js) - ACT_UP project Shopify embed (contains working example of collection configuration)
