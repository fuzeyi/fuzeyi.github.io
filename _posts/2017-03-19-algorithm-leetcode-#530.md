---
layout: post
title: LeetCode-#530-求二叉排序树的最小绝对差
date:   2017-03-19 20:45:00 +0800
categories: Algorithm
tag: 树
 
---

* content
{:toc}

有一颗非负数的二叉排序树，求它的最小绝对差

**例子**

{% highlight ruby %}
Input:

   1
    \
     3
    /
   2

Output:
1

Explanation:
The minimum absolute difference is 1, which is the difference between 2 and 1 (or between 2 and 3).
{% endhighlight %}

**注意: **二叉排序树中至少有两个节点

**JAVA:**

{% highlight ruby lineno %}
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    int minDiff = Integer.MAX_VALUE;
    public int getMinimumDifference(TreeNode root) {
        helper(root,Integer.MIN_VALUE,Integer.MAX_VALUE);
        return minDiff;

    }

    private void helper(TreeNode curr, int lb, int rb) {
        if (curr == null) {
            return;
        }
        if (lb != Integer.MIN_VALUE) {
            minDiff = Math.min(minDiff, curr.val - lb);
        }
        if (rb != Integer.MAX_VALUE) {
            minDiff = Math.min(minDiff,rb-curr.val);
        }
        helper(curr.left,lb,curr.val);
        helper(curr.right,curr.val,rb);
    }
}
{% endhighlight %}


 