# Regular Expressions

_Regular Expressions_ or _Regex_ as it's commonly known as is a very general term used for pattern searching, usually in a string(or a vector of strings). Although there're a lot to learn about _regex_, I've listed down to commonly used _regex_ functions.

- `grepl()`: Returns a logical value indicating that a certain pattern was found.

- `grep()`: Returns a vector of index locations reffering to the pattern matches.

_Examples:_

```R
text <- "Hi there, do you know who you are voting for?"

grepl('voting',text)
TRUE

grepl('Hi',text)
TRUE

grepl('Sammy',text)
FALSE

v <- c('a','b','c','d')

grep('a',v)
1

grep('c',v)
3
```