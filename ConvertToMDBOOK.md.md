# Migrating YOOFAB from MkDocs to mdBook

Yes, you can migrate YOOFAB from MkDocs to mdBook while reusing your existing Markdown files. However, there are some important considerations regarding compatibility and feature support.

## Compatibility Overview

**Basic Migration:**
Your Markdown content will largely work without modification, since both tools support standard Markdown syntax.

**Key Differences:**
* mdBook has a different configuration approach (TOML vs YAML)
* Some MkDocs-specific features require adaptation
* Theme customisation works differently

## Using Partials with mdBook

mdBook supports partial templates through its templating system. You can add MathJax and Mermaid via CDN by modifying the template files.

### Implementation Approach:

1. **Create custom header partial**
```
<!-- In theme/head.hbs -->
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({startOnLoad:true});
</script>
```

2. **Configure mdBook to use custom theme**
```toml
[output.html]
additional-css = ["custom.css"]
```

## Feature Comparison

| Feature | MkDocs | mdBook |
|---------|--------|--------|
| Markdown files | ✓ | ✓ |
| MathJax support | Plugin | Custom template |
| Mermaid support | Plugin | Custom template |
| Partial templates | Macros | Built-in templating |
| Configuration | YAML | TOML |

## Recommended Migration Steps

1. **Backup current site**
2. **Set up mdBook structure**
3. **Convert `mkdocs.yml` to `book.toml`**
4. **Test content rendering**
5. **Implement custom templates for MathJax/Mermaid**
6. **Adjust styling as needed**

## Internet search findings

I cannot access external websites or perform web searches. The information provided is based on general knowledge of static site generators and documentation tools. For details about YOOFAB's current implementation, you would need to examine the project's actual configuration and content structure.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3Nzg3NzgwXX0=
-->