\#\# Problem 1: String Pattern Matching

\*\*Problem Statement\*\*    
Given a text and a pattern, find all occurrences of the pattern in the text. Implement this using the Naive Pattern Matching algorithm.

\*\*Example Input\*\*    
Text: "ababcababcabc"    
Pattern: "ab"

\*\*Example Output\*\*    
Matches found at indices: \[0, 2, 7, 9\]

\---

\#\#\# 🔹 Hints  
1\. Loop through the text and check if the substring matches the pattern.  
2\. Use a sliding window to check every possible starting position of the pattern in the text.

\#\#\# 🔹 Brute Force Idea    
Loop through each position of the text and compare it with the pattern.

\---

\#\#\# 🔹 Optimized Idea    
Use the \*\*Knuth-Morris-Pratt (KMP)\*\* algorithm to avoid unnecessary comparisons after a mismatch.

\---

\#\#\# 🔹 Code Fragment  
\`\`\`python  
def naive\_pattern\_matching(text, pattern):  
	n \= len(text)  
	m \= len(pattern)  
	matches \= \[\]  
	for i in range(n \- m \+ 1):  
    	if text\[i:i+m\] \== pattern:  
        	matches.append(i)  
	return matches

## **Problem 2: Trie Data Structure**

**Problem Statement**  
 Implement a **Trie** data structure that supports the operations: insert and search.

**Example Input**  
 Insert("apple")  
 Insert("app")  
 Search("apple") \-\> True  
 Search("appl") \-\> False

**Example Output**  
 Search for "apple" \-\> True  
 Search for "appl" \-\> False

---

### **🔹 Hints**

1. Each node in the trie should represent a single character.

2. Use the insert function to add characters one by one, creating new nodes if necessary.

### **🔹 Brute Force Idea**

Use a list of strings and check if the search string matches any stored strings.

---

### **🔹 Optimized Idea**

Use a trie to store strings efficiently and allow for fast prefix matching.

---

### **🔹 Code Fragment**

