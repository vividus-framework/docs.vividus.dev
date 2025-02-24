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
    npm i -g @antora/cli@3.1.10 @antora/site-generator@3.1.10 @antora/lunr-extension@1.0.0-alpha.10
    ```
1. Install and configure an Asciidoctor.js extension that adds a tabs block to the AsciiDoc syntax.
    ```shell
    npm i @asciidoctor/tabs@1.0.0-beta.6
    ln -s "$(pwd)/node_modules/@asciidoctor/tabs/dist/js/tabs.js" supplemental-ui/js/vendor/tabs.js
    ln -s "$(pwd)/node_modules/@asciidoctor/tabs/dist/css/tabs.css" supplemental-ui/css/vendor/tabs.css
    ```
1. Generate a site
    ```shell
    antora antora-playbook-local.yml
    ```

*IMPORTANT*: the cloned `docs.vividus.dev` repository should be placed by default in the same folder as `vividus` repository (this behavior could be changed in the playbook).

### One liner
```shell
 npm i -g @antora/cli@3.1.10 @antora/site-generator@3.1.10 @antora/lunr-extension@1.0.0-alpha.10 && \
 git clone https://github.com/vividus-framework/vividus.git && \   
 git clone https://github.com/vividus-framework/docs.vividus.dev.git && \   
 cd docs.vividus.dev && \
 npm i @asciidoctor/tabs@1.0.0-beta.6 && \
 ln -s "$(pwd)/node_modules/@asciidoctor/tabs/dist/js/tabs.js" supplemental-ui/js/vendor/tabs.js && \
 ln -s "$(pwd)/node_modules/@asciidoctor/tabs/dist/css/tabs.css" supplemental-ui/css/vendor/tabs.css && \
 antora antora-playbook-local.yml && \  
 open ./public/index.html
 ```

### PDF Generation
1. Install Asciidoctor PDF
    ```shell
    gem install asciidoctor-pdf
    ```
1. Install the [Antora PDF Extension](https://gitlab.com/antora/antora-assembler/)
    ```shell
    npm i -g @antora/pdf-extension
    ```
1. Generate a PDF document
    ```shell
    antora --extension @antora/pdf-extension antora-playbook-local.yml
    ```
