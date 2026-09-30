## 🏗️ DIRECT CODE GENERATION - 360° Rotating Blueprint with Windows
### Explicit Implementation Prompt for ChatGPT

**PASTE THIS DIRECTLY INTO CHATGPT AND REQUEST FULL CODE OUTPUT**

---

```text
Generate a complete, working HTML/CSS/JavaScript implementation of a 360-degree rotating architectural blueprint for the AL-BOURDGE hero section.

CRITICAL: Do NOT provide a concept or explanation. Generate COMPLETE, WORKING, COPY-PASTE-READY CODE that produces exactly what is described below.

## Exact Requirements

1. **White background** (#ffffff) for the entire hero section
2. **Rotating 3D building** that continuously spins 360 degrees
3. **Detailed window grids** on all four sides of the building
4. **Continuous loop** that never stops (20-25 second rotation, seamless at 360°)
5. **Architectural details** including floor lines, mullions, dimensions, and labels
6. **Orange accents** (#ff8c00) highlighting entrances and key features
7. **Responsive design** that works on mobile and desktop
8. **High performance** with no stuttering or lag
9. **Readable headline and CTA** on the left side (do not cover with blueprint)

## HTML Structure

Create a single HTML file with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AL-BOURDGE | Built with Purpose</title>
    <style>
        /* ALL CSS STYLES GO HERE */
    </style>
</head>
<body>
    <!-- HERO SECTION WITH BLUEPRINT -->
    <!-- All HTML content here -->
    
    <canvas id="blueprint-canvas"></canvas>
    
    <script>
        // ALL JAVASCRIPT CODE GOES HERE
        // THREE.JS OR CANVAS API
    </script>
</body>
</html>
```

## Visual Design

### Left Side (Text Content - Fixed, Non-Rotating)
- Company logo and navigation header
- Headline: "Built with purpose." (large, bold, black #111827)
- Subheadline: "From the first plan to the final handover. Your construction and project management partner for clear, coordinated delivery."
- Two buttons:
  - "Explore our work" (orange #ff8c00 background, black text)
  - "Meet AL-BOURDGE" (text link with underline, black text)
- Location: "AL KHOBAR, SAUDI ARABIA"
- Year: "1987" with "Registered since 1987. Focused on what's next."

### Right Side (Rotating 3D Blueprint)
- Animated, continuously rotating building
- 3D isometric or perspective view
- Building rotates 360 degrees smoothly
- Takes 20-25 seconds for one full rotation
- Seamlessly loops (at 360° it continues to 0° with no jump)

## Building Architecture (4 Elevations)

The building must have FOUR distinct sides with detailed window patterns:

### Elevation 1: Main Façade (0° - 90°)
- North/front facing
- Primary entrance with orange highlight
- Window grid pattern:
  - Vertical mullions (columns) every 4-5 meters
  - Horizontal mullions every 4.2 meters (floor heights)
  - Secondary vertical mullions every 1.5 meters (window divisions)
  - Tertiary mullions creating small window panes (every 0.8m)
- Spandrel panels (solid grey areas) between floors
- Entrance doors at ground level shown with orange outline
- Labels: "MAIN ELEVATION", "+00.00", "+04.20", "+08.40", etc.
- Dimension lines showing floor-to-floor heights

### Elevation 2: Side A (90° - 180°)
- East/right side
- Different window pattern than main
- Service or secondary entrance with orange highlight
- Similar mullion structure but with variation
- Labels: "SIDE ELEVATION A"

### Elevation 3: Rear Façade (180° - 270°)
- South/back facing
- More utilitarian appearance
- Fewer windows, more solid wall areas
- Labels: "REAR ELEVATION"

### Elevation 4: Side B (270° - 360°)
- West/left side
- Corner condition visible
- Balcony or recessed areas
- Labels: "CORNER ELEVATION"

## Detailed Window Specification

Use this exact window line structure (NO SKIPPING):

**Line Weights & Hierarchy:**
- Outer building frame: 3px, dark navy #1f2937, 100% opacity
- Main vertical columns: 2px, dark navy #1f2937, 100% opacity
- Secondary mullions (1.5m spacing): 1.5px, grey #4b5563, 90% opacity
- Tertiary mullions (window divisions): 0.8px, grey #9ca3af, 70% opacity
- Floor lines: 2px, dark navy #1f2937, 100% opacity
- Spandrel panels: light grey #e5e7eb fill, 35% opacity
- Orange highlights: 2px, orange #ff8c00, 100% opacity

**Window Grid Pattern on Each Elevation:**

For a 6-bay x 5-floor building:

```
Column spacing: 5.0m, 5.0m, 5.0m, 5.0m, 5.0m, 5.0m (30m total width)
Floor spacing: 4.2m, 4.2m, 4.2m, 4.2m, 4.2m (21m total height)

Window divisions per bay:
- Bay width 5.0m ÷ 3 windows = 1.67m per window
- Each window further divided into 4 panes = 0.42m per pane

Interior window pane grid: 2 columns × 3 rows per window
Spandrel height: 0.9m (shown as solid grey area between floors)
```

This creates a realistic commercial building façade.

## Animation Implementation

Use JavaScript with HTML5 Canvas or Three.js to:

1. **Draw the building** as a 3D wireframe or simple 3D model
2. **Apply continuous rotation** around the Y-axis (vertical)
3. **Rotate 360 degrees** in 20-25 seconds
4. **Loop seamlessly** from 360° back to 0° with NO pause or jump
5. **Label each elevation** as it rotates into view
6. **Keep performance smooth** (60fps on modern devices, 30fps on mobile)

### Rotation Animation Logic

```javascript
let rotationAngle = 0;
const rotationSpeed = 360 / 25000; // degrees per millisecond (20 seconds per rotation)

function animate(timestamp) {
    rotationAngle += rotationSpeed * deltaTime;
    
    // Seamless loop: keep rotation between 0-360
    if (rotationAngle >= 360) {
        rotationAngle = rotationAngle % 360;
    }
    
    // Update 3D view with new rotation angle
    updateBuildingRotation(rotationAngle);
    
    requestAnimationFrame(animate);
}
```

## Implementation Approach (Choose One)

### Option A: Three.js (Recommended for 3D)
- Use Three.js library for 3D rendering
- Create building geometry with proper proportions
- Layer materials for mullion systems
- Render window grids precisely
- Smooth rotation with quaternions
- Include OrbitControls for optional mouse interaction

### Option B: Canvas API (Lighter Weight)
- Use HTML5 Canvas with requestAnimationFrame
- Draw building as 2D isometric projection
- Layer window grids using paths
- Simpler implementation, smaller file size
- Still smooth and performant

### Option C: SVG with CSS Transforms (Simplest)
- Create building as SVG
- Use CSS 3D transforms for rotation
- Simpler but may have performance limits on mobile

**Recommendation: Use Canvas API for balance of visual quality and performance**

## Mobile Optimization

On phones:
- Simplify window grid (reduce tertiary mullion density)
- Use lower resolution canvas
- Reduce rotation smoothness if needed (30fps instead of 60fps)
- Keep building smaller and centered
- Maintain responsive layout

## Color Palette (EXACT)

```
Hero Background: #ffffff
Text Primary: #111827
Text Secondary: #6b7280
Building Frame: #1f2937
Secondary Lines: #4b5563
Tertiary Lines: #9ca3af
Grid Lines: #d1d5db
Spandrel Fill: #e5e7eb
Orange Accent: #ff8c00
```

## Layout Breakdown

**Hero Section: 100vh (full viewport height)**

Left Side (40-50% width):
- Fixed position (does not rotate)
- Padding: 60px
- Contains logo, headline, CTA, company info
- Text remains readable while blueprint rotates

Right Side (50-60% width):
- Rotating blueprint canvas
- Centered in the space
- Responsive scaling
- Does not cover left-side text

**Responsive Behavior:**
- Desktop (1024px+): Side-by-side layout
- Tablet (768px-1023px): Side-by-side with reduced padding
- Mobile (< 768px): Stacked vertically (text on top, blueprint below)

## Typography

- Headline: 52px, bold, black, line-height 1.2
- Subheadline: 18px, regular, grey, line-height 1.6
- CTA buttons: 16px, bold, black on orange
- Labels/text: 14px, regular, grey/black
- Small text: 12px, regular, grey

All typography responsive (scale down on mobile)

## Deliverables - FULL CODE REQUIRED

Provide:

1. **Complete HTML file** - ready to open in browser
2. **All CSS styling** - no external stylesheets needed
3. **All JavaScript** - no external libraries except Three.js (if used)
4. **Working blueprint** - 3D rotating building with detailed windows
5. **Seamless loop** - 360° rotation that continues endlessly
6. **Responsive design** - works on mobile and desktop
7. **High performance** - smooth animation at 60fps
8. **All text content** - AL-BOURDGE branding included

## Testing Requirements

The code must:
- ✅ Open in a modern browser with one file
- ✅ Display a white hero section
- ✅ Show a continuously rotating building
- ✅ Have detailed window grids visible on all sides
- ✅ Rotate a full 360° in 20-25 seconds
- ✅ Loop seamlessly with no jump or pause
- ✅ Keep headline and CTA readable
- ✅ Display orange accents on entrances
- ✅ Work responsive on phones and laptops
- ✅ Run at 60fps without stuttering
- ✅ Include proper AL-BOURDGE branding

## DO NOT:
- Do NOT provide a framework or tutorial
- Do NOT explain architecture or design theory
- Do NOT create wireframes or mockups
- Do NOT generate partial code
- Do NOT ask for clarification or more details

## DO:
- Write COMPLETE, WORKING HTML/CSS/JavaScript code
- Include detailed window grids on all building sides
- Implement 360° continuous rotation
- Use proper 3D perspective or isometric projection
- Add architectural labels and dimensions
- Use orange accents strategically
- Test performance (assume 60fps requirement)
- Make it production-ready

Generate the code now. Output the complete HTML file that can be opened directly in a browser.
```

---

## Alternative: If Three.js Fails, Use Canvas

If ChatGPT struggles with Three.js, force it with this simpler demand:

```text
Ignore the Three.js approach. Use HTML5 Canvas API instead.

Generate a complete HTML file using ONLY:
- HTML5 Canvas element
- JavaScript with requestAnimationFrame
- No external libraries except basic Canvas API

The Canvas must draw:
1. A building in isometric projection (45-degree angle view)
2. Window grid lines on all visible sides
3. Continuous 360-degree rotation
4. Spandrel panels as grey fills
5. Orange highlights on doors/entrances
6. Floor and column labels

Use Canvas translate, rotate, and draw functions to create the rotation effect.

Output complete, working code that can be saved as index.html and opened in a browser.
```

---

## How to Use This Prompt

1. Copy the entire prompt above
2. Paste into ChatGPT (Claude or GPT-4 preferred)
3. Add at the end: **"Generate the complete HTML file now. I will copy and paste it into a text editor and open it in a browser."**
4. ChatGPT will output the full code
5. Copy the code into a `.html` file
6. Open in your browser

If it still doesn't work properly, try breaking it into smaller requests:

**Request 1:** "Generate the HTML structure for the AL-BOURDGE hero with white background"

**Request 2:** "Generate the CSS styling for the two-column layout (text left, canvas right)"

**Request 3:** "Generate JavaScript Canvas code to draw a rotating building with window grids"

**Request 4:** "Combine all three sections into one complete HTML file ready to use"

This forces step-by-step output instead of a vague explanation.
