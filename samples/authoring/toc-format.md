# TOC format

`toc.yml` lives anywhere in the repository. Links inside it are relative to the folder that contains the file. With the TOC at `samples/toc.yml`, `href: index.md` loads `samples/index.md`.

```yaml
items:
  - name: Overview
    href: index.md
  - name: Authoring
    items:
      - name: TOC format
        href: authoring/toc-format.md
  - name: External
    href: https://learn.microsoft.com
```

1. `name` is the label in the tree and in the breadcrumb.
2. `href` is the Markdown file, or an `https://` address.
3. `items` are the children. A node can be a folder with children and no `href`.
4. A path that starts with `~/` is read from the repository root.
5. A nested `toc.yml` is not expanded. Keep the tree in one file.

The optional **Home page** web part setting is also relative to the TOC folder. Leave it blank to open the first Markdown page in the tree.
