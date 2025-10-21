# Photo Wallet PWA - Figma Quick Start Guide

This guide walks you through recreating the Photo Wallet PWA design in Figma using the provided design system documentation.

---

## Step 1: Set Up Your Figma File

### Create a New Figma File
1. Open Figma
2. Create a new design file: **Photo Wallet PWA**
3. Set up these initial pages:
   - **Design System** (for tokens and styles)
   - **Components** (for reusable components)
   - **Screens** (for final screen designs)
   - **Prototypes** (for interactive flows)

### Configure Your Canvas
- **Mobile frame**: Use iPhone 14 Pro (393 × 852) or custom mobile size
- **Dark background**: Set canvas background to #0A0A0A for context

---

## Step 2: Create Design Tokens (Styles)

### A. Color Styles

Create these color styles in Figma (Edit > Edit Local Styles > Color):

**Background Colors (Dark Mode)**
```
background/primary          #141414 (HSL 0, 0%, 8%)
background/card             #1F1F1F (HSL 0, 0%, 12%)
background/popover          #292929 (HSL 0, 0%, 16%)
```

**Text Colors (Dark Mode)**
```
text/primary                #FAFAFA (HSL 0, 0%, 98%)
text/secondary              #9FA3AB (HSL 210, 6%, 65%)
text/muted                  #9FA3AB
```

**Border Colors (Dark Mode)**
```
border/primary              #333333 (HSL 0, 0%, 20%)
border/card                 #292929 (HSL 0, 0%, 16%)
border/popover              #383838 (HSL 0, 0%, 22%)
```

**Brand Colors**
```
brand/primary               #3399FF (HSL 210, 100%, 60%)
brand/primary-foreground    #FAFCFF
brand/destructive           #EE3939 (HSL 0, 85%, 60%)
brand/destructive-foreground #FFF8F8
```

**Interaction States**
```
interaction/hover           rgba(255, 255, 255, 0.04)
interaction/active          rgba(255, 255, 255, 0.09)
interaction/outline         rgba(255, 255, 255, 0.10)
```

💡 **Tip**: Name them with forward slashes to create hierarchical groups

---

### B. Text Styles

Create these text styles (Edit > Edit Local Styles > Text):

```
text/display/mobile         -apple-system, 32px, Weight 600, -0.02em tracking
text/display/desktop        -apple-system, 40px, Weight 600, -0.02em tracking
text/headline               -apple-system, 24px, Weight 600, -0.02em tracking
text/body/large             -apple-system, 16px, Weight 400, 1.5 line height
text/body/regular           -apple-system, 14px, Weight 400, 1.5 line height
text/caption                -apple-system, 14px, Weight 400, 0.01em tracking
text/small                  -apple-system, 12px, Weight 400
text/button                 -apple-system, 14px, Weight 500
```

💡 **Tip**: For -apple-system font, use SF Pro Display in Figma, or fallback to Inter

---

### C. Effect Styles (Shadows)

Create these effect styles (Edit > Edit Local Styles > Effect):

**Shadow 2XS**
```
Type: Drop shadow
X: 0, Y: 1, Blur: 2
Color: #000000 @ 40%
```

**Shadow SM**
```
Type: Drop shadow (layer 1)
X: 0, Y: 2, Blur: 4
Color: #000000 @ 50%

Type: Drop shadow (layer 2)
X: 0, Y: 1, Blur: 2
Color: #000000 @ 40%
```

**Shadow MD**
```
Type: Drop shadow (layer 1)
X: 0, Y: 4, Blur: 6
Color: #000000 @ 55%

Type: Drop shadow (layer 2)
X: 0, Y: 2, Blur: 4
Color: #000000 @ 45%
```

**Shadow LG**
```
Type: Drop shadow (layer 1)
X: 0, Y: 12, Blur: 24
Color: #000000 @ 65%

Type: Drop shadow (layer 2)
X: 0, Y: 6, Blur: 12
Color: #000000 @ 55%
```

**Shadow XL**
```
Type: Drop shadow (layer 1)
X: 0, Y: 24, Blur: 48
Color: #000000 @ 70%

Type: Drop shadow (layer 2)
X: 0, Y: 12, Blur: 24
Color: #000000 @ 60%
```

**Shadow 2XL**
```
Type: Drop shadow
X: 0, Y: 32, Blur: 64
Color: #000000 @ 75%
```

---

## Step 3: Set Up Icons

### Install Lucide Icons Plugin
1. Go to Plugins > Find more plugins
2. Search for **Iconify** or **Lucide Icons**
3. Install and authorize

### Common Icons Needed
- `plus` - Add photo
- `x` - Close
- `trash-2` - Delete
- `upload` - Upload action
- `wallet` - Empty state
- `share-2` - Share
- `settings` - Settings
- `chevron-left` - Previous
- `chevron-right` - Next

💡 **Tip**: Create a page for icon reference with all icons at 16px, 20px, and 24px sizes

---

## Step 4: Build Atomic Components

### 4.1 Button Component

1. **Create base button frame**
   - Frame: 40px height × auto width
   - Auto Layout: Horizontal, 16px padding (left/right), 10px (top/bottom)
   - Fill: Apply `brand/primary` color style
   - Border: 1px solid (slightly darker)
   - Corner radius: 9px
   - Effect: None (add on hover variant)

2. **Add text**
   - Text: "Button"
   - Style: Apply `text/button`
   - Color: White (#FFFFFF)
   - Center aligned

3. **Create component**
   - Right-click > Create component
   - Name: `Button`

4. **Add variants**
   - Create variants: Default, Hover, Active, Disabled
   - Create variants: Primary, Destructive, Ghost, Outline
   - Create size variants: Small (32px), Medium (40px), Large (44px)

**Variant Properties:**
```
Property: State
  - Default
  - Hover (add shadow-sm)
  - Active (scale 97%)
  - Disabled (50% opacity)

Property: Variant
  - Primary (blue background)
  - Destructive (red background)
  - Ghost (transparent)
  - Outline (border only)

Property: Size
  - Small (32px, 12px padding)
  - Medium (40px, 16px padding)
  - Large (44px, 20px padding)
```

---

### 4.2 Card Component

1. **Create frame**
   - Frame: Auto width × Auto height
   - Auto Layout: Vertical, 24px padding
   - Fill: Apply `background/card` (#1F1F1F)
   - Stroke: 1px, `border/card` (#292929)
   - Corner radius: 12px
   - Effect: Apply `shadow-sm`

2. **Add placeholder content**
   - Title text (text/headline)
   - Body text (text/body/regular)

3. **Create component**
   - Name: `Card`

---

### 4.3 Photo Card Component

1. **Create square frame**
   - Frame: 120px × 120px (will be resized in grid)
   - Constraints: Scale (to maintain aspect ratio)
   - Fill: Apply `background/card`
   - Stroke: 1px, `border/card`
   - Corner radius: 12px
   - Clip content: Yes

2. **Add placeholder image**
   - Rectangle: Fill frame
   - Fill: Image or placeholder color
   - Name layer: "Photo Image"

3. **Add delete button** (top-right)
   - Position: Absolute, 8px from top, 8px from right
   - Size: 32px × 32px
   - Fill: `brand/destructive`
   - Corner radius: 6px
   - Icon: `trash-2` (16px)
   - Default: Hidden or 0% opacity

4. **Add hover overlay**
   - Rectangle: Fill frame
   - Fill: Linear gradient (transparent to rgba(0,0,0,0.2))
   - Blend: Normal
   - Default: 0% opacity
   - Name: "Hover Overlay"

5. **Create component with variants**
   - Variant: Default (delete hidden, no overlay)
   - Variant: Hover (delete visible, overlay visible, slight scale)

**Component Structure:**
```
Photo Card [Component]
├─ Photo Image [Fill]
├─ Hover Overlay [0% → 100%]
└─ Delete Button [32×32, top-right]
   └─ Trash Icon [16px]
```

---

### 4.4 Add Photo Card Component

1. **Create frame** (same size as Photo Card)
   - Frame: 120px × 120px
   - Fill: Apply `background/card`
   - Stroke: 2px dashed, `border/primary`
   - Corner radius: 12px

2. **Add plus icon** (centered)
   - Icon: `plus` (24px)
   - Color: `text/secondary`
   - Position: Centered

3. **Create component with variants**
   - Variant: Default
   - Variant: Hover (border solid, icon color primary)
   - Variant: Disabled (50% opacity)

---

## Step 5: Build Composite Components

### 5.1 Header Component

1. **Create frame**
   - Auto Layout: Vertical
   - Width: Fill container (mobile frame width)
   - Padding: 16px horizontal, 32px top, 24px bottom
   - Fill: Transparent

2. **Add title row**
   - Auto Layout: Horizontal, Space between
   - Text: "Photo Wallet" (text/headline)
   - Button: Install button component

3. **Add subtitle**
   - Text: Tagline (text/body/regular, text/secondary)
   - Max width: 512px

4. **Create component**
   - Name: `Header`

---

### 5.2 Empty State Component

1. **Create card frame**
   - Max width: 448px
   - Auto Layout: Vertical, 48px padding
   - Centered in mobile frame
   - Apply Card component styles

2. **Add icon circle**
   - Frame: 80px × 80px
   - Corner radius: 50% (full circle)
   - Fill: `background/popover` (muted)
   - Icon: `wallet` (40px, centered)

3. **Add title**
   - Text: "No Photos Yet"
   - Style: text/headline
   - Margin-top: 24px

4. **Add description**
   - Text: Tagline
   - Style: text/body/regular, text/secondary
   - Margin-top: 12px

5. **Add button**
   - Use Button component (Large, Primary)
   - Text: "Add Your First Photo"
   - Width: Fill
   - Margin-top: 32px

6. **Create component**
   - Name: `Empty State`

---

### 5.3 Photo Grid Component

1. **Create frame**
   - Auto Layout: Horizontal wrap
   - Padding: 16px
   - Gap: 8px (horizontal and vertical)
   - Width: Fill container

2. **Add Photo Cards**
   - Insert 7 Photo Card components
   - Insert 1 Add Photo Card component
   - All cards will auto-resize based on 3-column grid

3. **Set up grid behavior**
   - Each card: Width Fill, Height 1:1 aspect ratio
   - Grid wraps at 3 items per row

4. **Create component**
   - Name: `Photo Grid`

💡 **Tip**: Use Auto Layout's "Wrap" feature for responsive grid

---

## Step 6: Create Full Screen Designs

### 6.1 Home Screen - Empty State

1. **Create mobile frame**
   - iPhone 14 Pro (393 × 852) or custom
   - Fill: `background/primary` (#141414)

2. **Add Header component** (top)

3. **Add Empty State component** (centered)

4. **Name frame**: "Home - Empty"

---

### 6.2 Home Screen - With Photos

1. **Duplicate previous frame**

2. **Remove Empty State component**

3. **Add Photo Grid component**
   - Position below header

4. **Name frame**: "Home - With Photos"

---

### 6.3 Photo Viewer Screen

1. **Create mobile frame**
   - Fill: rgba(0, 0, 0, 0.95)

2. **Add top bar**
   - Auto Layout: Horizontal, Space between
   - Padding: 16px
   - Close button (left): `x` icon, 40px button
   - Counter (center): "3 of 5" text
   - Share button (right): `share-2` icon, 40px button

3. **Add centered photo**
   - Image placeholder
   - Max width/height: Contained
   - Centered

4. **Add navigation arrows** (if multiple photos)
   - Left: `chevron-left` (40px button, 16px from left edge)
   - Right: `chevron-right` (40px button, 16px from right edge)

5. **Add zoom indicator** (bottom center)
   - Text: "2.0x"
   - Background: rgba(0, 0, 0, 0.6)
   - Padding: 4px 12px
   - Border radius: 999px (pill)

6. **Name frame**: "Photo Viewer"

---

## Step 7: Add Interactions (Prototype)

### Set up basic prototype flows:

1. **Empty State → Add Photo**
   - Click "Add First Photo" button
   - Transition: Instant (file picker simulation)

2. **Photo Card → Photo Viewer**
   - Click any photo card
   - Transition: Smart Animate, 300ms Ease Out
   - From: Photo card position
   - To: Full screen centered

3. **Photo Viewer → Close**
   - Click X button or swipe down (advanced)
   - Transition: Smart Animate, 300ms Ease In

4. **Navigation in Viewer**
   - Click arrow buttons
   - Transition: Smart Animate, 200ms Ease In-Out
   - Change current photo

💡 **Advanced**: Use Interactive Components for hover states

---

## Step 8: Organize & Document

### File Organization

```
📁 Photo Wallet PWA
├── 📄 Cover (Project overview)
├── 🎨 Design System
│   ├── Colors (Color styles reference)
│   ├── Typography (Text styles reference)
│   ├── Spacing (Spacing scale)
│   ├── Shadows (Effect styles reference)
│   └── Icons (Icon library)
├── 🧩 Components
│   ├── Button (All variants)
│   ├── Card
│   ├── Photo Card
│   ├── Add Photo Card
│   ├── Header
│   ├── Empty State
│   └── Photo Grid
├── 📱 Screens
│   ├── Home - Empty
│   ├── Home - With Photos
│   └── Photo Viewer
└── 🎭 Prototypes
    └── User Flow
```

### Add Documentation

1. **Cover page**
   - Project title and description
   - Color palette overview
   - Typography samples
   - Quick links to main sections

2. **Component annotations**
   - Add measurement guides
   - Note interaction behaviors
   - Document responsive rules

---

## Step 9: Export Assets (Optional)

If you need to export assets for development:

1. **Select component/frame**
2. **Right sidebar > Export**
3. **Settings:**
   - Format: PNG or SVG
   - Scale: 1x, 2x, 3x (for retina)
4. **Export**

### Common exports:
- Icons: SVG at 24px
- Components: PNG at 2x scale
- Screenshots: PNG for documentation

---

## Quick Tips for Success

### Use Auto Layout Everywhere
- Enables responsive behavior
- Makes components flexible
- Easier to maintain

### Create Variants for States
- Default, Hover, Active, Disabled
- Easier prototyping
- Consistent state management

### Use Constraints Properly
- Scale: For images and icons
- Left/Right: For full-width elements
- Center: For centered content

### Leverage Components
- Build once, use everywhere
- Update main component to update all instances
- Detach only when necessary

### Name Layers Clearly
- Use descriptive names
- Group related elements
- Use emoji for quick visual scanning 📱🎨🧩

### Maintain Consistency
- Always use color styles (never hardcode colors)
- Always use text styles
- Always use effect styles for shadows
- Follow the spacing system (8px grid)

---

## Troubleshooting

**Q: Fonts don't look right**
- Install SF Pro Display (Apple) or use Inter as fallback
- Ensure font weights are available (400, 500, 600)

**Q: Auto Layout not wrapping**
- Enable "Wrap" in Auto Layout settings
- Set child items to "Fixed" width or "Fill"

**Q: Shadows look different from specs**
- Double-check blur and opacity values
- Use multiple shadow layers for complex shadows
- Shadows in Figma may render slightly differently than CSS

**Q: Components not updating**
- Make sure you're editing the main component, not an instance
- Check if instance has overrides that prevent updates

**Q: Grid not aligning to 3 columns**
- Use Auto Layout with wrap
- Set each card to equal width (Fill)
- Ensure gap is set to 8px

---

## Next Steps

1. **Share with stakeholders**
   - Get feedback on design
   - Iterate based on user needs

2. **Create developer handoff**
   - Use Figma Inspect for measurements
   - Export assets as needed
   - Share Figma link for specs

3. **Maintain design system**
   - Update components as app evolves
   - Keep styles in sync with code
   - Document changes

4. **Consider design tokens export**
   - Use plugins like Design Tokens
   - Export to JSON for direct code use
   - Sync with development workflow

---

## Resources

### Figma Documentation
- Auto Layout: https://help.figma.com/hc/en-us/articles/360040451373
- Components: https://help.figma.com/hc/en-us/articles/360038662654
- Variants: https://help.figma.com/hc/en-us/articles/360055471353

### Design System References
- See `FIGMA_DESIGN_SYSTEM.md` for complete design tokens
- See `FIGMA_COMPONENTS_SPEC.md` for detailed component specs
- See `design_guidelines.md` for design philosophy

### Plugins to Install
- **Iconify** - Icon library access
- **Stark** - Accessibility checking
- **Contrast** - Color contrast validation
- **Auto Layout** - Advanced layout tools (built-in)

---

You now have everything you need to recreate the Photo Wallet PWA in Figma! Start with the design tokens, build atomic components, then compose them into full screens. Good luck!
