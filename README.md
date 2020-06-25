# Vividus documentation

## General info
This is a playbook repo. It's purpose is keeping the way we deploy Vividus' documentation and UI customizations.
We use [Antora](https://docs.antora.org/) as a static site generator and [Asciidoctor](https://asciidoctor.org/docs/) as a documentation format and text processor.

## Local environment

1. Install Node.js
2. Install antora using `npm i -g @antora/cli @antora/site-generator-default`
3. Use `antora antora-playbook-local.yml` to generate a site

*[IMPORTANT]*

Cloned docs.vividus.dev repository by default (you could change this in a playbook) should be placed in the same folder as a vividus itself.

### One liner
```shell
 npm i -g @antora/cli @antora/site-generator-default && \  
 git clone https://github.com/vividus-framework/vividus.git && \   
 git clone https://github.com/vividus-framework/docs.vividus.dev.git && \   
 cd docs.vividus.dev && antora antora-playbook-local.yml && \  
 open ./public/index.html
 ```
