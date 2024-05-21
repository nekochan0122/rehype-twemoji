# Rehype Twemoji

A rehype plugin to convert emoji to twemoji.

## Install

```bash
pnpm i -D @nekochan0122/rehype-twemoji
```

## Usage

```ts
import { rehypeImage } from '@nekochan0122/rehype-twemoji'
import type { RehypeImageOptions } from '@nekochan0122/rehype-twemoji'

...

{
  rehypePlugins: [
    [rehypeTwemoji, {
      format: 'svg',
      source: 'https://cdn.jsdelivr.net/gh/twitter/twemoji@latest',
    } satisfies RehypeTwemojiOptions],
  ]
}
```

Input:

```md
Hello World 👋
```

Output:

```html
<p>
  Hello World
  <img
    src="https://cdn.jsdelivr.net/gh/twitter/twemoji@latest/assets/svg/1f44b.svg"
    alt="👋"
    aria-label="waving hand"
    data-twemoji=""
  />
</p>
```

## Options

- `format`: `svg` or `png` (default: `svg`)
- `source`: source of twemoji (default: `https://cdn.jsdelivr.net/gh/twitter/twemoji@latest`)

## Styling

You can use `data-twemoji` attribute to style the emoji.

Here is an example of using with Tailwind CSS:

```css
[data-twemoji] {
  @apply size-[1.2em] inline-block align-text-bottom;
}
```

# License

MIT
