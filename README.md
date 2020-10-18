# LeetCode-Break-a-Palindrome-Solution
Solution to Break a Palindrome LeetCode

Hint: Change some letter to 'a'.

Any single letter string is palindrome. So if the length of the string is one, answer is "".

When we want to make something lexicographically smallest, we should be greedy. Here, greedy means that we start from the beginning of the string, we try to change (and make smaller) the first character possible. For example, in "bab", we change the first b to 'a'.

The question is, why we can't always change the first letter to 'a' and make the string lexicographically smallest, as we did above? Look at sample test #1, "abccba". The first letter is already 'a', so changing it to 'a' leads to a palindrome again.

So if the first letter is 'a', we try to change the second letter to 'a' instead. Sometimes it's not possible too, "aabaa". The solution is to change the first non-'a' letter to 'a'.

This is not always possible. Consider the case "aaaa". So if all of the letters are 'a', unfortunally, we need to change the last 'a' to 'b'.

Last question, do we always convert string to non-palindrome string? Because the initial string is palindrome, if it has odd length and we change the middle letter it leads to a palindrome string again. So if all of the letters except the middle letter is 'a', when the length of the string is odd, again we need to change the last 'a' to 'b'.

To summerize, we find the first non-'a' letter in the range [0, palindrome.size() / 2) (0-based) and change it to 'a', otherwise we change the last 'a' to 'b'.
