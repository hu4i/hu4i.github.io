---
title: "Blog Notes"
date: 2023-04-10T10:18:08+08:00
summary: "Just some notes, nothing interesting."
draft: false
---

## Themes

Based on hugo:

- [PaperMod](https://adityatelange.github.io/hugo-PaperMod/)
- [PaperModX](https://reorx.github.io/hugo-PaperModX/) (current)

## Shortcuts

- new post: `hugo new posts/name-of-the-post.md`
- local server: `hugo server`

## Extensions

### Math Typesetting

See PaperModX's [document](https://reorx.github.io/hugo-PaperModX/docs/math-typesetting/). (But it doesn't work for me)

### Admonition

- Use admonition shortcodes of [loveit](https://hugoloveit.com/) in [PaperModX](https://reorx.github.io/hugo-PaperModX/)
- How to transplant: see this [blog](https://lanwp.org/18-hugo-shortcodes-admonition/)
- Documentation of [loveit admonition](https://hugoloveit.com/theme-documentation-extended-shortcodes/#4-admonition)

- Example:

  {{< admonition tip "This is a tip" true >}}
  A **tip** banner
  {{< /admonition >}}

  It's code:

  ```markdown
  {{</* admonition type=tip title="This is a tip" open=true */>}}
  A **tip** banner
  {{</* /admonition */>}}
  ```

  or

  ```markdown
  {{</* admonition tip "This is a tip" true */>}}
  A **tip** banner
  {{</* /admonition */>}}
  ```
