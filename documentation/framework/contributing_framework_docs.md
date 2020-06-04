# Contributing to Framework documentation

Looking for module documentation? See [Module Docs](https://github.com/rapid7/metasploit-framework/wiki/Generating-Module-Documentation)

---

Thanks for wanting to contribute to the Framework documentation! Let's get setup. This setup is optional, but it will make your workflow much easier and cut down on errors. This includes adding a markdown formatter and setting up the style guide.

We do enforce formatting on the Markdown files. This is make them easier to quickly read and edit. 

## To get started

1. Review the Framework Style Guide
2. Review the plugins.
3. Install Markdown lint and Vale
4. Check the project for documentation ideas or just get started writing!

## Plugins

These plugins are recommended before writing Framework documentation. The two that are recommended are Markdown Lint and Vale.

### Markdown lint

Enforces markdown formatting rules for Framework documentation. You can review all the rules under Rules and Aliases, https://github.com/DavidAnson/markdownlint#rules--aliases. Some rules have been modified or excluded. 

### Modified rules Markdown lint

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
* After installing Vale, you may need to restart your text editor. 

#### Vale commands

* Test all markdown files (.md) in the current directory (.): `vale --glob='*.md' .`
* To test a single file: `vale filePath/fileName`

It's recommended to run Vale aganist your file after you are done writing it. 

#### Vale error levels

* **error** - You really shouldn't be doing that and should probably change it. 
* **warning** - This might be okay, but be prepared to defend it. 
* **suggestion** - This is okay as is. But following this rule could make it better.

### All plugins

| Name | Function | Availibiity | Recommended |
| ---|---|---|---|
| Markdown Lint https://github.com/DavidAnson/markdownlint | Standardizes the markdown formatting | Most text editors | Yes |
| Markdown All in One https://github.com/yzhang-gh/vscode-markdown | Shortcuts for markdown | VS Code | No |
| Markdown Link Check https://github.com/tcort/markdown-link-check | Check if markdown and web links are valid. | Any system. Install locally | No |
| HTTP/s and relative link checker https://github.com/microsoft/linkcheckermd |  Check if markdown and web links are valid. | VS Code | No |
| Vale https://errata-ai.gitbook.io/vale/ | Compare articles aganist the style guide | Any system. Install locally | Yes |


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