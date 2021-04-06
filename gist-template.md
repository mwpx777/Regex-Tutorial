# Title (Regex Email Verification Tutorial)

In this tutorial, I will explain a regex expression works by breaking down all of the components so that the reader will have an understanding of how and why this expression works.

## Summary

I will be breaking down the different parts of the following regex expression.  I will explain in detail the different search parameters that make up this expression, and give example code snippets of each part.

The email verification regex expression this tutorial will be covering

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)
- [Contact](#contact)

## Regex Components

### Anchors
    Anchors are the opening and closing tags of a regex expression.  The opening anchor consists of a forward slash and a carat symbol /^ .  The closing anchor of a regex expression is created with the dollar sign and a forward slash  $/ .

    An example of a regex expression with opening and closing tags
    /^\w+$/

    In this email regex example, the opening and closing tags of the expression are /^ and $/
    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Quantifiers
    Quantifiers are expressions that are listed after a meta-character to assign a value to the meta character.  

    Some examples of quantifiers 

    * - 0 or more characters
    + - 1 or more characters
    ? - 0 or 1 this can also denote an optional character
    {min, max} - this can be set as the minimum and maximum character values
    {number} - this can be set to a single specific number value

    In this email regex example, the + symbol is added after the parenthesis for the first word in the email address, and again after the domain.  This indicates that 1 or more characters are searched for by the search expression.  
    
    Also, the end of the domain (example `.com `) also has a quantifier of {2,6}.  This means that the characters after the . in the domain must between 2 and 6 characters.

    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


### Character Classes
    Character classes are denoted by square brackets [ ] .  Character classes define characters that are allowed in the expression.  

    An example of a character class is the name Mark.  The name Mark could be spelled either Mark or Marc.  This is an example of how to write a character class to allow a search for either spelling of the name.
    Mar[kc] 

    In the email verification regex example, character classes are inserted for the character types the expression will search for. 
    
    [a-z0-9_|.-] 
    For the name of the email address, the character class will search uppercase and lowercase letters (denoted by a-z), numbers (denoted by 0-9), an underscore (denoted by _) , a period (denoted by.), or a dash (denoted by -).  

    [\da-z\.-]
    In the first part of the domain, the character class will search for any number 0-9 (denoted by \d), uppercase and lowercase letters (denoted by a-z), a period (denoted by .) , or a dash (denoted by -).

    [a-z\.] 
    In the last part of the domain, the character class will search for any uppercase or lowercase letter (denoted a-z), and a period (denoted .).

### Flags
    not used
### Grouping and Capturing
    Regex grouping refers to grouping certain search characters into their own specific group.  
    An example of grouping would be capturing the first and last names of a list and reordering.  
    Mark Peterson
    Dave Jones
    Liam Gallagher
    Noel Gallagher

    An expression to capture the first and last names separately.  The first part of the expression (\w+) would capture the fist name in the list and assign it to group 1.  The second appearance of (\w+) in the expression will capture the last name from the list and assign it to group 2.
    (\w+)\s+(\w+)

    To create a regex expression to reorder the list to lastname, firstname would be as follows
    $2, $1

    $2 refers to the group 2 which is the lastname captured from the original list, and $1 refers to the firstname from the original list.  , is a literal that will add a comma, and the space will add a whitespace before the firstname.

    In the regex email expression, parenthesis are used to capture the username, domain name and extension respectively.  In this example, username would be assigned group 1, domain name would be assigned group 2, and extension would be assigned group 3.

    ([a-z0-9_\.-]+) - for username  group 1
    
    ([\da-z\.-]+) - for domain name  group 2
    
    ([a-z\.]{2,6}) - for extension after .  group 3


### Bracket Expressions
not used

### Greedy and Lazy Match
not used
 .* is a greedy match it will keep matching until it can no longer match
 .*? is not greedy

### Boundaries
not used

### Back-references
not used
/1 looking for duplicates


### Look-ahead and Look-behind
not used
## Author

This email regex tutorial was written as a weekly challenge assignment by Mark Peterson. I am currently a student in the Web Development Bootcamp through the University of Wisconsin.  

## Contact

Mark Peterson's contact links

* Github: (https://github.com/mwpx777)

* LinkedIn: (https://www.linkedin.com/in/mwpdesigns/)

* Email: (mwpx777@gmail.com)

