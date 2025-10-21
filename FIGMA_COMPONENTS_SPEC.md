# Photo Wallet PWA - Component Visual Specifications

This document provides detailed visual specifications for each component, including measurements, spacing, and layout details for Figma recreation.

---

## Screen Layouts

### Home Screen - Empty State

```
┌─────────────────────────────────────┐
│ Header                         16px │
│ ┌─────────────────────────────────┐ │
│ │ Photo Wallet      [Install Btn] │ │ 32px top
│ │                                 │ │
│ │ Your important photos at your   │ │ 24px bottom
│ │ fingertips...                   │ │
│ └─────────────────────────────────┘ │
│                                     │
│      [Empty State Card]             │ 60vh min-height
│      ┌─────────────────────┐       │
│      │     ╭─────╮          │       │ 48px padding
│      │     │  👛  │          │       │
│      │     ╰─────╯          │       │
│      │                     │       │
│      │   No Photos Yet     │       │ 12px gap
│      │                     │       │
│      │ Add your first      │       │
│      │ cherished photo...  │       │ 32px gap
│      │                     │       │
│      │ [Add First Photo]   │       │
│      └─────────────────────┘       │
└─────────────────────────────────────┘
```

**Measurements:**
- Header padding: 16px sides, 32px top, 24px bottom
- Empty state card: max-width 448px, centered
- Icon circle: 80px diameter
- Icon: 40px
- Title: 24px font size
- Description: 14px font size
- Button width: 100%

---

### Home Screen - With Photos

```
┌─────────────────────────────────────┐
│ Header                         16px │
│ ┌─────────────────────────────────┐ │
│ │ Photo Wallet      [Install Btn] │ │
│ │ Your important photos...        │ │
│ └─────────────────────────────────┘ │
│                                16px │
│ Photo Grid                          │
│ ┌────┬────┬────┐                   │
│ │ 📷 │ 📷 │ 📷 │  ← 3 columns      │
│ ├────┼────┼────┤    8px gap        │
│ │ 📷 │ 📷 │ 📷 │                   │
│ ├────┼────┼────┤                   │
│ │ 📷 │ ➕ │    │  ← Add card       │
│ └────┴────┴────┘                   │
│                                     │
└─────────────────────────────────────┘
```

**Measurements:**
- Grid padding: 16px all sides
- Grid gap: 8px between items
- Columns: 3 (equal width)
- Card aspect ratio: 1:1

---

### Photo Viewer (Full Screen)

```
┌─────────────────────────────────────┐
│ [X]          3 of 5         [Share] │ ← Top bar (16px padding)
│                                     │
│                                     │
│           ┌─────────────┐           │
│           │             │           │
│           │             │           │
│           │    PHOTO    │           │ ← Centered
│           │             │           │
│           │             │           │
│           └─────────────┘           │
│                                     │
│   [<]                         [>]   │ ← Nav arrows (16px from edge)
│                                     │
│              2.0x                   │ ← Zoom indicator (16px bottom)
└─────────────────────────────────────┘

Background: rgba(0,0,0,0.95)
```

**Measurements:**
- Top bar: 16px padding, full width
- Close button (top-left): 40px × 40px
- Photo counter: 14px font, centered
- Share button (top-right): 40px × 40px
- Nav arrows: 40px × 40px, 16px from edges
- Zoom indicator: 16px from bottom, centered

---

## Component Specifications

### 1. Button Component

#### Size Variants

**Small Button**
```
┌─────────────────┐
│   Button Text   │  Height: 32px
└─────────────────┘  Padding: 0 12px
                     Font: 14px
```

**Medium Button (Default)**
```
┌───────────────────┐
│   Button Text     │  Height: 40px
└───────────────────┘  Padding: 0 16px
                       Font: 14px
```

**Large Button**
```
┌─────────────────────┐
│    Button Text      │  Height: 44px
└─────────────────────┘  Padding: 0 20px
                         Font: 16px
```

**Icon Button**
```
┌─────┐
│  ⚙  │  Size: 40px × 40px
└─────┘  Icon: 20px
         Padding: 10px
```

#### With Icon

**Icon + Text**
```
┌─────────────────────┐
│  📤  Upload Photo    │  Icon: 20px
└─────────────────────┘  Gap: 8px (mr-2)
                         Icon margin-right: 8px
```

#### Visual Properties

**Primary Button**
```
Background: #3399FF (Primary blue)
Text: White
Border: 1px solid (computed darker)
Border-radius: 9px
Shadow: None (shadow on hover)

Hover:
  Background: Slightly lighter (elevate overlay)
  Shadow: SM elevation
  Transform: none

Active:
  Background: Darker (elevate-2)
  Transform: scale(0.97)
```

**Destructive Button**
```
Background: #EE3939 (Red)
Text: White
Border: 1px solid (computed darker)
Border-radius: 9px
```

**Ghost Button**
```
Background: Transparent
Text: Primary text color
Border: None
Border-radius: 9px

Hover:
  Background: rgba(255,255,255,0.04)
```

**Outline Button**
```
Background: Transparent
Text: Primary text color
Border: 1px solid border-color
Border-radius: 9px

Hover:
  Background: rgba(255,255,255,0.04)
```

---

### 2. Photo Card

#### Layout
```
┌─────────────────────────┐
│         [🗑]           │ ← Delete button (8px, 8px)
│                         │   32px × 32px
│                         │
│       PHOTO IMAGE       │   Aspect ratio: 1:1
│     (object-fit:        │   Border-radius: 12px
│        cover)           │
│                         │
│                         │
└─────────────────────────┘
```

**Measurements:**
- Aspect ratio: 1:1 (square)
- Border-radius: 12px
- Border: 1px solid #292929
- Background: #1F1F1F
- Shadow: SM elevation
- Delete button: 32px × 32px, positioned 8px from top-right

**Delete Button Detail**
```
┌──────┐
│  🗑  │  Size: 32px × 32px
└──────┘  Icon: 16px
          Background: #EE3939 (destructive)
          Border-radius: 6px
          Opacity: 0 (default), 1 (on card hover)
          Scale: 0.75 (default), 1 (on card hover)
```

**Hover State**
```
Card:
  Transform: scale(1.05)
  Shadow: XL elevation
  Transition: 150ms ease-out

Overlay gradient:
  From: transparent (top)
  To: rgba(0,0,0,0.20) (bottom)
  Opacity: 0 → 1 (on hover)

Delete button:
  Opacity: 0 → 1
  Scale: 0.75 → 1
  Transition: all 150ms
```

---

### 3. Add Photo Card

```
┌─────────────────────────┐
│                         │
│                         │
│           ┌───┐         │
│           │ ➕ │         │   Icon: 24px
│           └───┘         │   Color: Text secondary
│                         │
│                         │
│                         │
└─────────────────────────┘

Border: 2px dashed #333333
Background: #1F1F1F
Border-radius: 12px
Aspect ratio: 1:1
```

**Hover State**
```
Border color: #3399FF (primary)
Icon color: #3399FF
Background: rgba(255,255,255,0.04)
```

**Disabled State (10 photos)**
```
Opacity: 0.5
Cursor: not-allowed
Hover effects: none
```

---

### 4. Card Component (Generic)

```
┌─────────────────────────────────┐
│                                 │ ← 24px padding
│  Card Title (18px, semibold)    │
│                                 │   8px gap
│  Card content goes here...      │
│  (14px, regular)                │
│                                 │
│                                 │
│                            [CTA]│ ← Aligned right
└─────────────────────────────────┘

Background: #1F1F1F
Border: 1px solid #292929
Border-radius: 12px
Padding: 24px
Shadow: SM elevation
```

---

### 5. Header Component

```
┌─────────────────────────────────────────┐
│                                         │ ← 32px top
│  Photo Wallet              [Install]    │   16px sides
│                                         │
│  Your important photos at your          │
│  fingertips, like how your dad had      │   24px bottom
│  them in his wallet back in the day.    │
└─────────────────────────────────────────┘

Layout:
  - Flex column
  - First row: Title + Install button (space-between)
  - Second row: Subtitle (max-width 512px)
```

**Title**
- Font size: 24px
- Weight: 600 (semibold)
- Tracking: -0.02em
- Color: Text primary

**Subtitle**
- Font size: 14px
- Weight: 400 (regular)
- Color: Text secondary (#9FA3AB)
- Max-width: 512px
- Margin-top: 8px

---

### 6. Empty State Component

```
┌─────────────────────────────┐
│                             │ ← 48px padding
│        ╭──────────╮         │
│        │          │         │   80px circle
│        │    👛    │         │   40px icon
│        │          │         │
│        ╰──────────╯         │
│                             │   24px gap
│    No Photos Yet            │   24px title
│                             │
│  Add your first cherished   │   12px gap
│  photo to start building    │   14px description
│  your digital wallet        │
│  collection.                │
│                             │   32px gap
│  ┌───────────────────────┐ │
│  │  📤 Add Your First    │ │   44px button
│  │      Photo            │ │
│  └───────────────────────┘ │
│                             │
└─────────────────────────────┘

Card max-width: 448px
Centered in viewport
```

**Icon Circle**
- Size: 80px × 80px
- Border-radius: 50%
- Background: #292929 (muted)
- Icon: 40px, color #9FA3AB

**Spacing**
- Padding: 48px all sides
- Icon to title: 24px
- Title to description: 12px
- Description to button: 32px

---

### 7. Dialog/Modal Component

```
╔═════════════════════════════╗
║                             ║ ← 24px padding
║  Dialog Title               ║   18px font, semibold
║                             ║
║  This is the dialog         ║   8px gap
║  description text that      ║   14px font, secondary
║  explains what's happening. ║
║                             ║   24px gap
║                             ║
║              [Cancel] [OK]  ║ ← Buttons (8px gap)
╚═════════════════════════════╝

Background: #292929 (popover)
Border: 1px solid #383838
Border-radius: 16px
Padding: 24px
Max-width: 512px
Shadow: 2XL elevation
```

**Backdrop**
```
Background: rgba(0,0,0,0.80)
Backdrop-blur: 4px (optional)
```

**Footer Buttons**
- Display: flex
- Justify: flex-end
- Gap: 8px
- Margin-top: 24px

---

### 8. Photo Grid Layout

```
┌────────────────────────────────┐
│                                │ ← 16px padding
│  ┌──────┬──────┬──────┐       │
│  │      │      │      │       │   3 columns
│  │  📷  │  📷  │  📷  │       │   8px gap
│  │      │      │      │       │
│  └──────┴──────┴──────┘       │
│         ↑ 8px gap              │
│  ┌──────┬──────┬──────┐       │
│  │      │      │      │       │
│  │  📷  │  📷  │  📷  │       │
│  │      │      │      │       │
│  └──────┴──────┴──────┘       │
│                                │
│  ┌──────┬──────┬──────┐       │
│  │      │      │      │       │
│  │  📷  │  ➕  │      │       │   Add card
│  │      │      │      │       │
│  └──────┴──────┴──────┘       │
│                                │
└────────────────────────────────┘
```

**Grid Specifications**
- Container: `display: grid`
- Columns: 3 (equal width)
- Gap: 8px (both row and column)
- Padding: 16px all sides
- Bottom padding: 32px (for spacing)

**Auto Layout in Figma**
- Direction: Horizontal wrap
- Spacing: 8px
- Padding: 16px
- Sizing: Fill container

---

### 9. Install Prompt (Toast)

```
┌─────────────────────────────────────┐
│                                     │
│  📲  Add Photo Wallet to your       │ ← 16px padding
│      home screen                    │   Icon: 24px
│                                     │   Gap: 12px
│                [Not now] [Install]  │
│                                     │
└─────────────────────────────────────┘

Position: Fixed bottom
Border-radius: 16px 16px 0 0 (top corners only)
Background: #1F1F1F (card)
Border-top: 1px solid #333333
Padding: 16px
Shadow: XL elevation
```

**Layout**
- Display: flex
- Justify: space-between
- Align: center
- Gap: 12px

**Message**
- Font size: 14px
- Weight: 500 (medium)
- Icon: 24px, margin-right 12px

**Buttons**
- "Not now": Ghost variant
- "Install": Primary variant
- Gap: 8px

---

### 10. Gesture Tutorial Overlay

```
┌─────────────────────────────────────┐
│                                [X]  │ ← Close button
│                                     │
│        Gesture Tutorial             │   24px title
│                                     │
│  ┌───────────────────────────────┐ │
│  │                               │ │
│  │   👆 Swipe left/right         │ │   Illustration
│  │   Navigate between photos     │ │   + text
│  │                               │ │
│  │   🤏 Pinch to zoom            │ │
│  │   Zoom 1x to 3x              │ │
│  │                               │ │
│  │   👆👆 Double-tap             │ │
│  │   Toggle zoom                 │ │
│  │                               │ │
│  │   ⬇️ Swipe down              │ │
│  │   Close viewer                │ │
│  │                               │ │
│  └───────────────────────────────┘ │
│                                     │
│           [Got it]                  │   Primary button
│                                     │
└─────────────────────────────────────┘

Background: Semi-transparent overlay
Card: Same as dialog specs
Auto-dismiss after first viewing
```

---

## Component State Matrix

### Photo Card States

| State      | Transform   | Shadow  | Overlay | Delete Btn |
|------------|-------------|---------|---------|------------|
| Default    | none        | SM      | 0%      | 0% opacity |
| Hover      | scale(1.05) | XL      | 100%    | 100% opacity |
| Active     | scale(0.97) | SM      | 100%    | 100% opacity |
| Focus      | none        | SM+Ring | 0%      | 0% opacity |

### Button States

| State      | Background      | Shadow | Transform   |
|------------|-----------------|--------|-------------|
| Default    | Primary color   | None   | none        |
| Hover      | Elevated (+1)   | SM     | none        |
| Active     | Elevated (+2)   | None   | scale(0.97) |
| Focus      | Primary color   | Ring   | none        |
| Disabled   | 50% opacity     | None   | none        |

### Add Card States

| State      | Border        | Icon Color  | Background     |
|------------|---------------|-------------|----------------|
| Default    | Dashed gray   | Secondary   | Card           |
| Hover      | Solid primary | Primary     | Elevated (+1)  |
| Active     | Solid primary | Primary     | Elevated (+2)  |
| Disabled   | Dashed gray   | Secondary   | 50% opacity    |

---

## Spacing Reference Chart

```
Component                   Top    Right   Bottom  Left
────────────────────────────────────────────────────────
Header                      32px   16px    24px    16px
Empty State Icon            -      -       24px    -
Empty Title                 -      -       12px    -
Empty Description           -      -       32px    -
Card                        24px   24px    24px    24px
Photo Grid Container        16px   16px    32px    16px
Photo Grid Gap              8px (all sides)
Dialog                      24px   24px    24px    24px
Dialog Footer (margin-top)  24px   -       -       -
Install Prompt              16px   16px    16px    16px
Button Small                -      12px    -       12px
Button Medium               -      16px    -       16px
Button Large                -      20px    -       20px
```

---

## Typography Reference Chart

```
Element                Size    Weight  Tracking  Line-Height
──────────────────────────────────────────────────────────
Display Mobile         32px    600     -0.02em   1.2
Display Desktop        40px    600     -0.02em   1.2
Headline               24px    600     -0.02em   1.3
Body Large             16px    400     0         1.5
Body Regular           14px    400     0         1.5
Caption                14px    400     0.01em    1.4
Small                  12px    400     0         1.4
Button                 14px    500     0         1
```

---

## Color Reference (Quick Lookup)

```
Element                      Dark Mode           Light Mode
────────────────────────────────────────────────────────────
Background                   #141414             #FAFAFA
Card                         #1F1F1F             #F5F5F5
Text Primary                 #FAFAFA             #1A1A1A
Text Secondary               #9FA3AB             #54585E
Border                       #333333             #E0E0E0
Primary Blue                 #3399FF             #3399FF
Destructive Red              #EE3939             #EE3939
```

---

This specification document provides all the measurements and visual details needed to recreate each component accurately in Figma. Use these as precise guides when building your design file.
