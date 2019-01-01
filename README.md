# The Hugo Theme for SIOC RDF

*This is not a standalone theme. This is a Hugo theme component.*

This theme make able to generate RDF files including
[SIOC](http://rdfs.org/sioc/spec/) representation for each pages.

Example output:

```xml
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:sioc="http://rdfs.org/sioc/ns#"
         xmlns:dc="http://purl.org/dc/elements/1.1/"
         xmlns:aowl="http://bblfish.net/work/atom-owl/2006-06-06/"
         xmlns:content="http://purl.org/rss/1.0/modules/content/">
  <sioc:Post rdf:about="https://tblog.acomagu.me/ccs">
    <dc:title>The RDF for this blog post</dc:title>
    <sioc:content>
      <rdf:Description>
        <rdf:type rdf:resource="http://bblfish.net/work/atom-owl/2006-06-06/Content"/>
        <aowl:type>text/html</aowl:type>
        <aowl:body rdf:datatype="http://www.w3.org/1999/02/22-rdf-syntax-ns#HTML">&lt;p&gt;Body...&lt;/p&gt;</aowl:body>
      </rdf:Description>
    </sioc:content>
    <sioc:content rdf:datatype="http://www.w3.org/1999/02/22-rdf-syntax-ns#HTML">&lt;p&gt;Body...&lt;/p&gt;</sioc:content>
    <sioc:content>## Markdown Content...</sioc:content>
    <content:encoded rdf:datatype="http://www.w3.org/1999/02/22-rdf-syntax-ns#HTML">&lt;p&gt;Body...&lt;/p&gt;</content:encoded>
  </sioc:Post>
</rdf:RDF>
```

## Installation

1. Clone this repo to `<your-site-dir>/themes/hugo-sioc-rdf` directory.
2. Add these your site's `config.toml`:
   - Add "hugo-sioc-rdf" as the left-most element of the `theme`
     list variable.
     ```toml
     theme = ["hugo-sioc-rdf", "my-theme"]
     ```
   - Add "RDF" to list of output formats for Page Kind.
     ```toml
     [outputs]
     page = ["HTML", "RDF"]
     ```
