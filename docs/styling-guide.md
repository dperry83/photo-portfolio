# Photography Website Styling Guide

This guide is the working reference for styling decisions on the photography website. It exists to keep the CSS simple, mobile-first, and easy to extend without turning every new section into a one-off styling problem. The project uses plain HTML, CSS, and vanilla JavaScript for version 1, with a small custom design system instead of a framework-heavy approach. [file:150][file:151]

## Purpose

The styling system should help the site feel credible, calm, modern, human, and low-drama. It should support the photography and the message instead of competing with them, which matches the documented design direction for version 1. [file:151]

This guide is also meant to make styling decisions easier for a beginner. The goal is not to memorize clever CSS tricks. The goal is to learn a repeatable way to build and adjust styles with less guesswork. [file:150]

## Core principles

- Start mobile first. Build the smallest-screen version first, then add larger-screen changes with `min-width` media queries. This is the standard mobile-first responsive approach and keeps layout decisions simpler. [web:299][web:298]
- Separate concerns. Keep design tokens, base styles, layout rules, component styles, and media-query upgrades in distinct parts of the CSS so the stylesheet stays understandable. [web:298]
- Reuse values. Define colors, spacing, and type sizes as CSS custom properties in `:root` so changes stay consistent across the site. CSS custom properties are designed for exactly this kind of reuse. [web:309]
- Let containers control layout. Use wrapper elements and container widths instead of forcing layout with big left/right paddings on individual elements. This makes responsive behavior more predictable. [web:298]
- Keep the visual system restrained. The site’s chosen direction is warm neutrals plus one restrained accent color, with readable text on both light and dark backgrounds. [cite:290][file:151]
- Use photography and copy as the main event. Layout and styling should create structure and trust, not steal attention from the images or the founder-focused message. [file:151][cite:177]

## The CSS structure

A good working order for the stylesheet is:

1. Design tokens
2. Reset / global cleanup
3. Base element styles
4. Layout wrappers
5. Component styles
6. Media-query upgrades

This structure makes it easier to know where a change belongs. Responsive design guidance generally starts with simple defaults, then layers on layout enhancements as screen size increases. [web:298][web:299]

### 1. Design tokens

Put reusable values in `:root`.

Examples:

- Colors
- Font families
- Type scale
- Spacing scale
- Border radius values
- Container widths

This is the control panel for the site. If a value shows up repeatedly, it probably belongs here instead of being hardcoded in three or four places. CSS custom properties are specifically meant to support this kind of shared system. [web:309]

### 2. Reset / global cleanup

Use a small reset so the browser does less unexpected work behind the scenes.

Common examples:

- `box-sizing: border-box;`
- `body { margin: 0; }`
- `img { max-width: 100%; display: block; }`

This gives layout a cleaner baseline, which is especially helpful when building responsive pages. [web:298]

### 3. Base element styles

Style the main HTML elements once before styling individual components.

Typical base elements:

- `body`
- `h1`, `h2`, `h3`
- `p`, `li`
- `a`
- `button`
- `img`

Think of these as the site’s defaults. If a paragraph sits somewhere with no special class, it should still look correct. [web:298]

### 4. Layout wrappers

Use wrappers to control width, spacing, and centering.

Examples:

- `.container`
- `.header-inner`
- section width rules

A common beginner mistake is to position things by adding large paddings directly to children, such as pushing the logo right with `padding-left: 125px`. A wrapper is usually the better answer because it controls the whole group, not one child. [file:297]

### 5. Component styles

After tokens, reset, base styles, and layout wrappers are in place, style the actual page pieces.

Examples:

- Header
- Navigation
- Hero
- Buttons
- Cards
- Forms

Components are where project-specific styling should live. This is the part that should change most from one site to another. [file:151]

### 6. Media-query upgrades

Add larger-screen enhancements only after the mobile version works.

Example pattern:

```css
@media (min-width: 48rem) {
  .navigation {
    display: flex;
  }
}
```

In a mobile-first setup, the default styles are the mobile version. The media query is the upgrade layer for wider screens. [web:299][web:298]

## A repeatable approach

When building a new section, use this order:

1. Start with the content and HTML structure.
2. Make sure the content order makes sense on mobile.
3. Use existing tokens for color, spacing, and type.
4. Apply existing layout classes or patterns where possible.
5. Only add new component styles if the existing system truly cannot handle the section.
6. Add a larger-screen adjustment only after the mobile version feels right. [web:299][web:298][file:151]

This approach keeps the work smaller and prevents “CSS sprawl,” where every new section gets its own special one-off rules. [file:151]

## How to decide whether to add new styles

Before writing a new class or new rule, ask these questions in order:

1. Can this be solved with existing HTML structure?
2. Can this be solved by reusing an existing class or component?
3. Can this be solved by using existing spacing, type, or color tokens?
4. Is this a true new pattern that will appear more than once?
5. If it is new, where does it belong: token, base style, layout rule, or component rule?

If the answer is “this is just another paragraph, heading, button, or container,” then it usually does **not** need a brand-new style. It probably just needs to sit inside the right structure. [file:150][file:151]

## Adding new HTML without adding new styles

A good design system should let many pieces of HTML work with existing rules.

Examples:

- Add a new paragraph inside a section that already inherits body copy styles.
- Add a new heading inside a content block that already uses global heading styles.
- Add another CTA link using the existing `.primary` or `.secondary` button classes.
- Add another section inside the site’s standard width wrapper instead of inventing a new width rule.

This works best when the base styles are strong and the layout structure is clear. If raw HTML looks reasonable before custom styling, the system is doing its job. [web:298][file:151]

## When a new style *is* justified

A new style is usually justified when one of these is true:

- A new component appears that has a distinct purpose, like a testimonial card or portfolio grid item.
- A new pattern will be reused across multiple pages.
- A section needs a different layout, not just more content.
- A state needs styling, such as hover, active, open, or error.

A new style is usually **not** justified when the real issue is just spacing, bad HTML structure, or trying to push things around manually. [file:297][web:298]

## How to make style changes safely

When changing styles, use this small workflow:

1. Identify the problem in plain language, such as “the hero text is too wide on mobile.”
2. Decide what layer the change belongs to: token, base, layout, component, or media query.
3. Change one thing at a time.
4. Refresh and check the smallest screen first.
5. Only after mobile looks right, check larger widths.
6. Stop once the actual problem is solved.

This avoids the common trap of changing five unrelated rules at once and not knowing which one actually fixed or broke the layout. [web:299][web:298]

## Choosing between Grid and Flexbox

A simple rule of thumb:

- Use **Grid** for larger page sections and two-dimensional layout problems.
- Use **Flexbox** for one-dimensional groups, such as a row of nav items or a vertical stack of buttons.

For example, a hero section with an image area and a text area is often a Grid problem, while CTA buttons are often a Flexbox problem. MDN describes Grid as more suitable for two-dimensional layout and Flexbox for one-dimensional layout. [web:304][web:310]

## Working with spacing

Use the spacing scale before inventing random numbers.

Instead of asking “what padding should this have,” ask:

- Is this a tight internal gap?
- Is this a normal content gap?
- Is this a section-level gap?

Then choose from the existing spacing steps. Reusing spacing values creates rhythm and makes the whole site feel more intentional. [web:309][file:151]

## Working with color and text contrast

The site uses a warm-neutral palette with one restrained accent color and separate text roles for light and dark backgrounds. That means the system should include main text, muted text, text on dark backgrounds, and muted text on dark backgrounds. [cite:290]

Before adding or changing a color, ask:

- Is this a surface color, a text color, or an accent?
- Is this being used on a light background or a dark one?
- Does this reuse an existing token, or is it introducing unnecessary variation?

In most cases, the right move is to use the existing token system instead of introducing another hex code. [cite:290][file:151]

## A beginner decision tree

When something looks wrong, ask:

- Is the problem really structure, not styling?
- Is the content order wrong on mobile?
- Is a wrapper missing?
- Am I fighting the container instead of fixing the container?
- Am I adding a new class when an existing one already does the job?
- Am I solving a mobile problem with a desktop-first rule?

These questions help keep styling changes honest and small. [web:299][file:297]

## Recommended working habits

- Keep one branch focused on one styling goal at a time. [file:150]
- Define success before changing CSS, for example “header and hero feel calm and readable on mobile.” [file:151]
- Build the mobile version first and resist early desktop polishing. [web:299][web:298]
- Reuse tokens and classes before inventing new ones. [web:309]
- Comment the stylesheet in sections so it is easy to scan later.
- When a section feels messy, simplify the HTML structure before adding more CSS. [file:297]

## A simple checklist before writing new CSS

- What is the actual problem?
- What layer does the fix belong to?
- Can an existing token solve it?
- Can an existing class solve it?
- Does the HTML need to be cleaner first?
- Does the mobile version work before the desktop version is considered?

If those questions are answered first, styling work becomes much easier to manage. [web:299][file:151]

## Final reminder

The goal is not to write the shortest CSS possible or the fanciest CSS possible. The goal is to write CSS that is easy to understand, easy to extend, and calm enough that the site’s photography and message can do the real work. That matches the project’s documented version-one direction: simple, clear, static, founder-focused, and low-drama. [file:150][file:151][cite:177]
