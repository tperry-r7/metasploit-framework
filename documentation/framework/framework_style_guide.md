# Framework Documentation Style Guide

To do:
[ ] - Add content type examples
[ ] - Add a debugging or troubleshooting?
[ ] - Define what a recipe or how to is for quick examples?
 
Remember a style guide is a living document. It can change as the documentation evolves or we find better ways to do things. 

## On this page
* [Framework Documentation Style Guide](#framework-documentation-style-guide)
  * [On this page](#on-this-page)
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
  * [Callouts](#callouts)
    * [Critical](#critical)
    * [Success](#success)
    * [Caution](#caution)
    * [Good to know](#good-to-know)
  * [Numbers](#numbers)
  * [Dates](#dates)
  * [Measurements](#measurements)
  * [Acronyms and abbreviations](#acronyms-and-abbreviations)
  * [Common Spellings](#common-spellings)
  * [Page elements](#page-elements)
    * [Title](#title)
      * [Title do](#title-do)
      * [Title don't](#title-dont)
    * [Introductions](#introductions)
      * [Introductions do](#introductions-do)
      * [Introductions don't](#introductions-dont)
    * [Requirements](#requirements)
    * [Page headings](#page-headings)
      * [Page headings do](#page-headings-do)
      * [Page headings don't](#page-headings-dont)
    * [Paragraphs](#paragraphs)
      * [Paragraphs do](#paragraphs-do)
      * [Paragraphs don’t](#paragraphs-dont)
    * [Steps](#steps)
      * [Steps do](#steps-do)
    * [Best practices](#best-practices)
    * [What's next](#whats-next)
      * [What's next do](#whats-next-do)
      * [What's next don't](#whats-next-dont)
  * [Documentation templates](#documentation-templates)
    * [Concepts and explanations](#concepts-and-explanations)
      * [Concepts do](#concepts-do)
    * [Procedural / Tutorial](#procedural--tutorial)
      * [Procedural do](#procedural-do)
    * [Reference](#reference)
      * [Reference DO](#reference-do)
    * [General Template](#general-template)

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

## Callouts

If you want to emphasize additional or important information, you can use a callout.

* All callouts include a descriptive title using sentance case.

### Critical


```
> **Critical**
> Title, keep it short, but descriptive
> Use it to provide critical warnings concerning potential data loss or program breaking.
```

### Success

```
> **Success**
> Title, keep it short, but descriptive
> Used to describe the results of successful task completion.
```

### Caution

```
> **Caution**
> Title, keep it short, but descriptive
> Used to suggest caution to avoid potential issues.
```

### Good to know

```
> **Good to know**
> Title, keep it short, but descriptive
> Used to highlight helpful information or neat features, or to make recommendations or provide best practices. If you have a long list of best practices, it's better to move them to a heading instead. 
```

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

## Page elements

Learn about the standards and guidelines for each common help page element.

### Title

Titles help people decide which content to access. 

#### Title do

* Use title case.
* Create a unique title for each page
* Write action-oriented titles for procedural content, starting with the most powerful and accurate verb you can muster. 
* Write descriptive titles for conceptual and reference content using noun phrases. 
* Keep titles as short as possible while ensuring they accurately represent the content available in the article. Aim for 5 words or less.

#### Title don't

* Don’t use gerunds (-ing words). Titles with gerunds sound action-oriented, but they are less direct because they lack an implied subject.
* Avoid generic and ambiguous words and phrases. Take “quickstart guide” as an example--does this article or series of articles contain deployment and installation information, basic concepts and procedural information for ramping-up new readers, or both? We shouldn’t make our readers guess, and they shouldn’t be surprised by what they find.

### Introductions

Introductions help users understand the content on a page by answering 2 questions:

* What’s on this page?
* Why should I read it?

While introductions are helpful, we know people read very little on web pages, so we can’t waste words. Ruthlessly edit your introductions to encourage users to read them and to save space for more priority content.

#### Introductions do

* Make introductions just long enough to explain the topic of the article and why the information is valuable. 

#### Introductions don't

* Introductions don’t need headings like “Overview.” Their nature and location on a page provide enough context, so headings are excessive.

### Requirements

If the reader needs to have or do anything before making use of the information on this page, call it out immediately after the introduction in a section with a heading called “Requirements”.

Include:

* hardware
* software
* previous steps

### Page headings

Headings are important because they visually signal a page’s underlying structure.

#### Page headings do

* Be descriptive. Users should know what to expect within a particular section based on the header. Think of a heading as a summary. If someone just read the headings on the page, they should get the gist of the content available on it.
* Write action-oriented headings for procedural content and descriptive headings for conceptual or reference content.
* Nest headings logically. Be sure that content within each section maps to other content on the page as indicated by headings. For example, content under an H2 should be less important or in some way subordinate to the content under the associated H1.

#### Page headings don't

* Don’t use gerunds (-ing words). Gerunds sound action-oriented, but they are less direct because they lack an implied subject.
* Don’t skip heading levels. Putting an H3 under an H1 instead of H2, for example, may be tempting from a visual perspective. But skipping heading levels can leave the impression that content is missing, which causes confusion.
* Don’t leave headings empty or have headings with no associated content.

### Paragraphs

Paragraphs are logical groupings of related ideas. They help us segment information on a page, which improves scannability.

#### Paragraphs do

Start paragraphs with a topic sentence, which expresses the main idea. With the main idea at the beginning of the paragraph, readers are more likely to find and get the information they need as they scan and forage.
Try to keep paragraphs short, 3-5 sentences, to maximize segmentation and improve scannability.

#### Paragraphs don’t

We don’t use indentations to delimit paragraphs. Instead, line breaks, images, headings, and other objects help us distinguish between separate paragraphs on the page.

### Steps

Steps appear in procedural content and instruct users about how to complete a task.

#### Steps do

* Use a numbered list because steps are sequential--the order matters.
* Each step should be its own list item. The exception to this guideline is for series of steps that happen in quick succession and in the same location on the page. In that situation, you can use a navigational path to summarize. **Settings > User > Email.**
* If you need to direct the reader to a location on the interface within a step, do that first and follow the direction with the action they need to take.
* Bold navigational paths and the interface elements you direct users to interact with.
* Label interface elements using the formula label + element. This enhances the user’s ability to connect your instructions to the interface.

### Best practices

Best practices are actions we recommend to users in our documentation. 
Best practices preempt issues and promote the “happy path”--the best possible use of the application. Instead of living in a separate category of documentation, best practices should be interwoven within our content so our readers have the best chance of finding and using that information to their advantage. 

### What's next

This gives us the chance to lead users to the next step in a chronological sequence, or to encourage a bit of helpful browsing. 

#### What's next do

* Create links to additional resources using article titles as hypertext.
* If you link to multiple resources within the “What’s next?” section, order them from most to least relevant.

#### What's next don't

* Don’t include the “What’s next?” section for the sake of having it. It’s not a requisite component on any given page. If there is no other directly related content to link to, leave it out.

## Documentation types

These are the most common documention types along with basic templates and some helpful hints for writing.

| Name | Description | Resources |
|---|---|---|
| Conceptual article | Use this type when your readers need to know or understand something. Conceptual articles explain abstract ideas or convey general knowledge. Concept pages help lay the groundwork for, and usually includes links to, other types of content. May contain use cases and best practices. | [Guidelines](#concepts-and-explanations) and Examples |
| Procedural / Tutorial | Use this type when your readers need to do something. Procedural articles provide information needed to perform a task. They should build on and link to supporting conceptual and reference content.  May contain use cases, best practices, and troubleshooting. | [Guidelines](#procedural--tutorial) and Examples |
| Reference article | Use this type when your readers need to check or interpret something. Reference articles provide definitions or simple, fact-driven coverage of a topic. Examples include glossaries and data tables. | [Guidelines](#reference) and Examples |

### Concepts and explanations

Explanation, or discussions, clarify and illuminate a particular topic. They broaden the documentation’s coverage of a topic. They can also explain why things are so - design decisions, historical reasons, technical constraints.  It’s not the place of an explanation to instruct the user in how to do something. 

Metasploit has a lot of concepts related specifically to Metasploit. Take care to use plain language. The user you are writing for has security experience, may not use English as their first language and they need to know how Metasploit works. 

#### Concepts do

* Organize conceptual content hierarchically, starting with the most important information.
* Conceptual content can be dense, so segment information into logical groupings with descriptive headings to improve scannability.
* Link to complementary procedural or reference content on other pages where appropriate.

### Procedural / Tutorial

Procedural content provides information needed to perform a task. It’s inherently task-oriented and it should often build on and link to supporting conceptual and reference content.

#### Procedural do

* Procedural content is chronological by nature, so use ordered lists.
* Provide context. Explain, at least briefly, the why behind the how. 
* Segment longer procedures into a series of shorter ones to improve scannability and reduce the potential for readers to be overwhelmed by too many steps. 
* Group related procedures together. 
* Write task-oriented article titles. There’s no need to write “How to,” but task-oriented titles help readers anticipate what type of information can be found on the page as well as how it applies to them and their work.
* Use descriptive headings to improve scannability and help readers understand how procedures are related to each other and broader objectives.
* Stay focused. If conceptual or reference information is needed to support a procedure, summarize it and link to related pages where readers can find more information instead of combining content types on a single page.


### Reference

Reference content provides definitions or simple, fact-driven coverage of a topic. Examples include glossaries, data tables and API definitions. Reference content is typically designed to help readers interpret content in other help docs or in the product interface.

#### Reference DO

* Cross-reference other pages to provide additional details and contextualized help.
* Keep reference content focused and lean.
* Organize content in a highly predictable and perceptible way. Reference content is typically dense, so use alphabetical order or something similar to promote easy retrieval.

## General Template

```

---
title: Page title
version: [] //Metasploit versions this applies to.
---

# On this page
//generate a table of contents here. If there is only one element on the page, you can skip this. See this pages toc as an example of a toc. 

After your table of contents, you’ll have an introduction that helps users understand what’s on the page and why they should read it--keep it brief while providing some context. 

## Requirements

If the reader needs to have or do anything before making use of the information on this page, call it out immediately after the introduction in a section with a heading called “Requirements”. 

## Page heading

Headings are important because they visually signal a page’s underlying structure, and that helps readers forage for information and scan. Make sure your headings are succinct, descriptive, as action-oriented as possible, and parallel, meaning they all reflect the same grammatical structure. Avoid using gerunds (-ing words). See additional heading guidelines.

Use paragraphs within each section to logical groups of related ideas and prevent the dreaded wall of text. See additional paragraph guidelines. You can also prevent text overload by linking to relevant pages instead of summarizing or restating the information found in those other resources. See additional link guidelines.

Include images to help illustrate your content, especially if you’re documenting a complex task. 

### Page subheading

You may have topics nested within larger topics and will therefore need to use subheadings to organize your content. Heading rules apply to subheadings, just be sure your subheadings relate obviously and naturally to the headings they’re nested under.

You may want to use a bulleted list to organize non-sequential yet related items into an easy-to-read group. If so, here’s how you do it.

**Write a complete sentence lead-in in bold text, and follow these other rules:** 

* Capitalize the first letter of each item.
* Use a period only if the item is a complete sentence.

If you want to emphasize additional or important information, you can use a callout. All callouts include a descriptive heading. 


## What’s next?

* Link to related article
* Link to related article
* Link to related article
```
