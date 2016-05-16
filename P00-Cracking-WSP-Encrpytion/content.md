---
title: "Cracking WSP Encryption"
slug: cracking-wsp
---

# Cracking WSP Encryption

### Project Background
An unnamed government security agency has recently begun intercepting numerous messages encrypted with a state of the art, never before seen algorithm. Because everything in government needs an acronym, the application of this algorithm has been nicknamed "WSP Encryption."

Up to this point in time, a team of seven highly paid PhD analysts has been staffed to manually decrypt each and every WSP-encrypted message they receive. The analysts have not slept or eaten in twelve days, and many of them are
beginning to face burnout. Meanwhile, the stack of encrypted messages continues to grow.

As a frantic last ditch effort, the director of the unnamed agency performed a late night PRISM search to identify a coder capable of automating the decryption processes. As a top Make School student, YOU have been selected to carry out this task!

### Specifications


* Each WSP message consists of a rectangular grid of letters. The grids vary in sizes.
* Many of the letters in the grids are "junk" letters. They serve merely to mask the encoding.
* Hidden amongst the junk letters, one or more words are spelled out in each
WSP message.
* A word can be spelled out horizontally, vertically, or diagonally. The
correct spelling of the words can run backwards or forwards.
* When words are found that overlap by more than a single letter (e.g. "hell" and "hello"), only the longest word should be detected as a true word.
* Each location in a given letter grid corresponds to an ordering number. The upper left letter of the grid is location 1. Numbers count to the right in each row and then wrap onto the beginning of the next row. For example, this would be the ordering of a 3 x 3 grid:

````
1 2 3
4 5 6
7 8 9
````

* Words should be output in order. Ordering is determined entirely by the first letter of the found word. A word whose first letter is at a lower ordered square should be output before a word whose first letter is at a higher number.
* In cases where two words both begin at the same location, directionality should be used to break ordering ties in this order: horizontal left-to-right, horizontal right-to-left, vertical top-to-bottom, vertical bottom-to-top, diagonal left-to-right downwards, diagonal left-to-right upwards, diagonal right-to-left downwards, diagonal left-to-right upwards.
* In the rare case of a palindrome, the version of the palindrome detected with a lower ordering should be detected as the "true" word.

For consistency, the following protocols must also be followed in your solution:

* The format of input data should exactly match the sample data below.
* The format of output data should exactly match the sample output data below, with all found words in order according to the rules above, with each word separated by a newline.
* It should be possible to swap dictionaries in case the language used for the encryption ever changes, but in general /usr/share/dict/words can be provided as the dictionary as the second command line argument to invoke your program.
* Analysts must be able to invoke your program from a command line. The input file should be provided with a single command line argument.
* All output should be written to standard output. When you'd like to save your output, you can redirect it to a file by using ` > output` at the end of your invocation.
* The choice of language is up to you, but Python and Ruby are encouraged.

### Sample Data

#### Invocation
`./crack_wsp.rb /path/to/input_matrix.txt /usr/share/dict/words`

#### Input Matrix

````
Q H E L L O
F Q Q Q Q Q
S R A M Q Q
Q Q O Q Q Q
Q Q Q M Q Q
````

#### Output

````
hello
from
mars
````

### Architectural Guidelines

If your solution is successful at improving efficiencies, it may be expanded to meet other needs in a second contract. Accordingly, it should be built in a modular fashion. The following architectural guidelines should be upheld:

* Object-oriented programming should be used.
* It should be fully covered by automated tests covering many potential arrangements and boundary conditions as described in the specifications.
* All variables and constants should be named clearly.
* All rules should be clearly defined in ways that make them easy to change later.
* Performance should be optimized. Some grids encountered may contain hundreds of thousands of characters.

### Evaluation

In order to evaluate your success, your project will be executed against a set of hidden tests containing many different grid types. You are encouraged to think like a tester and write many of your own cases before you submit your project to the test server.
