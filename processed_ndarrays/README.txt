Processed ndarrays readme
Lee B. Hinkle May 25, 2022

These are numpy ndarrays stored during development and analysis.

The overall method of building the X,y,sub arrays allows for different
sliding window sizes, sample rates, etc.   Also by storing the arrays
things like hold-one-subject out can be executed much faster.

The primary reason I've put these here however is for the unscripted
sequences which were performed by subject 1 and 2 but not 3.  The
issue is that the code default is to drop a sliding window which has
more than one label.  This does not occur frequently during the scripted
sequences but causes problems in the unscripted since it shortens the
length and throws the timing off for the closed-captioning.  So a 
quick change was made to use the mode and keep those sliding windows.

I hope to integrate this capability into the code but for now am using
the stored versions of the unscripted arrays from a quick run of 
modified code.

