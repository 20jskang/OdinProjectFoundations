# Elements and Tags

A full paragraph element looks like this:

```html
<p>This is a paragraph element.</p>
```

## Let's break this down:

- `<p>` is the opening tag
- `</p>` is the closing tag
- The text between them is the content of the paragraph

You can think of elements as containers for content.

The opening and closing tags tell the browser what content the element contains. The browser can then use that information to determine how it should interpret and format the content.

---

# Void Elements

Some HTML elements do not have a closing tag.

These elements just have a single tag, like:

```html
<br />
<img />
```

They are known as **void elements** because they are void of any content — there is nothing inside them.

No closing tag means they can't wrap content like other tags do.

---

# Examples

The `<br />` tag is used to create a line break.

```html
<br />
```

It doesn't contain content, so it doesn't need a closing tag.

The `<img />` tag is used to embed an image into a webpage.

```html
<img />
```

It also doesn't contain content, so it doesn't need a closing tag either.

---

# Self-Closing Tags

You might also see these referred to as **self-closing tags**.

Example:

```html
<br />
<img />
```

These are simply void elements with a forward slash at the end.

They are commonly used for historical reasons.

Browsers can still render them correctly, but the latest HTML specification discourages their use and considers them invalid.

Modern HTML usually writes them like this instead:

```html
<br>
<img>
```

---

# Reference

MDN HTML Elements Reference:

https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements