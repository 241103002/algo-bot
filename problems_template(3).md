

---

**Problem 1: Pattern Matching with Naive Approach**

**Problem Statement**  
 Given a text and a pattern, find all occurrences of the pattern in the text using the **Naive String Matching Algorithm**.

**Example Input**  
 Text: "ababcababcabc"  
 Pattern: "ab"

**Example Output**  
 Matches found at indices: \[0, 2, 7, 9\]

---

**🔹 Hints**

1. Loop through the text and check if the substring matches the pattern.

2. Use a sliding window to check every possible starting position of the pattern in the text.

**🔹 Brute Force Idea**  
 Use a **brute force** approach by comparing the pattern with every substring of the text one by one.

---

**🔹 Optimized Idea**  
 Use the **Knuth-Morris-Pratt (KMP)** algorithm, which uses preprocessing to avoid unnecessary comparisons and improve efficiency.

---

**🔹 Code Fragment**

\# Naive Pattern Matching Algorithm  
def naive\_pattern\_matching(text, pattern):  
	n \= len(text)  
	m \= len(pattern)  
	matches \= \[\]  
	for i in range(n \- m \+ 1):  
    	if text\[i:i+m\] \== pattern:  
        	matches.append(i)  
	return matches

---

