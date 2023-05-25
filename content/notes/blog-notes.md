---
title: "Blog Notes"
date: 2023-04-10T10:18:08+08:00
summary: "Just some notes, nothing interesting."
draft: false
mermaid: true
---

## Themes

Based on hugo:

- [PaperMod](https://adityatelange.github.io/hugo-PaperMod/)
- [PaperModX](https://reorx.github.io/hugo-PaperModX/) (current)

## Shortcuts

- new post: `hugo new posts/name-of-the-post.md`
- local server: `hugo server`

## Techniques & Gadgets

### Draw diagrams

1. Use [mermaid](#mermaid)
2. Hugo natively support [approach](https://gohugo.io/content-management/diagrams/) (use [asciiflow](https://asciiflow.com/) or [Diagon](https://arthursonzogni.com/Diagon/) + [GoAT](https://github.com/bep/goat))

  Example:

  ```goat
                         ┌────────┐
      ┌─────────────────►│ Action ├──────────────────────┐
      │                  └───┬────┘                      │
      │                      │                           │
      │                      ▼                           ▼
  ┌───┴───┐               ┌──────┐                 ┌───────────┐
  │ Agent │◄──────────────┤Reward│◄────────────────┤Environment│
  └───────┘               └──┬───┘                 └─────┬─────┘
      ▲                      │                           │
      │                      ▼                           │
      │                 ┌───────────┐                    │
      └─────────────────┤Observation│◄───────────────────┘
                        └───────────┘
  ```

  Its code (be careful when copying the code, because there are two extra spaces in every line):

  ```markdown
    ```goat
                           ┌────────┐
        ┌─────────────────►│ Action ├──────────────────────┐
        │                  └───┬────┘                      │
        │                      │                           │
        │                      ▼                           ▼
    ┌───┴───┐               ┌──────┐                 ┌───────────┐
    │ Agent │◄──────────────┤Reward│◄────────────────┤Environment│
    └───────┘               └──┬───┘                 └─────┬─────┘
        ▲                      │                           │
        │                      ▼                           │
        │                 ┌───────────┐                    │
        └─────────────────┤Observation│◄───────────────────┘
                          └───────────┘
    ```
  ```

## Extensions

### Math Typesetting

I use MathJax.

Basic usage of Mathjax: [MathJax basic tutorial and quick reference](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference) or [MathJax - Tex : Quick Reference Guide](https://www.sqlpac.com/en/documents/mathjax-tex-practical-handbook-quick-reference.html)

### Admonition

- Use admonition shortcodes of [loveit](https://hugoloveit.com/) in [PaperModX](https://reorx.github.io/hugo-PaperModX/)
- How to transplant: see this [blog](https://lanwp.org/18-hugo-shortcodes-admonition/)
- Documentation of [loveit admonition](https://hugoloveit.com/theme-documentation-extended-shortcodes/#4-admonition)

- Example:

  {{< admonition tip "This is a tip" true >}}
  A **tip** banner
  {{< /admonition >}}

  Its shortcode:

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

### Mermaid

Mermaid lets you create diagrams by writing text in markdown files.

- See this [blog](https://navendu.me/posts/adding-diagrams-to-your-hugo-blog-with-mermaid/) to add this extension to your blog.
  
  But I want to use mermaid v10, so I change the `mermaid.html` from

  ```html
  <script
    type="application/javascript"
    src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"
  ></script>
  <script>
    var config = {
      startOnLoad: true,
      theme:'{{ if site.Params.mermaid.theme }}{{ site.Params.mermaid.theme }}{{ else }}dark{{ end }}',
      align:'{{ if site.Params.mermaid.align }}{{ site.Params.mermaid.align }}{{ else }}center{{ end }}',
    };
    mermaid.initialize(config);
  </script>
  ```

  to

  ```html
  <script
    type="module"
  >
    var config = {
      startOnLoad: true,
      theme:'{{ if site.Params.mermaid.theme }}{{ site.Params.mermaid.theme }}{{ else }}default{{ end }}',
      align:'{{ if site.Params.mermaid.align }}{{ site.Params.mermaid.align }}{{ else }}center{{ end }}',
    };
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
    mermaid.initialize(config);

  </script>
  ```

- Its [offical documentation](https://mermaid.js.org/intro/)
- Its [live editor](https://mermaid.live/edit)
- And I choose the theme [neutral](https://mermaid.js.org/config/theming.html#available-themes)
- Example:

  {{< mermaid >}}
  sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
  {{< /mermaid>}}

  Its shortcode:

  ```markdown
  {{</* mermaid */>}}
  sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
  {{</* /mermaid */>}}
  ```

### Hugo-cite

I use [hugo-cite](https://github.com/loup-brun/hugo-cite) to create citations and modified some settings:

- modifies the `cite.html` to show only the first author in citations.
- modifies the css of `hugo-cite-bibliography` class.

I use [Zotero](https://www.zotero.org/) with [Better BibTeX for Zotero](https://retorque.re/zotero-better-bibtex/) to export CSL-JSON file. Some tips:

- Here is the citation key formula I prefer: `auth.capitalize + year`
- When you have changed the formula, remember to refresh BibTeX key
- Choose `Better CSL JSON` rather than `CSL JSON` when exporting.
