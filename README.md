| 动态规划&nbsp; | 二叉树 | 回溯算法&nbsp;|二分查找| &nbsp;贪心算法&nbsp;&nbsp;|&nbsp;待定&nbsp;&nbsp;|待定| &nbsp;&nbsp;待定&nbsp;&nbsp; |待定| &nbsp;&nbsp;待定&nbsp;&nbsp; |
| :---: | :----: | :---: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [:pencil2:](#pencil2-动态规划) | [:computer:](#computer-二叉树) | [:cloud:](#cloud-回溯算法) | [:art:](#art-二分查找) | [:floppy_disk:](#floppy_disk-贪心算法) |[:coffee:](#coffee-待定)| [:bulb:](#bulb-待定) |[:wrench:](#wrench-待定)| [:watermelon:](#watermelon-待定) |[:memo:](#memo-待定)|


## :pencil2: 动态规划
- [	#322 零钱兑换](https://leetcode-cn.com/problems/coin-change/) dp[i-coin]
- [	#198 打家劫舍](https://leetcode-cn.com/problems/house-robber/) dp[i]=max(dp[i-1],dp[i-2]+nums[i]),int tmp,dp_i,dp_pre_i压缩空间
- [	#213 打家劫舍 II](https://leetcode-cn.com/problems/house-robber-ii/) 调用两次，一次偷前不偷尾，另一次相反
- [337. 打家劫舍 III](https://leetcode-cn.com/problems/house-robber-iii/) pair中first不偷second偷，看root偷yes和不偷no哪个大
- [	#121 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/) dp[i][k][1]=(dp[i-1][k][1],dp[i-1][k-1][0]-prices[i])k=1去k，右边只剩-prices[i],dp_i_0,dp_i_1压缩空间
- [	#122 买卖股票的最佳时机 II](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-ii/) k可直接去除
- [	#309 最佳买卖股票时机含冷冻期](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/)//买入时dp[i-2][0]-prices[i],如果不是前2天卖而是前好几天，本应是dp[i-1][0]-prices[i]但二者结果相同因为i-1天没有交易
- [	#714 买卖股票的最佳时机含手续费](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/) -fee
- [	#123 买卖股票的最佳时机 III](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-iii/)//同下
- [	#188 买卖股票的最佳时机 IV](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-iv/) 2k>n时去除k，否则，dp[i][k][0]=max(dp[i-1][k][0],dp[i-1][k][1]+prices[i])dp[i][k][1]=max(dp[i-1][k][1],dp[i-1][k-1][0]-prices[i])
- [#518 零钱兑换 II](https://leetcode-cn.com/problems/coin-change-2/) 完全背包dp[i][j]=max(dp[i-1][j],dp[i][j-coins[i-1])
- [	#416 分割等和子集](https://leetcode-cn.com/problems/partition-equal-subset-sum/) 01背包dp[i][j]=dp[i-1][j]||dp[i-1][j-nums[i-1]]
- [	#1143 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/) 相同dp[i][j]=1+dp[i-1][j-1],不同dp[i][j]=max(dp[i-1][j],dp[i][j-1])
- [	#516 最长回文子序列](https://leetcode-cn.com/problems/longest-palindromic-subsequence/) 左右相同dp[i][j]=2+dp[i+1][j-1],不同dp[i][j]=max(dp[i+1][j],dp[i][j-1])
- [	#53 最大子序和](https://leetcode-cn.com/problems/maximum-subarray/) 子序必须以nums[i]结尾dp[i]=max(dp[i-1]+nums[i],nums[i]),dp_i压缩空间，res不断更新最大值
- [	#72 编辑距离](https://leetcode-cn.com/problems/edit-distance/) 相同，dp[i][j]=dp[i-1][j-1],不同，删a，删b，都删dp[i][j]=max(dp[i-1][j],max(dp[i][j-1],dp[i-1][j-1])+1
- [	#剑指 Offer 10- I 斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/) 注意取模,dp_i,dp_pre_i,tmp压缩空间
- [	#746 使用最小花费爬楼梯](https://leetcode-cn.com/problems/min-cost-climbing-stairs/) 从上阶梯或上上阶梯来dp[i]=max(dp[i-1]+cost[i-1],dp[i-2]+cost[i-2]),int tmp,dp_pre_i,dp_i压缩空间
- [	#718 最长重复子数组](https://leetcode-cn.com/problems/maximum-length-of-repeated-subarray/) 子数组包含A[i],B[i]，A[i]B[i]等，dp[i][j]=dp[i-1][j-1]+1,不等，dp[i][j]=0;
- [	#300 最长上升子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/) dp[i]=max(dp[j]+1,dp[i])要么从j过来要么不要
- [	#279 完全平方数](https://leetcode-cn.com/problems/perfect-squares/) dp[i]=min(dp[i-j* j]+1,dp[i])要么用j要么不用
- [	#1277 统计全为 1 的正方形子矩阵](https://leetcode-cn.com/problems/count-square-submatrices-with-all-ones/) dp[i][j]=min(dp[i-1][j],min(dp[i][j-1],dp[i-1][j-1]),dp[i][j]是以i,j为右下顶点，全是1的最大正方形边长，也是个数，不断count+=dp[i][j]
- [	#152 乘积最大子数组](https://leetcode-cn.com/problems/maximum-product-subarray/) 由于负负可能很大，维护max_dp[i] min_dp[i],二个每次都要在max_dp[i-1]* nums[i],min_dp[i-1]* nums[i], nums[i]中取一个最大和最小保存
- [	#120 三角形最小路径和](https://leetcode-cn.com/problems/triangle/) 下三角，dp[i][j]=min(dp[i-1][j-1],dp[i-1][j])+nums[i][j],res选出最后一行最小值,可降维但可读性低
- [	#70 爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/) dp[i]=dp[i-1]+dp[i-2]，可tmp，dp_i,dp_pre_i压缩
- [	#64 最小路径和](https://leetcode-cn.com/problems/minimum-path-sum/) dp[i][j]=min(dp[i-1][j],dp[i][j-1])+nums[i][j]
- [	#62 不同路径](https://leetcode-cn.com/problems/unique-paths/) dp[i][j]=dp[i-1][j]+dp[i][j-1]
- [	#63 不同路径 II	](https://leetcode-cn.com/problems/unique-paths-ii/) if(!nums[i][j])dp[i][j]=dp[i-1][j]+dp[i][j-1] 如果有障碍物就是0
- [	#5 最长回文子串](https://leetcode-cn.com/problems/longest-palindromic-substring/) 求begin和end用substr复制子字符串，如果左右不等就是false，相等，长度<=3为true，相等且长度大于3,dp[i][j]=dp[i+1][j-1],只要true就不断更新begin=i，end=j
- [	#343 整数拆分](https://leetcode-cn.com/problems/integer-break/) 要么拆一个j，(i-j) * j,要么不变，dp[i]要么继续拆j * dp[i-j]
- [	#221 最大正方形](https://leetcode-cn.com/problems/maximal-square/) max_dp不断找出dp[i][j]最大值就是最大边长
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :computer: 二叉树
- [513. 找树左下角的值](https://leetcode-cn.com/problems/find-bottom-left-tree-value/) 层序遍历，i=0时res保存，到最后一层res就是答案
- [222. 完全二叉树的节点个数](https://leetcode-cn.com/problems/count-complete-tree-nodes/) int left=help(root->left),实现(不管root是哪个root，它的left就一定能表示这个root左子树有多少个节点)，需要做到(if(没有节点)return 0),return 1+left+right求出root作为根结点的节点个数
- [112 路径总和](https://leetcode-cn.com/problems/path-sum/) bool left=help(root->left) 实现(不管root是哪个root，它的left就一定能表示这个root从左边下去最终能否符合题意),需要做到(if(到了叶节点)return root->val==sum,sum在每一次递归前要sum-=root->val)，return left||right求出root作为根节点能否符合题意
- [110 平衡二叉树](https://leetcode-cn.com/problems/balanced-binary-tree/) 第一步{int left=help(root->left) 实现(不管root是哪个root，它的left就一定能表示这个root左子树高度),需要做到(if(没有节点)return 0),return max(left,right)+1求出root作为根节点最大高度}  第二步{bool left=isBalanced(root->left),实现(不管root是哪个root，它的left就一定能表示这个root左子树的左右子树也满足题意),需要做到(if(没有节点)return true,if(abs(height(root->left) - height(root->right)) <= 1)才能进入下次递归，return left&&right求出root作为根结点能否符合题意 }
- [#104 二叉树的最大深度](https://leetcode-cn.com/problems/maximum-depth-of-binary-tree/) - [110 平衡二叉树](https://leetcode-cn.com/problems/balanced-binary-tree/)已经实现
- [	#100 相同的树](https://leetcode-cn.com/problems/same-tree/) bool left=help(p->left,q->left) 实现(不管p q是哪个p q，他们的left就一定能表示这两个p q左子树是否相同),需要做到(if(!q&&!p)return true;if(!p&&q)return false;if(p&&!q)return false;if(p->val!=q->val)return false),return left&&right求出pq作为根结点能否符合题意
- [	#101 对称二叉树](https://leetcode-cn.com/problems/symmetric-tree/) bool out=help(p->left,q->right),实现(不管p q是哪个p q，他们的out就一定能表示这两个pq靠外的子树是否相同),需要做到(if(!q&&!p)return true;if(!p&&q)return false;if(p&&!q)return false;if(p->val!=q->val)return false),return out&&in求出pq作为根结点能否符合题意
- [501. 二叉搜索树中的众数](https://leetcode-cn.com/problems/find-mode-in-binary-search-tree/) 特殊题，unordered_map<int,int>map在中序遍历中用map[root->val]++统计频率,vector<pair<int,int>>vec_sort(map.begin(),map.end())给频率排序，vector<int>res给频率最大几个vec_sort取出return
- [429. N叉树的层序遍历](https://leetcode-cn.com/problems/n-ary-tree-level-order-traversal/) 层序遍历，特点是for(auto child:children)q.push(child)
- [	#257 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/) help(root->left),实现(不管root是哪个root，从左边下去时都能添加root->val和->到string path),需要做到(if(!root)return;path+=to_string(root->val);if(到了根结点)return path;求出路径)
- [404. 左叶子之和](https://leetcode-cn.com/problems/sum-of-left-leaves/) help(root->left),实现(不管root是哪个root，从左边下去都能添加左叶子到int res),需要做到(if(!root)return 0;if(到了左叶子父节点)res+=root->left->val;),return res求出root作为根结点的左子叶数
- [	#236 二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/)TreeNode* left=help(root->left),实现(不管root是哪个root，它的left就一定能在这个root左子树有p或q时返回p或q，否则返回空),需要做到(if(!root)return nullptr;if(有p或q)返回p或q，后序遍历，上去时if(!left)返回right)如果left&&right return root求出后序遍历时第一个祖先;
- [	#235 二叉搜索树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) 同上
- [	#226 翻转二叉树](https://leetcode-cn.com/problems/invert-binary-tree/) invertTree(root->left),实现(不管root是哪个root，从左边下去经过每个节点都能翻转)，需要做到(if(!);swap(root->left,root->right);)return root;
- [	#199 二叉树的右视图](https://leetcode-cn.com/problems/binary-tree-right-side-view/) 层序遍历，特点是在i=level_size-1时把pop的节点放进res
- [	#124 二叉树中的最大路径和](https://leetcode-cn.com/problems/binary-tree-maximum-path-sum/) int left=max(0,help(root->left)),实现(不管root是哪个root，这个root的left就一定能表示左子树一条路径所能贡献的最大值)，需要做到(if(!)return 0;后序遍历返回root的值的左子树所能贡献最大值),return res,res在过程中不断更新root->val+left+right求出所有节点可能值中的最大
- [	#129 求根到叶子节点数字之和](https://leetcode-cn.com/problems/sum-root-to-leaf-numbers/)
- [	#117 填充每个节点的下一个右侧节点指针 II	](https://leetcode-cn.com/problems/populating-next-right-pointers-in-each-node-ii/)
- [	#116 填充每个节点的下一个右侧节点指针](https://leetcode-cn.com/problems/populating-next-right-pointers-in-each-node/)
- [701. 二叉搜索树中的插入操作](https://leetcode-cn.com/problems/insert-into-a-binary-search-tree/)
- [687. 最长同值路径](https://leetcode-cn.com/problems/longest-univalue-path/)
- [617. 合并二叉树](https://leetcode-cn.com/problems/merge-two-binary-trees/)
- [543. 二叉树的直径](https://leetcode-cn.com/problems/diameter-of-binary-tree/)
- [297. 二叉树的序列化与反序列化](https://leetcode-cn.com/problems/serialize-and-deserialize-binary-tree/)
- [449. 序列化和反序列化二叉搜索树](https://leetcode-cn.com/problems/serialize-and-deserialize-bst/)
- [剑指 Offer 27. 二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)
- [剑指 Offer 26. 树的子结构](https://leetcode-cn.com/problems/shu-de-zi-jie-gou-lcof/)
- [572. 另一个树的子树](https://leetcode-cn.com/problems/subtree-of-another-tree/)
- [1367. 二叉树中的列表](https://leetcode-cn.com/problems/linked-list-in-binary-tree/)
- [	#437 路径总和 III](https://leetcode-cn.com/problems/path-sum-iii/)
- [#113 路径总和 II](https://leetcode-cn.com/problems/path-sum-ii/)
- [	#1382 将二叉搜索树变平衡](https://leetcode-cn.com/problems/balance-a-binary-search-tree/)
- [	#108 将有序数组转换为二叉搜索树](https://leetcode-cn.com/problems/convert-sorted-array-to-binary-search-tree/)
- [	#107 二叉树的层次遍历 II](https://leetcode-cn.com/problems/binary-tree-level-order-traversal-ii/)
- [	#103 二叉树的锯齿形层次遍历](https://leetcode-cn.com/problems/binary-tree-zigzag-level-order-traversal/)
- [	#102 二叉树的层序遍历](https://leetcode-cn.com/problems/binary-tree-level-order-traversal/)
- [	#99 恢复二叉搜索树](https://leetcode-cn.com/problems/recover-binary-search-tree/)
- [	#94 二叉树的中序遍历](https://leetcode-cn.com/problems/binary-tree-inorder-traversal/)
- [	#98 验证二叉搜索树](https://leetcode-cn.com/problems/validate-binary-search-tree/)
- [	#889 根据前序和后序遍历构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/)
- [	#114 二叉树展开为链表](https://leetcode-cn.com/problems/flatten-binary-tree-to-linked-list/)
- [	#96 不同的二叉搜索树](https://leetcode-cn.com/problems/unique-binary-search-trees/)
- [	#95 不同的二叉搜索树 II](https://leetcode-cn.com/problems/unique-binary-search-trees-ii/)
- [#106 从中序与后序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/)
- [	#105 从前序与中序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)
- [	#654 最大二叉树](https://leetcode-cn.com/problems/maximum-binary-tree/)
- [	#145 二叉树的后序遍历](https://leetcode-cn.com/problems/binary-tree-postorder-traversal/)
- [	#144 二叉树的前序遍历](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/)
- [	#450 删除二叉搜索树中的节点](https://leetcode-cn.com/problems/delete-node-in-a-bst/)
- [	#700 二叉搜索树中的搜索](https://leetcode-cn.com/problems/search-in-a-binary-search-tree/)
- [#538 把二叉搜索树转换为累加树](https://leetcode-cn.com/problems/convert-bst-to-greater-tree/)
- [	#230 二叉搜索树中第K小的元素](https://leetcode-cn.com/problems/kth-smallest-element-in-a-bst/)
- [	#111 二叉树的最小深度](https://leetcode-cn.com/problems/minimum-depth-of-binary-tree/)
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :cloud: 回溯算法
- [46. 全排列](https://leetcode-cn.com/problems/permutations/)
- [47. 全排列 II](https://leetcode-cn.com/problems/permutations-ii/)
- [78. 子集](https://leetcode-cn.com/problems/subsets/)
- [90. 子集 II](https://leetcode-cn.com/problems/subsets-ii/)
- [77. 组合](https://leetcode-cn.com/problems/combinations/)
- [39. 组合总和](https://leetcode-cn.com/problems/combination-sum/)
- [40. 组合总和 II](https://leetcode-cn.com/problems/combination-sum-ii/)
- [60. 排列序列](https://leetcode-cn.com/problems/permutation-sequence/)
- [79. 单词搜索](https://leetcode-cn.com/problems/word-search/)
- [22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/)
- [130. 被围绕的区域](https://leetcode-cn.com/problems/surrounded-regions/)
- [51. N 皇后](https://leetcode-cn.com/problems/n-queens/)
- [37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/)
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :art: 二分查找
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :floppy_disk: 贪心算法
- [	#452 用最少数量的箭引爆气球](https://leetcode-cn.com/problems/minimum-number-of-arrows-to-burst-balloons/)
- [#983 最低票价](https://leetcode-cn.com/problems/minimum-cost-for-tickets/)
- [	#55 跳跃游戏](https://leetcode-cn.com/problems/jump-game/)
- [	#435 无重叠区间](https://leetcode-cn.com/problems/non-overlapping-intervals/)
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()

## :coffee: 待定 
## :bulb: 待定
## :wrench: 待定
## :watermelon: 待定
## :memo: 待定
