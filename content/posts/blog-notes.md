---
title: "Blog Notes"
date: 2023-04-10T10:18:08+08:00
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

Example:

{{< admonition type=tip title="This is a tip" open=true >}}
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

Types:

{{< admonition title="note">}}
A **note** banner
{{< /admonition >}}

{{< admonition title="abstract" >}}
An **abstract** banner
{{< /admonition >}}

{{< admonition info >}}
A **info** banner
{{< /admonition >}}

{{< admonition tip >}}
A **tip** banner
{{< /admonition >}}

{{< admonition success >}}
A **success** banner
{{< /admonition >}}

{{< admonition question >}}
A **question** banner
{{< /admonition >}}

{{< admonition warning >}}
A **warning** banner
{{< /admonition >}}

{{< admonition failure >}}
A **failure** banner
{{< /admonition >}}

{{< admonition danger >}}
A **danger** banner
{{< /admonition >}}

{{< admonition bug >}}
A **bug** banner
{{< /admonition >}}

{{< admonition example >}}
An **example** banner
{{< /admonition >}}

{{< admonition quote >}}
A **quote** banner
{{< /admonition >}}
