# Photo Wallet PWA - Figma Design System Export

## Overview

This document provides a comprehensive design system specification for recreating the Photo Wallet PWA in Figma. It includes all design tokens, component specifications, and layout guidelines needed for pixel-perfect design recreation.

---

## Design Tokens

### Color System

#### Dark Mode (Primary Theme)

**Backgrounds**
```
Background Primary:     HSL(0, 0%, 8%)     RGB(20, 20, 20)      #141414
Card Background:        HSL(0, 0%, 12%)    RGB(31, 31, 31)      #1F1F1F
Popover Background:     HSL(0, 0%, 16%)    RGB(41, 41, 41)      #292929
Surface Elevated:       HSL(0, 0%, 16%)    RGB(41, 41, 41)      #292929
```

**Text Colors**
```
Text Primary:           HSL(0, 0%, 98%)    RGB(250, 250, 250)   #FAFAFA
Text Secondary:         HSL(210, 6%, 65%)  RGB(159, 163, 171)   #9FA3AB
Text Muted:             HSL(210, 6%, 65%)  RGB(159, 163, 171)   #9FA3AB
```

**Borders & Dividers**
```
Border Primary:         HSL(0, 0%, 20%)    RGB(51, 51, 51)      #333333
Card Border:            HSL(0, 0%, 16%)    RGB(41, 41, 41)      #292929
Popover Border:         HSL(0, 0%, 22%)    RGB(56, 56, 56)      #383838
```

**Brand & Accent Colors**
```
Primary Blue:           HSL(210, 100%, 60%) RGB(51, 153, 255)   #3399FF
Primary Foreground:     HSL(210, 100%, 98%) RGB(250, 252, 255)  #FAFCFF
Destructive Red:        HSL(0, 85%, 60%)    RGB(238, 57, 57)    #EE3939
Destructive Foreground: HSL(0, 85%, 98%)    RGB(255, 248, 248)  #FFF8F8
```

**Interaction States**
```
Hover Elevate:          rgba(255, 255, 255, 0.04)
Active Elevate:         rgba(255, 255, 255, 0.09)
Button Outline:         rgba(255, 255, 255, 0.10)
```

**Photo Viewer Overlay**
```
Backdrop:               HSL(0, 0%, 5%) @ 95% opacity  #0D0D0D
UI Chrome Visible:      White @ 20% opacity
UI Chrome Faded:        White @ 5% opacity
Gradient Overlay:       Linear gradient from transparent to rgba(0,0,0,0.20)
```

#### Light Mode (Secondary Theme)

**Backgrounds**
```
Background Primary:     HSL(0, 0%, 98%)    RGB(250, 250, 250)   #FAFAFA
Card Background:        HSL(0, 0%, 96%)    RGB(245, 245, 245)   #F5F5F5
Popover Background:     HSL(0, 0%, 92%)    RGB(235, 235, 235)   #EBEBEB
```

**Text Colors**
```
Text Primary:           HSL(0, 0%, 10%)    RGB(26, 26, 26)      #1A1A1A
Text Secondary:         HSL(210, 8%, 35%)  RGB(84, 88, 94)      #54585E
```

**Borders**
```
Border Primary:         HSL(0, 0%, 88%)    RGB(224, 224, 224)   #E0E0E0
Card Border:            HSL(0, 0%, 91%)    RGB(232, 232, 232)   #E8E8E8
```

---

## Typography

### Font Family
```
Primary Font Stack: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif
```

### Type Scale

**Display (Hero Headings)**
```
Mobile:   32px / 2rem
Desktop:  40px / 2.5rem
Weight:   600 (Semibold)
Tracking: -0.02em (tight)
```

**Headline (Section Titles)**
```
Size:     24px / 1.5rem
Weight:   600 (Semibold)
Tracking: -0.02em
```

**Body Large**
```
Size:     16px / 1rem
Weight:   400 (Regular)
Line Height: 1.5 (24px)
```

**Body Regular**
```
Size:     14px / 0.875rem
Weight:   400 (Regular)
Line Height: 1.5 (21px)
```

**Caption/Metadata**
```
Size:     14px / 0.875rem
Weight:   400 (Regular)
Tracking: 0.01em (wide)
Opacity:  Use text-secondary color
```

**Small/Helper Text**
```
Size:     12px / 0.75rem
Weight:   400 (Regular)
```

---

## Spacing System

### Spacing Scale (Base: 4px)
```
spacing-2:   8px   (0.5rem)
spacing-4:   16px  (1rem)
spacing-6:   24px  (1.5rem)
spacing-8:   32px  (2rem)
spacing-12:  48px  (3rem)
spacing-16:  64px  (4rem)
```

### Layout Spacing Conventions
```
Tight spacing:    8px   (gap between related items)
Standard spacing: 16px  (default padding/margin)
Generous spacing: 32px  (section padding)
Section spacing:  48-64px (major section breaks)
```

### Container Padding
```
Mobile:   16px horizontal padding (px-4)
Desktop:  Max-width 1152px (max-w-6xl) centered
```

---

## Border Radius

### Radius Scale
```
sm:  3px   (0.1875rem)  - Small elements
md:  6px   (0.375rem)   - Inputs, small buttons
lg:  9px   (0.5625rem)  - Standard buttons, cards
xl:  12px  (0.75rem)    - Photo cards, modals
2xl: 16px  (1rem)       - Large surfaces
full: 50%              - Circular elements (FAB, avatars)
```

---

## Shadows & Elevation

### Shadow Scale (Dark Mode)

**2XS** - Subtle touch
```
0px 1px 2px 0px hsl(0 0% 0% / 0.40)
```

**XS** - Light elevation
```
0px 1px 3px 0px hsl(0 0% 0% / 0.45)
```

**SM** - Card hover
```
0px 2px 4px 0px hsl(0 0% 0% / 0.50),
0px 1px 2px -1px hsl(0 0% 0% / 0.40)
```

**MD** - Standard elevation
```
0px 4px 6px 0px hsl(0 0% 0% / 0.55),
0px 2px 4px -1px hsl(0 0% 0% / 0.45)
```

**LG** - Photo cards
```
0px 12px 24px 0px hsl(0 0% 0% / 0.65),
0px 6px 12px -3px hsl(0 0% 0% / 0.55)
```

**XL** - Modals, dialogs
```
0px 24px 48px 0px hsl(0 0% 0% / 0.70),
0px 12px 24px -6px hsl(0 0% 0% / 0.60)
```

**2XL** - Floating action button
```
0px 32px 64px 0px hsl(0 0% 0% / 0.75)
```

---

## Grid System

### Photo Grid Layout
```
Mobile (default):  3 columns  (grid-cols-3)
Gap:               8px (gap-2)
```

### Grid Item Aspect Ratio
```
Photo Cards:       1:1 (square)
```

---

## Component Specifications

### 1. Header Component

**Container**
- Padding: 16px horizontal, 32px top, 24px bottom
- Layout: Flex row, space-between

**App Title**
- Text: "Photo Wallet"
- Size: 24px (1.5rem headline)
- Weight: 600 (Semibold)
- Color: Text Primary
- Tracking: -0.02em

**Subtitle/Tagline**
- Text: "Your important photos at your fingertips..."
- Size: 14px (0.875rem)
- Color: Text Secondary (muted-foreground)
- Max-width: 512px (max-w-lg)
- Margin-top: 8px

**Install Button** (top-right)
- Positioned absolute or flex-end
- See Button component specs

---

### 2. Photo Card Component

**Container (Card)**
- Aspect ratio: 1:1 square
- Border radius: 12px (rounded-xl)
- Overflow: hidden
- Cursor: pointer
- Position: relative
- Background: Card color (#1F1F1F in dark mode)
- Border: 1px solid card-border

**Image**
- Object-fit: cover
- Width: 100%
- Height: 100%
- Loading: lazy

**Hover State**
- Transform: scale(1.05)
- Transition: 150ms ease-out
- Shadow: Elevated (shadow-xl)

**Gradient Overlay** (on hover)
- Position: absolute, inset 0
- Gradient: linear-gradient(to top, rgba(0,0,0,0.20), transparent)
- Opacity: 0 default, 100 on hover
- Transition: opacity 300ms

**Delete Button** (top-right corner)
- Position: absolute, top 8px, right 8px
- Size: 32px × 32px (w-8 h-8)
- Icon: Trash2, 16px (w-4 h-4)
- Background: Destructive red
- Border radius: 6px (rounded-md)
- Opacity: 0 default, 100 on card hover
- Transform: scale(0.75) default, scale(1) on hover
- Transition: all 150ms

---

### 3. Add Photo Card Component

**Container**
- Same as Photo Card (1:1 aspect ratio, 12px radius)
- Border: 2px dashed border color
- Background: Card background
- Cursor: pointer

**Content (Centered)**
- Icon: Plus (+) symbol
- Size: 24px (w-6 h-6)
- Color: Text Secondary (muted-foreground)

**Hover State**
- Border color: Primary blue
- Icon color: Primary blue
- Background: Slightly elevated (hover-elevate)
- Transition: all 150ms

**Disabled State** (when 10 photos reached)
- Opacity: 50%
- Cursor: not-allowed
- Hover effects: disabled

---

### 4. Empty State Component

**Container (Card)**
- Padding: 48px (p-12)
- Max-width: 448px (max-w-md)
- Centered in viewport
- Background: Card color
- Border radius: 12px
- Shadow: MD elevation

**Icon Container**
- Size: 80px × 80px (w-20 h-20)
- Border radius: 50% (rounded-full)
- Background: Muted (#292929 dark mode)
- Icon: Wallet, 40px (w-10 h-10)
- Color: Muted foreground
- Margin-bottom: 24px

**Title**
- Text: "No Photos Yet"
- Size: 24px (2xl)
- Weight: 600 (Semibold)
- Color: Text Primary
- Margin-bottom: 12px

**Description**
- Text: "Add your first cherished photo..."
- Size: 14px
- Color: Text Secondary
- Margin-bottom: 32px

**CTA Button**
- Size: Large (lg)
- Width: 100%
- Icon: Upload, 16px, margin-right 8px
- See Button specs

---

### 5. Photo Viewer (Full-Screen)

**Backdrop**
- Position: fixed, inset 0
- Background: rgba(0, 0, 0, 0.95) or HSL(0, 0%, 5%, 0.95)
- Z-index: 50

**Top UI Bar**
- Position: absolute, top 0, left 0, right 0
- Padding: 16px
- Display: flex, space-between
- Background: transparent
- Opacity: 1 (visible), 0 (hidden)
- Transition: opacity 300ms
- Auto-hide: after 3 seconds

**Close Button** (top-left)
- Size: 40px icon button
- Icon: X, 24px (w-6 h-6)
- Color: White
- Background: transparent
- Hover: rgba(255, 255, 255, 0.20)

**Photo Counter** (top-center)
- Text: "3 of 5"
- Size: 14px (sm)
- Color: White
- Background: transparent

**Share Button** (top-right, if supported)
- Size: 40px icon button
- Icon: Share2, 24px
- Color: White
- Hover: rgba(255, 255, 255, 0.20)

**Photo Image (Center)**
- Position: centered
- Max-width: 100vw
- Max-height: 100vh
- Object-fit: contain
- Touch-action: none (for gestures)

**Zoom Indicator** (bottom-center, when zoomed)
- Position: absolute, bottom 16px, centered
- Text: "2.0x"
- Size: 14px (sm)
- Color: White
- Background: rgba(0, 0, 0, 0.60)
- Padding: 4px 12px
- Border radius: 999px (rounded-full)

**Navigation Arrows** (left/right, if multiple photos)
- Size: 40px icon buttons
- Position: absolute, centered vertically
- Left: 16px / Right: 16px from edge
- Color: White
- Border: 1px solid rgba(255, 255, 255, 0.50)
- Background: transparent
- Hover: rgba(255, 255, 255, 0.20)

---

### 6. Button Component

**Sizes**

**Small**
```
Height: 32px
Padding: 0 12px
Font size: 14px
Icon size: 16px
```

**Medium (Default)**
```
Height: 40px
Padding: 0 16px
Font size: 14px
Icon size: 20px
```

**Large**
```
Height: 44px
Padding: 0 20px
Font size: 16px
Icon size: 20px
```

**Icon Only**
```
Size: 40px × 40px
Padding: 10px
Icon size: 20px
```

**Variants**

**Primary (Default)**
- Background: Primary blue (#3399FF)
- Text: Primary foreground white
- Border: Computed darker border
- Hover: Elevate background
- Active: More elevation

**Destructive**
- Background: Destructive red (#EE3939)
- Text: White
- Border: Darker red
- Hover: Elevate

**Ghost**
- Background: Transparent
- Text: Primary text color
- Border: None
- Hover: Elevate-1 overlay

**Outline**
- Background: Transparent
- Text: Primary text
- Border: 1px solid border color
- Hover: Elevate-1 overlay

**Border Radius**
- Default: 9px (lg)
- Icon buttons: 6px (md)

**Minimum Touch Target**
- 44px × 44px for all interactive buttons

---

### 7. Card Component

**Base Card**
```
Background: Card color (#1F1F1F dark mode)
Border: 1px solid card-border (#292929)
Border radius: 12px (rounded-xl)
Padding: 24px (p-6)
Shadow: SM elevation
```

**Hover State**
```
Shadow: MD elevation
Transition: shadow 150ms ease-out
```

---

### 8. Dialog/Modal Component

**Overlay (Backdrop)**
```
Position: fixed, inset 0
Background: rgba(0, 0, 0, 0.80)
Z-index: 50
Backdrop-blur: 4px (optional)
```

**Dialog Container**
```
Background: Popover color (#292929 dark)
Border: 1px solid popover-border
Border radius: 16px (rounded-2xl)
Padding: 24px (p-6)
Max-width: 512px (max-w-lg)
Shadow: 2XL elevation
Position: centered
```

**Dialog Title**
```
Size: 18px (lg)
Weight: 600 (Semibold)
Margin-bottom: 8px
```

**Dialog Description**
```
Size: 14px (sm)
Color: Text Secondary
Margin-bottom: 24px
```

**Dialog Footer**
```
Display: flex
Justify: flex-end
Gap: 8px
Margin-top: 24px
```

---

### 9. Install Prompt/Banner

**Toast Style Prompt** (bottom)
```
Position: fixed, bottom 0, left/right 0
Background: Card color
Border-top: 1px solid border
Border-radius: 16px 16px 0 0 (rounded-t-2xl)
Padding: 16px
Shadow: XL elevation
```

**Message Text**
```
Text: "Add Photo Wallet to your home screen"
Size: 14px
Weight: 500 (Medium)
```

**Buttons**
```
"Install" - Primary variant
"Not now" - Ghost variant
Display: inline-flex
Gap: 8px
```

---

## Animations & Transitions

### Timing Functions
```
Ease-out standard:   150ms cubic-bezier(0, 0, 0.2, 1)
Spring physics:      300ms stiffness, 30 damping
Fade transitions:    200ms linear
Photo viewer open:   400ms spring animation
```

### Transform Animations

**Hover Scale**
```
Transform: scale(1.05)
Transition: 150ms ease-out
```

**Active Press**
```
Transform: scale(0.97)
Transition: 100ms ease-out
```

**Photo Viewer Entry**
```
Initial: scale(0.3), opacity 0
Animate: scale(1), opacity 1
Duration: 400ms spring
```

**Photo Viewer Exit**
```
Initial: scale(1), opacity 1
Animate: scale(0.3), opacity 0
Duration: 300ms ease [0.32, 0.72, 0, 1]
```

### Gesture Feedback

**Swipe Threshold**
```
Distance: 80px drag
Velocity: 0.3
```

**Pinch Zoom**
```
Range: 1x to 3x
Rubber banding: enabled
Physics: spring
```

**Double-tap Zoom**
```
Toggle: 1x ↔ 2x
Duration: 250ms ease-out
```

---

## Accessibility Requirements

### Touch Targets
```
Minimum size: 44px × 44px
Recommended: 48px × 48px for primary actions
```

### Focus Indicators
```
Ring: 2px solid ring color (primary blue)
Offset: 2px
Border radius: inherit from element
```

### Color Contrast Ratios
```
Text Primary on Background: ≥ 7:1 (AAA)
Text Secondary on Background: ≥ 4.5:1 (AA)
Button text on Primary: ≥ 4.5:1 (AA)
```

### ARIA & Semantic HTML
- All interactive elements have accessible names
- Images have descriptive alt text
- Live regions for dynamic updates (photo count)
- Keyboard navigation fully supported

---

## Iconography

### Icon Library
**Lucide React** (or Lucide icons in Figma)

### Icon Sizes
```
xs:  16px (w-4 h-4)
sm:  20px (w-5 h-5)
md:  24px (w-6 h-6)
lg:  32px (w-8 h-8)
xl:  40px (w-10 h-10)
```

### Commonly Used Icons
```
Plus (+):       Upload/Add photo
X:              Close/Cancel
Trash2:         Delete
Upload:         Upload action
Wallet:         Empty state
Share2:         Share photo
Settings:       Settings menu
ChevronLeft:    Previous
ChevronRight:   Next
```

### Icon Colors
- Default: Inherit from parent
- Muted: Text Secondary
- Primary actions: Primary blue
- Danger actions: Destructive red
- On dark backgrounds: White

---

## Responsive Breakpoints

### Grid Columns
```
Mobile (default):    3 columns
```

### Typography Responsive
```
Display heading:
  Mobile:  32px (2rem)
  Desktop: 40px (2.5rem)
```

### Component Sizing
```
Modal max-width:     512px
Content max-width:   1152px (max-w-6xl)
Empty state:         448px (max-w-md)
```

---

## States & Variations

### Component States

**Default**
- Base appearance

**Hover**
- Interactive elements show elevation
- Cursor changes to pointer
- Subtle animations (scale, shadow)

**Active/Pressed**
- Stronger elevation or scale down
- Visual feedback for touch

**Focus**
- 2px ring, primary color
- High contrast for accessibility

**Disabled**
- Opacity: 50%
- Cursor: not-allowed
- Hover effects: none
- Color: desaturated

**Loading**
- Spinner or skeleton
- Reduced opacity
- Disabled interactions

---

## Special Design Notes

### Content-First Philosophy
- Photos always take visual priority
- UI chrome fades into background
- Minimal visual noise
- Maximum focus on photo content

### Dark Mode Primary
- App designed dark-mode first
- Light mode is secondary theme
- Dark backgrounds reduce eye strain
- Photos pop against dark surfaces

### Gesture-Based Interaction
- Touch-friendly design
- Large hit areas
- Visual feedback for all gestures
- Tutorial shown on first use

### Privacy & Trust Indicators
- Wallet metaphor reinforces personal ownership
- "Local only" messaging throughout
- No cloud/sync iconography
- Secure, intimate aesthetic

---

## Implementation in Figma

### Recommended Figma Setup

1. **Create Color Styles**
   - Create all color tokens as Figma color styles
   - Group by: Background, Text, Border, Brand, Interaction
   - Name convention: `color/category/variant`

2. **Create Text Styles**
   - Set up all typography styles
   - Name convention: `text/size/weight`
   - Example: `text/display/semibold`, `text/body/regular`

3. **Create Effect Styles**
   - Set up all shadow levels
   - Name convention: `shadow/size`
   - Example: `shadow/lg`, `shadow/xl`

4. **Create Components**
   - Build atomic components first (Button, Card, Input)
   - Then composite components (PhotoCard, EmptyState)
   - Use Auto Layout for responsive behavior
   - Create variants for states (hover, pressed, disabled)

5. **Create Grid Layout**
   - Set up 3-column grid with 8px gutters
   - Use Auto Layout for photo grid
   - Create responsive frames for different screen sizes

6. **Document with Annotations**
   - Add spacing guides
   - Note interaction behaviors
   - Link to prototype for gestures

### Figma Plugins to Consider
- **Iconify** - For Lucide icons
- **Stark** - Accessibility checking
- **Contrast** - Color contrast validation
- **Auto Layout** - Built-in for responsive design
- **Component** - Advanced component management

---

## File Organization Suggestion

```
📁 Photo Wallet PWA
├── 📄 Cover / Overview
├── 🎨 Design System
│   ├── Colors
│   ├── Typography
│   ├── Spacing
│   ├── Shadows
│   └── Icons
├── 🧩 Components
│   ├── Atoms (Button, Input, Card)
│   ├── Molecules (PhotoCard, EmptyState)
│   └── Organisms (PhotoGrid, PhotoViewer, Header)
├── 📱 Screens
│   ├── Home - Empty State
│   ├── Home - With Photos
│   ├── Photo Viewer
│   └── Settings/Dialogs
└── 🎭 Prototypes
    └── Interactive gestures flow
```

---

This design system provides everything needed to recreate the Photo Wallet PWA in Figma with pixel-perfect accuracy. Use this as a reference when building components and screens in your design file.
