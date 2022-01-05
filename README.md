# Stijn Callebaut's Resume

This repository contains my resume.

The resume is maintained in a JSON file, using the [JSONResume](https://jsonresume.org/) schema.

JSONResume is the open source initiative to create a JSON-based standard for resumes.

## Creating your own resume

The easiest way to get started is using the JSONResume CLI.

 ``` javascript

 npm install -g resume-cli 
 
 ```

After installation, just use `resume init` to generate your resume.json.
Answer any prompts and a started file with fake data.

All that rests, is installing a theme when used in combination with export. For example the following command installs the flat theme.
More info on [jsonresume themes](https://jsonresume.org/themes/) can be found on their website.

``` javascript

npm install jsonresume-theme-flat

```

## Handy vsCode tasks

The repo comes with some handy vscode tasks preconfigured for your convenience.

- __validate__, to validate your resume against the jsonresume schema
- __export__, to export to html or pdf
- __serve__, to serve your resume locally

> For more info about vscode tasks, check the [documentation](https://code.visualstudio.com/docs/editor/tasks) online.

## To do

 Below you can find my to-do list to keep enriching my resume and Github repo.

- [x] create basic json resume
  - [x] add basics
  - [x] add work
  - [x] add education
  - [x] add languages
- [ ] enrich resume
  - [ ] add past presentations as projects
  - [ ] add interests (? maybe - as duplicate on site and profiles)
- [ ] Enhance developer experience
  - [x] create devcontainer
    - [x] support json and markdown
    - [x] jsonresume cli
    - [x] useful extensions
  - [x] add workflow
    - [x] add test job using resume cli
    - [x] add release job using semantic release
    - [x] add dependabot for actions

## Dev container setup

As a base dockerfile javascript-node 16, bullseye is used from the [vscode devcontainer repo](https://github.com/microsoft/vscode-dev-containers/tree/main/containers/javascript-node).
The development container also contains the following elements:

- npm packages:
  - resume-cli
- extenstions:
  - "dbaeumer.vscode-eslint"
  - "jsonresume.vscode-jsonresume"
  - "yzhang.markdown-all-in-one"
  - "bierner.github-markdown-preview"
  - "streetsidesoftware.code-spell-checker"
  - "davidanson.vscode-markdownlint"
  - "shd101wyy.markdown-preview-enhanced"
  - "mohsen1.prettify-json"

> As my main machine is a Apple M1 a dirty workaround is needed. The [resume-cli Github issue #590](https://github.com/jsonresume/resume-cli/issues/590) has all info needed.

For reference:

``` dockerfile

ENV PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=1
ENV PUPPETEER_EXECUTABLE_PATH=/usr/bin/chromium-browser
ENV RESUME_PUPPETEER_NO_SANDBOX=1
RUN npm install -g resume-cli --unsafe-perm=true --allow-root
RUN npm install jsonresume-theme-even
RUN ln /usr/bin/chromium /usr/bin/chromium-browser

```
