**Remove Duplicate Letters to Get Lexicographically Smallest Result. You are given a string s. You need to remove duplicate letters so that:Each letter appears only once.
The result is the smallest in lexicographical order among all possible results.**

**Test Cases**
1. Input: s = "cbacdcbc"      Output:"acdb"
2. Input: s = "aaaaa"         Output:"a"


**Intuition:**
1. We want to keep each character exactly once.
2. But we must choose the order carefully:
3. If a smaller character can appear later, we should wait for it.
4. Use a stack to build the answer.

**Algorithm Flow:**
1. Count the frequency of each character in the string.
2. Maintain a stack (to store result characters) and a set (to know which characters are already used).
3. Traverse characters one by one:
  Decrease the frequency count.
  If the character is already in the stack → skip it.
  Otherwise, pop characters from the stack if:
    The top of the stack is greater than the current character, and
    That character still appears later (frequency > 0).
  Push the current character into the stack.
4. The stack at the end gives the result string.

**Complexity Analysis:**
Time Complexity: O(n) 
Space Complexity: O(1)
