# Copilot Instructions for my-project-da24tta

## Project Overview
This is an educational web project containing multiple HTML pages with CSS styling and JavaScript functionality. The project demonstrates learning of web development fundamentals including forms, tables, and basic interactivity.

**Language**: Vietnamese  
**Type**: Static HTML/CSS/JavaScript educational site  
**Main Components**: Multiple standalone HTML pages (personal profile, login form, multiplication table, invoice, etc.)

## Directory Structure & Patterns

- `index.html` - Main landing page with navigation links to all pages
- `html/` - Individual page modules:
  - `gioithieu.html` - Personal introduction page (uses `style.css`)
  - `dangnhap.html` - Login form page (uses `style2.css`)
  - `bangcuuchuong.html` - Multiplication table generator with inline JavaScript
  - `hoadonbanhang.html` - Invoice display page (uses `style1.css`)
  - `dientichhinhvuong.html` & `hienthithongbao.html` - Additional pages
- `css/` - Separate stylesheets:
  - `style.css` - Basic layout with `.container` (margin: 10px 100px)
  - `style1.css` - Modern gradient theme with pink/black colors, invoice styling
- `js/lib.js` - Currently empty, intended for shared utilities
- `assets/image/` - Image directory (references `avatar.jpg` in gioithieu.html)

## HTML/CSS Conventions

### Page Structure
- All pages use Vietnamese language (`lang="vi"`)
- UTF-8 encoding (`<meta charset="UTF-8">`)
- Container pattern: `<div class="container">` wraps main content
- Relative CSS imports: `href="../css/style.css"`

### Common CSS Classes
- `.container` - Main content wrapper with left/right margin of 100px, light gray background
- `.form-group` - Form field grouping (used in login page)
- `.form-control` - Form input styling
- `#bang1`, `#bang2` - Table styling (bang = table in Vietnamese)

### Table Patterns
- Tables use `id` attribute for styling (`#bang1`, `#bang2`)
- Table 1: Simple layout, images in cells
- Table 2: Bordered table with headers, 1px solid black border, 5px padding

## JavaScript Patterns

### Inline vs External
- Inline scripts: Most pages embed `<script>` directly in HTML (e.g., bangcuuchuong.html)
- Event handling: Use `onclick="functionName()"` and `addEventListener()` for key events
- Form interactions: Input validation with `getElementById()` and DOM manipulation via `innerHTML`

### Example Pattern (bangcuuchuong.html)
```javascript
function hienThiBangCuuChuong() {
  let number = document.getElementById('number').value;
  if (number === '' || number < 1 || number > 9) {
    alert('Vui lòng nhập số từ 1 đến 9'); // Vietnamese validation message
    return;
  }
  // Build HTML string and set via innerHTML
}
```

- Use `let` for variables
- String concatenation for HTML generation (not template literals)
- `addEventListener('keypress')` for Enter key handling on forms

## Development Workflows

### Adding New Pages
1. Create `html/newpage.html` with Vietnamese lang attribute
2. Link from main navigation in `index.html`
3. Reference CSS via `../css/style.css` (adjust based on styling needs)
4. Add any page-specific JavaScript inline in `<script>` tag

### Styling Approaches
- **Minimal styling** (`style.css`): Basic reset, container layout, table borders
- **Modern styling** (`style1.css`): Gradients, CSS variables (--pink, --black), flexbox/grid

Use `style.css` for simple educational pages; use `style1.css` for visually enhanced pages.

### Cross-Page Navigation
All pages link back through relative paths. Verify `../css/` and `../assets/` paths when creating new pages in `html/` directory.

## Project-Specific Considerations

- **Vietnamese conventions**: All page titles, labels, and validation messages are in Vietnamese
- **No backend**: Purely static frontend; form validation is client-side only
- **Inline JavaScript**: Prefer keeping JavaScript in HTML for simple utilities rather than external files
- **CSS per-page**: Different visual themes (style.css vs style1.css) show flexibility in design approach
- **No build process**: Serve directly via HTTP server or open HTML files locally

## Common File References
- Entry point: [index.html](../index.html)
- Multiplication table logic: [html/bangcuuchuong.html](../html/bangcuuchuong.html#L25)
- Modern styling template: [css/style1.css](../css/style1.css#L1-L30)
- Standard page layout: [html/gioithieu.html](../html/gioithieu.html)
