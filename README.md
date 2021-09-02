# VIVIDUS documentation

This is a playbook repo. It's purpose is keeping the way we deploy VIVIDUS documentation and UI customizations.
We use
- [Antora](https://docs.antora.org/) as a static site generator
- [Asciidoctor](https://asciidoctor.org/docs/) as a documentation format and text processor
- [Lunr](https://lunrjs.com/) as an offline search engine.

## Local environment

1. Install Node.js
1. Install Antora and [Antora Site Generator With Lunr](https://github.com/Mogztter/antora-site-generator-lunr)
```shell
npm i -g @antora/cli antora-site-generator-lunr
```
3. Generate a site
```shell
DOCSEARCH_ENABLED=true DOCSEARCH_ENGINE=lunr DOCSEARCH_INDEX_VERSION=latest NODE_PATH="$(npm -g root)" antora --generator antora-site-generator-lunr antora-playbook-local.yml
```

*IMPORTANT*: the cloned `docs.vividus.dev` repository should be placed by default in the same folder as `vividus` repository (this behavior could be changed in the playbook).

### One liner
```shell
 npm i -g @antora/cli antora-site-generator-lunr && \  
 git clone https://github.com/vividus-framework/vividus.git && \   
 git clone https://github.com/vividus-framework/docs.vividus.dev.git && \   
 cd docs.vividus.dev && \
 DOCSEARCH_ENABLED=true DOCSEARCH_ENGINE=lunr DOCSEARCH_INDEX_VERSION=latest NODE_PATH="$(npm -g root)" antora --generator antora-site-generator-lunr antora-playbook-local.yml && \  
 open ./public/index.html
 ```
