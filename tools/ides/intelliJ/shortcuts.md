# IntelliJ Shortcuts

A collection of very useful shortcuts in IntelliJ to speed up development, but to mainly provide a safer development
and refactoring process.

| Shortcut | Description |
| ------- | ----------- |
| cmd + backspace | Delete the current line |
| cmd + d | Duplicate the current line |
| double shift | Search everything |
| cmd + k | Commit latest changes |
| shift + cmd + k | Push latest changes |
| cmd + shift + t | Open/create test class |
| cmd + t | Update project |
| shift + f6 | Rename selected text |

## IntelliJ Features Trainer
Building on my previous notes, part of my PDP learning is going through the IntelliJ features plugin to learn more about
the various shortcuts IntelliJ has to improve my overall productivity.

I'm displaying the most useful ones here:

### Essentials

#### Find Action
The find action shortcut provides a popup search box to find all of the other actions that Intellij provides. 
Just press command + shift + a. ⌘⇧A.

Need to commit a recent code change but you don't know the shortcut? Use the find actions shortcut and 
then search for commit.

#### Search Everywhere
To search everything and anything within Intellij, whether it's an action, class or file etc, you can use the search everywhere 
tool by pressing shift ⇧ twice.

**TIP:** Use the prefix of the required words you're searching for. For example, if you're searching for a class called ProductServiceImp, 
use 'psi' to filter the results faster.

#### Basic Completion
Intellij will recommend a set of code completions whenever you're typing. However, you can also trigger the code completion/suggestions 
window by pressing control ⌃ + space. This is especially useful for argument suggestions. Place the cursor inside the parenthesis and use ⌃ + space for recommendations. 
Once chosen, complete any code suggestion by pressing ⌘⇧↵.

#### Expand Code Selection
You can select chunks of code by expanding the selection from where your cursor is placed. Useful for selecting a 
whole word, or code block with ease. Press ⌥ + ↑. Deselect by using the down arrow.

![Code Selection](https://raw.githubusercontent.com/BradNichol/Brain/8c05de9dd1642b2cdf3e12e5edb92e1ffe74ce93/media/img/codeselection.gif)

### Editor Basics

#### Comment / Uncomment Line
Either place cursor on a single line or select multiple lines and press ⌘/

#### Duplicate Current Line
Duplicate any single line or selection of lines by pressing command + d. ⌘D

#### Delete Current Line
Press command and backspace ⌘⌫

#### Move Code Fragments
To move a code section up, place the cursor at the beginning of the line and press option, shift + up key. ⌥⇧↑.
You can also move a whole method by placing the cursor at the beginning of the method name and press command, shift + up key. ⌘⇧↑.

![Moving code](https://raw.githubusercontent.com/BradNichol/Brain/f1a35ba98fb3103cbd5523a1d584336e070f1a01/media/img/movecode.gif)

#### Code Collapse
It can be easier to read code by collapsing sections of it. Depending on where your cursor is placed, you can collapse a conditional statement or
a method by pressing command + -. ⌘-. Press ⌘= to expand the code.
You can also collapse all methods in a class by pressing ⌘⇧-

![Collapse Code](https://raw.githubusercontent.com/BradNichol/Brain/189c49015c36f8db8a5ffb5342c6dd054d1160bd/media/img/collapsecode.gif)

#### Surround and unwrap
To surround code with an if statement, or try/catch block etc, place the cursor on the code fragment and press ⌘⌥T.
To unwrap a code fragment, press fn⌘⇧⌫

![Surround](https://raw.githubusercontent.com/BradNichol/Brain/485a625aeb954e474c107dbcdef28b5a912a6b46/media/img/surroundunwrap.gif)

#### Select Multiple Occurrences
If you want to change a selection of code that has many occurrences in a file, select the fragment and press control + G. ⌃G.
Keep pressing to select more occurrences. If you want to select all of the occurrences, first select with ⌃G, then press ⌘⌃G.
You can now edit in bulk.

![Select Occurrences](https://raw.githubusercontent.com/BradNichol/Brain/0434ccc5b014f88bb1d2c00e31cc0e397df40f1a/media/img/selectoccurrences.gif)


### Code Completion

#### Smart Type Completion
Smart type  completion will filter the list of code completion suggestions that are applicable within the current scope context.
Use ⌃⇧Space to open the list.
You can also use this for **return statement** completion when placing the cursor after return. 

#### Statement Completion
Use this to complete statements. For example, you can finish an if statement by typing if, followed by ⌘⇧↵.
When you're inside a conditional parenthesis, you can use it to jump out once you've entered the conditions.

![Statement completion](https://raw.githubusercontent.com/BradNichol/Brain/91a374bc6ee1e1b9a36dbd7174516d23c7b1d151/media/img/statementcompletion.gif)

#### Completion with Tab
When you're selecting code from a list, ALWAYS use Tab instead of Enter. It's mostly useful when you're replacing an existing
option, as tab will replace it.

### Refactorings

#### Rename
To rename an item, whether it's a field, file or method etc, just press shift + F6. (⇧F6). You can then rename, and 
press enter to confirm. You maybe prompted to rename corresponding items, i.e. getters/setters.

#### Extract Variable
If you have multiple occurrences of an expression, it is best practice to extract this to a variable.
Select the expression and press ⌘⌥V. Intellij will prompt you for all occurrences that you'd like to replace.
Once you've entered the variable name, hit enter to complete.

![Extract variable](https://raw.githubusercontent.com/BradNichol/Brain/a6a6ac1cbfe116a89627a00674c3926422a8be9c/media/img/extractvariable.gif)

#### Extract Method
Similar to above, to extract a method use ⌘⌥M. Intellij will create a method with a suggested name, and ask you 
to replace all other occurrences.

#### Refactoring Menu
If you're unsure of what refactoring options you have, or cannot remember a certain shortcut, you can use the refactoring menu instead.
Select your code and press ⌃T.


### Code Assistance
Shortcuts to format code, obtain param info and preview quick popups.

#### Code Format
It's a good practice to reformat your code as much as possible. Reformatting can be done in a couple of ways:
* Reformat a selection of code by highlighting it and press ⌥⌘L
* Reformat a whole file by deselecting any code and press ⌥⌘L
* Use reformat settings to choose what to reformat, press ⌥⌘⇧L

#### Parameter Info
To see what parameters are required inside a method, place your cursor in the method parenthesis and press ⌘P.

### Navigation

#### Find and replace in files

You can use ⌘⇧F and then use the search box.
* Use ⌥W to narrow down the search to your keyword
* ⌘⇧R to replace all
* ⌥D to narrow to current directory only

#### File structure
When you're inside a large class and you want to reduce the noise to search the method names only:
* Press fn⌘F12 for popup view
* Press ⌘7 for toolbar view

You can then cycle through the methods.

#### Declaration and usages
To jump to the declaration of a method, place the cursor on the method call and press ⌘B
* Press ⌘B again to see all usages of the method
* Press fn⌥F7 to see a detailed view of usages

#### Recent files and locations
* Press ⌘E to see all recent files access, in a popup tool box.
* You can delete any access files from this history by clicking backspace on them.
* ⌘⇧E will show your recent code fragments.






