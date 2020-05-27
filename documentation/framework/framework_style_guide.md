---
title: "Framework Documentation Style Guide"
description: 
---
Remember a style guide is a living document. It can change as the documentation evolves or we find better ways to do things. 

- [Inclusivity](#inclusivity)
- [Colloquialisms, idioms, humor, and metaphor](#colloquialisms-idioms-humor-and-metaphor)
- [Documentation Types](#documentation-types)
- [Capitalization](#capitalization)
- [Headers](#headers)
- [When to use a list vs table](#when-to-use-a-list-vs-table)
- [Tables](#tables)
- [Lists](#lists)
- [Code](#code)
- [Examples](#examples)
- [Text Format](#text-format)
- [Links, URLs, and websites](#links-urls-and-websites)
- [Punctiation](#punctiation)
- [Numbers](#numbers)
- [Dates](#dates)
- [Measurements](#measurements)
- [Common Spellings](#common-spellings)

The Framework documentation should be:

- **Clear** -  The documentation is easy to read. It’s concise, specific, and organized. And it’s simple, not oversimplified, so readers can get the information they need without wasting time or effort.

- **Accessible and inclusive** - We strive to write for everyone. We make sure our content is for beginners to advanced readers. We avoid language that isolates or excludes others. And we make sure our content is available to people with a diverse range of hearing, movement, sight, and cognitive abilities.

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

## Colloquialisms, idioms, humor, and metaphor

Slang, humor, regional phrases, and metaphor can be confusing, even to native speakers, and rarely translate well. Expressions like “an app portfolio is a complex beast” are not universally understood or appreciated, and it’s hard to find equivalent meanings in other languages. So it's usually best to avoid language with implied or regional meaning. That includes anthropomorphism, a type of metaphor that attributes human characteristics or behavior to non-humans.

## Language

This is a list of guidlines that can help make the documentation easy to scan and parse. 

- Try write more consise sentances. Avoid filler words like simply or just. 
- Don't use plurals in parenthesis. For example, module(s)
- Keep sentences short. Less than 40 words is a good guide. 
- Don't use foo, bar or foobar for code. Use actual data.
- Use question marks and exclamation points sparingly. 
- Spell out words if they are unfamiliar to the audience. 

## Documentation Types

To do:

- [ ] Tutorials
- [ ] Concept
- [ ] Reference and task based
- [ ] Create templates for each
- [ ] Provide links to the best examples of each

## Capitalization

Use sentence case for:

- List lead-ins
- Table headings
- Page headings

Title case is reserved for page titles. 

## Headers

- Headers should be sequential. 
- Start a page at h2 `##`. Titles are rendered using an h1 and should not be used. 
- Headers use sentence-case.
- Enter a line break between a heading and its content.
- We use h2 `##`, h3 `###` and h4 `####`. Use caution with h4 since they often look bold. 
- Be informative and descriptive
- Concise and scannable
- Avoid empty headings

## When to use a list vs table

`Pulled from https://developers.google.com/style/tables.`

Tables and lists are both ways to present a set of similarly structured items; sometimes it's not obvious when to choose one presentation over the other. To decide which presentation to use, consult the following table:

|Item type| Example | How to present |
|---|---|---|
| Each item is a single unit. |A list of programming language names, or a list of steps to follow. |
| Each item is a pair of pieces of related data. | A list of term/definition pairs.| Use a description list.|
| Each item is three or more pieces of related data. | A set of parameters, where each parameter has a name, a data type, and a description. | Use a table. |

## Tables

In many contexts, tables are the best way to represent sets of related pieces of data. However, in some contexts, other approaches are better choices.

* Don’t add more than one paragraph in a table cell. 
* Use sentence case for table headings.
* Don't end table headings with punctuation, including a period, an ellipsis, or a colon.
* If you have only one column in your table, turn the table into a list.
* Don't use tables to lay out code snippets.
* Don't use tables to lay out long one-dimensional lists in multiple columns. For example, if you have a long list of function names, don't try to save space by splitting the list in half and presenting the two halves as a two-column table. Use tables only to present two-dimensional data—that is, material that semantically makes sense to display in rows and columns.
* Add a lead-in sentace that explains the tables contents. 

## Lists

Use ordered list when describing a procedure or when a user needs to take an action before taking another, such as a tutorial. Use unordered lists for defintions and when the order of the data doesn't matter.

- Capitalize the initial letter in each list item and use a period to end a list item only if the item is a complete sentence  
- If using a list for defintions, then bold the definition.
- Use a lead in sentence for lists with a colon. 

**Do**

Unordered list example:

Before you begin: 

- You have installed an apt-based Linux environment, such as Ubuntu or Kali.
- You have created a GitHub account and associated an ssh key with it.
- You have familiarity with Git and Github, or have completed the Github bootcamp.
- For optional database and REST API functionality, you will need regular user account that is not root.

Definition list example:

- **SSH** - Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. 

**Don't**

- SSH - Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. 

## Code

Code should be executable. Don't abbreviate code examples. They reader should be able to copy and paste and use the sample with minimal effort. 

- When referring to code in a sentence use backticks. 
- If the code spans more than one line, use a code block. For example, functions will be a code block.
- Use code blocks for executable code.
  - Use common sense, if it's hard to read, move it to a new line. 
- Label each code block with the language.
- Placeholders should use brackets <>. 

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

## Examples

* Introductory information should be provided if some context is needed to orient the user and can also be used to introduce code blocks.  
* All code examples should have a title. The title should start with a verb and should describe the task the example is outlining. It should use sentance case.

**Do**

Lead in:

If you want to get the raw HTTP response (including the response message/code, headers, body, etc), then you can use:

```ruby
res = send_request_cgi({'uri'=>'/index.php'})
```


Title:

Grabbing an element from a specific element tree.

```ruby
html = res.get_html_document
greeting = html.at('div//div')
```

## Text Format

- Use bolded text to emphasize an important word or phrase or to create visual separation and callouts.
- Do not use italics. Use bold.
- Do not use underline. Use bold. 
- Use quotation marks ("") to indicate a direct, word-for-word quotation.
- See [Backticks](#backticks) for more on referring to files and variable names etc. 

## Links, URLs, and websites

We discuss and direct people to online locations and resources a lot, so let's do it right.

* Use descriptive hypertext when linking between articles. Descriptive link text makes navigation easier and more efficient because it’s easier to skim and allows users to make informed decisions about whether to follow them. Using the article title is the easiest ways to do this. 
* Use full links when directing to an external link. Make sure to reference the entire link. Do not embed like descriptive text.

**Do**

* To learn more about Login Scanners, see `[Creating Metasploit Framework LoginScanners](#link)`. 
* * If you are still confused about rebasing in Git, see https://git-scm.com/book/en/v2/Git-Branching-Rebasing. 

**Don't**

* To learn more about Login Scanners, click `[here](#link)`.
* Learn more about rebasing in [Git](https://git-scm.com/book/en/v2/Git-Branching-Rebasing). 



## Punctiation

* Limit semicolon usage. Instead, try two simple sentences.
* Don't use end punctuation (e.g., periods or colons) in headings.
* Use periods at the end of list items if it is a sentence or completes a sentence.
* Use the [Oxford (a.k.a. serial) comma](https://en.wikipedia.org/wiki/Serial_comma).

## Numbers

Numerals attract the eye because they typically represent the facts readers want and are visually different from the words that populate the majority of the page. Using them enhances the scannability of web content because they provide points of visual fixation.

* Spell-out numbers when they don’t represent specific facts, for example, “There are thousands of modules.”
* Use an en dash, not a hyphen, to form negative numbers. Hyphens are small and easy to miss. 
* Use commas in numbers that have four or more digits.
* Use numerals when writing about a specific number, regardless of how big it is or where it appears in the sentence.
* Spell out ordinal numbers in text.
* Do not add -ly to ordinal numbers, as in firstly and secondly.
* Do not use ordinal numbers for dates.
* Use an en dash in a range of numbers. Try to avoid between and through. 

**Do**

* 1,024 bytes
* 1,093 pages
* We support Java versions 7–11
* Ruby versions 2.0–2.5
* There 250 pages of documentation. 
* –75
* There are thousands of modules.

**Don't**

* We support Java versions from 7-11.
* Ruby versions between 2.0 and 2.5
* 1024 bytes
* 1093 pages
* There are 1,000's of modules.

## Dates
We use ISO 8601 https://www.iso.org/iso-8601-date-and-time-format.html for time and date formats. `YYYY-MM-DD-[hh]:[mm]:[ss]`

**Do**

* 2019-09-04

**Don't**

* September 04, 2019

## Measurements

* Use numerals for all measurements instead of spelling-out the numbers.
* For 2 or more quantities, repeat the unit of measure.
* Add a space betwen the number and term. 

**Do**

* 1 GB or 2 GB of disk space for each 10 GB of data

**Don't**

* 1 or 2 GB of disk space for each 10 GB

If it's not in this table, it needs to be spelled out. 

| Term | Accepted abbrevetation |
|---|---|
| gigabits per second| Gbps |
| megabits per second	 | Mbps |
| megabytes per second	| MBps |	
| kilobytes| KB|
| megabytes| MB|
| gigabytes | GB |

## Common Spellings

Below are common words and the accepted spelling. If a word is on this list, please use the accepted spelling. This list is subject to change.

- Metasploit 
- Rapid7
- Metasploit Pro
- Metasploit Framework
- module
- exploit
- Msfvenom or msfvenom
- Kali Linux
- Powershell
- Post exploitation