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
		a(bc)*		-> match string 'a' followed by zero or more copies of sequence 'bc'
		a(bc){2,5}	-> match string 'a' followed by two to five copies of sequence 'bc'


	2.4. Operator:
	--------------

		a(b|c)      -> 'a' followed by 'b' or 'c'
		a[b|c]		-> 'a' followed by 'b' or 'c'

	2.5. special charecters:
	------------------------
		In general. if you use backslash '\' before any charecter, then this will remove the property of special charecter.

		\n          -> looks for a newline   
		\t          -> looks for a tab
		\b          -> matches word boundary (skip whitespaces)
		\B          -> matches no word boundary 
		\d          -> matches a single charecter that is a digit
		\w          -> matches any alphaneumeric/word charecter (i.e. [a-zA-Z0-9])
		\W          -> matches any non-word charecter (i.e. [^a-zA-Z0-9])
		\d          -> matches any digit  (i.e. [0-9])
		\D          -> matches any non-digit  (i.e. [^0-9])
		\s          -> matches whitespace charecters
		\S          -> matches non-whitespace charecters
		\.          -> looks for '.'

	2.6. Alternative and parenthesis:
	---------------------------------

		jelly|cream   	-> jelly or cream
		(eg|le)gs	  	-> eggs or legs
		(da)+			->da or dada or dadada ......
		









3. Regex methods in python:
----------------------------

