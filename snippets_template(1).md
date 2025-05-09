**Snippet 1: String Matching Algorithms**

String matching is a process of finding occurrences of a pattern within a text. There are several algorithms designed for this, including:

* **Naive Algorithm**: This is a simple brute force approach where we compare the pattern with every substring of the text.

* **KMP Algorithm**: This improves upon the naive approach by avoiding redundant comparisons through preprocessing the pattern.

* **Rabin-Karp Algorithm**: Uses hashing to improve efficiency, especially when looking for multiple patterns in a text.

# **Optional code example**

\# Knuth-Morris-Pratt (KMP) algorithm    
def KMP\_search(text, pattern):    
	n, m \= len(text), len(pattern)    
	lps \= \[0\] \* m  \# longest prefix suffix array    
	j \= 0  \# index for pattern

	\# Preprocess the pattern    
	compute\_lps(pattern, lps)

	\# Search the pattern in the text    
	i \= 0  \# index for text    
	while i \< n:    
    	if pattern\[j\] \== text\[i\]:    
        	i \+= 1    
        	j \+= 1    
    	if j \== m:    
        	print(f"Pattern found at index {i \- j}")    
        	j \= lps\[j \- 1\]    
    	elif i \< n and pattern\[j\] \!= text\[i\]:    
        	if j \!= 0:    
            	j \= lps\[j \- 1\]    
        	else:    
            	i \+= 1

def compute\_lps(pattern, lps):    
	length \= 0  \# length of the previous longest prefix suffix    
	i \= 1    
	while i \< len(pattern):    
    	if pattern\[i\] \== pattern\[length\]:    
        	length \+= 1    
        	lps\[i\] \= length    
        	i \+= 1    
    	else:    
        	if length \!= 0:    
            	length \= lps\[length \- 1\]    
        	else:    
            	lps\[i\] \= 0    
            	i \+= 1

