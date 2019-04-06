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

	2.2. Metacharecter:
	--------------------

		^			-> starts with (each line that is after each '\n')
		$			-> ends wit	(each line that is before each '\n')
		^....$		-> starts and ends with
		[]			-> A set of charecters
		{}			-> Exactly specific number of occurance  
		|			-> Either or
		()			-> Capture and Group

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
		\A          -> matches at the start of string alone. 
		\n          -> looks for a newline   
		\t          -> looks for a tab
		\b          -> matches word boundary (skip whitespaces)
		\B          -> matches no word boundary 
		\w          -> matches any alphaneumeric/word charecter (i.e. [a-zA-Z0-9])
		\W          -> matches any non-word charecter (i.e. [^a-zA-Z0-9])
		\d          -> matches any digit  (i.e. [0-9])
		\D          -> matches any non-digit  (i.e. [^0-9])
		\s          -> matches whitespace charecters
		\S          -> matches non-whitespace charecters
		\.          -> looks for '.'
		\Z          -> matches at the end of string alone.

	2.6. Alternative and parenthesis:
	---------------------------------

		jelly|cream   	-> jelly or cream
		(eg|le)gs	  	-> eggs or legs
		(da)+			->da or dada or dadada ......
		

3. Regex methods in python:
----------------------------
	3.1. findall(<pattern>,<input_string>):
	---------------------------------------
		- This method will return a list contains the all matched pattern from the input string.
		- If the pattern is not found, it will return an empty string.
		- syntax: re.findall(<pattern>,<input_string>)

		e.g:

			import re
			text="""Eden Michael Hazard (French pronunciation: ​[edɛn azaʁ]; born 7 January 1991)
			 is a Belgian professional footballer who plays for English club Chelsea and captains
			 the Belgium national team. Primarily playing as an attacking midfielder and as a
			 wide midfielder, Hazard is known for his creativity, speed, dribbling and excellent
			 passing.[4][5]. He has earned critical acclaim for his playing style, with the media,
			 coaches, and players drawing comparisons to Ballon d'Or winners Lionel Messi and 
			 Cristiano Ronaldo,[16][7][28][59] and Hazard is widely considered one of the best pl"""  

			out=re.findall("\[\d{1,}\]",text)      
			print(out)      # ['[4]', '[5]', '[16]', '[7]', '[28]', '[59]']

	3.2. split(<pattern>,<input_string>,maxsplit):
	-----------------------------------------------
		- This method will split the string where the match occurred and returns as list.
		- Maxsplit argument is an integer which will split the number of times as per argument.
		- It will remove the pattern from the string while splitting.
		- If the pattern is not found, it will return the complete input.
		- syntax: re.split(<pattern>,<input_string>,maxsplit)

		e.g:

			import re
			text="""Eden Michael Hazard (French pronunciation: ​[edɛn azaʁ]; born 7 January 1991)
			 is a Belgian professional footballer who plays for English club Chelsea and captains
			 the Belgium national team. Primarily playing as an attacking midfielder and as a
			 wide midfielder, Hazard is known for his creativity, speed, dribbling and excellent
			 passing.[4][5]. He has earned critical acclaim for his playing style, with the media,
			 coaches, and players drawing comparisons to Ballon d'Or winners Lionel Messi and 
			 Cristiano Ronaldo,[16][7][28][59] and Hazard is widely considered one of the best pl"""  

			out=re.split("\. ",text)      
			print(out)      			 # split each sentence as per pattern given

	3.3. sub(<matching_pattern>,<replacing_pattern>,<input_string>,count):
	----------------------------------------------------------------------
		- This method will substitute the matching pattern with replacing pattern and return it as new string.
		- count argument is an integer which will substitute the number of times as per argument.
		- If the pattern is not found, it will return the complete input.
		- syntax: re.sub(<matching_pattern>,<replacing_pattern>,<input_string>,count)

		e.g:

			import re
			text="Eden Michael Hazard is a Belgian professional footballer. He plays for English club Chelsea. He captains the Belgium national team."  
			out=re.sub("\. ",".\n",text)      
			print(out)      # splitting each sentence as per pattern using substitute function


	3.4. subn(<matching_pattern>,<replacing_pattern>,<input_string>):
	-----------------------------------------------------------------
		- This method is similar to sub() except it returns a tuple containing the substituted string and the count of number of times substitution happened.
		- count argument is an integer which will substitute the number of times as per argument.
		- If the pattern is not found, it will return the complete input.
		- syntax: re.subn(<matching_pattern>,<replacing_pattern>,<input_string>)

		e.g:

			import re
			text="Eden Michael Hazard is a Belgian professional footballer. He plays for English club Chelsea. He captains the Belgium national team."  
			out=re.subn("\. ",".\n",text)      
			print(out)      # tuple containing the substituted string and the number of times substitution happened


	3.5. search(<matching_pattern>,<input_string>):
	-----------------------------------------------
		- This method is will return an object which has location of the first match and matched charecter.
		- If match is not found, then it will return None.
		- syntax: re.search(<matching_pattern>,<input_string>)

		e.g:

			import re
			text="Chelsea Eden Michael Hazard is a Belgian professional footballer. He plays for English club Chelsea. He captains the Belgium national team."  
			out=re.search("Chelsea",text)      
			print(out)          # object containing matched pattern location and matched string
			print(out.span())   # returns span (location) of the match  
			print(out.start())  # returns starting location of the match
			print(out.end())    # returns ending location of the match
			print(out.group())  # returns mathed pattern from the object
			if out:
			    print("match found")
			else:
			    print("match not found")

	3.6. Raw string using r prefix:
	--------------------------------
		- If r prefix is used before the search pattern  which means the special charecters are not considered.
		- syntax: (r'<seach_string>')

		e.g:

			import re
			string = '\n and \r are escape sequences.'
			result = re.findall(r'[\n\r]', string) 
			print(result)

4. Use of Grouping and sets along with other special charecters:
----------------------------------------------------------------
	- Sets [] and Grouping () is often used in regex to find the complex matching patterns. we will see these combination in the 	below examples.

	4.1. Grouping ():
	-----------------
		- Grouping is something which will match the all the string inside the () and group together.

		e.g:

		import re
		text="""Chelsea Football Club is a professional football club in Chelsea, London,
		 England, that competes in the Premier League, the highest tier of English football.
		 The club has won six top division titles, eight FA Cups, five League Cups, four FA 
		 Community Shields, two UEFA Cup Winners' Cups, one UEFA Champions League, one UEFA
		 Europa League, and one UEFA Super Cup.[5644][3322342345][112121226] [544] [66] [78]
		Founded in 1905, the club's [233] home ground since then has been Stamford Bridge.[7]
		 honours under Abramovich, second in that time only to Manchester United.[9][10] 
		between 2004 and 2005.[note 1] Chelsea have traditionally wore a royal blue kit
		 with white socks, and the club's crest features a ceremonial lion rampant regardant
		 holding a staff.[11] The club have rivalries with neighbouring clubs Fulham, Arsenal,
		 and Tottenham Hotspur.  the world, worth £1.54 billion ($2.06 billion), and are the eighth
		 highest-earning football club in the world, with earnings of over €428 million in the 
		 2017–18 season.[12][13]"""

		result=re.findall("(\[\d*\])",text)
		print(result)
