# VIVIDUS documentation

This is a playbook repo. It's purpose is to keep the way we deploy VIVIDUS documentation and UI customizations.
We use
- [Antora](https://docs.antora.org/) as a static site generator
- [Asciidoctor](https://asciidoctor.org/docs/) as a documentation format and text processor
- [Lunr](https://lunrjs.com/) as an offline search engine.

## Local environment

1. Install Node.js
1. Install Antora and [Antora Lunr Extension](https://gitlab.com/antora/antora-lunr-extension)
```shell
npm i -g @antora/cli@3.1.1 @antora/site-generator@3.1.1 @antora/lunr-extension@1.0.0-alpha.8
```
3. Generate a site
```shell
antora antora-playbook-local.yml
```

*IMPORTANT*: the cloned `docs.vividus.dev` repository should be placed by default in the same folder as `vividus` repository (this behavior could be changed in the playbook).

### One liner
```shell
 npm i -g @antora/cli@3.1.1 @antora/site-generator@3.1.1 @antora/lunr-extension@1.0.0-alpha.8 && \
 git clone https://github.com/vividus-framework/vividus.git && \   
 git clone https://github.com/vividus-framework/docs.vividus.dev.git && \   
 cd docs.vividus.dev && \
 antora antora-playbook-local.yml && \  
 open ./public/index.html
 ```
