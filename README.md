# unwind
Unwind lists of numbers represented by strings, using Python.

A python function to unwind lists of numbers represented by a string, 
separated by any non-numeric character, and potentially including numeric ranges.
The function will "unwind" a range originally indicated by "1,7-9" as "1,7,8,9".

Parameters:

	(1) string
		A string representing a list of numbers, using atomic values or ranges.

	(2) Range delimiter
		The delimiter used to denote numeric ranges, often a dash ("-") or a colon (":").
		e.g. To indicate all numbers between 1 and 5, you can use "1-5" or "1:5"

	(3) Sort
		True/False. Indicates whether to sort the final array or not.

	(4) Distinct
		True/False. Indicates whether to remove duplicate values from the final array.

	(5) Debug
		True/False. Indicates whether or not to output processing steps and flags to the 
		console.

Output:

	(1) An array with the unwund list of numeric values.

Testing:
You may use the following function calls to illustrate the function's purpose:

	# Testing general cases
	print unwind( "1,7,9-12" )#, debug=True )
	print unwind( "1" )
	print unwind( 1 )
	print unwind( "asdf" )
	print unwind( "-" )
	print unwind( "999,1,2,3,10-10,20-22,4,5,90--92,95---97,101--104-108,a,b,c,d6-7,9.7,10,10,10,99.8-102,   87.8-89.2  , 668" )
	print unwind( "1,17-21,50-56,67-109,111-114" )
	print unwind( "29-32,34-39,40-46" )
	print unwind( "6,7,10-16,22,23,25-28" )
	print unwind( "2,8,47,61,62,64" )
	print unwind( "3,58,59" )
	print unwind( "4,5,24,33,48,57,60,63,65" )
	print unwind( "9,49,66,110" )

	# Testing with different range delimiters
	print unwind( "999,1,2,3,10-10,20-22,4,5,90--92,95---97,101--104-108,a,b,c,d6-7,9.7,10,10,10,99.8-102,   87.8-89.2  , 668" )
	print unwind( "1,2,7-9,15-18" )
	print unwind( "1,2,7:9,15:18", rangeDelimiter=":" )
	print unwind( "1,2,7:9,15-13" )

	# Testing for negative numbers support (requires ":" range delimiter)
	print unwind( "1,-2,9" )
	print unwind( "1,-2,9", rangeDelimiter=":" )
	print unwind( "-1000:-3", rangeDelimiter=":" )
	print unwind( "1,-2,7:9,15:13", rangeDelimiter=":" )#, debug=True )
	print unwind( "1,-5:-2,7:9", rangeDelimiter=":" )


The MIT License (MIT)
Copyright (c) 2016 Carlos Alvidrez 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
