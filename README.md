# [Bionic Reader - Read Faster!](https://bionicreader.netlify.app)


<!-- [![banner](src/icons/marquee.png)](https://chrome.google.com/webstore/detail/bionify-read-faster-with/gomhfpbcjfidhpffhecghfdieincgncc) -->

A simple chrome extension designed to help you read faster and more efficiently.

Here's an example of Bionified text to demonstrate the speed!

[![read](read.png)](https://bionicreader.netlify.app)

(example text from jiffy reader)

<!-- ## Download

Bionify is available on the Chrome web store!

Get it here: Chrome extension link

Official website: https://bionicreader.netlify.app -->

## Development

First, clone the repository

```
git clone https://github.com/rahulkarda/bionic-reader.git
```

Then, follow [this instruction](https://developer.chrome.com/docs/extensions/mv3/getstarted/#unpacked) to develop unpacked extensions in Chrome.

## Algorithm Specification

We allow you to customize highlight algorithm using a string similar to this:

```
- 0 1 1 2 0.4
```

Note that all numbers and characters are separated by a space. Here is what this string means:

```
- 0 1 1 2 0.4
^
```

The first character can be either `-` or `+`. If it is `-`, we don't highlight common english words (for example 'a', 'and', etc.) if it is '+' we highlight all words.

```
- 0 1 1 2 0.4
  ^
```

This specifies the number of highlighted characters for words with length 1. For example 'a' and 'I'. Here we have specified that we don't want to highlight these characters.

```
- 0 1 1 2 0.4
    ^
```

This specifies the number of highlighted characters for words with length 2. For example 'an' and 'or'. Here we have specified that we highlight the first character of these words.

```
- 0 1 1 2 0.4
      ^
```

Highlight the first character of 3 letter words.

```
- 0 1 1 2 0.4
        ^
```

Highlight the first two character of 4 letter words.

```
- 0 1 1 2 0.4
           ^
```

Unlike the previews entries, the last entry is a fractional value between 0 and 1 which specified which fraction of words that are not specified by previous rules must be highlighted.
For example, here we highlight the first 40% characters of words with 5 or more characters.

## Credit

Bionic Reader is a modified fork of Bionify.
