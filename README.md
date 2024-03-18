<h1 align="center">Spell Checker</h1>

<p align="center">
 <a href="https://github.com/wow-actions/spell-checker/actions/workflows/release.yml"><img alt="build" src="https://img.shields.io/github/actions/workflow/status/wow-actions/spell-checker/release.yml?branch=master&logo=github&style=flat-square" ></a>
  <a href="/wow-actions/spell-checker/blob/master/LICENSE"><img alt="MIT License" src="https://img.shields.io/github/license/wow-actions/spell-checker?style=flat-square"></a>
  <a href="https://www.typescriptlang.org" rel="nofollow"><img alt="Language" src="https://img.shields.io/badge/language-TypeScript-blue.svg?style=flat-square"></a>
  <a href="https://github.com/wow-actions/spell-checker/pulls"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-Welcome-brightgreen.svg?style=flat-square" ></a>
  <a href="https://github.com/marketplace/actions/spell-checker" rel="nofollow"><img alt="website" src="https://img.shields.io/static/v1?label=&labelColor=505050&message=Marketplace&color=0076D6&style=flat-square&logo=google-chrome&logoColor=0076D6" ></a>
 
</p>

<p align="center">
  <strong>Check and Annotate files with spelling suggestions to help you write better.</strong>
</p>

## Usage

wong wat

Create a `.github/workflows/spell-checker.yml` file in the repository you want to install this action:

```yml
name: Spell Checker
on: push
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: wow-actions/spell-checker@v1
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          include: |
            **/*.md
            **/*.txt
```

### What it checks

A non-exhaustive list of the various checks that are run:

- Correct spelling (and provides possible corrections).
- Use of non-inclusive/profane/offensive language.
- Various prose-related checks, find the full list [here](https://github.com/btford/write-good#checks).

### Inputs

Various inputs are defined to let you configure the action:

> Note: [Workflow command and parameter names are not case-sensitive](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-commands-for-github-actions#about-workflow-commands).

| Name | Description | Default |
| --- | --- | --- |
| `GITHUB_TOKEN` | The GitHub token for authentication | N/A |
| `include` | File [patterns](https://www.npmjs.com/package/minimatch) to match files to check. | `[]` |
| `exclude` | File [patterns](https://www.npmjs.com/package/minimatch) to ignore files. | `[]` |
| `alex` | The options of [alex](https://www.npmjs.com/package/alex). Set `false` to disable it. | N/A |
| `write-good` | The options of [write-good](https://www.npmjs.com/package/write-good). Set `false` to disable it. | N/A |
| `markdown-spellcheck` | The options of [alex](https://www.npmjs.com/package/markdown-spellcheck). Set `false` to disable it. | N/A |

### Credits

This Action is mostly a wrapper around existing open source libraries. The majority of the work is done by those, and they deserve a ton of thanks:

- [alex](https://github.com/get-alex/alex)
- [write-good](https://github.com/btford/write-good)
- [node-spellchecker](https://github.com/atom/node-spellchecker)
- [node-markdown-spellcheck](https://github.com/lukeapage/node-markdown-spellcheck)

## License

The application code and associated documentation is under the [MIT License](LICENSE)
