vale.ini example. Vale has trouble finding the style guide if its in a different folder, so sometimes the full file path is required. 

```
# This goes in a file named either `.vale.ini` or `_vale.ini`.
StylesPath = /Users/user_name/Documents/{folder_name}/UX-Style-Guide-master
MinAlertLevel = suggestion # suggestion, warning or error

# Only Markdown and .txt files; change to whatever you're using.
[*.{md,txt}]
# List of styles to load. Loading our styles from .github/valeStyles
BasedOnStyles = helpdocs # this should match what you are writing for. 
```
