# Contributing to Framework documentation

Looking for module documentation? See [Module Docs](https://github.com/rapid7/metasploit-framework/wiki/Module-Documentation)
---

* [Contributing to Framework documentation](#contributing-to-framework-documentation)
  * [Looking for module documentation? See Module Docs](#looking-for-module-documentation-see-module-docs)
  * [To get started](#to-get-started)
  * [Plugins](#plugins)
    * [Markdown lint](#markdown-lint)
    * [Excluded rules](#excluded-rules)
    * [Vale](#vale)
      * [Install Vale](#install-vale)
      * [Vale commands](#vale-commands)
      * [Vale error levels](#vale-error-levels)
  * [All plugins](#all-plugins)
  * [Visual Studo Code (VS Code) workspace file](#visual-studo-code-vs-code-workspace-file)
  * [What's next](#whats-next)
  * [FAQ](#faq)
    * [I ran Vale but don't agree with the results](#i-ran-vale-but-dont-agree-with-the-results)

Thanks for wanting to contribute to the Framework documentation! Let's get setup. This setup is optional, but it will make your workflow much easier and cut down on errors. This includes adding a markdown formatter, which is enforced, and setting up the style guide.

## To get started

1. Review the [Framework Style Guide](/documentation/framework/framework_style_guide.md)
2. Review the [plugins](#plugins).
3. Install [Markdown lint](#markdown-lint) and [Vale](#vale)
4. Check the project for documentation ideas or just get started writing!

## Plugins

These plugins are recommended before writing Framework documentation. The two that are recommended are Markdown Lint and Vale.

### Markdown lint

Enforces markdown formatting rules for Framework documentation. You can review all the rules under Rules and Aliases, https://github.com/DavidAnson/markdownlint#rules--aliases. Some rules have been excluded. In case you're wondering what markdown that has been enforced looks like, this file is a good example. Of course if you need to ignore the rules to make what you are writing easier to read, that's fine too. But...follow the formatter rules. 

### Excluded rules

* "MD047": false,
* "MD034": false,
* "MD033": false,
* "MD009": false,
* "MD025": false,
* "MD041": false,
* "MD004": false

### Vale

Vale https://errata-ai.gitbook.io/vale/ is a prose style linter that can enforce a [style guide](documentation/framework/framework_style_guide.md) locally. There are two versions, you should be using the open source version. 

Vale is just a reminder. It does not know your intent or meaning by choosing a certain wording or phrase. If you think it adds to the understanding of the documentation, leave it it. Be ready to defend it if someone asks about it. 

* Framework already has a `.vale.ini` file and the style yaml files are in the `.github` folder. 
* Vale can be used using the command line or in a text editor terminal. https://errata-ai.gitbook.io/vale/getting-started/installation#using-vale-with-a-text-editor-or-another-third-party-application. 

#### Install Vale

1. Follow the instructions to install Vale here https://errata-ai.gitbook.io/vale/#installation. 
   1. If you prefer Vale also provides a Docker image. https://errata-ai.gitbook.io/vale/getting-started/installation#using-vale-from-the-command-line
2. Run Vale aganist a markdown file. `vale filePath/fileName`. Try this one `vale documentation/framework/contributing_framework_docs.md`. 
   1. There are intentional spelling and grammar errors. You'll also notice not every error is applicable. Vale is a tool and doesn't know intent. 
3. If you are using a text editor and the terminal in the text editor, you may need to restart the text editor after installing Vale.

#### Vale commands

* Test all markdown files (.md) in the current directory (.): `vale --glob='*.md' .`
* To test a single file: `vale filePath/fileName`

It's recommended to run Vale aganist your file after you are done writing it. 

#### Vale error levels

* **error** - You really shouldn't be doing that and should probably change it. 
* **warning** - This might be okay, but be prepared to defend it. 
* **suggestion** - This is okay as is. But following this rule could make it better.

## All plugins

This is a list of plugins that could help you write Framework documentation.

| Name | Function | Availibiity | Recommended |
| ---|---|---|---|
| Markdown Lint https://github.com/DavidAnson/markdownlint | Standardizes the markdown formatting | Most text editors | Yes |
| Markdown All in One https://github.com/yzhang-gh/vscode-markdown | Shortcuts for markdown | VS Code | No |
| Markdown Link Check https://github.com/tcort/markdown-link-check | Check if markdown and web links are valid. | Any system. Install locally | No |
| HTTP/s and relative link checker https://github.com/microsoft/linkcheckermd |  Check if markdown and web links are valid. | VS Code | No |
| Vale https://errata-ai.gitbook.io/vale/ | Compare articles aganist the style guide | Any system. Install locally | Yes |

## Visual Studo Code (VS Code) workspace file

Feel free to edit this file for how you like to work. The important configurations are `markdown.extension` and `markdownlint`. 

```json
{
  "folders": [
    {
      "path": "."
    }
  ],
  "settings": {
    "editor.formatOnSave": true,
    "editor.trimAutoWhitespace": true,
    "files.trimTrailingWhitespace": true,
    "workbench.editor.highlightModifiedTabs": true,
    "markdown.extension.completion.root": ".",
    "markdown.extension.toc.updateOnSave": false,
    "markdown.extension.toc.unorderedList.marker": "*",
    "[markdown]": {
      "editor.formatOnSave": false,
      "files.trimTrailingWhitespace": false
    },
    "editor.minimap.enabled": false,
    "editor.tabSize": 2,
    "markdownlint.config": {
      "MD047": false,
      "MD034": false,
      "MD033": false,
      "MD009": false,
      "MD025": false,
      "MD041": false,
      "MD004": false,
    }
  },
  "extensions": {
    "recommendations": [
      "yzhang.markdown-all-in-one",
      "DavidAnson.vscode-markdownlint",
      "blackmist.LinkCheckMD"
    ]
  }
}
```

## What's next

* Review the [style guide](/documentation/framework/framework_style_guide.md)
* See the project for documentation needs.

## FAQ

### I ran Vale but don't agree with the results

Vale checks aganist the style guide. It's not aware of intent. Submit a PR so it can be reviwed.