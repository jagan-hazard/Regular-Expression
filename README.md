# Regular Expression:
---------------------

1. Introduction:
----------------
	- Regular Expression is a sequence of characters that define a search pattern mentioned as a string of charecters. 
	
	- The concept arose in the 1950s when the American mathematician Stephen Cole Kleene formalized the description of a regular language. The concept came into common use with Unix text-processing utilities. Since the 1980s, different syntaxes for writing regular expressions exist, one being the POSIX standard and another, widely used, being the Perl syntax. 
	
	- Regular expression are used for
		- Find. 
		- Find and replace (subsitution).

	- Regular expression plays a major role in
		- Text processing tasks (string processing).
		- Data scrapping (web scrapping).
		- Parsing.
		- Syntax highlighting.
		- Internet search engine.

2. Regex special charecters
---------------------------

	2.1. Pattern:
	-------------
		.    ->  matches any single charecter.

	2.2. Anchors:
	-------------

		^			-> starts with
		$			-> ends with	
		^....$		-> starts and ends with

	2.3. Quantifiers:
	-----------------

		abc*		-> match string 'ab' followed by zero or more 'c'
		abc+		-> match string 'ab' followed by one or more 'c'
		abc?		-> match string 'ab' followed by zero or one 'c'
		abc{2}		-> match string 'ab' followed by two 'c'
		abc{2,}		-> match string 'ab' followed by atleast two or more 'c'
		abc{2,5}	-> match string 'ab' followed by two to five 'c'

	2.4. 










3. Regex methods in python:
----------------------------

