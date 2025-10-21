# Photo Wallet PWA - Figma Design Specification

This document provides a complete specification for recreating the Photo Wallet PWA design in Figma.

## Design System Setup

### 1. Color Styles

Create these color styles in Figma (HSL values for precision):

#### Dark Mode (Primary Theme)
```
Background/Primary         HSL(0, 0%, 8%)      #141414
Background/Surface         HSL(0, 0%, 12%)     #1F1F1F
Background/Elevated        HSL(0, 0%, 16%)     #292929
Border/Default             HSL(0, 0%, 20%)     #333333

Text/Primary               HSL(0, 0%, 98%)     #FAFAFA
Text/Secondary             HSL(0, 0%, 65%)     #A6A6A6
Text/Muted                 HSL(0, 0%, 70%)     #B3B3B3

Accent/Primary             HSL(210, 100%, 60%) #3399FF
Accent/Hover               HSL(210, 100%, 55%) #1A8CFF
Accent/Active              HSL(210, 100%, 50%) #0080FF

Destructive/Primary        HSL(0, 85%, 60%)    #EB5757
Destructive/Hover          HSL(0, 85%, 55%)    #E84040
Destructive/Active         HSL(0, 85%, 50%)    #E52929

Success/Primary            HSL(142, 76%, 36%)  #16A34A
Warning/Primary            HSL(38, 92%, 50%)   #F59E0B

Photo Viewer Backdrop      HSL(0, 0%, 5%)      #0D0D0D at 95% opacity
UI Chrome Active           White               #FFFFFF at 20% opacity
UI Chrome Inactive         White               #FFFFFF at 5% opacity

Overlay/Gradient Start     Transparent         rgba(0,0,0,0)
Overlay/Gradient End       Black               rgba(0,0,0,0.2)
```

### 2. Typography Styles

Create these text styles in Figma:

#### Font Family
**System Font Stack**: SF Pro (macOS), Segoe UI (Windows), Roboto (Android)
For Figma: Use **SF Pro Display** or **Inter** as fallback

#### Text Styles
```
Display/Large (Desktop)
- Font: SF Pro Display
- Weight: 600 (Semibold)
- Size: 40px (2.5rem)
- Line Height: 48px (1.2)
- Letter Spacing: -0.8px (-0.02em)

Display/Small (Mobile)
- Font: SF Pro Display
- Weight: 600 (Semibold)
- Size: 32px (2rem)
- Line Height: 40px (1.25)
- Letter Spacing: -0.64px (-0.02em)

Headline
- Font: SF Pro Display
- Weight: 600 (Semibold)
- Size: 24px (1.5rem)
- Line Height: 32px (1.33)
- Letter Spacing: -0.48px (-0.02em)

Body/Default
- Font: SF Pro Text
- Weight: 400 (Regular)
- Size: 16px (1rem)
- Line Height: 24px (1.5)
- Letter Spacing: 0

Body/Medium
- Font: SF Pro Text
- Weight: 500 (Medium)
- Size: 16px (1rem)
- Line Height: 24px (1.5)
- Letter Spacing: 0

Body/Semibold
- Font: SF Pro Text
- Weight: 600 (Semibold)
- Size: 16px (1rem)
- Line Height: 24px (1.5)
- Letter Spacing: 0

Small/Caption
- Font: SF Pro Text
- Weight: 400 (Regular)
- Size: 14px (0.875rem)
- Line Height: 20px (1.43)
- Letter Spacing: 0.14px (0.01em)

Tiny/Metadata
- Font: SF Pro Text
- Weight: 400 (Regular)
- Size: 12px (0.75rem)
- Line Height: 16px (1.33)
- Letter Spacing: 0.12px (0.01em)
```

### 3. Spacing System

Create these spacing values as **Layout Grid** or **Spacing Tokens**:

```
Space-1: 4px   (0.25rem)
Space-2: 8px   (0.5rem)
Space-3: 12px  (0.75rem)
Space-4: 16px  (1rem)
Space-5: 20px  (1.25rem)
Space-6: 24px  (1.5rem)
Space-8: 32px  (2rem)
Space-10: 40px (2.5rem)
Space-12: 48px (3rem)
Space-16: 64px (4rem)
Space-20: 80px (5rem)
```

### 4. Corner Radius

Create these radius tokens:

```
Radius-SM:  6px   (rounded-md)
Radius-MD:  8px   (rounded-lg)
Radius-LG:  12px  (rounded-xl)
Radius-XL:  16px  (rounded-2xl)
Radius-Full: 9999px (rounded-full)
```

### 5. Shadows

Create these shadow effects:

```
Shadow-SM:
  X: 0, Y: 1, Blur: 2, Spread: 0
  Color: Black at 5% opacity

Shadow-MD:
  X: 0, Y: 4, Blur: 6, Spread: -1
  Color: Black at 10% opacity

Shadow-LG (Photo Cards):
  X: 0, Y: 10, Blur: 15, Spread: -3
  Color: Black at 10% opacity

Shadow-XL (Hover State):
  X: 0, Y: 20, Blur: 25, Spread: -5
  Color: Black at 15% opacity

Shadow-2XL (FAB Button):
  X: 0, Y: 25, Blur: 50, Spread: -12
  Color: Black at 25% opacity
```

---

## Screen Layouts

### Frame Sizes

Create these artboards in Figma:

```
Mobile Portrait:  375 x 812  (iPhone 13 Mini)
Mobile Large:     414 x 896  (iPhone 11 Pro Max)
Tablet Portrait:  768 x 1024 (iPad)
Desktop:          1440 x 900 (Standard Desktop)
```

---

## Component Specifications

### 1. App Header (With Photos)

**Frame:** `Header - With Photos`
**Size:** Full width × 72px height
**Layout:**
- Padding: 16px horizontal, 16px top, 8px bottom
- Flex: Horizontal, Space Between, Align Center

**Left Side:**
- Text: "Photo Wallet"
- Style: Headline (24px, 600 weight)
- Color: Text/Primary

**Right Side:**
- PhotoCounter Component (see below)
- Settings Icon Button (see below)
- Gap: 8px

---

### 2. Photo Counter Badge

**Component:** `PhotoCounter`
**Size:** Auto width × 32px height
**Layout:**
- Padding: 8px horizontal
- Border Radius: Radius-Full (pill shape)
- Background: Background/Surface
- Border: 1px solid Border/Default

**Content:**
- Text: "5/10" (example)
- Style: Small/Caption (14px)
- Color: Text/Secondary
- Alignment: Center

---

### 3. Settings Icon Button

**Component:** `IconButton/Settings`
**Size:** 40px × 40px
**Layout:**
- Border Radius: Radius-MD (8px)
- Background: Transparent
- Hover State: Background/Surface

**Icon:**
- Settings icon (gear/cog)
- Size: 20px × 20px
- Color: Text/Primary
- Centered

---

### 4. Photo Grid

**Component:** `PhotoGrid`
**Layout:**
- Grid Columns:
  - Mobile: 3 columns
  - Tablet: 3 columns
  - Desktop: 4 columns
- Gap: 8px (gap-2)
- Padding: 16px

**Grid Items:**
- PhotoCard components
- AddPhotoCard component (last position)

---

### 5. Photo Card

**Component:** `PhotoCard`
**Size:** Square (aspect ratio 1:1)
**Responsive Sizing:**
- Mobile (375px): ~111px × 111px each
- Tablet (768px): ~243px × 243px each
- Desktop (1440px): ~343px × 343px each

**Structure:**
```
└─ Card Container
   ├─ Photo Image (fill container, object-fit: cover)
   ├─ Gradient Overlay (bottom, from transparent to black/20%)
   └─ Delete Button (top-right, 8px inset)
```

**Default State:**
- Border Radius: Radius-LG (12px)
- Shadow: Shadow-LG
- Image: User photo (use placeholder)

**Hover State:**
- Transform: Scale 1.05
- Shadow: Shadow-XL
- Gradient Overlay: Opacity 100%
- Delete Button: Visible (scale 1.0, opacity 100%)

**Default State (Delete Button):**
- Opacity: 0%
- Scale: 0.75
- Transition: 150ms ease-out

---

### 6. Add Photo Card

**Component:** `AddPhotoCard`
**Size:** Same as PhotoCard (square, 1:1)
**Structure:**
```
└─ Card Container
   ├─ Dashed Border (2px, Border/Default)
   ├─ Plus Icon (centered, 32px)
   └─ Text: "Add Photo" (centered below icon)
```

**Styling:**
- Background: Background/Surface
- Border: 2px dashed Border/Default
- Border Radius: Radius-LG (12px)
- Padding: 16px

**Content (Centered Vertically & Horizontally):**
- Plus Icon: 32px × 32px, Color: Text/Secondary
- Text: "Add Photo"
  - Style: Small/Caption (14px)
  - Color: Text/Secondary
  - Margin-top: 12px from icon

**Hover State:**
- Background: Background/Elevated
- Border Color: Accent/Primary
- Icon & Text Color: Accent/Primary

---

### 7. Empty State

**Component:** `EmptyState`
**Frame:** Full width × Full height (centered content)

**Structure (Vertically Centered):**
```
└─ Container (max-width: 400px, centered)
   ├─ Wallet Icon Illustration (80px)
   ├─ Headline Text
   ├─ Body Text
   └─ Upload Button
```

**Content:**
1. **Icon**: Wallet with photo slots
   - Size: 80px × 80px
   - Color: Text/Secondary
   - Style: Line art/outline

2. **Headline**: "Your Photo Wallet is Empty"
   - Style: Display/Small (32px, 600 weight)
   - Color: Text/Primary
   - Margin-top: 24px from icon

3. **Body**: "Add up to 10 photos that matter most to you. They're stored privately on your device."
   - Style: Body/Default (16px)
   - Color: Text/Secondary
   - Max-width: 400px
   - Text-align: Center
   - Margin-top: 12px from headline

4. **Button**: "Add Your First Photo"
   - Component: Button/Primary (see below)
   - Margin-top: 32px from body

---

### 8. Button Components

#### Primary Button
**Component:** `Button/Primary`
**Size:** Auto width × 44px height (minimum touch target)
**Layout:**
- Padding: 12px horizontal, 10px vertical
- Border Radius: Radius-MD (8px)
- Background: Accent/Primary
- Min-width: 120px

**Text:**
- Style: Body/Medium (16px, 500 weight)
- Color: White
- Text-align: Center

**States:**
- Default: Background Accent/Primary
- Hover: Background Accent/Hover
- Active: Background Accent/Active, Scale 0.98
- Disabled: Opacity 50%, Cursor not-allowed

#### Destructive Button
**Component:** `Button/Destructive`
- Same as Primary but:
- Background: Destructive/Primary
- Hover: Destructive/Hover
- Active: Destructive/Active

#### Ghost Button
**Component:** `Button/Ghost`
- Same dimensions as Primary
- Background: Transparent
- Text Color: Text/Primary
- Hover: Background Background/Surface

#### Icon Button
**Component:** `Button/Icon`
**Size:** 40px × 40px (minimum 44px touch target)
- Padding: 10px (for 20px icon)
- Border Radius: Radius-MD (8px)
- Background: Transparent
- Icon Size: 20px × 20px

---

### 9. Photo Viewer (Full Screen)

**Component:** `PhotoViewer`
**Frame:** Device size (e.g., 375 × 812)

**Structure:**
```
└─ Backdrop (full screen)
   ├─ Top Bar (overlay)
   │  ├─ Close Button (X icon, top-left)
   │  ├─ Photo Index (centered: "3 of 5")
   │  └─ Share Button (top-right, if supported)
   ├─ Photo Container (centered)
   │  └─ Photo Image (max-width/height, object-fit: contain)
   ├─ Navigation Buttons (left/right)
   │  ├─ Previous Button (chevron left, left side)
   │  └─ Next Button (chevron right, right side)
   └─ Zoom Indicator (bottom-center: "2.0x")
```

**Backdrop:**
- Background: Photo Viewer Backdrop (HSL(0, 0%, 5%) at 95% opacity)
- Fill entire frame

**Top Bar:**
- Height: 64px
- Padding: 16px
- Flex: Horizontal, Space Between
- Background: Transparent
- Opacity States:
  - Active (showing): 100%
  - Inactive (auto-hide after 3s): 0%
- Transition: 300ms ease

**Top Bar Components:**
1. **Close Button** (top-left):
   - Component: IconButton
   - Icon: X (20px)
   - Color: White
   - Background: Transparent
   - Hover: Background White at 20% opacity

2. **Photo Index** (centered):
   - Text: "3 of 5"
   - Style: Small/Caption (14px)
   - Color: White

3. **Share Button** (top-right):
   - Component: IconButton
   - Icon: Share2 (20px)
   - Color: White
   - Background: Transparent
   - Hover: Background White at 20% opacity

**Navigation Buttons:**
- Position: Absolute, centered vertically
- Left button: 16px from left edge
- Right button: 16px from right edge
- Size: 44px × 44px
- Border Radius: Radius-Full (circle)
- Background: Transparent
- Border: 1px solid White at 50% opacity
- Icon: Chevron (24px), White
- Hover: Background White at 20% opacity
- Same opacity behavior as Top Bar

**Zoom Indicator:**
- Position: Bottom-center, 16px from bottom
- Padding: 8px horizontal, 4px vertical
- Border Radius: Radius-Full (pill)
- Background: Black at 60% opacity
- Text: "2.0x"
- Style: Small/Caption (14px)
- Color: White
- Only visible when scale > 1

---

### 10. Delete Confirmation Dialog

**Component:** `Dialog/DeleteConfirmation`
**Size:** 400px width (mobile: 90% width) × Auto height
**Position:** Centered in viewport

**Structure:**
```
└─ Dialog Container
   ├─ Header
   │  └─ Title: "Delete Photo?"
   ├─ Content
   │  ├─ Description text
   │  └─ Filename (bold)
   └─ Footer
      ├─ Cancel Button (ghost)
      └─ Delete Button (destructive)
```

**Container:**
- Background: Background/Elevated
- Border Radius: Radius-XL (16px)
- Padding: 24px
- Shadow: Shadow-2XL
- Backdrop: Black at 50% opacity (blur: 4px)

**Header:**
- Margin-bottom: 16px

**Title:**
- Text: "Delete Photo?"
- Style: Headline (24px, 600 weight)
- Color: Text/Primary

**Description:**
- Text: "Are you sure you want to delete this photo? This action cannot be undone."
- Style: Body/Default (16px)
- Color: Text/Secondary
- Line-height: 1.5

**Filename:**
- Text: "IMG_1234.jpg" (example)
- Style: Body/Medium (16px, 500 weight)
- Color: Text/Primary
- Margin-top: 16px

**Footer:**
- Margin-top: 24px
- Flex: Horizontal, End alignment
- Gap: 12px

**Buttons:**
- Cancel: Button/Ghost, text "Cancel"
- Delete: Button/Destructive, text "Delete"

---

### 11. Welcome Screen

**Component:** `WelcomeScreen`
**Frame:** Full viewport (e.g., 375 × 812)
**Overlay:** True (covers entire app)

**Structure:**
```
└─ Backdrop (full screen)
   └─ Content Container (centered, max-width: 500px)
      ├─ App Icon (120px)
      ├─ App Name: "Photo Wallet"
      ├─ Tagline
      ├─ Features List
      │  ├─ Feature 1: Private & Local
      │  ├─ Feature 2: 10 Photos Max
      │  └─ Feature 3: Gesture Navigation
      └─ CTA Button: "Get Started"
```

**Backdrop:**
- Background: Background/Primary
- Full screen overlay
- Z-index: 100

**Content (Centered Vertically & Horizontally):**
1. **App Icon**: 120px × 120px
   - Wallet icon illustration
   - Color: Accent/Primary
   - Margin-bottom: 32px

2. **App Name**: "Photo Wallet"
   - Style: Display/Large (40px, 600 weight)
   - Color: Text/Primary
   - Text-align: Center
   - Margin-bottom: 12px

3. **Tagline**: "Your most precious photos, privately stored."
   - Style: Body/Default (16px)
   - Color: Text/Secondary
   - Text-align: Center
   - Max-width: 400px
   - Margin-bottom: 48px

4. **Features List**:
   - Flex: Vertical
   - Gap: 24px
   - Max-width: 400px
   - Margin-bottom: 48px

   Each Feature:
   ```
   ├─ Icon (24px, Accent/Primary)
   └─ Text Container
      ├─ Title (Body/Semibold, Text/Primary)
      └─ Description (Small/Caption, Text/Secondary)
   ```

   **Feature 1**:
   - Icon: Lock
   - Title: "Private & Secure"
   - Description: "All photos stored locally on your device"

   **Feature 2**:
   - Icon: ImageStack (or number 10)
   - Title: "10 Photos Maximum"
   - Description: "Keep only what matters most"

   **Feature 3**:
   - Icon: Hand with gesture
   - Title: "Natural Gestures"
   - Description: "Swipe, pinch, and zoom like native apps"

5. **Get Started Button**:
   - Component: Button/Primary
   - Text: "Get Started"
   - Width: Full width (max 400px)

---

### 12. Install Banner

**Component:** `InstallBanner`
**Position:** Bottom of screen (fixed)
**Size:** Full width × Auto height

**Structure:**
```
└─ Banner Container
   ├─ Icon (App logo, 40px)
   ├─ Text Content
   │  ├─ Title: "Add to Home Screen"
   │  └─ Description: "Install Photo Wallet for quick access"
   └─ Actions
      ├─ Dismiss Button (X icon)
      └─ Install Button
```

**Container:**
- Background: Background/Surface
- Border-top: 1px solid Border/Default
- Padding: 16px
- Shadow: 0px -4px 12px Black at 10%
- Position: Fixed bottom
- Z-index: 50

**Layout:**
- Flex: Horizontal
- Gap: 16px
- Align: Center

**Icon:**
- Size: 40px × 40px
- Border-radius: Radius-MD (8px)
- App icon/logo

**Text Content:**
- Flex: Vertical
- Gap: 4px
- Flex-grow: 1

**Title:**
- Text: "Add to Home Screen"
- Style: Body/Medium (16px, 500 weight)
- Color: Text/Primary

**Description:**
- Text: "Install Photo Wallet for quick access"
- Style: Small/Caption (14px)
- Color: Text/Secondary

**Actions:**
- Flex: Horizontal
- Gap: 8px

**Dismiss Button:**
- Component: IconButton (32px)
- Icon: X (16px)
- Color: Text/Secondary

**Install Button:**
- Component: Button/Primary (compact)
- Text: "Install"
- Padding: 8px 16px
- Height: 36px

---

### 13. Gesture Tutorial Overlay

**Component:** `GestureTutorial`
**Frame:** Full viewport overlay
**Appears:** First time user opens PhotoViewer

**Structure:**
```
└─ Backdrop (semi-transparent)
   └─ Tutorial Card (centered)
      ├─ Title: "Photo Gestures"
      ├─ Gesture List
      │  ├─ Swipe left/right: Navigate
      │  ├─ Swipe down: Close viewer
      │  ├─ Pinch: Zoom in/out
      │  ├─ Double tap: Toggle zoom
      │  └─ Long press: Delete photo
      └─ Close Button: "Got it"
```

**Backdrop:**
- Background: Black at 80% opacity
- Blur: 8px
- Full screen

**Tutorial Card:**
- Width: 90% (max 400px)
- Background: Background/Elevated
- Border-radius: Radius-XL (16px)
- Padding: 32px
- Shadow: Shadow-2XL

**Title:**
- Text: "Photo Gestures"
- Style: Headline (24px, 600 weight)
- Color: Text/Primary
- Margin-bottom: 24px
- Text-align: Center

**Gesture List:**
- Flex: Vertical
- Gap: 20px

Each Gesture Item:
```
├─ Icon (animated gesture visual, 48px)
└─ Text Container (flex: vertical, gap: 4px)
   ├─ Gesture: "Swipe left/right" (Body/Medium)
   └─ Action: "Navigate between photos" (Small/Caption, Text/Secondary)
```

**Close Button:**
- Component: Button/Primary
- Text: "Got it"
- Width: Full width
- Margin-top: 32px

---

### 14. Settings Dialog

**Component:** `SettingsDialog`
**Size:** 400px width (mobile: 90% width) × Auto height

**Structure:**
```
└─ Dialog Container
   ├─ Header
   │  ├─ Title: "Settings"
   │  └─ Close Button (X)
   ├─ Content
   │  ├─ Section: Photo Management
   │  │  └─ Button: Manage Photos
   │  ├─ Section: Storage
   │  │  └─ Storage Info (5 photos, ~12.3 MB)
   │  └─ Section: Danger Zone
   │     └─ Button: Reset App
   └─ Footer
      └─ Version info
```

**Container:**
- Background: Background/Elevated
- Border-radius: Radius-XL (16px)
- Padding: 24px
- Shadow: Shadow-2XL

**Header:**
- Flex: Horizontal, Space Between
- Margin-bottom: 24px

**Title:**
- Text: "Settings"
- Style: Headline (24px, 600 weight)
- Color: Text/Primary

**Sections:**
- Flex: Vertical
- Gap: 32px

Each Section:
```
├─ Section Title (Small/Caption, Text/Secondary, margin-bottom: 12px)
└─ Section Content
```

**Photo Management Section:**
- Button: Full width, Ghost style
- Icon: Grid (20px, left)
- Text: "Manage Photos"
- Chevron: Right (16px, right)

**Storage Section:**
- Text: "5 photos • 12.3 MB"
- Style: Body/Default
- Color: Text/Secondary

**Danger Zone Section:**
- Button: Full width, Destructive style
- Icon: Trash (20px, left)
- Text: "Reset App"

**Footer:**
- Margin-top: 32px
- Text: "Version 1.0.0"
- Style: Tiny/Metadata (12px)
- Color: Text/Muted
- Text-align: Center

---

## Animation & Interaction Specs

### Transitions
All transitions use CSS easing functions:

```
Ease-Out:      cubic-bezier(0.16, 1, 0.3, 1)
Ease-In-Out:   cubic-bezier(0.45, 0, 0.55, 1)
Spring:        cubic-bezier(0.32, 0.72, 0, 1)
```

### Durations
```
Fast:    150ms  (hover states)
Normal:  200ms  (page transitions)
Medium:  300ms  (modal open/close)
Slow:    400ms  (photo viewer open)
```

### Transform Animations

**Photo Card Hover:**
- Scale: 1.0 → 1.05
- Duration: 150ms
- Easing: Ease-Out

**Button Press:**
- Scale: 1.0 → 0.98
- Duration: 100ms
- Easing: Ease-In-Out

**Photo Viewer Open:**
- Scale: from thumbnail position → full size
- Opacity: 0 → 1
- Duration: 400ms
- Easing: Spring

**Swipe Gesture:**
- Follow finger position
- Momentum: Spring physics
- Threshold: 50px or 0.3 velocity

---

## Prototyping in Figma

### Interactive Flow

1. **Home Screen (Empty State)**
   - Tap "Add Your First Photo" → Photo Grid

2. **Home Screen (With Photos)**
   - Tap Photo Card → Photo Viewer
   - Tap Settings → Settings Dialog
   - Tap Photo Counter → (no action)

3. **Photo Viewer**
   - Tap Close → Home Screen
   - Swipe left/right → Navigate photos
   - Tap photo → Hide/show UI chrome
   - Long press → Delete Confirmation

4. **Delete Confirmation**
   - Tap Cancel → Close dialog
   - Tap Delete → Return to grid (photo removed)

5. **Settings Dialog**
   - Tap Close → Home Screen
   - Tap Manage Photos → Manage Photos Dialog
   - Tap Reset App → Confirmation dialog

6. **Welcome Screen** (first launch)
   - Tap Get Started → Home Screen

7. **Install Banner**
   - Tap Install → (native install)
   - Tap Dismiss → Banner disappears

### Smart Animate

Use Smart Animate for:
- Photo Viewer open/close (scale from card position)
- Photo navigation (slide left/right)
- Dialog open/close (scale + fade)

---

## Assets Needed

### Icons (20px standard size)
Use **Lucide Icons** (same as code implementation):
- X (close)
- Settings (gear/cog)
- Trash2 (delete)
- Plus (add)
- ChevronLeft (navigation)
- ChevronRight (navigation)
- Share2 (share)
- Lock (security)
- Image (photos)
- Hand (gestures)
- Grid (manage)
- AlertTriangle (warning)

### Illustrations
- **Empty State Wallet**: Line-art wallet with photo slots (80px)
- **App Icon**: Wallet logo for welcome screen (120px)

### Placeholder Images
For photo grid mockups, use:
- Square images (1:1 aspect ratio)
- Varied subjects (portraits, landscapes, etc.)
- Size: 800×800px minimum

---

## Figma Plugins Recommendations

1. **Iconify**: For Lucide icons
2. **Unsplash**: For placeholder photos
3. **Content Reel**: For photo filenames
4. **Color Contrast Checker**: Verify accessibility
5. **Stark**: Full accessibility audit

---

## Export Settings

### Components to Export
- All button states (default, hover, active, disabled)
- Photo cards (default, hover)
- Dialog variants
- Icon set (SVG)

### Export Specifications
```
Icons:        SVG (24px viewbox)
Components:   2x PNG + SVG
Screenshots:  2x PNG (for documentation)
Colors:       JSON (design tokens)
Spacing:      JSON (design tokens)
```

---

## Design Tokens Export (JSON)

```json
{
  "colors": {
    "background": {
      "primary": "#141414",
      "surface": "#1F1F1F",
      "elevated": "#292929"
    },
    "text": {
      "primary": "#FAFAFA",
      "secondary": "#A6A6A6",
      "muted": "#B3B3B3"
    },
    "accent": {
      "primary": "#3399FF",
      "hover": "#1A8CFF",
      "active": "#0080FF"
    },
    "destructive": {
      "primary": "#EB5757",
      "hover": "#E84040",
      "active": "#E52929"
    }
  },
  "spacing": {
    "1": "4px",
    "2": "8px",
    "3": "12px",
    "4": "16px",
    "6": "24px",
    "8": "32px",
    "12": "48px",
    "16": "64px"
  },
  "borderRadius": {
    "sm": "6px",
    "md": "8px",
    "lg": "12px",
    "xl": "16px",
    "full": "9999px"
  },
  "typography": {
    "display": {
      "large": {
        "fontSize": "40px",
        "lineHeight": "48px",
        "fontWeight": 600,
        "letterSpacing": "-0.8px"
      },
      "small": {
        "fontSize": "32px",
        "lineHeight": "40px",
        "fontWeight": 600,
        "letterSpacing": "-0.64px"
      }
    },
    "headline": {
      "fontSize": "24px",
      "lineHeight": "32px",
      "fontWeight": 600,
      "letterSpacing": "-0.48px"
    },
    "body": {
      "fontSize": "16px",
      "lineHeight": "24px",
      "fontWeight": 400,
      "letterSpacing": "0"
    },
    "caption": {
      "fontSize": "14px",
      "lineHeight": "20px",
      "fontWeight": 400,
      "letterSpacing": "0.14px"
    }
  }
}
```

---

## Next Steps

1. **Create Figma File**: Start with mobile frames (375×812)
2. **Set Up Styles**: Import colors, typography, shadows
3. **Build Components**: Start with atoms (buttons, cards), then molecules (photo grid)
4. **Create Screens**: Empty state → Photo grid → Photo viewer
5. **Add Interactions**: Use prototype mode with Smart Animate
6. **Test Flow**: Click through entire user journey
7. **Export Assets**: Icons, components, and design tokens

---

## Figma File Structure Recommendation

```
📁 Photo Wallet PWA
├─ 📄 Cover (thumbnail + description)
├─ 🎨 Design System
│  ├─ Colors
│  ├─ Typography
│  ├─ Spacing
│  ├─ Shadows
│  └─ Icons
├─ 🧩 Components
│  ├─ Buttons
│  ├─ Cards
│  ├─ Dialogs
│  ├─ Navigation
│  └─ Overlays
├─ 📱 Screens - Mobile
│  ├─ Welcome Screen
│  ├─ Home - Empty State
│  ├─ Home - With Photos
│  ├─ Photo Viewer
│  ├─ Settings
│  └─ Manage Photos
├─ 💻 Screens - Desktop
│  └─ (Same as mobile, adapted)
└─ 🔄 Prototypes
   ├─ User Flow
   └─ Gesture Interactions
```

---

This specification provides everything needed to recreate the Photo Wallet PWA design in Figma with pixel-perfect accuracy. All measurements, colors, and interactions match the implementation in your React codebase.
