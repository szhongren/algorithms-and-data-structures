# Boyer-Moore string matching algorithm

suitable when

* alphabet is large
* pattern is long

general idea:
* check last letter of patten with corresponding letter in string
* if they match, check next last letter
* if not, check if the letter in string is in the pattern
* if it is, move the pattern so that the letters match, and repeat
* if not, move the entire pattern past this letter, and repeat

bad character rule:

When a match from the end fails, find the next same character to the left in the pattern, and shift the entire pattern such that the characters match

If the character in the string does not exist in the patten, move the pattern past the character

good suffix rule:

Suppose for a given alignment of P and T, a substring t of T matches a suffix of P, but a mismatch occurs at the next comparison to the left. Then find, if it exists, the right-most copy t' of t in P such that t' is not a suffix of P and the character to the left of t' in P differs from the character to the left of t in P. Shift P to the right so that substring t' in P aligns with substring t in T. If t' does not exist, then shift the left end of P past the left end of t in T by the least amount so that a prefix of the shifted pattern matches a suffix of t in T. If no such shift is possible, then shift P by n places to the right. If an occurrence of P is found, then shift P by the least amount so that a proper prefix of the shifted P matches a suffix of the occurrence of P in T. If no such shift is possible, then shift P by n places, that is, shift P past t.
