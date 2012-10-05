---
layout: post
title: Configuring Sublime Text
date: 2012-10-06 02:25
---
**Original:** http://drupal.org/node/1346890

[Sublime Text](http://sublimetext.com/) is a sophisticated text editor for code, html and prose. You'll love the slick user interface and extraordinary feature.

It is available for windows, linux and mac osx

## Screenshot ##

![Screenshot](http://drupal.org/files/sublime.png)

## Configuration ##

Go to `"Preferences" => "Settings - User"` and change the folowing settings.

	{
	  "rulers": [80],
	  "tab_size": 2,
	  "translate_tabs_to_spaces": true,
	  "use_tab_stops": true,
	  "trim_automatic_white_space": true,
	  "trim_trailing_white_space_on_save": true,
	  "ensure_newline_at_eof_on_save": true,
	  "fallback_encoding": "UTF-8",
	  "default_line_ending": "unix",
	  "shift_tab_unindent": true,
	  "word_separators": "./\\()\"'-:,.;<>~!@#%^&*|+=[]{}`~?"
	}

## Links ##

* [sublime_completion](http://drupal.org/project/sublime_completion): A drush based Drupal autocomplete file generator for ST2.
* [Drupal Sublime Text snippets](https://gitorious.org/sublime-text-snippets): Quickly insert Drupal function templates using ST2 snippets from this project on gitorious.