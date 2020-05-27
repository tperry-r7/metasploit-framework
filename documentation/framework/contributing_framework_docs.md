# Contributing to Framework documentation

Looking for module documentation? See [Module Docs](#link)

---

Thanks for wanting to contribute to the Framework documentation! Let's get setup. This setup is optional, but it will make your PR's more likely to be approved. 

## Setup

1. Download the plugins. You should install any required plugins.
2. Install Vale

### Download Plugins

After installing Markdown Lint, update your configuration to match `markdownlint.config` in the VS Code workspace file. 

| Name | Function | Availibiity | Required |
| ---|---|---|---|
| Markdown Lint https://github.com/DavidAnson/markdownlint | Standardizes the markdown formatting | Most text editors | Yes |
| Markdown All in One https://github.com/yzhang-gh/vscode-markdown | Shortcuts for markdown | VS Code | No |
| Markdown Link Check https://github.com/tcort/markdown-link-check | Check if markdown and web links are valid. | Any system. Install locally | No |
| HTTP/s and relative link checker https://github.com/microsoft/linkcheckermd |  Check if markdown and web links are valid. | VS Code | No |

#### Visual Studo Code (VS Code) workspace file

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
      "MD004": { "style": "asterisk"},
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

### Install Vale

Vale https://errata-ai.gitbook.io/vale/ is a prose style linter that can enforce a style guide locally. There are two versions, you should be using the open source version. 

Vale is just a reminder. It does not know your intent or meaning by choosing a certain wording or phrase. If you think it adds to the understanding of the documentation, leave it it. Be ready to defend it if someone asks about it. 

* Framework already has a `.vale.ini` file and the style yaml files are in the `.github` folder. 
* After installing Vale, you may need to restart your text editor. 

#### Vale commands

* Test all markdown files (.md) in the current directory (.): `vale --glob='*.md' .`
* To test a single file: `vale filePath/fileName`

It's recommended to run Vale aganist your file after you are done writing it. 

#### Vale error levels

* **error** - You really shouldn't be doing that and should probably change it. 
* **warning** - This might be okay, but be prepared to defend it. 
* **suggestion** - This is okay as is. But following this rule could make it better.

## What's next

* Review the [style guide](/documentation/framework/framework_style_guide.md)
* See the project for documentation needs.
