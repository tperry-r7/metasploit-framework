# Framework Documentation Style Guide

Remember a style guide is a living document. It can change as the documentation evolves or we find better ways to do things. 

* [Framework Documentation Style Guide](#framework-documentation-style-guide)
  * [Inclusivity](#inclusivity)
  * [Language and tone](#language-and-tone)
  * [Colloquialisms, idioms, humor, and metaphor](#colloquialisms-idioms-humor-and-metaphor)
  * [Capitalization](#capitalization)
  * [Formatting](#formatting)
    * [Headers](#headers)
    * [Sentences](#sentences)
    * [Lists](#lists)
    * [Tables](#tables)
    * [When to use a list vs table](#when-to-use-a-list-vs-table)
    * [Code](#code)
    * [Markdown](#markdown)
  * [Text Format](#text-format)
    * [Bold Text](#bold-text)
    * [Spacing](#spacing)
    * [Italics](#italics)
  * [Links, URLs, and websites](#links-urls-and-websites)
  * [Punctuation](#punctuation)
    * [Dashes](#dashes)
      * [Hyphen](#hyphen)
      * [En Dash](#en-dash)
      * [Em Dash](#em-dash)
  * [Numbers](#numbers)
  * [Dates](#dates)
  * [Measurements](#measurements)
  * [Acronyms and abbreviations](#acronyms-and-abbreviations)
  * [Common Spellings](#common-spellings)
  * [Documentation types](#documentation-types)

The Framework documentation should be:

- **Clear** -  The documentation is easy to read. It’s concise, specific, and organized. It’s simple, not oversimplified, so readers can get the information they need without wasting time or effort.

- **Accessible and inclusive** - We strive to write for everyone. We make sure our content is for beginners to advanced readers. We avoid language that isolates or excludes others. We make sure our content is available to people with a diverse range of hearing, movement, sight, and cognitive abilities.

- **Correct** - Work hard to make sure the documentation you are writing is accurate. Others rely on your expertise, so provide the best information you have at the time. 

## Inclusivity

Avoid using language that isolates or excludes. For example, don’t reference a person’s age, disability, or gender unless it’s relevant. Here are some other guidelines to keep in mind.

**Do**

- If you need to mention a disability, ask whether the person or people being referenced prefer person-first language (“they have a disability”) or identity-first language (“they are disabled”).
- Use gender neutral language whenever possible.
- If you’re writing about a hypothetical person, use they or them instead of he/she. He/she is tedious to read and doesn’t account for people with non-binary gender identities.

**Don’t**

- Don’t refer to people using age-related descriptors like young, old, or elderly.
- When writing about a person with disabilities, don’t use the words suffer, victim, or handicapped.

## Language and tone

The documentation should be easy to read and understand. It should be  friendly and helpful. 

* Use active instead of passive voice when possible. [https://www.grammarly.com/blog/active-vs-passive-voice/](https://www.grammarly.com/blog/active-vs-passive-voice/)
* Use present tense. Assume the reader is doing the activity while reading the documentation. [https://en.wikipedia.org/wiki/Present_tense](https://en.wikipedia.org/wiki/Present_tense)
* Avoid the use of "may". Either they can or cannot do something. 
  * If they cannot add a troubleshooting section to lead them through errors. 
* Use second person, "you". It makes the documentation more personable. [https://www.grammarly.com/blog/first-second-and-third-person/](https://www.grammarly.com/blog/first-second-and-third-person/)

| Do | Don't|
|---|---|
| You can review our [Guidelines for Accepting Modules and Enhancements](https://github.com/rapid7/metasploit-framework/wiki/Guidelines-for-Accepting-Modules-and-Enhancements) to find out what we expect when we see pull requests for new Metasploit modules. | We should review the  [Guidelines for Accepting Modules and Enhancements](https://github.com/rapid7/metasploit-framework/wiki/Guidelines-for-Accepting-Modules-and-Enhancements) to find out what we expect when we see pull requests for new Metasploit modules.|
| You can use Metasploitable as a vulnerable target. | You may use Metasploitable as a vulnerable target. |


## Colloquialisms, idioms, humor, and metaphor

Slang, humor, regional phrases, and metaphor can be confusing, even to native speakers, and rarely translate well. Expressions like “under the hood” are not universally understood or appreciated, and it’s hard to find equivalent meanings in other languages. So it's usually best to avoid language with implied or regional meaning. That includes anthropomorphism, a type of metaphor that attributes human characteristics or behavior to non-humans.

| Do | Don't|
|---|---|
| Metasploit is based on Ruby. | Under the hood, Metasploit uses Ruby.|

## Capitalization

Use sentence case for:

* List lead-ins
* Table headings
* Page headings

Title case is reserved for page titles. 

| Do | Don't|
|---|---|
| `## Set up your local copy of the repository` | `# Set up your local copy of the repository` |

## Formatting

This section details how to format the markdown. 

### Headers

* Headers should be sequential. 
* Start a page at h2 `##`. Titles are rendered using an h1 and should not be used. 
* Headers use sentence-case.
* Enter a line break between a heading and its content.
* We use h2 `##`, h3 `###` and h4 `####`. 
* Try to only use bold in a sentence or for emphasis.
* Headings should be informative, concise, and scannable.
* Avoid empty headings
* Avoid gerunds in heading titles (-ing) [https://owl.purdue.edu/owl/general_writing/mechanics/gerunds_participles_and_infinitives/index.html](https://owl.purdue.edu/owl/general_writing/mechanics/gerunds_participles_and_infinitives/index.html)
* No need to add Metasploit Framework in the heading. They are already in the documentation. 

| Do | Don't|
|---|---|
|Create a LoginScanners | Creating Metasploit Framework LoginScanners |
How to use the Obfuscation CRandomizer| How to use Metasploit Framework Obfuscation CRandomizer |

### Sentences

* Try write more concise sentences. Avoid filler words like simply or just. 
* Keep sentences short. Less than 40 words is a good guide. 

### Lists

* Ordered list - Use an ordered list when describing a procedure or when a user needs to take an action before taking another, such as a tutorial. 
* Unordered list - Use unordered lists for definitions and when the order of the data doesn't matter.
* Capitalize the initial letter in each list item and use a period to end a list item only if the item is a complete sentence . 
* If using a list for definitions, then bold the definition.
* Use a lead in sentence for lists with a colon. 

**Do**

 ```
Before you begin: 
* You have installed an apt-based Linux environment, such as Ubuntu or Kali.
* You have created a GitHub account and associated an ssh key with it.
* You have familiarity with Git and Github, or have completed the Github bootcamp.
* For optional database and REST API functionality, you will need regular user account that is not root.
```

- **SSH** - Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. 


**Don't**

- SSH - Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. 


### Tables

In many contexts, tables are the best way to represent sets of related pieces of data. However, in some contexts, other approaches are better choices.

* Don’t add more than one paragraph in a table cell. 
* Use sentence case for table headings.
* Don't end table headings with punctuation, including a period, an ellipsis, or a colon.
* If you have only one column in your table, turn the table into a list.
* Don't use tables to lay out code snippets.
* Don't use tables to lay out long one-dimensional lists in multiple columns. 
* Add a lead-in sentence that explains the tables contents. 
* Keep table formatting simple. 
	* You can use more than 3 dashes, but they dashes need to be equal for all columns. 

**Do**

```
| Name | Description |
| ---|---|
| Value one | Description of value |
```

**Don't**

```
| Syntax | Description |
| --- | ----------- |
| Header | Title |
| Paragraph | Text |
```

### When to use a list vs table

`Pulled from https://developers.google.com/style/tables.`

Tables and lists are both ways to present a set of similarly structured items; sometimes it's not obvious when to choose one presentation over the other. To decide which presentation to use, consult the following table:

|Item type| Example | How to present |
|---|---|---|
| Each item is a single unit. |A list of programming language names, or a list of steps to follow. |Use a numbered list or bulleted list.|
| Each item is a pair of pieces of related data. | A list of term/definition pairs.| Use a definition list.|
| Each item is three or more pieces of related data. | A set of parameters, where each parameter has a name, a data type, and a description. | Use a table. |

### Code

Code should be executable. Don't abbreviate code examples. The reader should be able to copy and paste and use the sample with minimal effort. 

* When referring to code in a sentence use backticks. 
* If the code spans more than one line, use a code block. For example, functions will be a code block.
* Use code blocks for executable code.
  * Use common sense, if it's hard to read, move it to a new line. 
* Label each code block with the language.
* Placeholders should use brackets <>. 
* Don't use `foo`, `bar` or `foobar` for code. Use actual data or code.

**Do**

```
```python
def name():
  print("Metasploit")
name()
```

**Don't**

```
def name():
  print("Metasploit")
name()
```

### Markdown

If you haven't, install the Markdown Lint https://github.com/DavidAnson/markdownlint plugin for your text editor. See [Contributing to Framework documentation](#documentation/framework/contributing_framework_docs.md) for more on configuration. This is to make sure the markdown is easy to read and all the documentation is the same for anyone who wants to edit. 

## Text Format

### Bold Text

* Use bolded text to emphasize an important word or phrase or to create visual separation and callouts.
* Do not use italics. Use bold.
* Do not use underline. Use bold. 

### Spacing

* Use `<br>` if you need to add space between elements. 

### Italics

Do not use.

## Links, URLs, and websites

We discuss and direct people to online locations and resources a lot, so let's do it right.

* Use descriptive hypertext when linking between articles within Framework. Descriptive link text makes navigation easier and more efficient because it’s easier to skim and allows users to make informed decisions about whether to follow them. Using the article title is the easiest ways to do this.
* Use full links when redirecting to an external link. Make sure to reference the entire link. Do not embed like descriptive text.

| Do | Don't|
| ---|---|
| To learn more about Login Scanners, see `[Creating Metasploit Framework LoginScanners](#link)`. | To learn more about Login Scanners, click `[here](#link)`.
| If you are still confused about rebasing in Git, see https://git-scm.com/book/en/v2/Git-Branching-Rebasing. | Learn more about rebasing in [Git](https://git-scm.com/book/en/v2/Git-Branching-Rebasing). |


## Punctuation

* Limit semicolon usage. Try two simple sentences.
* Don't use end punctuation (e.g., periods or colons) in headings.
* Use periods at the end of list items if it is a sentence or completes a sentence.
* Use the Oxford (a.k.a. serial) comma. https://en.wikipedia.org/wiki/Serial_comma
* Use quotation marks ("") to indicate a direct, word-for-word quotation.
* See [Backticks](#backticks) for more on referring to files and variable names etc. 
* Do not use quotation marks for emphasis.
* Use a hyphen for compound words.
* Use question marks and exclamation points sparingly. 
* Don't use plurals in parenthesis. For example, module(s).

|Do| Don't  |
|--|--|
| short-term | short–term |
| modules | modules(s)|

### Dashes

There are three types of dashes, hyphen, en and em. Each has their uses. 

* [https://www.thepunctuationguide.com/hyphen.html](https://www.thepunctuationguide.com/hyphen.html)
* [https://www.thepunctuationguide.com/en-dash.html](https://www.thepunctuationguide.com/en-dash.html)
* [https://www.thepunctuationguide.com/em-dash.html](https://www.thepunctuationguide.com/em-dash.html)

You are free to use all three if you choose. Review the guides to make sure you are using them correctly. 

#### Hyphen

* **Windows:** Minus sign 
* **Linux /Mac:** Minus sign 

#### En Dash

* **Windows:** If you have a keypad, turn in numlock and use  Alt + 0150. You can also use the emoji keyboard.
* **Linux/Mac:** Option + minus 

#### Em Dash

* **Windows:** If you have a keypad, turn in numlock and use  Alt + 0151. You can also use the emoji keyboard.
* **Linux/Mac:** Shift + Option + Minus

## Numbers

Numerals attract the eye because they typically represent the facts readers want and are visually different from the words that populate the majority of the page. Using them enhances the scannability of web content because they provide points of visual fixation.

* Spell-out numbers when they don’t represent specific facts, for example, “There are thousands of modules.”
* Use an en dash ( – ), not a hyphen (-):
	* To form negative numbers. 
	* In a range of numbers such as versions. Try to avoid and, through and between.
* Use commas in numbers that have four or more digits.
* Use numerals when writing about a specific number, regardless of how big it is or where it appears in the sentence.
* Spell out ordinal numbers in text.
* Do not add -ly to ordinal numbers, as in firstly and secondly.
* Do not use ordinal numbers for dates.

|Do| Don't |
|--|--|
| 1,024 bytes | 1024 byes  |
| Ruby versions 2.0–2.5 (en dash) | Ruby versions 2.0-2.5 (hyphen) |
|Ruby versions 2.0–2.5 (en dash) | Ruby versions between 2.0 and 2.5 |
| There 250 pages of documentation.  |There are two-hundred and fifty pages of documentation.|
| –75 (en dash) | -75 (hyphen) |
| There are thousands of modules. | There are 1,000s of modules.|


## Dates

We use ISO 8601 https://www.iso.org/iso-8601-date-and-time-format.html for time and date formats. `YYYY-MM-DD-[hh]:[mm]:[ss]`. You can also use `Month-Day-Year`. The month should always be spelled out. 

Avoid abbreviating dates unless you need to save space, such as a table. 

If the date appears differently in the code sample, no need to change them to match this formatting. Just copy and paste as is. 

|Do| Don't  |
|--|--|
|  2019-09-04 |20190904  |
| September 4, 2019 | Sept 4, 2019 |

## Measurements

* Use numerals for all measurements instead of spelling-out the numbers.
* For 2 or more quantities, repeat the unit of measure.
* Add a space between the number and term. 

| Do | Don't  |
|--|--|
| 1 GB or 2 GB of disk space for each 10 GB of data |1 or 2 GB of disk space for each 10 GB  |

If it's not in this table, it needs to be spelled out. 

| Term | Accepted abbreviation |
|---|---|
| gigabits per second| Gbps |
| megabits per second	| Mbps |
| megabytes per second| MBps |	
| kilobytes| KB|
| megabytes| MB|
| gigabytes | GB |

## Acronyms and abbreviations

If using an acronym and it's not well known, write it out in the first use. For example, VS Code (Visual Studio Code). 

## Common Spellings

Below are common words and the accepted spelling. If a word is on this list, please use the accepted spelling. This list is subject to change.

* Metasploit 
* Rapid7
* Metasploit Pro
* Metasploit Framework
* module
* exploit
* Msfvenom or msfvenom
* Kali Linux
* Powershell
* Post exploitation


## Documentation types

To do:

- [ ] Tutorials
- [ ] Concept
- [ ] Reference and task based
- [ ] Create templates for each
- [ ] Provide links to the best examples of each