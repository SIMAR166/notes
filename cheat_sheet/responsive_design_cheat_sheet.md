
# 📒 Responsive Web Design Cheat Sheet



## 1. Meta Tag for Viewport
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
Ensures website scales properly on all devices.

## 2. Flexible Layout Properties
| Property        | Syntax                  | Purpose |
|-----------------|-------------------------|---------|
| width           | `width: 80%;`          | Makes element width relative to parent |
| height          | `height: 50vh;`        | Height relative to viewport |
| max-width       | `max-width: 1200px;`   | Prevents element from getting too large |
| min-width       | `min-width: 300px;`    | Prevents element from shrinking too much |
| box-sizing      | `box-sizing: border-box;` | Includes padding and border inside element width |
| padding/margin  | `%`, `em`, `rem`       | Makes spacing relative |
| display         | `block`, `flex`, `grid`| Controls layout type |

## 3. Flexbox for Responsiveness
```css
display: flex;
flex-direction: row | column;
flex-wrap: wrap;
justify-content: space-between;
align-items: center;
align-content: stretch;
```

## 4. CSS Grid for Responsiveness
```css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
gap: 20px;
```

## 5. Media Queries
```css
@media screen and (max-width: 768px) {
  body { font-size: 14px; }
}
```
Example breakpoints:
```css
@media (max-width: 1200px) { ... }
@media (max-width: 992px) { ... }
@media (max-width: 768px) { ... }
@media (max-width: 480px) { ... }
```

## 6. Responsive Typography
| Property | Syntax | Purpose |
|----------|--------|---------|
| font-size | `font-size: 1em;` | Relative to parent font size |
| rem | `font-size: 2rem;` | Relative to root font size |
| clamp | `font-size: clamp(1rem, 2vw, 2rem);` | Fluid font scaling |
| vw | `font-size: 2vw;` | Relative to viewport width |

## 7. Responsive Images
| Property | Syntax | Purpose |
|----------|--------|---------|
| max-width | `max-width: 100%;` | Prevents images from overflowing |
| height | `height: auto;` | Maintains aspect ratio |
| object-fit | `object-fit: cover;` | Properly crops/scales image |
| srcset/picture | HTML attribute | Loads different images for different devices |
Example:
```html
<img src="image.jpg" 
     srcset="image-400.jpg 400w, image-800.jpg 800w"
     sizes="(max-width: 600px) 400px, 800px">
```

## 8. Relative Units for Responsiveness
| Unit | Meaning |
|------|---------|
| % | Relative to parent element |
| vw/vh | Relative to viewport width/height |
| em | Relative to parent element’s font size |
| rem | Relative to root font size |
| fr | Fraction of available space in CSS Grid |

## 9. Positioning
- Use relative units instead of fixed pixels.
- Avoid fixed positioning unless necessary.
- Use Flexbox/Grid for responsive positioning.

## 10. CSS Functions for Responsiveness
| Function | Syntax | Purpose |
|----------|--------|---------|
| min() | `width: min(90%, 1200px);` | Chooses the smaller value |
| max() | `width: max(300px, 10vw);` | Chooses the larger value |
| clamp() | `font-size: clamp(1rem, 2vw, 2rem);` | Restricts a value within a range |

## 11. Viewport Units
| Unit | Meaning |
|------|---------|
| 1vw | 1% of viewport width |
| 1vh | 1% of viewport height |
| vmin | Smaller of vw and vh |
| vmax | Larger of vw and vh |

## 12. Responsive Navigation
```css
@media (max-width: 768px) {
  nav { display: none; }
  .menu-icon { display: block; }
}
```

## 13. CSS Variables for Breakpoints
```css
:root {
  --breakpoint-mobile: 480px;
  --breakpoint-tablet: 768px;
  --breakpoint-desktop: 1200px;
}

@media (max-width: var(--breakpoint-mobile)) { ... }
```

## 14. Accessibility for Responsiveness
- Use readable font sizes.
- Ensure touch targets are at least 48px.
- Test on different devices and browsers.

## 15. Tools for Responsive Testing
- Chrome DevTools (Toggle Device Toolbar)
- BrowserStack, Responsinator

---

**Pro Tip:**  
Three pillars of responsive design:
1. Relative units (`%, vw, vh, em, rem`)  
2. Flexbox/Grid layout  
3. Media queries
