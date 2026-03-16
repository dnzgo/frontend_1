# HTML Basics — What You Need to Know

A short guide to the HTML you need for **Mini Project 1: Personal Landing Page**. Learn these concepts, then build your page.

---

## 1. What is HTML?

- **HTML** = HyperText Markup Language.
- It describes the **structure** of a web page: headings, paragraphs, links, images, sections.
- It is **not** a programming language; it’s **markup**: you wrap content in **tags** so the browser knows what each part is.
- Files are saved as `.html` and opened in a browser.

---

## 2. How HTML Works: Tags and Elements

- **Tag**: a keyword in angle brackets. Most content is wrapped in an **opening** and **closing** tag.
- **Element**: opening tag + content + closing tag.

```html
<p>This is a paragraph.</p>
```

- `<p>` = opening tag  
- `</p>` = closing tag (same name with a slash)  
- The text in between is the **content** of the element.

Some elements have **no content** and no closing tag. They are **self-closing**:

```html
<img src="photo.jpg" alt="My photo">
<br>
```

---

## 3. Document Structure: Every Page Starts Here

Every valid HTML page has this skeleton:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Page Title</title>
  </head>
  <body>
    <!-- Your visible content goes here -->
  </body>
</html>
```

What each part does:

| Part | Purpose |
|------|--------|
| `<!DOCTYPE html>` | Tells the browser this is HTML5. Put it on the very first line. |
| `<html lang="en">` | Wraps the whole page. `lang="en"` helps accessibility and search engines. |
| `<head>` | **Not shown on the page.** Metadata: charset, viewport, title, later: CSS/JS links. |
| `<meta charset="UTF-8">` | So the browser can display letters and symbols correctly. |
| `<meta name="viewport" ...>` | So the page scales nicely on phones (responsive basics). |
| `<title>` | Text that appears in the browser tab. |
| `<body>` | **Everything the user sees** goes inside `<body>`. |

For Mini Project 1, you only edit the content inside `<body>` (and the `<title>` in `<head>`).

---

## 4. Essential Elements for Your Landing Page

### Headings

Use for titles and section titles. There are six levels; use them in order (one `h1` per page, then `h2`, `h3`, etc.).

```html
<h1>Main title (e.g. your name)</h1>
<h2>Section title</h2>
<h3>Subsection</h3>
```

### Paragraphs

Use for normal text.

```html
<p>This is a paragraph. It can be short or long.</p>
```

### Links

Links go to other pages or to sections on the same page.

```html
<a href="https://github.com/yourusername">My GitHub</a>
<a href="mailto:you@example.com">Email me</a>
```

- `href` = where the link goes (URL or `mailto:...`).
- The text between `<a>` and `</a>` is what the user clicks.

### Images

Images are inserted with `<img>`. They don’t have a closing tag.

```html
<img src="path/to/your-photo.jpg" alt="Short description of the image">
```

- **`src`**: path to the image file (same folder = just the filename, e.g. `photo.jpg`).
- **`alt`**: short description. Important for accessibility and when the image doesn’t load. Always add it.

### Lists

**Unordered list** (bullets):

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

**Ordered list** (numbers):

```html
<ol>
  <li>Step one</li>
  <li>Step two</li>
</ol>
```

Use `<ul>` for “links”, “skills”, “hobbies”. Use `<ol>` only if order really matters (e.g. steps).

### Line break

To force a new line inside a paragraph or heading:

```html
<p>First line.<br>Second line.</p>
```

---

## 5. Semantic HTML: Meaningful Sections

Semantic tags describe **what a section is**, not just “a box”. They help accessibility and structure.

Use these for your landing page:

| Tag | Use for |
|-----|--------|
| `<header>` | Top of the page: logo, main title, maybe a short tagline. |
| `<main>` | The main content of the page (one per page). |
| `<footer>` | Bottom: copyright, extra links, contact. |
| `<nav>` | Navigation: links to main sections or external sites. |
| `<section>` | A logical block of content (e.g. “About me”, “Links”). |

Example structure for Mini Project 1:

```html
<body>
  <header>
    <h1>Your Name</h1>
    <p>Short tagline or role</p>
  </header>

  <main>
    <section>
      <h2>About me</h2>
      <p>A few sentences about you.</p>
    </section>

    <section>
      <h2>Links</h2>
      <nav>
        <ul>
          <li><a href="https://github.com/you">GitHub</a></li>
          <li><a href="https://linkedin.com/in/you">LinkedIn</a></li>
        </ul>
      </nav>
    </section>
  </main>

  <footer>
    <p>© 2025 Your Name</p>
  </footer>
</body>
```

You don’t have to use every tag, but using `header`, `main`, and at least one `section` is a good habit.

---

## 6. Attributes: Extra Information on Tags

Attributes go **inside the opening tag** and usually come in pairs: `name="value"`.

Examples you’ll use:

- **Links:** `href="url"`
- **Images:** `src="path"`, `alt="description"`
- **Language:** `lang="en"` on `<html>`
- **Metadata:** `charset="UTF-8"`, `name="viewport"` in `<meta>`

General rules:

- Attribute name, then `=`, then the value in **quotes** (single or double).
- Multiple attributes are separated by spaces: `<a href="..." target="_blank">`.

---

## 7. Comments (Notes for You, Invisible on the Page)

Comments are ignored by the browser. Use them to leave notes or mark sections.

```html
<!-- This is a comment. It won't show on the page. -->
<section>
  <!-- About me section -->
  <h2>About me</h2>
</section>
```

---

## 8. Good Habits

1. **Indent** nested elements (e.g. content inside `<body>` and inside each section) so the structure is easy to read.
2. **Use lowercase** for tag and attribute names: `<section>`, not `<SECTION>`.
3. **Always close tags** that need closing: every `<p>` has a `</p>`, every `<li>` has a `</li>`.
4. **Always add `alt`** to `<img>` for accessibility.
5. **Use semantic tags** where they fit: `header`, `main`, `footer`, `nav`, `section`.

---

## 9. Checklist for Mini Project 1

Your first page should include:

- [ ] Full document structure: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
- [ ] `<title>` and at least `<meta charset="UTF-8">` in `<head>`
- [ ] One `<h1>` (e.g. your name)
- [ ] At least one `<p>` (short bio or tagline)
- [ ] One image (`<img>` with `src` and `alt`)
- [ ] At least two links (`<a href="...">`) — e.g. GitHub, LinkedIn, or email
- [ ] Use of at least: `header`, `main`, and one `section` (or more)
- [ ] Optional: a list (`<ul>` with `<li>`) for your links
- [ ] Optional: a `<footer>` with your name or “© 2025”

---

## 10. Quick Reference

| You want…        | Use… |
|------------------|------|
| Page title (tab) | `<title>` in `<head>` |
| Main heading     | `<h1>` |
| Section heading  | `<h2>` |
| Paragraph        | `<p>` |
| Link             | `<a href="url">text</a>` |
| Image            | `<img src="path" alt="description">` |
| Bullet list      | `<ul>` and `<li>` |
| Numbered list    | `<ol>` and `<li>` |
| Top of page      | `<header>` |
| Main content     | `<main>` |
| Content block    | `<section>` |
| Navigation links | `<nav>` |
| Bottom of page   | `<footer>` |
| New line         | `<br>` |
| Invisible note   | `<!-- comment -->` |

---

Once you’re comfortable with these, open a new `.html` file, start from the document structure in section 3, and build your personal landing page. No CSS or JavaScript needed for this first project—just clean, valid HTML.
