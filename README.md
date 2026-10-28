# xemelgo-etse

Typst template for the TFG report of the Computer Engineering degree (GrEI) at the ETSE, USC.
A clone of the official LaTeX templates, in Spanish, Galician or English.

**Unofficial**: not affiliated with the USC or the ETSE.

<p>
  <img alt="Cover page with the university name, the title, the author and tutors, and the degree" src="docs/cover.png" width="24%">
  <img alt="Table of contents with bold chapters and dotted section entries" src="docs/outline.png" width="24%">
  <img alt="First page of a chapter with the large chapter number and title" src="docs/chapter.png" width="24%">
  <img alt="Page with a running header, a figure, a table and section headings" src="docs/header.png" width="24%">
</p>

## QUICKEST QUICK START

Send this prompt to your favourite LLM:

```txt
I want to write my TFG memoria (GrEI, ETSE-USC) in Typst with the package
`xemelgo-etse` (latest version). Ask me everything through your question/choice
tool, never as a list in chat.

1. Ask me about every option in the template (model A/B/C, language, title,
   authors and tutors, front pages, layout, code style...), giving "Placeholder"
   as an option for text fields.
2. Create the project with `typst init`, using the example for my model from
   https://typst.app/universe/package/xemelgo-etse#examples (B and C are in the
   GitHub repo's `examples/` folder). Write the chapter text in my chosen
   language, mark placeholders with `// TODO`, and check that it compiles.
3. Then interview me about my project and draft the Introduction from my
   answers. Don't invent data, results or references: leave a `// TODO` and ask.
```

## How to use

1. Create the project: *Start from template* in the web app, or `typst init @preview/xemelgo-etse:0.1.0`.
2. Choose your [model](#which-model): `modeloA`, `modeloB` or `modeloC` in `main.typ`.
3. Fill in the [options](#options): title, authors (you first, then tutors)…
4. Write: `=` chapter, `==` section. Appendices go after `#show: apendices`.
5. Cite with `@key` from `refs.bib`.
6. Remove `#include "ejemplos.typ"` before submitting.

## Which model?

Same layout, different suggested chapters. Ask your tutor if unsure.

| Model | TFG type |
|-------|----------|
| `modeloA` | Research or experiments |
| `modeloB` | Software or hardware system |
| `modeloC` | Project or business plan |

See the [examples](#examples) for each model's chapters.

## Options

| Option             | Default   | Description |
|--------------------|-----------|-------------|
| `title`            | `[Title]` | Title. |
| `subtitle`         | `none`    | Subtitle. |
| `authors`          | `()`      | Student, then tutors: `(name: "...")`. Tutors may add `department: "..."`. |
| `logo`             | `auto`    | `auto` is the USC logo, `none` hides it, or pass an `image(..)`. |
| `date`             | `auto`    | A `datetime`. `auto` is today. |
| `lang`             | `"es"`    | `"es"`, `"gl"` or `"en"`. |
| `i18n`             | `(:)`     | Change texts: `(es: (abstract: [Sinopsis]))`. Keys in [`src/i18n.typ`](src/i18n.typ). |
| `certification`    | `true`    | Tutors' certification page. |
| `acknowledgements` | `none`    | Acknowledgements page. |
| `abstract`         | `none`    | Abstract page. |
| `blank-pages`      | `true`    | Chapters on odd pages, for printing. `false` for a compact PDF. |
| `code-style`       | `"latex"` | `"latex"` or `"wired"` (as in [wired-ieee](https://typst.app/universe/package/wired-ieee)). |
| `code-numbers`     | `false`   | Line numbers, with `code-style: "wired"`. |
| `bibliography`     | `none`    | A `bibliography(..)`, in IEEE style. |

## Other functions

| Function      | Use |
|---------------|-----|
| `apendices`   | `#show: apendices` before the appendices (A, B, C…). |
| `short-title` | `= Long title #short-title[Short]`: short title for the index and the header. |
| `caratula`    | CD cover. Options: `title`, `authors`, `course`, `session`, `lang`, `i18n`, `logo`. |

## Examples

- [Model A](template/main.typ) (the `typst init` template)
- [Model B](examples/modeloB.typ)
- [Model C](examples/modeloC.typ)
- [CD cover](examples/caratula.typ)

## License

Code: [MIT](LICENSE). Template files: [MIT-0](LICENSE-MIT-0), so your TFG needs no license notice.

The USC logo (`assets/logo_usc.pdf`) is not covered by these licenses: it belongs to the USC, which allows its use in this template. See the [USC visual identity](https://www.usc.gal/gl/usc/institucional/imaxe-corporativa).
