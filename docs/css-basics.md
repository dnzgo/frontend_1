## CSS Basics — What You Need to Know

A short guide to the CSS you need for **Mini Project 2: Style Your Personal Landing Page**. Learn these concepts, then apply them to your existing `index.html`.

---

### 1. What is CSS?

- **CSS** = Cascading Style Sheets.
- It controls **how** your page looks: colors, fonts, sizes, spacing, layout, etc.
- HTML gives you structure; CSS gives you **presentation**.
- CSS can live:
  - Inside a `<style>` tag (in the HTML file), or
  - In a **separate file** (e.g. `styles.css`) linked from your HTML. For real projects, this is preferred.

---

### 2. Basic Syntax: Selectors, Properties, Values

A CSS rule looks like this:

```css
selector {
  property: value;
}
```

Example:

```css
body {
  background-color: #f5f5f5;
  font-family: Arial, sans-serif;
}
```

- **Selector** (`body`) = which HTML element(s) the rule applies to.
- **Property** (`background-color`, `font-family`) = what you want to change.
- **Value** (`#f5f5f5`, `Arial, sans-serif`) = how you want it to look.
- Each property ends with a **semicolon** `;`.

---

### 3. How to Add CSS to Your Page

For Mini Project 2, we’ll use a **separate CSS file**.

1. Create a file called `styles.css` in the same folder as `index.html`.
2. Link it in your HTML `<head>`:

```html
<head>
  <title>First Web Page</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
</head>
```

- `<link rel="stylesheet" href="styles.css">` tells the browser to load your CSS.
- Make sure `href` matches the actual path/filename.

You can also write CSS inside an HTML file using `<style>...</style>`, but for this mini project we’ll practice with an external file.

---

### 4. Types of Selectors You’ll Use

#### a) Element (type) selectors

Target all elements of a given type:

```css
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}

h1 {
  font-size: 2rem;
}

p {
  line-height: 1.5;
}
```

#### b) Class selectors

Use classes when you want to style **some** elements in a special way.

In HTML:

```html
<section class="card">
  <h2>Links</h2>
  ...
</section>
```

In CSS:

```css
.card {
  background-color: white;
  border-radius: 8px;
  padding: 16px;
}
```

- In HTML, `class="card"`.
- In CSS, `.card` (a dot before the name).
- You can reuse the same class on many elements.

#### c) ID selectors (use rarely at first)

IDs must be **unique** on the page.

In HTML:

```html
<header id="top">
  ...
</header>
```

In CSS:

```css
#top {
  background-color: #222;
}
```

- In HTML, `id="top"`.
- In CSS, `#top` (a hash before the name).
- Prefer **classes** for styling; use IDs mainly for unique things or jump links.

---

### 5. Colors, Backgrounds, and Text

#### Colors

You can specify colors by:

- Name: `red`, `blue`, `black`, `white`, `gray`, `tomato`, etc.
- Hex: `#ff0000`, `#333333`, `#f5f5f5`, etc.
- RGB: `rgb(255, 0, 0)` (red).

Examples:

```css
body {
  background-color: #f5f5f5;
  color: #222222;
}

a {
  color: #1e88e5;
}

a:hover {
  color: #1565c0;
}
```

#### Text and fonts

Useful properties:

- `font-family`
- `font-size`
- `font-weight`
- `line-height`
- `text-align`

Example:

```css
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  font-size: 16px;
}

h1 {
  font-size: 2.2rem;
  font-weight: 700;
  text-align: center;
}

p {
  line-height: 1.6;
}
```

- `px` = pixels (fixed size).
- `rem` = relative to the root font size (recommended for scalable sizes).

---

### 6. Spacing: Margin and Padding

- **Padding**: space **inside** the element, between its border and its content.
- **Margin**: space **outside** the element, between it and neighbors.

Example:

```css
section {
  padding: 16px;
  margin: 16px 0;
}
```

Shorthands:

```css
/* one value: all sides */
padding: 16px;

/* two values: top/bottom, left/right */
margin: 16px 8px;

/* four values: top, right, bottom, left */
margin: 16px 8px 24px 8px;
```

For your landing page, you’ll use margin to add space between sections and padding inside “card”-like blocks.

---

### 7. Borders and Border Radius

Borders go around elements:

```css
.card {
  border: 1px solid #dddddd;
  border-radius: 8px;
}
```

- `border`: width, style, and color.
- `border-radius`: how rounded the corners are (e.g. `8px`, `50%` for circles).

A common pattern: a white card with rounded corners and a shadow.

```css
.card {
  background-color: white;
  border-radius: 12px;
  padding: 16px 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}
```

---

### 8. Layout with Flexbox (basic)

Flexbox helps you align elements horizontally or vertically.

To center your main content, you can make the `body` or a wrapper a flex container:

```css
body {
  min-height: 100vh;
  margin: 0;
  display: flex;
  justify-content: center; /* horizontal */
  align-items: center;     /* vertical */
}
```

But often you’ll want a **column** layout (top to bottom) with centered content:

```css
body {
  margin: 0;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  background-color: #f5f5f5;
}

main {
  max-width: 600px;
  margin: 32px auto;
  padding: 0 16px;
}
```

- `max-width: 600px` keeps content from stretching too wide.
- `margin: 32px auto` centers a block horizontally and adds top/bottom space.
- `auto` left and right margins are what center the block.

For Mini Project 2, you can use simple `max-width` + `margin: auto` layout without deep Flexbox yet.

---

### 9. Styling Links, Images, and Footer

#### Links

```css
a {
  color: #1e88e5;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```

- `:hover` is a **pseudo-class**: it styles the element when the mouse is over it.

#### Images

```css
img {
  max-width: 100%;
  height: auto;
  display: block;
  margin: 0 auto 16px;
  border-radius: 50%;
}
```

- `max-width: 100%` keeps the image from overflowing its container.
- `display: block` + `margin: 0 auto` centers the image.
- `border-radius: 50%` makes it circular (if width = height).

#### Footer

```css
footer {
  margin-top: 32px;
  padding: 16px 0;
  text-align: center;
  font-size: 0.9rem;
  color: #666666;
}
```

---

### 10. Good Habits for CSS

1. **Keep CSS in its own file** (`styles.css`) for anything more than a tiny experiment.
2. **Use classes** instead of IDs for styling.
3. **Group related rules** together (e.g. header styles, main content styles, footer styles).
4. **Avoid magic numbers** (random values). Try to be consistent (e.g. multiples of 4 or 8 for spacing).
5. **Reset default margins** if needed:

   ```css
   body {
     margin: 0;
   }
   ```

---

### 11. Checklist for Mini Project 2

You will create a `styles.css` file and apply it to your existing `index.html` (Mini Project 1).

Your CSS should:

- [ ] Link a `styles.css` file in `<head>` using `<link rel="stylesheet" href="styles.css">`.
- [ ] Set a **global font** and base text color for `body`.
- [ ] Give the page a light **background color** and keep the content in a centered column (`max-width` + `margin: auto`).
- [ ] Style the **header**: maybe background color, padding, centered text, and larger `h1`.
- [ ] Make the **image** a circle or nicely framed (border-radius, maybe a border or shadow).
- [ ] Style the **Links section** as a “card” with background, padding, border-radius, and maybe a slight shadow.
- [ ] Remove underlines from links by default and show a clear hover state.
- [ ] Style the **footer** with smaller text, center alignment, and subtle color.
- [ ] Add some **spacing** between sections using `margin` and `padding`.

Optional extras:

- [ ] Use a different background color for the page and white cards for content.
- [ ] Add a hover effect to the list items (e.g. slightly darker background on hover).
- [ ] Make the layout look good on both mobile and desktop (text not too wide, content not squished).

---

Once you’re comfortable with these basics, open `styles.css`, start with the `body`, `header`, `main`, `section`, `img`, `ul`, `li`, `a`, and `footer` selectors, and iteratively refresh the browser to see your changes.

