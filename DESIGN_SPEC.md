# Design Spec Summary

## 1. Design Direction

- Style keywords: `clean`, `high whitespace`, `glassmorphism`, `light gray background`, `blue accent`
- Visual structure: `global capsule nav` + `large rounded main container` + `floating aside card`

## 2. Color System

- Page background: `#f5f5f7`
- Primary text: `#1d1d1f`
- Secondary text: `#57575c`
- Link/accent: `#0066cc` (spot highlight `#0071e3`)
- Base border: `rgba(29, 29, 31, 0.14)`
- Card background: `rgba(255, 255, 255, 0.7~0.9)`

## 3. Typography

- Primary stack: `'SF Pro Display'`, `-apple-system`, `'SF Pro Text'`, `system-ui`, ...
- Heading letter-spacing: negative spacing (`-0.02em ~ -0.035em`)
- Body font size: `17px~18px`, line-height `1.7+`
- Secondary text: `14px~16px`

## 4. Radius & Shadow

- Main container radius: `28px` (mobile `20px`)
- Standard card radius: `14px~18px`
- Capsule controls: `999px`
- Main shadow: `0 10px 30px rgba(0,0,0,.08)`
- Highlight card shadow: blue-tinted (e.g. `rgba(0,82,204,.1)`)

## 5. Spacing Scale

- Base tokens:
  - `--space-1: 8px`
  - `--space-2: 12px`
  - `--space-3: 16px`
  - `--space-4: 20px`
  - `--space-5: 24px`
- Usage rule: use scale values for inner spacing; page rhythm centered on `20/24/32`.

## 6. Layout Rules

- Max content width: `1200px`
- Main area: translucent glass container (`backdrop-filter: blur + saturate`)
- Aside: dedicated `aside-card` containing nav and search
- Top area: sticky `global-nav` capsule (desktop and mobile)

## 7. Component Rules

- Hero: gradient + glow background, large `clamp(...)` heading
- List items: cardized; first item can be treated as featured card
- Tags: capsule tags (`border-radius: 999px`)
- Pagination buttons: capsule shape with consistent touch height
- Media blocks: unified display cards; multi-image 2-column (mobile 1-column)

## 8. Motion Rules

- Page enter: slight translate + fade (`~0.6s`)
- List stagger: first 3 items (`0.35/0.45/0.55s`)
- Hover feedback: subtle lift (`translateY(-2px)`)
- Parallax: Hero uses `view-timeline`; graceful fallback if unsupported

## 9. Responsive Rules

- Breakpoints: `600px` (mobile), `799px` (mid-range)
- Mobile strategy:
  - reduce main container radius and spacing
  - collapse multi-column media/tag layouts to single column
  - keep nav/aside controls touch-friendly

## 10. Readability & Usability

- Improved text contrast with clear primary/secondary hierarchy
- Unified control paddings for better touch usability
- Minimal animation, strong information hierarchy, reading-first approach
