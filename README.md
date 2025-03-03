# Pronto runner that uses Aspell for spell checking

[![Code Climate](https://codeclimate.com/github/prontolabs/pronto-spell.png)](https://codeclimate.com/github/prontolabs/pronto-spell)
[![Build Status](https://travis-ci.org/prontolabs/pronto-spell.png)](https://travis-ci.org/prontolabs/pronto-spell)
[![Gem Version](https://badge.fury.io/rb/pronto-spell.png)](http://badge.fury.io/rb/pronto-spell)
[![Dependency Status](https://gemnasium.com/prontolabs/pronto-spell.png)](https://gemnasium.com/prontolabs/pronto-spell)

Pronto runner that uses [Aspell](https://github.com/YorickPeterse/ffi-aspell) for spell checking. [What is Pronto?](https://github.com/prontolabs/pronto)

## Prerequisites

You'll need to install Aspell:

* Arch Linux: `sudo pacman -S aspell`
* OS X: (`brew install aspell --lang=en`)

## Configuration

In order to change configuration, you need to create `.pronto_spell.yaml` file in your project root directory. Awailable options are:

```YAML
suggestion_mode: 'fast' # default
language: 'en_US' # default
min_word_length: 5 # default
max_word_length: 999 # default is Infinity
max_suggestions_number: 3 # default
keywords: # spell check will be performed only the diff contains a word in this list
  - context
  - it
  - describe
ignored_words: # words in this list won't be marked as misspelled
  - aspell
  - boolean
  - datetime
```

It's also handy to have `.pronto.yml`. Here is configuration, designed for rails project:
```YAML
spell:
  exclude:
    - 'yarn.lock'
    - 'Gemfile.lock'
    - 'Gemfile'
    - 'package.json'
    - '.*.yml'
    - '*.json'
```
