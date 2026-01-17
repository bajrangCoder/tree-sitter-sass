# tree-sitter-sass

[![Tests](https://img.shields.io/badge/tests-26%20passing-brightgreen)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

A full-featured [Tree-sitter](https://tree-sitter.github.io/) grammar for **Sass indented syntax** (`.sass` files).

## Features

This grammar provides comprehensive parsing support for Sass indented syntax, aligned with VS Code's Sass highlighting capabilities:

### Syntax Elements

- **Variables** - `$color: red` with `!default` and `!global` flags
- **Selectors** - Full CSS selector support:
  - Tag, class (`.class`), ID (`#id`), universal (`*`)
  - Nesting selector (`&`) with suffix support (`&-header`)
  - Pseudo-classes (`:hover`) and pseudo-elements (`::after`)
  - Attribute selectors (`[attr=value]`)
  - Placeholder selectors (`%clearfix`)
  - Combinators (`>`, `+`, `~`, descendant)
- **Properties** - CSS property declarations with values
- **Values** - Numbers (with units including `%`), colors, strings, booleans, null, lists, maps
- **Expressions** - Binary (`+`, `-`, `*`, `/`, `%`, `==`, etc.), unary, parenthesized
- **Interpolation** - `#{$variable}` in strings and identifiers

### CSS Property Keywords

Recognized CSS keywords for semantic highlighting:

- **Display**: `block`, `inline`, `flex`, `grid`, `inline-block`, etc.
- **Position**: `absolute`, `relative`, `fixed`, `sticky`, `static`
- **Layout**: `center`, `left`, `right`, `top`, `bottom`, `space-between`, `flex-start`, etc.
- **Global**: `inherit`, `initial`, `unset`, `revert`, `auto`, `none`
- **And many more**: `normal`, `bold`, `solid`, `dashed`, `hidden`, `visible`, etc.

### Color Keywords

All 147+ CSS named colors are recognized:

- Basic: `red`, `blue`, `green`, `black`, `white`, `transparent`
- Extended: `rebeccapurple`, `cornflowerblue`, `darkolivegreen`, etc.
- Special: `currentColor`, `transparent`

### CSS Functions

Dedicated recognition for CSS functions:

- **Color functions**: `rgb()`, `rgba()`, `hsl()`, `hsla()`, `hwb()`, `lab()`, `lch()`, `oklch()`, `oklab()`, `color()`, `color-mix()`
- **Gradient functions**: `linear-gradient()`, `radial-gradient()`, `conic-gradient()`, and repeating variants
- **Math functions**: `calc()`, `min()`, `max()`, `clamp()`, `abs()`, `sign()`, `round()`, `mod()`, `rem()`, `sin()`, `cos()`, `tan()`, `pow()`, `sqrt()`, `hypot()`, `log()`, `exp()`
- **CSS Custom Properties**: `var(--custom-prop)` with fallback support

### At-Rules

- **Module System** - `@use`, `@forward` with `as`, `with`, `hide`, `show`
- **Import** - `@import`
- **Mixins** - `@mixin`/`@include` and shorthand `=`/`+`
- **Control Flow** - `@if`/`@else if`/`@else`, `@each`, `@for`, `@while`
- **Functions** - `@function` with `@return`
- **Media Queries** - `@media`, `@supports`
- **Keyframes** - `@keyframes` with vendor prefixes (`@-webkit-keyframes`, etc.)
- **Extend** - `@extend` with `!optional`
- **Other** - `@charset`, `@namespace`, `@at-root`, `@error`, `@warn`, `@debug`, `@content`, `@font-face`

### Indentation-Based Syntax

The grammar uses an external scanner (`src/scanner.c`) to properly handle Sass's indentation-based block structure:

- **INDENT** - Increased indentation starts a block
- **DEDENT** - Decreased indentation ends a block
- **NEWLINE** - Line breaks separate statements

## License

MIT - see [LICENSE](LICENSE) for details.
