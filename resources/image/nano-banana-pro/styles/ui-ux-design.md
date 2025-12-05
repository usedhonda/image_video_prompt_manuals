# UI/UX Design Styles

Styles optimized for app interfaces, web design, and digital product mockups.

---

## Style: Glassmorphism

**Use Case**: Modern app UI, cards, overlays, modal dialogs

**Keywords**:
```
glassmorphism, frosted glass effect, semi-transparent background,
blur behind, subtle border glow, soft shadows,
layered cards, depth effect
```

**Characteristics**:
- Background blur: 10-20px
- Opacity: 60-80%
- Border: 1px white at 20% opacity
- Shadow: Soft, diffused

**Schema Example**:
```json
{
  "style": "glassmorphism",
  "card": {
    "background": "rgba(255, 255, 255, 0.2)",
    "blur": "backdrop-blur-lg",
    "border": "1px solid rgba(255, 255, 255, 0.3)",
    "shadow": "soft diffused shadow"
  },
  "background": "gradient or image with blur"
}
```

---

## Style: Neomorphism (Soft UI)

**Use Case**: Buttons, toggles, input fields, embedded controls

**Keywords**:
```
neumorphism, soft UI, extruded shapes, inset shadows,
monochrome palette, subtle depth, tactile feel,
light source from top-left
```

**Characteristics**:
- Background matches element color
- Two shadows: light (top-left) and dark (bottom-right)
- Subtle, not dramatic depth

**Schema Example**:
```json
{
  "style": "neumorphism",
  "element": {
    "background": "#e0e0e0",
    "shadow_light": "-5px -5px 10px #ffffff",
    "shadow_dark": "5px 5px 10px #bebebe",
    "border_radius": "rounded"
  }
}
```

---

## Style: Material Design 3

**Use Case**: Android apps, Google-style interfaces

**Keywords**:
```
Material Design 3, dynamic color, rounded corners,
elevation shadows, FAB button, bottom navigation,
card-based layout, tonal surfaces
```

**Characteristics**:
- Rounded corners (16-28px radius)
- Tonal color surfaces
- Clear elevation hierarchy
- Dynamic color from image

**Schema Example**:
```json
{
  "style": "material_design_3",
  "components": {
    "cards": "rounded 16px, tonal surface",
    "buttons": "rounded pill shape, filled or outlined",
    "navigation": "bottom nav with FAB",
    "icons": "outlined or filled style"
  },
  "colors": {
    "primary": "dynamic from content",
    "surface": "tonal variations",
    "on_surface": "high contrast text"
  }
}
```

---

## Style: iOS/Apple Design

**Use Case**: iPhone apps, Apple-style interfaces

**Keywords**:
```
iOS style, SF Pro font, rounded rectangles,
subtle blur backgrounds, system colors,
tab bar navigation, large titles, vibrancy effects
```

**Characteristics**:
- SF Pro typography
- System blue (#007AFF)
- Large navigation titles
- Subtle vibrancy/blur effects

**Schema Example**:
```json
{
  "style": "ios_design",
  "components": {
    "navigation": "large title, back chevron",
    "lists": "grouped inset style",
    "buttons": "rounded rectangle, system blue",
    "toggles": "green when on"
  },
  "typography": {
    "titles": "SF Pro Bold, large",
    "body": "SF Pro Regular",
    "captions": "SF Pro Light, gray"
  }
}
```

---

## Style: Wireframe / Blueprint

**Use Case**: UX documentation, early-stage design, technical specs

**Keywords**:
```
wireframe style, blueprint aesthetic, technical drawing,
gray boxes, placeholder text, annotation lines,
grid background, component labels
```

**Two Variants**:

### Low-Fidelity Wireframe
```json
{
  "style": "lo_fi_wireframe",
  "elements": {
    "shapes": "gray rectangles, crossed boxes for images",
    "text": "lorem ipsum lines",
    "annotations": "numbered callouts",
    "background": "white or light gray"
  }
}
```

### Blueprint Style
```json
{
  "style": "blueprint",
  "elements": {
    "lines": "white on blue background",
    "grid": "visible technical grid",
    "measurements": "dimension lines with values",
    "annotations": "technical labels"
  }
}
```

---

## Style: Dashboard / Admin Panel

**Use Case**: Admin interfaces, analytics dashboards, control panels

**Keywords**:
```
admin dashboard, sidebar navigation, data tables,
chart widgets, status indicators, dark or light mode,
card-based layout, header with user profile
```

**Schema Example**:
```json
{
  "style": "admin_dashboard",
  "layout": {
    "sidebar": "collapsible, icon + label",
    "header": "search, notifications, profile",
    "content": "card grid with charts and tables"
  },
  "components": {
    "stat_cards": "large number, trend indicator",
    "tables": "sortable, pagination",
    "charts": "line, bar, pie widgets"
  }
}
```

---

## Style: E-commerce / Shopping

**Use Case**: Product listings, shopping carts, checkout flows

**Keywords**:
```
e-commerce UI, product grid, add to cart button,
price display, star ratings, filter sidebar,
clean product cards, trust badges
```

**Schema Example**:
```json
{
  "style": "ecommerce",
  "product_card": {
    "image": "square, hover zoom",
    "title": "truncated to 2 lines",
    "price": "prominent, sale price highlighted",
    "rating": "star icons with count"
  },
  "layout": {
    "grid": "responsive 2-4 columns",
    "filters": "sidebar or top bar",
    "pagination": "numbered or infinite scroll"
  }
}
```

---

## Style: Social Media App

**Use Case**: Feed interfaces, profile pages, story formats

**Keywords**:
```
social media UI, feed layout, avatar circles,
like and comment buttons, story bubbles,
infinite scroll, engagement metrics
```

**Schema Example**:
```json
{
  "style": "social_media",
  "feed_item": {
    "header": "avatar, username, timestamp",
    "content": "image or text post",
    "actions": "like, comment, share, save",
    "engagement": "like count, comment preview"
  },
  "stories": {
    "format": "circular avatars with ring",
    "indicator": "gradient ring for unseen"
  }
}
```

---

## Two-Step Wireframe to Hi-Fi Recipe

**Step 1**: Generate wireframe
```
Generate a low-fidelity wireframe for a [app type].
Gray boxes for images, lines for text,
basic layout structure, no colors,
technical annotation style
```

**Step 2**: Use wireframe as reference, apply style
```
Using this wireframe as layout reference (image slot 1),
create a high-fidelity UI mockup with:
- [Style: glassmorphism / material / ios]
- [Color palette]
- Realistic content and images
```

---

## Device Frames

### Mobile Mockup
```
iPhone 15 Pro frame, realistic device mockup,
screen showing [app interface],
subtle shadow, 3/4 angle view
```

### Desktop Mockup
```
MacBook Pro frame, browser window,
website displayed on screen,
clean desk background, soft lighting
```

### Multi-Device
```
responsive design showcase,
iPhone, iPad, MacBook displaying same interface,
floating arrangement, subtle shadows
```
