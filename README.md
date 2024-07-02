# Alphabetic-Substring
This was a java project that I created as a part of my final for my AP Computer Science class.

For this program, given two strings s and t of lengths m and n respectively, I was tasked to return the minimum window substring of s such that every character in t (including duplicates) is included in the window. While developing the algorithm for this program, many of my approaches did not consider duplicates and empty substrings. I tried to use extra variables and a separate array to keep track of the pattern, t, in the original string. After some research and consideration, I came to understand a more efficient approach to creating a solution for the program. I decided to use one boolean method to check if all characters of t are in the original string s, because this method would help me return an empty string if there is no substring with the characters of t in s. I created an array named count, initializing it to 256 according to the number of ASCII characters. I use a for loop to count the amount of characters in t, then I use 2 other for loops which work together by decrementing count and checking count for each character, and if the substring does not contain a character in the pattern, the method returns false. Otherwise, the method returns true. The other method I use, minWindow, returns a String named answer with the correct window of the substring of s. I use 2 variables for the lengths of both strings passed into the method, len1 for s and len2 for t. I use these lengths in 2 for loops, which both work together to create and check possible substrings with the boolean method valid. If the call returns true, I make currentLength the length of the substring being checked, and if that length is less than the minimum length of a substring that is valid, then I make minimum that length and assign the substring to answer. Therefore, these loops check every possibility of substrings, and if there is no substring with all the characters of t, the answer string remains blank and the program returns an empty string. I checked this program with s containing two 2 possible return values, but with one having a shorter length than the other. The program returned the shorter of the two after printing out the call to the method with s and t.

Example 1:

Input: s = "ADOBECODEBANC", t = "ABC"
Output: "BANC"
Explanation: The minimum window substring "BANC" includes 'A', 'B', and 'C' from string t.

Example 2:

Input: s = "a", t = "a"
Output: "a"
Explanation: The entire string s is the minimum window.

Example 3:

Input: s = "a", t = "aa"
Output: ""
Explanation: Both 'a's from t must be included in the window.
Since the largest window of s only has one 'a', return an empty string.
 
Constraints:

m == s.length
n == t.length
1 <= m, n <= 105
s and t consist of uppercase and lowercase English letters.
