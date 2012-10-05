---
layout: post
title: Configuring vim
date: 2012-10-06 02:08
---
**Original:** http://drupal.org/node/29325

[Vim](http://www.vim.org/) is an advanced text editor that seeks to provide the power of the de-facto UNIX editor `'vi'`, with a more complete feature set.

## Vim Plugin for Drupal ##

The Vim Plugin for Drupal (available on Drupal.org) provides the configuration information below along with additional goodies and hints for Drupal 6, 7, and 8.

* Vim Plugin for Drupal Documentation
* Other Recommended Vim Plugins for Drupal

## Indentation ##

The following commands will indent your code the right amount, using spaces rather than tabs and automatically indent after you start. The commands should be added to a `.vimrc` file in your home directory `(~/.vimrc)`, you may need to create this.

	set expandtab
	set tabstop=2
	set shiftwidth=2
	set autoindent
	set smartindent

If you would prefer not to have all your vim sessions use these settings, you can activate them in specific files using a `"modeline"`. That is, within the first or last 5 lines of the file you are editing, add the following line:

	// vim: set filetype=php expandtab tabstop=2 shiftwidth=2 autoindent smartindent:

Note that not everyone uses vim to edit files, so this line is for your convenience and may be removed prior to submitting changes. For more information on how to use modelines, type `:help` modeline in vim or gvim.

## Syntax highlighting ##

If you enjoy syntax highlighting, it may be worth remembering that many of Drupal's PHP files are `*.module` or `*.inc`, among others.

Vim seems to syntax highlight `*.inc` files properly by default but doesn't know that some other files are PHP content. For `*.module` and `*.install`, use this snippet in `.vimrc`:

	if has("autocmd")
	  " Drupal *.module and *.install files.
	  augroup module
	    autocmd BufRead,BufNewFile *.module set filetype=php
	    autocmd BufRead,BufNewFile *.install set filetype=php
	    autocmd BufRead,BufNewFile *.test set filetype=php
	    autocmd BufRead,BufNewFile *.inc set filetype=php
	    autocmd BufRead,BufNewFile *.profile set filetype=php
	    autocmd BufRead,BufNewFile *.view set filetype=php
	  augroup END
	endif
	syntax on

## Using these settings only with Drupal ##

* Copy your `.vimrc` to `.vimrc-drupal`
* Append these settings to the end
* Run  `vim -u ~/.vimrc-drupal`

To make this easier (using bash on UNIX or Linux), you could create an alias by typing:

	alias vid="vim -u ~/.vimrc-drupal"

This allows you to just use the vid command instead of vi when you want to edit a Drupal file.

Note: To make this alias permanent add the above line to the .bashrc file in your home directory `(*nix)`. More on the alias command
Using the snippetsEmu package for Drupal

There is a script which provides similar snippets functions to TextMate: http://www.vim.org/scripts/script.php?script_id=1318
Just copy the `php_snippets.txt` to your `~/.vim/after/ftplugin/php_snippets.php` and overwrite the old one

Now you can type fieldset and you get a definition for the fieldsets, if you just want to add single lines add for example #collapsed

## Using the snipMate package for Drupal ##

There is another plugin which allows you to easily use and create snippets: http://www.vim.org/scripts/script.php?script_id=2540 . There are currently two projects that provide drupal snippets:

D6 mixed snippets: http://github.com/theunraveler/Drupal-Snippets-for-Vim

Vim snippets for Drupal 7: https://github.com/tanarurkerem/drupal-snippets. Please refer the README file for detailed installation instructions.