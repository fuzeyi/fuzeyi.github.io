---
layout: post
title: LeetCode-#409-求最长的回文
date:   2017-03-26 21:52:00 +0800
categories: Algorithm
tag: LeetCode
 
---

* content
{:toc}

Given a string which consists of lowercase or uppercase letters, find the length of the longest palindromes that can be built with those letters.
This is case sensitive, for example `"Aa"` is not considered a palindrome here.

**Note:**
>Assume the length of given string will not exceed 1,010.

**Example:**
{% highlight ruby lineno %}
Input:
"abccccdd"

Output:
7

Explanation:
One longest palindrome that can be built is "dccaccd", whose length is 7.
{% endhighlight %}

**JAVA:**
{% highlight ruby lineno %}
public int longestPalindrome(String s) {
        if(s==null || s.length()==0) return 0;
        HashSet<Character> hs = new HashSet<Character>();
        int count = 0;
        for(int i=0; i<s.length(); i++){
            if(hs.contains(s.charAt(i))){
                hs.remove(s.charAt(i));
                count++;
            }else{
                hs.add(s.charAt(i));
            }
        }
        if(!hs.isEmpty()) return count*2+1;
        return count*2;
}
{% endhighlight %}


 