# Logos Homepage Template

The template repository for homepage using [logos-docusaurus-plugins](https://github.com/acid-info/logos-docusaurus-plugins).


## Use cases
- [nomos.tech](https://nomos.tech/)
- [waku.org](https://waku.org/)
- [nomos.tech](https://nomos.tech/)
- [codex.storage](https://codex.storage/)


## How to Run Locally

1. Clone this repository
```bash
$ git clone https://github.com/acid-info/logos-homepage-template.git
```

2. Install the dependencies:
```bash
$ yarn install
```

3. Start the website:
```bash
$ yarn start
```

4. Visit `http://localhost:3000` in your browser


## Configuration
Edit the `docusaurus.config.js` file in the repository's root directory, and update the value of the `businessUnit` field in presets section; below is a list of valid values:
- Logos
- Codex
- Waku
- Nimbus
- Nomos
- VacResearch
- Acid.info

Example:
```js
presets: [
  [
    '@acid-info/logos-docusaurus-preset',
    {
      businessUnit: 'Codex',
    },
  ],
],
```

This is typically sufficient for most cases, as the Logos plugins will automatically populate other configurations related to the specified business unit. If you encounter any errors in the information provided by Logos Plugins, please visit the [Logos Docusaurus Plugins](https://github.com/acid-info/logos-docusaurus-plugins) repository and open an issue.


## Landing page

The code for a landing page is located in `src/pages/index.mdx`. This file employs the `mdx` format and utilizes React components from the [Logos Docusaurus Plugins](https://github.com/acid-info/logos-docusaurus-plugins/tree/main/packages/logos-docusaurus-theme/src/client/components/mdx) package.


## Adding subpages

To include subpages (e.g., https://nomos.tech/about/architect), create a `.md` or `mdx` file within the `about` directory. You can use [Frontmatter](https://docusaurus.io/docs/markdown-features#front-matter) to add metadata to your markdown file.

The content in `about/index.md` will be utilized as the index page for the `/about` section.


## Root pages

Subpages that do not belong to the `About` page (e.g., [Terms of Use](https://nomos.tech/terms)) can be situated in the `root-pages` directory.


## Customization

You can find instructions for adding additional documentation sections, implementing localization, and managing versioning on the [Docusaurus](https://docusaurus.io/docs) website.

> Please note that theme customization is somewhat restricted; for more detailed instructions on customizing your theme, visit the [Logos Docusaurus Theme](https://github.com/acid-info/logos-docusaurus-plugins/tree/main/packages/logos-docusaurus-theme/) repository.


## CI/CD

- The `master` branch is automatically deployed to the production server (e.g., logos.co) through [CI](https://ci.infra.status.im)
- The `develop` branch is automatically deployed to the staging server (e.g., dev.logos.co) through [CI](https://ci.infra.status.im)


## Change Process

1. Create a new working branch from `develop`: `git checkout develop; git checkout -b my-changes`.
2. Make your changes, push them to the `origin`, and open a Pull Request against the `develop` branch.
3. After approval, merge the pull request, and verify the changes on the staging server (e.g., https://dev.vac.dev).
4. When ready to promote changes to the live website, rebase the `master` branch on the staging changes: `git checkout master; git pull origin master; git rebase origin/develop; git push`.
