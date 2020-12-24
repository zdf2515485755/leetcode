二叉搜索树的最近公共祖先

题目介绍

给定一个二叉搜索树, 找到该树中两个指定节点的最近公共祖先。

百度百科中最近公共祖先的定义为：“对于有根树 T 的两个结点 p、q，最近公共祖先表示为一个结点 x，满足 x 是 p、q 的祖先且 x 的深度尽可能大（一个节点也可以是它自己的祖先）。”

例如，给定如下二叉搜索树:  root = [6,2,8,0,4,7,9,null,null,3,5]

解题思路

由于二叉搜索树的特殊属性，有两种方法解决，第一种，我们可以遍历树，分别记录pnode和qnode的路径，然后路径列表中最后一个相同数就是最近公共祖先，方法二，我们可以遍历一次，判断当前node是否比pnode和其node都大，或者都小，除此之外，说明该node就是最近公共祖先

while root:
	if root.val > q.val and root.val > p.val:
		root = root.left
	elif root.val < q.val and root.val < p.val:
		root = root.right
	else:
		return root
return root
