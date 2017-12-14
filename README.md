# Vim-Adept

This is an attempt at a Vim mode for [Textadept](https://foicica.com/textadept/).

## Installation

To install, clone this repo to `~/.textadept/modules/vim-adept` and add `require 'vim-adept'` to `~/.textadept/init.lua`.

## Usage

Currently supported modes are Normal, Insert, Visual and Visual Line. They are (reasonably) complete as far as movements and editing go.

## Plugins

It is my intention to add functionality similar to some popular VIM plugins.

Currently suported:

* vim-commentary: Commenting plugin from Tim Pope. Press `gcc` in normal mode to comment a line. `gc` in visual modes to comment lines.

## What's missing'

Some notable missing features:

* Text objects (e.g., `caw` or `di(`)
* Marking
* Folding
* Ex mode
* Splitting (textadept has built-in splitting which works just fine)
* Probably others I'm not thinking of at this time.
* Multiple clipboards (deleing, changing, yanking, etc. uses the system clipboard by default)

## Custom Keys

This makes use of Textadept's excellent mode-based key editing system. It also makes it very easy to add your own. A common
idiom in the Vim world is to add an insert mode key binding for going back to normal mode without having to hit escape.
Normally, this mapped to `jj` to `jk`. Personally, I use `;;`. You can set this up yourself by adding something like
the following to `~/.textadept/init.lua`:

```lua
keys[';'] = {
  [';'] = _VIM.normalMode,
}
```


## leader functionality 

Another common idiom in the Vim world is the **leader key** , which is usually mapped to  `,`.

```lua
 keys.normal_mode[','] = {
   ['t'] = function() io.quick_open() end,
   ['b'] = function() ui.switch_buffer(true) end,
 }
 ```
